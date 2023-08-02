# My Athena Site :D

Hello! If you've stumbled upon this (or more likely, I showed you what this is because I got excited), you're currently looking at the code for a website hosted by MIT through something called AFS, a distributed file system. Details on how to make one for yourself can be found [here](http://kb.mit.edu/confluence/x/Ep47).

## How to Make a Similar Website

Ensure you have the following programs installed on your computer:

- [Git](https://git-scm.com/)
- [Go](https://go.dev/)
- [Hugo](https://gohugo.io/)

I used the Shell theme, which can be found [here](https://themes.gohugo.io/themes/hugo-theme-shell/) or [here](https://github.com/Yukuro/hugo-theme-shell). Follow the instructions found on either website (the Github site will probably be the most updated/accurate though).

## How to Publish

These are instructions for future me, so that I don't forget.

 1. Pull the repository and edit whatever you have to change. If you want, edit `./static/.htaccess.mit` file and follow instructions [here](http://kb.mit.edu/confluence/x/ApMBCQ) to create access priviledges.
 2. Run `hugo server -w -D` to test your changes locally. If it looks fine, *make sure to check if the URL would work on the remote server*. If so, proceed.
 3. Run `hugo` (or alternatively, to save space, `hugo --minify`) to build the website. All static website files, such as `index.html` should be present in `./public/`.
 4. SSH into Athena using `ssh KERB@athena.dialup.mit.edu` (and do all the log-in stuff), navigate to the remove website folder located at `~/www/` and delete all files currently present by using `rm -r ./*`.
 5. Back in your local machine, copy all files to the remote website folder using the command `scp -r ./public/ KERB@athena.dialup.mit.edu:~/www/`.

Consider automating this in the future using Github Actions?
