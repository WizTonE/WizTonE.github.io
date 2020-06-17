---
title: 'Next.js Assets, Metadata & CSS'
tags:
  - Next.js
  - JavaScript
  - React
categories:
  - Next.js
date: 2020-06-17 19:10:57
---


## Next.js handles static assets such as images and video. Metadata like HTML tag. CSS styling allows you to import css and scss files.

<!-- More -->

- ## Assets
    When we put static files like images and video under top-level 'public' folder. Files in the public folder can be referenced by pages.
    
    So we can use the picture vercel.svg into our first-post page.
    
    ```<img src="/vercel.svg" alt="Vercel Logo" className="logo" />```

    The page will show vercel picture.
    {% asset_img 02.png %}

- ## Metadata
  Metadata like html tag ```<head>``` has been instead of ```<Head>``` , which is React component in Next.js.
  We can add ```<Head>``` into our first-post.js

  {% asset_img 01.png %}

- ## CSS
  - Next.js use styled-jsx which is a CSS in JS, we can write the CSS only for the specific component. Besides, Next.js allows to import .css and .scss files.
  - We can also create the _app.js for the global entry point, then import CSS file for the global CSS styling.

- ## Layout Component
  We can create a layout as a component with CSS styling import.
  
  - Create the folder ```components``` and ```styles``` in the top level.
  - Create layout.js and layout.module.css in the components folder.
  {% asset_img 03.png %}
  - Create the folder  in the top level
  - Create a utility CSS classes utils.module.css in styles folder for reuse css style.
  {% asset_img 04.png %}
  - Now we can easy use the layout.js in our first-post.js
  
  {% codeblock line_number:false %}
  import Head from 'next/head'
  import Layout, { siteTitle } from '../components/layout'
  import utilStyles from '../styles/utils.module.css'

  export default function Home() {
    return (
      <Layout home>
        <Head>
          <title>{siteTitle}</title>
        </Head>
        <section className={utilStyles.headingMd}>
          <p>[Your Self Introduction]</p>
          <p>
            (This is a sample website - you’ll be building a site like this on{' '}
            <a href="https://nextjs.org/learn">our Next.js tutorial</a>.)
          </p>
        </section>
      </Layout>
    )
  }
  {% endcodeblock %}

- ## Result
  {% asset_img 05.png %}

- # Link
  - {% link "Assets, Metadata, and CSS" https://nextjs.org/learn/basics/assets-metadata-css%}