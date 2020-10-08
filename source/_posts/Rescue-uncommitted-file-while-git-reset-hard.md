---
title: Rescue uncommitted files while using git reset --hard
date: 2020-10-07 14:47:47
tags: [git]
---

{% asset_img 01.jpg %}

<!-- more -->

Sometimes we have an existing folder, 'git init' and 'git add .' ready to commit.

Then we realize some unnecessary files have been added.

In this situation, usually using 'git reset --soft' to reset the stage status. 

BUT we might use 'git reset --hard' by accident...

Some articles said we can use 'git reflog' to find out the lost commits. 

However, because our git repo is the initialed one without any commit so reflog might be useless.

If using 'git reset --hard' at very beginning then want to rescue files back, this article might be help.

---

# Scenario
Assume that we have a folder Experiment and there is 3 files inside.
Which is Demo1.txt Demo2.txt ApiController.cs
{% asset_img 02.png %}
Then:
- Using {% blockquote %}git init{% endblockquote %} {% asset_img 03.png %}

- Using {% blockquote %}git add .{% endblockquote %} {% asset_img 04.png %}

- Using {% blockquote %}git reset --hard{% endblockquote %} for demo and we can see those files are gone.{% asset_img 05.png %}

- Using {% blockquote %}git reflog{% endblockquote %} then realize does not have any commit {% asset_img 06.png %}

So how do we rescue the files?

# First : Collect all dangling files to lost-found folders
We can collect all dangling files by this command {% codeblock line_number:false %} git fsck --lost-found {% endcodeblock %}
{% asset_img 07.png %}
After that, it'll show those dangling files. Go to .git/lost-found/other {% asset_img 08.png %}

# Second : Grep the keyword from those dangling files
Using grep command to search the keyword. EX : grep -rw "Demo1"
{% asset_img 09.png %}
So we can make sure 85002821eb3812840.... is the Demo1.txt

We can gerp ApiController, too.
{% asset_img 10.png %}

# Third : Copy to the original folder and rename it
Finally, just copy those files to the original path and rename it, and Bob’s your uncle.
{% asset_img 11.png %}

# Link
- {% link "git-fsck" https://git-scm.com/docs/git-fsck%}
- {% link "Reset commit" https://gitbook.tw/chapters/using-git/reset-commit.html%}
- {% link "Reflog" https://gitbook.tw/chapters/using-git/restore-hard-reset-commit.html%}