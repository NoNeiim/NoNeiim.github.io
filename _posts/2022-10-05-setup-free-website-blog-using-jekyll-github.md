---
title: Setting up a website using Jekyll and Github pages
date: 2022-10-04 17:00:00 -500
categories: [hosting,website]
tags: [website,blog,notes,wiki]
---

>## Jekyll
>Jekyll is a piece of software that transforms your plain text files into HTML that later can be served on a webserver for the world to
see :)
>
>## Github pages
>Github pages is a service from, your guessed it, Github. Github pages lets you host a website(or a repository) to the public, free of charge.

You can do alot with Jekyll, but in this case our goal is to setup a blog as quick as possible. 

To speed things along we won´t be designing anything ourselves, instead we will be using a pre-made template for our Blog. 

### Create a Github account / Log into your Github account
> [Link to Github.com](https://www.github.com)

### Copy the Quick starter template
> [Link to Chirpy starter template](https://github.com/cotes2020/jekyll-theme-chirpy#quick-start)

When you click on the Chirpy Starter link on the page above, you will copy that repository to your own. Make sure you name the new repository as follows:


> [your username].github.io

Make sure your copy of the repository is "public".<br><br>
The naming of the repository is only necessary if we are hosting our site on Github pages, and because we are hosting on Github, it is necessary :)

Great, so now you should have a copy of the "Chirspy starter" repository on your own Github repo.

Now it's time to install Jekyll and clone our newly copied repo to our local machine.

### Installing Jekyll
Jekyll is written in Ruby, so first of all we need to install Ruby on our machine, alongside Ruby we need some extra dependencies that Jekyll needs to work properly. Run the following in your Terminal:

```bash
sudo apt update 
sudo apt install ruby-full build-essential zlib1g-dev git
```
Now that we have Ruby installed, we can use Ruby Gems to install Jekyll:

```bash
gem install jekyll bundler
```

### Clone your github repo to your local machine
```bash
git clone url to your Chirpy repo
```
You find this url on the green button inside the repo on Github.

Next we need to install the dependencies needed for Chirpy/Jekyll to work:

```bash
cd into the repo you created with git clone above
bundle
```

### Create a post
Now we should be able to create out first blogpost. Open the repository with your favorite text editor, i use Visual Code.

Once you have the the folder open, locate the "_post" folder.

Inside this folder you can create your first post by making a new .md file.

Make sure you name the file as follows:

> YEAR-MONTH-DAY-how-to-write-a-blog.md

Inside the file you need to specify a few things, you can copy/paste from me just to try it out:

```
---
title: Setting up a website using Jekyll and Github pages
date: 2022-10-04 17:00:00 -500
categories: [hosting,website]
tags: [website,blog,notes,wiki]
---

>## Jekyll
>Jekyll is a piece of software that transforms your plain text files into HTML that later can be served on a webserver for the world to
see :)
>
>## Github pages
>Github pages is a service from, your guessed it, Github. Github pages lets you host a website(or a repository) to the public, free of charge.
```

### Push to Github
Before we push our site to Github, checkout the config.yml file and make necessary changes.

Now lets push our new site to Github:

```git
git add .
git commit -m "my first push"
git push
```
In your Github account, checkout the Actions tab in your repo to see when your site has deployed, shouldnt take more than 2 minutes.

Once completed you should be able to visit:

> https://[your username].github.io
