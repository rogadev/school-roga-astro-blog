---
layout: "../../layouts/BlogPost.astro"
title: "Tailwind CSS for Your Astro Blog"
description: "How I added Tailwind CSS to my Astro blog"
pubDate: "November 25, 2022"
heroImage: "/placeholder-hero.jpg"
---

For as long as I can remember, Tailwind CSS has been my all-time favorite CSS framework. I've used it on countless projects and I've never been disappointed. It's easy to use, easy to customize, and, perhaps most importantly for those new developers out there, it's easy to learn. I've been using Tailwind CSS for years and I'm still learning new things about it. It is, in my opinion, the best CSS framework out there. Let's get it set up in our new Astro blog.

> NOTE: Installing Tailwind CSS will immediately create a style reset for your entire site. If you were relying on default browser styles, you're about to have some work to do adding styles back in. I don't recommend doing this on the main branch of your blog repo if you're site is live somewhere on the web. Create a dev branch, add Tailwind CSS, do your styling update, then merge it into your main branch when it's ready.

## Step 1: Install Tailwind CSS

Astro has *amazing* documentation. If you haven't poked around yet, I strongly recommend checking it out. [Here is a link](https://docs.astro.build/en/guides/integrations-guide/tailwind/) to the section in the docs tha talks about setting up integrations within Astro. You're more than welcome to skip my blog completely and watch the short, 1:05 video that Astro has created. But if you're like me and you just want the Cole's Notes, then read on.

> NOTE: If your dev server is running, you'll need to stop it before installing Tailwind CSS. You can do this by pressing `Ctrl + C` in your terminal.

First thing's first - let's install Tailwind CSS by running the following command:

```bash
npx astro add tailwind -y
```

The `-y` flag will automatically answer yes to any prompts that come up. I'll spell out the prompts below, but if you're just following along, you can use the -y flag. Skip to the next section if you're using the -y flag.

**If you didn't use the `-y` flag...** Astro will just ask if installing tailwind is what you intended to do - of course we'll say yes:

```bash
? Continue? » Y
```

Astro then informs you that it will generate a minimal ./tailwind.config.js file for you. This is fine, so we'll say yes to that as well:

```bash
? Continue? » Y
```

Astro will then let you know it's about to make some changes to your config file. That's what we're here for, so we'll say yes to that as well:

```bash
? Continue? » Y
```

## Step 2: Add Tailwind CSS to your Astro project

Let's spin our dev server back up and have a look at our site, now that we've installed Tailwind.

```bash
npm run dev
```

You should immediately notice that a lot of default styles just broke. Don't worry, that's to be expected. Tailwind CSS adds a pretty thorough style reset to your site. Let me briefly show you how to use Tailwind CSS, if you're unfamiliar, and we'll get started on fixing some of our styles.

### Using Tailwind CSS

Tailwind CSS is a utility-first CSS framework. This means that instead of writing CSS classes like `.my-class` and `.my-other-class`, you write classes like `.my-class .my-other-class`. This is a little different than what you might be used to, but it's actually pretty easy to get used to. Let's take a look at a simple example:

```html
<div class="bg-gray-100 p-4 rounded-lg">
  <h1 class="text-2xl font-bold">Hello, World!</h1>
  <p class="text-gray-500">This is a paragraph.</p>
</div>
```

In the above example, we're using Tailwind CSS to add a background color, padding, and rounded corners to a `div` element. We're also using Tailwind CSS to add a title and a paragraph to our `div`. The `bg-gray-100` class adds a light gray background to our `div`. The `p-4` class adds 1rem of padding to our `div`. The `rounded-lg` class adds rounded corners to our `div`. The `text-2xl` class makes our title text 2x the default size. The `font-bold` class makes our title text bold. The `text-gray-500` class makes our paragraph text a medium gray. Pretty simple, right?

### Change the Blog Theme to Make Our Blog Pretty Again

So my blog articles look pretty ugly. Paragraphs are no longer neatly spaced apart. A lot of little things just basically broke. Let's fix that.

You'll notice at the head of your blog articles, there's a `layout` variable. This is the file that Astro looks at to apply a given layout to your blog article. Let's open up `src/layouts/BlogPost.astro` and start exploring ways we can style our blog posts.

At the top of our BlogPost.astro layout, we have the following:

```html
<html lang="en">
	<head>
		<BaseHead title={title} description={description} />
		<style>
			.title {
				font-size: 2em;
				margin: 0.25em 0 0;
			}
			hr {
				border-top: 1px solid #ddd;
				margin: 1rem 0;
			}
		</style>
	</head>
  ...
</html>
```

This style tag will apply to everything in our blog post. We can add additional style tags and use Tailwind CSS to style our blog posts. Importantly, Tailwind CSS styles need a `lang="postcss"` attribute on the style tag. Let's add a new style tag to our BlogPost.astro layout, just below the existing style tag, and remember to add a `lang="postcss"` attribute to it:

```html
<html lang="en">
	<head>
		<BaseHead title={title} description={description} />
		<style>
			...
		</style>
    <style lang="postcss">
      /* Add your Tailwind CSS styles here */
    </style>
	</head>
  ...
</html>
```