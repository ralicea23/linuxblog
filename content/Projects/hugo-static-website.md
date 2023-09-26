---
title: "Hugo Static Website on GitHub"
date: "2023-08-01"
description: "Introduction to Hugo"
tags:
- linux
- hugo
- security
ShowReadingTime: "True"
toc: "true"
---

![New Linux User](/img/hugo.jpg)

Creating a static website with Hugo and hosting it on GitHub can seem daunting, but I'll break it down into simple steps that beginners can follow. By the end of this post, you'll have your static website up and running. Let's get started:
Step 1: Install Hugo

### First, you need to install Hugo, a popular static site generator. 

You can download it from the official website at [Hugo Themes](https://themes.gohugo.io/). Follow the installation instructions for your specific operating system.

### Step 2: Create a New Hugo Site

Now that you have Hugo installed, open your terminal or command prompt and run the following command to create a new Hugo site:
```
hugo new site my-website
```
Replace "my-website" with the name you want for your website.

### Step 3: Choose a Hugo Theme

Hugo offers a variety of themes to choose from. You can find themes on the Hugo Themes website. Pick a theme you like, and then navigate to your Hugo site's folder using the terminal:
```
cd my-website
```
Install the theme using Git. Replace theme-name with the name of your chosen theme:
```
git submodule add https://github.com/<theme-author>/<theme-name>.git themes/<theme-name>
```
### Step 4: Configure Your Site

Edit the Hugo configuration file (config.toml) to set up your site's basic information, like the title, author, and other settings. Open the config.toml file in a text editor:
```
nano config.toml
```
Replace "nano" with the text editor you prefer.

### Step 5: Create Content

Use Hugo to create content pages for your website. Run the following command to create a new post:
```
hugo new posts/my-first-post.md
```
This will generate a Markdown file for your first post. Edit this file to add your content.

### Step 6: Build Your Site

Generate the static website files using Hugo:
```
hugo server -w
```
This command processes your content and builds your site in a "public" folder.

### Step 7: Create a GitHub Repository

Go to GitHub and create a new repository for your website. Choose a name, and make it public or private as you prefer.

### Step 8: Initialize Git in Your Hugo Project

Initialize a Git repository in your Hugo project folder:
```
git init
```
### Step 9: Add and Commit Your Files

Add your Hugo project files to the Git repository:
```
git add .
```
Commit your changes:
```
git commit -m "Initial commit"
```
### Step 10: Push to GitHub

Link your local Git repository to the GitHub repository you created:
```
git remote add origin https://github.com/your-username/your-repo-name.git
```
Replace "your-username" and "your-repo-name" with your GitHub username and repository name.

Push your Hugo project to GitHub:
```
git push -u origin master
```
### Step 11: Enable GitHub Pages

Go to your GitHub repository settings, scroll down to the GitHub Pages section, and choose the "master branch" as your source. GitHub will now host your static website at https://your-username.github.io/your-repo-name/.

It may take a few minutes for your site to become live.

Congratulations! You've created a static website with Hugo and hosted it on GitHub. Now you can continue adding content and customizing your site as needed.

![New Linux User](/img/logo.svg)
