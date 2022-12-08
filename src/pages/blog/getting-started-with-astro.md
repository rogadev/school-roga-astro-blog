---
layout: "../../layouts/BlogPost.astro"
title: "Creating A Blog In Astro"
description: "How I created my developer blog using Astro"
pubDate: "November 25, 2022"
heroImage: "/astro-hero.jpg"
---

Creating a blog in Astro is surprisingly easy. I was able to get this blog up and running in less than an hour. I'm going to walk you through the steps I took to get this blog up and running.

## Step 1: Install Astro

If you're going to be using GitHub, I personally create my new repo first, then open the repo locally in VS Code to begin installing packages. Whatever floats your boat. When you're ready, the first step is to install Astro. You can do this by running the following command:

```bash
npm create astro@latest
```

Step through the prompts and you'll have a new Astro project up and running in no time. Here's what I chose:

```bash
? Where would you like to create your new project? > .
```

Entering `.` tells Astro you'd like to use the current project repository. If you'd like to create a new repository, you can do that by specifying the name of a new directory.

```bash
? What template would you like to use? > a personal website starter
```

This will create a new Astro project using the `Personal website starter` template. These options have changed over time, so if you're really not sure, or if you'd like to start with a blank slate, you can choose the `Just the basics (recommended)` template. They used to have a `Personal portfoio` template which has since been removed. It's a shame, because I really liked that template.

Next you'll be asked if you'd like to install the dependencies. I always choose `Yes` here.

```bash
? Would you like to install dependencies? > Y
```

Next, you'll be asked if you'd like to initialize a git repository. I typically initialize my repos before installing packages, so for me this is a `No` but you can choose `Yes` if you'd like.

```bash
? Would you like to initialize a git repository? > N
```

After that, you'll be asked if you'd like to setup TypeScript. You don't have to use TypeScript, but I *love* TypeScript, so I choose `Yes`.

```bash
? How would you like to setup TypeScript? > Strict (recommended)
```

That basically does it. One thing you'll notice is that VS Code probably doesn't know how to read your `.astro` files. You'll need [the Astro extension](https://marketplace.visualstudio.com/items?itemName=astro-build.astro-vscode) for this, so head over to the Marketplace and install that now.

Just like that, you're up and running. You can run `npm run dev` to start the dev server and you'll be able to see your new Astro site at `localhost:3000`. If you'd like to work in MDX files, you might also want to install an extension for that. I use [MDX](https://marketplace.visualstudio.com/items?itemName=unifiedjs.vscode-mdx).