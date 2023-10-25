+++
title = 'Hello There'
date = 2023-10-25T03:30:04-04:00
+++

![](/images/firstpost.jpg)

# Creating My Hugo Blog: A Step-by-Step Recap

Setting up a Hugo blog can be straightforward, but there are always little challenges along the way. Here's a brief overview of the steps and hiccups I encountered while setting up mine.

## 1. **Forking & Modifying the Etch Theme**
Before diving into the actual Hugo site setup, I started by forking the Etch theme for Hugo. Its a simple, easy to use theme, but I wanted to use the Dracula color theme with it. After making necessary modifications to the CSS files, I was ready to move on to the next step.

## 2. **Setting up the Hugo Site**
With the modified theme in hand, I initiated a new Hugo site using:
```bash
hugo new site blog
```

## 3. **Adding the Forked Theme**
After creating the new site, I wanted to add my forked Etch theme. Using Git submodules seemed to be the right way to go, but I encountered an error:
```
fatal: not a git repository (or any of the parent directories): .git
```
This was because I forgot to run 'git init' in the directory. I managed to resolve it and successfully added the theme to my site.

## 4. **Testing the Site Locally**
Once the theme was added, I ran Hugo's built-in server to test the site:
```bash
hugo server
```
I was pleased to see my changes were reflected correctly.

## 5. **Pushing to GitHub**
With everything looking good locally, the next step was to push the new Hugo blog to my GitHub repository. But I ran into another hiccup:
```
error: failed to push some refs to 'https://github.com/alexanderpareja/blog.git'
```
Not really sure what happened here, but I updated the submodule and it worked.
```bash
git submodule init
git submodule update
```
## 6. **Adding Images to Blog Posts**
One last thing to figure out was the right way to add images in markdown for my blog posts. With Hugo, it's pretty straightforward. The images can be stored in the `static` directory, and then referenced in the markdown file.

## **Conclusion**
All in all, setting up a Hugo blog was an enlightening experience. With the challenges came learning, and now I have a personalized blog, ready to be filled with content.
