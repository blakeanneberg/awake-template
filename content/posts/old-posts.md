---
title: Old Posts
subtitle: Old stuff
category:
  - About Awake
author: Blake
date: 2021-5-02T10:10:10.800Z
featureImage: /uploads/markup-hero.jpg
---
The `ResourceGrid` powers the grid display of both posts and categories in the Awake template. It's a powerful, fast, and flexible component to grab a grid of any size or content when you need it.

| Prop     | Description                                          | Type   | Default           |
| -------- | ---------------------------------------------------- | ------ | ----------------- |
| perRow   | how many resources to displayed per row              | Number | 3                 |
| number   | total number of resources to display                 | Number | all (lazy loaded) |
| category | for posts filters posts only in supplied category(s) | Array  | \[]               |
| resource | the resource to be retrieved and displayed           | String | Required          |

There are 2 simple wrappers built around the `ResourceGrid` for easily displaying a categories grid or a posts grid, easily enough they are `CategoriesGrid` and `PostsGrid`.

## Examples
```
<--! All posts in grid with 3 per row lazy loaded until no more-->
<posts-grid />

<--! 3 posts in grid in single row -->
<posts-grid :number="3" />

<--! 3 posts in grid in single row in category-1 (exactly how related posts at end of single post is accomplished) -->
<posts-grid :number="3" :category="['category-1']" />

<--! All categories in grid with 3 per row lazy loaded until no more-->
<categories-grid />

<--! etc -->
```


