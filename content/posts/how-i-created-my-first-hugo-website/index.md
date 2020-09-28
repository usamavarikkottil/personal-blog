---
title: "How I created my first Hugo Website, A Beginner's Guide"
date: 2020-09-17T20:28:21+05:30
draft: false
description: "Guide to build a website in Hugo for complete beginners"
author: "Usama Varikkottil"
tags : [
    "markdown",
    "css",
    "html",
    "themes",
    "hugo",
    "blog"
]
categories : [
    "web development",
    
]
---

# How I created my first Hugo Website?

## What is Hugo?
Hugo is a simple tool if you want to create a blog website. It is one of the fastest static site generator. Speed, Flexibility and Simplicity makes it stand out among the other frameworks. Hugo's Go-based templating provides just the right amount of logic to build anything from the simple to complex.

## How to Install Hugo?
Hugo works on macOS, Windows, Linux, FreeBSD, and others.
Hugo Websites can be hosted on any server or your favorite CDN.

1. ### Installing on linux
```bash
sudo apt-get update
sudo apt-get install hugo
```
For more details about installation, Check [Hugo Official Website](https://gohugo.io/getting-started/installing/)

## How to build Our First Website Using Hugo?

Before creating a hugo website, let's create a directory for storing everything related to hugo.

so here, we are creating a folder called `Hugo`. Open Terminal and enter below command to create a new folder `Hugo` in your current directory. 

```bash
mkdir Hugo
cd Hugo
```
### 1. Let's create our hugo website by entering below command in the terminal.

```bash
hugo new site blog-test
```
![create-new-site-in-hugo](/images/how-i-created-my-hugo-website/1-mkdir-new-site.png)

We have now created our first website called `blog-test`. 

To make our website look awesome, we want to use a Hugo theme. You can find many Hugo themes here in [themes.gohugo.io](https://themes.gohugo.io/). 

( We will use a theme used to create this website. You can find it [here](https://themes.gohugo.io/devise). )

### 2. Download the theme from GitHub and add it to our site’s themes directory by entering below commands.
```bash
cd blog-test
git init
git submodule add https://github.com/austingebauer/devise.git themes/devise
```

![add-new-theme-in-hugo-website](/images/how-i-created-my-hugo-website/2-git-init-git-submodule-add.png)

### 3. Next, open the `config.toml` file in the root of our `blog-test` site and set the theme: by adding below line to the `config.toml` file.

```toml
theme = "devise"
```
![set-new-theme-in-hugo-website](/images/how-i-created-my-hugo-website/3-theme=devise.png)

### 4. We can check what we've made so far, by running `server` command.
```bash
hugo server
```
![start-hugo-local-server](/images/how-i-created-my-hugo-website/4-hugo-server.png)
Open Browser and go to the address shown on the terminal. In our case it is http://localhost:1313 .
![hugo-website-hugo-first-look](/images/how-i-created-my-hugo-website/5-website-first-look.png)

Since we have not created any posts yet, we would see only a page with a good design and no content. So We can try creating a new post.

### 5. Create a new post by entering:

```bash
hugo new posts/my-first-post.md
```
This will create a new `markdown` file under the directory content/posts/my-first-post.md

![hugo-website-create-new-post](/images/how-i-created-my-hugo-website/6-create-new-post---draft-value-false.png)


### 6. Open newly created file and add our content into that file.
        
Below is an example for a content. Add this code into the end of the file `my-first-post.md`.
```html
# This is our new file main header
paragraph for main header section goes here...

### This is a sub header
paragraph for sub header section goes here...
```
and in the file set the `draft` value to `false`  

![add-content-into-hugo-post](/images/how-i-created-my-hugo-website/7-first-post.png)

### 7. Run the server again to check our website.
```bash
hugo server
```
Hugo will auto refresh whenever we make changes to any file in our website, so We don't need to re-run our server every time.

Open Browser and go to the address http://localhost:1313 .
We are now able to see our newly created post.

### 8. Create a new repository in github.

To make our website live we want to upload our website files into github first. Let's create a new repository and copy repository link.
If you don't know to do that go over [here](https://google.com/search?q=create%20a%20new%20github%20repository).

My repository link is https://github.com/usamavarikkottil/blog-test .

### 9. Push our Website files into github.

On the previous terminal session, enter below commands.
```bash
git add --all
git commit -m "initial commit"
git remote add origin https://github.com/usamavarikkottil/blog-test.git
git push -u origin master
```
![git-commit-hugo](/images/how-i-created-my-hugo-website/8-git-commit--add-origin.png)

Replace my repository URL on the above command (3rd line) with your repository URL.
![git-push-hugo](/images/how-i-created-my-hugo-website/9-git-push.png)
### 10. Hosting Hugo Website on Netlify.

We are now done with putting everything into github. We've already tested the website on our local server. Next, to make our website live, we should host it somewhere else. We are going to use [Netlify](https://app.netlify.com/) to make our website work on the web.

   * Sign in to your [Netlify](https://app.netlify.com/) Account, and click on` New Site from Git`.
   * Select `Github` Option and Authorize.
   * Select the repository we just created before.
   ![netlify-website-from-github-hugo](/images/how-i-created-my-hugo-website/10-netlify-select-repo.png)
   * Input Build command as "`hugo`" and Publish Directory "`public`".
   * Click on "` Advanced Settings `" and add `key` "HUGO_VERSION" and `value` to our hugo version value. In my case it is 0.74.3 . 

        Enter below command on your terminal to get your hugo version.
        ```bash
        hugo version 
        ```

![netlify-build-command-for-hugo-website](/images/how-i-created-my-hugo-website/11-add-env-variable-and-deploy.png)
   * Click on "`Deploy site`".
   * Once it finishes deployment we would be provided a link to our website.
   

![netlify-hugo-website-deploy-finish](/images/how-i-created-my-hugo-website/12-finish-deploy.png)
   * Copy this link and paste it on `config.toml` as value of `baseURL` parameter.
   * After that, Enter the below commands in the terminal.

```bash
git add --all
git commit -m "add baseURL"
git push -u origin master
```

![add-baseURL-hugo-config-toml](/images//how-i-created-my-hugo-website/14-add-base-url-git-push.png)

### 13. Final website
![netlify-hugo-final-website-look](/images/how-i-created-my-hugo-website/13-final-website.png)

#### First Post

![netlify-hugo-final-website-post-look](/images/how-i-created-my-hugo-website/15-final-website-post-1.png)

---

## How to edit my hugo website details?
