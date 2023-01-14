# Diego Temkin's Athena Site

Hello! If you've stumbled upon this (or more likely, I showed you what this is because I got excited), you're currently looking at the code for a website hosted by MIT (through something called AFS, or Athena File System). Details on how to make one for yourself can be found [here](http://kb.mit.edu/confluence/pages/viewpage.action?pageId=3907090).

## How to Make a Similar Website

Ensure you have the following programs installed on your computer:

 - [Git](https://git-scm.com/)
 - [Go](https://go.dev/)
 - [Hugo](https://gohugo.io/)

I used the Shell theme, which can be found [here](https://themes.gohugo.io/themes/hugo-theme-shell/) or [here](https://github.com/Yukuro/hugo-theme-shell). Follow the instructions found on either website (the Github site will probably be the most updated/accurate though).

## How to Publish

These are instructions for future me, so that I don't forget.

 1. Pull the repository and edit whatever you have to change.
 2. Run `hugo server -t hugo-theme-shell -w -D` to test your changes locally. If it looks fine, *make sure to check if the URL would work on the remote server*. If so, proceed.
 3. Run `hugo --theme='hugo-theme-shell'` to build the website. All static website files, such as `index.html` should be present in `./public/`.
 4. SSH into Athena using `ssh dtemkin@athena.dialup.mit.edu` (and do all the log-in stuff), navigate to the remove website folder located at `~/www/` and delete all files currently present by using `rm -r ./*`.
 5. Back in your local machine, go into the `./public/` folder using `cd public` and copy all files to the remote website folder using the SCP command `scp -r ./* dtemkin@athena.dialup.mit.edu:~/www/`.

Consider automating this in the future using Github Actions.
