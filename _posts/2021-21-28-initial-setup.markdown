---
layout: post
title:  "Initial Setup"
date:   2021-12-28 15:40:21 -0500
categories: website 
author: "Matt Nicotra"
---

We want to transition our website from a WYSIWYG hosting service to [GitHub Pages](https://pages.github.com/) because it will be cheaper (free). We also hope that it will enable us to share web maintenance duties more easily.

To set up the site I first learned about GitHub pages and Jekyll from [this excellent set of youtube videos by Bill Raymond](https://www.youtube.com/watch?v=EvYs1idcGnM&list=PLWzwUIYZpnJuT0sH4BN56P5oWTdHJiTNq). 

Then, I did the following.

### Set up repo on GitHub

1. Created a repo called "[cnidofest-website](https://github.com/matthewnicotra/cnidofest-website)" in my GitHub account. The repo is empty, but that is okay because it will be filled with files from Jekyll soon.

2. Created a README.md file for the repo. Note: this establishes the "main" branch of the repo, which is what I will select in the next step.

3. Enabled the repo as be a GitHub Pages website by going to Settings > Pages, then selecting "main" from the dropdown under **source**. I kept the folder at "/root", then clicked "save".

4. I also edited the "About" box (circled at top of screenshot below) to include the path to the site for ease of access later on.

![Screenshot of the repo page ](path-to-image.png)

5. After a few minutes, an "Environment" appeared at the bottom of the <code> tab for the repo, which meant that GitHub had build the page (using Jekyll). Right now, Jekyll just uses the README.md in place of an index.html page, so the site is pretty bland:

![Screenshot of the site](path-to-image2.png)

### Clone repo and build site with Jekyll

Now, I am going to clone the repo and use Jekyll to create the site. This will let me develop the site on my local computer before pushing it back to GitHub, where Jekyll will build the site for GitHub pages. 

I have already installed Jekyll on my computer.

1. On my laptop, I created a folder called `Sites`. I then moved into that folder and cloned the `cnidofest-website` directory.

```bash
cd Sites
git clone https://github.com/matthewnicotra/cnidofest-website.git
```

2. I then changed into this directory and used Jekyll to create a new site. The `bundle exec jekyll new` creates the new site, the `.` tells Jekyll to create the site in this directory, and the `--force` is used because Jekyll will balk at created a new site if there are files in the existing directory.

```bash
bundle exec jekyll new . --force
```

3. _This step was only required for me because, for some reason, I need to manually add webrick to jekyll. 

```bash
bundle add webrick
```

4. Now I can test the site by running 

```bash
bundle exec jekyll serve
```