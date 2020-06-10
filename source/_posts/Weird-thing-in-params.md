---
title: Weird thing in params
date: 2020-06-11 00:06:41
tags:
  - C#
  - Java
  - Python
  - params
---

## Params is a basic design in programming language, with different name but the same purpose

<!-- More -->

Following the C# code, guess the output
{% codeblock line_number:false %}
static void Main(string[] args)
{
    var o = default(object);
    A(o);
    A(null);
    A(null, null);
}

private static void A(params object[] a)
{
    if(a == null) 
        Console.WriteLine("...");
    else
        Console.WriteLine(a.Length);
}
{% endcodeblock %}

The answer is:
{% codeblock line_number:false %}
1
...
2
{% endcodeblock %}

Here is the Java code:
{% codeblock line_number:false %}
public static void main(String[ ] args) {
    Object o = null;
        A(o);
        A(null);
        A(null, null);
}

private static void A(Object... a)
{
    if(a == null) 
            System.out.println("...");
        else
            System.out.println(a.length);
}
{% endcodeblock %}

The answer is the same with C#:
{% codeblock line_number:false %}
1
...
2
{% endcodeblock %}

Now let's try Python version:
{% codeblock line_number:false %}
def foo(*therest):
    if therest is None:
        print("...")
    else:
        print(len(therest))
NoneObj = type(None)()
foo(NoneObj)
foo(None)
foo(None, None)
{% endcodeblock %}

Finally, we got different answer:
{% codeblock line_number:false %}
1
1
2

In [1]: 
{% endcodeblock %}

It's because Python doesn't have Null object.

---

Now, try to compare the C# code with IL Code

C# code:
{% codeblock first_line:9 %}
var o = default(object);
A(o);
A(null);
A(null, null);
{% endcodeblock %}

IL Code:
{% codeblock line_number:false lang:C# %}
// [9 13 - 9 37]
IL_0001: ldnull
IL_0002: stloc.0      // o

// [10 13 - 10 18]
IL_0003: ldc.i4.1
IL_0004: newarr       [System.Runtime]System.Object
IL_0009: dup
IL_000a: ldc.i4.0
IL_000b: ldloc.0      // o
IL_000c: stelem.ref
IL_000d: call         void ConsoleApp1.Program::A(object[])
IL_0012: nop

// [11 13 - 11 21]
IL_0013: ldnull
IL_0014: call         void ConsoleApp1.Program::A(object[])
IL_0019: nop

// [12 13 - 12 27]
IL_001a: ldc.i4.2
IL_001b: newarr       [System.Runtime]System.Object
IL_0020: call         void ConsoleApp1.Program::A(object[])
IL_0025: nop
{% endcodeblock %}

Now it's clear, we can see ```A(0)``` and ```A(null, null)```, 

The IL code will create a new array with elements of type object then pass to the function A

But ```A(null)``` just pass null as a parameter, so we will get different answer.

That means when compiler try to explain the syntax with different way.

# Link
- {% link "ldnull" https://docs.microsoft.com/en-us/dotnet/api/system.reflection.emit.opcodes.ldnull?view=netcore-3.1%}
- {% link "newarr" https://docs.microsoft.com/en-us/dotnet/api/system.reflection.emit.opcodes.newarr?view=netcore-3.1%}
- {% link "Null object in python" https://appdividend.com/2019/08/16/null-object-in-python-example-python-null-value-tutorial/%}
- {% link "Python : Multiple Function Arguments" https://www.learnpython.org/en/Multiple_Function_Arguments%}
