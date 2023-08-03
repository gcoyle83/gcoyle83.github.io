---
layout: post
title:  "Notes on starting this site"
---

# Intro
Since this is my first blog and my first GitHub Pages website, I figure a good first blog post topic is how I went about setting up the website.

## Step 1 - Install Ruby and Jekyll
Following [these instructions](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll) from GitHub was *mostly* straightforward, with some necessary deviations: 

-  Download the [latest Ruby installer for windows](https://rubyinstaller.org/downloads/) and run the default settings. 
	-  The installer asks about specific install options and I just used the Enter button to indicate I didn't know.
	-  Per step two on [this page](https://jekyllrb.com/docs/installation/windows/), be sure to run the `ridk install` step on the last stage of the installation wizard, and `MSYS2 and MINGW development tool chain` from the resulting options.
-  Open a new command prompt and enter the following command to add the rubygems.org site to the approved list (or at least bypass the SSL certs): `gem source –a http://rubygems.org/`
-  Run any additional update commands that are suggested at the completion of the above step
-  Install Jekyll and Bundler with command `gem install jekyll bundler`
-  Check that Jekyll is installed with `jekyll -v`

## Step 2 - Setup git repo to host site
I chose to set this up using my `username.github.io` user website. After cloning the repo into a working directory on my local machine, I opted to host the site from a `gh-pages` branch (again from GitHub instructions):
```
$ git checkout --orphan gh-pages
# Creates a new branch, with no history or contents, called gh-pages, and switches to the gh-pages branch
$ git rm -rf .
# Removes the contents from your default branch from the working directory
```
Then in the repo settings for Pages, select the option to host the site from the `gh-pages` branch and `root` folder in order to use this branch as the site repository.

## Step 3 - Setup basic Jekyll site for repo
Then generate the initial site files using the following command:
```
$ jekyll new --skip-bundle .
# Creates a Jekyll site in the current directory
```
At this point there is an option to test the site locally, but repeated `CertificateFailureError` warnings related to SSL prevented successful local tests. Instead just pushing to the repo with `git push -u origin gh-pages` and using the runners there for testing (repo actions are set up automatically if all steps above are followed)

Continue following the rest of the GitHub tutorial instructions to complete the initial setup. 

## Step 4 - Edit site contents
Draw the rest of the owl.

**Next steps**
Per GitHub tutorial:
-  To add a new page or post to your site, see ["Adding content to your GitHub Pages site using Jekyll."](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll)
-  You can add a Jekyll theme to your GitHub Pages site to customize the look and feel of your site. For more information, see ["Adding a theme to your GitHub Pages site using Jekyll."](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)