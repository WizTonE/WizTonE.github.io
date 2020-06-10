---
title: Next.js Link to each other
date: 2020-06-10 18:47:08
tags:
  - Next.js
  - JavaScript
  - React
categories:
  - Next.js
---

## Using <Link> when linking between pages

Next.js uses <Link> to wrap the <a> tag. The tag <Link > can let you navigate to the client-side page.

First, import the Link library on both the very top of index.js and first-post.js
{% codeblock %}
import Link from 'next/link'
{% endcodeblock %}

Second, Add the link "My First Post" into the tag <div className="grid"> in index.js. Type the following contents.
{% codeblock %}
<Link href="/posts/first-post"><a className="card"><h3>First post!</h3></a></Link>
{% endcodeblock %}

Finally, we add a Link into our first-post.js by following contents.
{% codeblock %}
export default function FirstPost() {
    return(
     <>
      <h1>First Post</h1>
     <h2>
         <Link href="/">
           <a>Back to home</a>
         </Link>
       </h2>
     </>
    )
  }
{% endcodeblock %}

Then we can see the link on the page
{% asset_img 01.png %}
{% asset_img 02.png %}

So, we can navigate between each other by <Link>