## Pre-rendering
Before we talk about data fetching, let’s talk about one of the most important concepts in Next.js: Pre-rendering.

- By default, Next.js pre-renders every page. This means that Next.js generates HTML for each page in advance, instead of having it all done by client-side JavaScript. Pre-rendering can result in better performance and SEO.

- Each generated HTML is associated with minimal JavaScript code necessary for that page. When a page is loaded by the browser, its JavaScript code runs and makes the page fully interactive. (This process is called hydration.)

- You should see that your app is rendered without JavaScript. That’s because Next.js has pre-rendered the app into static HTML, allowing you to see the app UI without running JavaScript.

## Two Forms of Pre-rendering
Next.js has two forms of pre-rendering: Static Generation and Server-side Rendering. The difference is in when it generates the HTML for a page.

Static Generation is the pre-rendering method that generates the HTML at build time. The pre-rendered HTML is then reused on each request.
Server-side Rendering is the pre-rendering method that generates the HTML on each request.


## Static Generation with and without Data
Static Generation can be done with and without data.

So far, all the pages we’ve created do not require fetching external data. Those pages will automatically be statically generated when the app is built for production.

## Static Generation with Data using getStaticProps
How does it work? Well, in Next.js, when you export a page component, you can also export an async function called getStaticProps. If you do this, then:

getStaticProps runs at build time in production, and…
Inside the function, you can fetch external data and send it as props to the page.

## Parsing the Blog Data on getStaticProps
Now, let’s update our index page (pages/index.js) using this data. We’d like to:

Parse each markdown file and get title, date, and file name (which will be used as id for the post URL).
List the data on the index page, sorted by date.
To do this on pre-render, we need to implement getStaticProps.

--------------------------------------------

[Table Of Content](https://github.com/omarXzain/401-reading-notes)