Awake uses the awesome npm package [markdown-it ](https://github.com/markdown-it/markdown-it)by [Vitaly Puzrin](https://github.com/puzrin) to provide a wealth of markup options for your posts

# h1 Heading

## h2 Heading

### h3 Heading

#### h4 Heading

##### h5 Heading

###### h6 Heading

## Horizontal Rules

- - -

## Typographic replacements

(c) (C) (r) (R) (tm) (TM) (p) (P) +-

test.. test... test..... test?..... test!....

!!!!!! ???? ,,  -- ---

"Smartypants, double quotes" and 'single quotes'

## Emphasis

**This is bold text**

**This is bold text**

_This is italic text_

_This is italic text_

~~Strikethrough~~

## Blockquotes

> Blockquotes can also be nested...
>
> > ...by using additional greater-than signs right next to each other...
> >
> > > ...or with spaces between arrows.

## Lists

Unordered

* Create a list by starting a line with `+`, `-`, or `*`
* Sub-lists are made by indenting 2 spaces:
  * Marker character change forces new list start:
    * Ac tristique libero volutpat at
    * Facilisis in pretium nisl aliquet
    * Nulla volutpat aliquam velit
* Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. You can use sequential numbers...
5. ...or keep all the numbers as `1.`

Start numbering with offset:

57. foo
58. bar

## Code

Inline `code`

Indented code

```
// Some comments
line 1 of code
line 2 of code
line 3 of code
```

Block code "fences"

```
Sample text here...
```

## Tables

| Option | Description                                                               |
| ------ | ------------------------------------------------------------------------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default.    |
| ext    | extension to be used for dest files.                                      |

Right aligned columns

| Option | Description                                                               |
| ------ | ------------------------------------------------------------------------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default.    |
| ext    | extension to be used for dest files.                                      |

## Links

[link text](https://danielkelly.io)

[link with title](https://danielkelly.io "title text!")

Autoconverted link https://danielkelly.io

## Images

![cat](/uploads/cat-1045782_1920.jpg)

## Subscript/SuperScript

* 19^th^
* H\~2\~O

## Footnotes

Footnote 1 link\[^first].

Footnote 2 link\[^second].

Inline footnote^\[Text of inline footnote] definition.

Duplicated footnote reference\[^second].

\[^first]: Footnote **can have markup**

```
and multiple paragraphs.
```

\[^second]: Footnote text.

### [Definition lists](https://github.com/markdown-it/markdown-it-deflist)

Term 1

:   Definition 1
with lazy continuation.

Term 2 with _inline markup_

:   Definition 2

```
    { some code, part of Definition 2 }

Third paragraph of definition 2.
```

_Compact style:_

Term 1
  ~ Definition 1

Term 2
  \~ Definition 2a
  \~ Definition 2b







You're publishing great content! Make sure people can get it easily right in their inbox with Awake's ready to go Mailchimp integration. Follow these instructions to get your newsletter up and running

## 1. Signup with Mailchimp

If you don't already have a mailchimp account, head on over to [mailchimp.com](https://mailchimp.com) and sign up (don't worry they have free tiers that will give you all you probably need).

## 2. Create a New Campaign

Go to "Campaigns" in the main navigation of the Mailchimp dashboard and then click the "Create Campaign" button on the top right.

## 3. Start Signup Form

From the modal overlay that appears choose "Signup Form", then click "Begin" under "Embedded Form"

![Mailchimp create signup form](/uploads/screen-shot-2019-08-01-at-1.03.08-pm.png)

## 4. Get Form Action

Under "Copy/paste onto your site" you'll see the markup  for the newsletter form. Just copy the form action value from the form

![copy form action from mailchimp](/uploads/screen-shot-2019-08-01-at-1.05.09-pm.png)

## 5. Add the Action to the Awake Site Configuration

```
// Can be the form action on a mail chimp form, a hubspot form,
// or any other url you want to post the form data tomailchimp: {
    on: true,
    formAction:'enter url here'
}
```





Typically the convenience of a CSS framework like Bulma comes at the cost of sending loads of unused css to the browser increasing load times and hindering user experience. So just don't use Bulma (or Bootstrap, Tailwind, or otherwise) right? No, that can't be the answer. These frameworks add to the designer's experience and ability to quickly turn around a finished design. 

Enter [Purge CSS](https://www.purgecss.com/). Purge CSS crawls through your html and css comparing them and removing any unused selectors from your stylesheets at build time so that they can be as slim as possible. So all those useful classes that Bulma has but you just aren't using right now won't slow down your site. And then maybe you decide to use one of them in the future. BOOM, it's there next time you compile with no thought on your part. 

Since Awake is built on the JAM Stack, it can easily take advantage of this technology and so Purge CSS is baked right in. It's that simple. Use Bulma to your hearts content without the bloat.



# Caveats

There are some caveats to Purge CSS especially around dynamically created classes. Since these classes aren't fully fleshed out in the .vue files, Purge CSS doesn't know they exist and therefore will strip out their  corresponding css. The fix is pretty simple though, Purge CSS allows us to whitelist classes that should never be purged whether they are found in the html or not. The whitelisting process is described in full in the [Purge CSS docs](https://www.purgecss.com/whitelisting). You can set the `whitelist` option as well as any other purge css option in `config/build.js`.
Sometimes when dev mode and adding markup that uses classes that have not previously been in use, you must restart dev mode for Purge CSS to pick up on the change. 





Awake is a Nuxt.js template for generating a beautifully robust static site with blog. 

# Features

* Simple modern design based on the Bulma css framework (with unused css purged via [purgecss](https://www.purgecss.com/))
* Site search
* Statically generated API for posts and categories
* Disqus powered comments
* Mailchimp powered newsletter
* Highly customizable with out of the box configurations
* Built with performance in mind
* Isolated Netlify CMS driver (with more CMS drivers planned for future) for easily migrating between various headless cms'
* Images automatically resized for various screens and given srcsets

# Use Awake on Netlify

Simply click the "Deploy to Netlify" button and then configure it to fit your needs as described below.

[![Deploy to Netlify!!](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/danielkellyio/awake-template)

# Configuration

Site configuration is found in `/config/_siteConfig.js`. Here you can customize site settings such as the site name, layout, disqus and mailchimp setup, image sizes and more. Any of these can be setup to use environment variables if you so desire, in order to be able to configure them directly from the Netlify interface. See the setup for google analytics which already uses an environment variable as an example of this.

```
googleAnalytics: {
    on: true,
    id: process.env.GOOGLE_ANALYTICS_ID
},
```

# Editing Content

Posts and categories can be edited in Netlify CMS at \[your-site-url]/admin. At this time any new pages must be created in the code itself and committed to the repo. Before you visit the admin for the first time, make sure you have [Netlify Identity](https://www.netlify.com/docs/identity/) setup with your user and make sure "Git Gateway" is enabled via the Identity Settings page in the Netlify admin. 

# Local Development

Since all content is store in the git repo with Netlify CMS, local development is a breeze. Simply install node, pull down the repo, install the dependencies with `npm install`, and run `npm run dev`.

# Having Issues?

If you're having any issues feel free to reach out to me on twitter [@danielkelly.io](https://twitter.com/danielkelly_io) or report an issue in [github repo](https://github.com/danielkellyio/awake-template).




Disqus brings the power of commenting to the Awake template. It provides features like moderation, reactions, filtering, and social sharing out of the box. Best of all, it's free and super easy to setup!

## Step 1

Go to disqus.com and click on "Get Started"

![Screenshot of Disqus homepage](/uploads/disqus-get-started.jpg)

## Step 2

Choose "I want to install Disqus on my site"

![Disqus button "I want to install Disqus on my site"](/uploads/disqus-add-to-website.jpg)

## Step 3

Sign-up or sign in

## Step 4

Enter site name, Disqus URL and select a category. The Disqus URL name is your site’s name in your account where you can access all the required settings.

## Step 5

Select a plan. There are several premium versions available, but don't worry the free one works just great too!

## Step 6

Disqus supports a number of different platforms but also works great in static sites like Awake. Scroll to the very bottom of the list and choose: "I don't see my platform listed, install manually with"

![Disqus button "I don't see my platform listed, install manually with"](/uploads/disqus-platform-button.jpg)

## Step 7

You can ignore everything on this page, as the Awake template has already configured it for you. All you have to do is find your "Site Short Name" (it's the first part of the url) and add it to `config/_siteConfig.js`.

Take it from here:

![Site Short Name in url](/uploads/disqus-site-short-name.jpg)

and put it here:

```
// config/_siteConfig.js
export default {
...
// Disqus
  disqus: {
    on: false,
    loadingStrategy: 'button', // Options: onload, lazy, button
    siteShortName: 'testing-bjsj2bjl0i'
  },
}
```

## Step 8

That's it! You've got comments up and running on your site. Go checkout a post and see your new fancy comments section.


Awake is fast for a couple different reasons. It both capitalizes on the platform it's built for (JAM Stack) and the framework it's built on (Nuxt.js) as well as includes some intentional optimizations to improve the end user experience when it comes to speed. 

## The JAM Stack

The JAM stack is a way of building websites that compile down basically to html, css, and javascript and then is served over a CDN. API's are then sprinkled in to add more advanced functionality where needed. Because there is no server, no computations to run, initial response time is like lightening. 

## Nuxt.js

[Nuxt.js](https://www.nuxtjs.org) has the ability to generate static sites that are served on the JAM Stack, building plain old html files... but those html files are super-powered with Vue.js. What this means, is that pages have content "hard coded" into the html files for top-rate SEO scores but after initial page load behave as a traditional SPA with smooth page transitions, minimal data served between requests, etc. This means Awake is fast both on both the first page visitors hit and even faster on subsequent pages.

## Purge CSS

Awake uses the [Bulma](https://bulma.io/) framework for a starting place for styles but certainly doesn't use every style the Bulma framework provides. [Purge CSS](https://www.purgecss.com/) minimizes the css sent to the browser by removing any unused styles at compile time. You can read more about how Awake uses Purge CSS in this [post](/light-css-footprint).

## Opti-Image + Responsive Loader

[Opti-Image](https://www.npmjs.com/package/opti-image) is a little vue component I wrote to be able to serve images in the most performant way possible. It supports webp's for browser's that support it (though not using the webp functionality for Awake, yet...), lazy loading out of the box, and easy srcset management. [Responsive Loader (the Nuxt Flavor)](https://www.npmjs.com/package/nuxt-responsive-loader) auto optimizes image quality for best performance in the browser and creates multiple sizes for different devices. Combine these 2 together and all image on Awake are basically guaranteed to fly. 

## Font Awesome 5

Awake comes with Font Awesome 5 support out of the box, so you have a wealth of free quality icons at your finger tips. However, if you're used to using Font Awesome in the more traditional manner without a build step you may be thinking: "What about all those icons I don't actually use? Aren't they just bloat?" Not so with Awake, with webpack we can bundle only the icons we're using. This does mean an extra step of registering a new icon when you want to use it, but that's as easy as adding it to an array in `config/modules.js` like so: 

```
 icons: ['faTimes', 'faSearch', 'faEnvelope', 'faUser', 'faBriefcase']
```

## Lazy Loading Like Crazy

In order to speed up both compile time and page load time, basically everything but the header, footer, hero, and main content of the posts are lazy loaded. All grids are lazy loaded with infinite scroll and all images (feature images and those in posts) are also lazy loaded. Comments can be lazy loaded or loaded on click of "Show Comments" button.

## Pretty Stinkin' Fast, I'd Say

I've taken a number of steps to try and make Awake as fast and snappy as possible for the end user and I think you'll find it's been handled fairly well. Last I ran one of the posts through Page Speed Insights I got a 99 score for desktop and 89 for mobile. [Give it a try for yourself!](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Fawake-template.netlify.com%2Fpost-markup-and-formatting%2F&tab=desktop)

![Page speed insights score 99!!](/uploads/page-speed-insights.jpg)
