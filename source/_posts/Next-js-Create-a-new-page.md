---
title: Next.js Create a new page
tags:
  - Next.js
  - JavaScript
  - React
categories:
  - Next.js
date: 2020-06-10 18:14:22
---

## Create a new post under the "pages" folder

<!-- More -->

A page in Next.js means a React Component exported from the file in pages folder.

So we can easily add a post under the pages folder. For better file management, creating a "posts" folder under the pages folder.

{% asset_img 01.png %}

Then we can add the first post file "first-post.js" manually into the posts folder.

{% asset_img 02.png %}
Type the following contents in the "first-post.js"

{% codeblock %}
export default function FirstPost() {
  return <h1>First Post</h1>
}
{% endcodeblock %}

After saving the file, we can check the local wetsite using the post path http://localhost:3000/posts/first-post

{% asset_img 03.png %}