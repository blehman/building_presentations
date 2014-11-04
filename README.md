Building Presentations
======================

Helpful tools for creating easily sharable presentations. Make sure that [node.js](http://nodejs.org/) is installed.
## [Yeoman](http://yeoman.io/)
An organized makefile that sets up dependencies in packages.json,
bower.js. When this generator runs, it bascially builds a scafolding for
the presentation in reveal.js. 

<pre>
npm install -g yo
</pre>

We need to install [Generator-reveal](https://www.npmjs.org/package/generator-reveal) that is js that turn markdown into a slide deck.

<pre>
npm install -g generator-reveal
yo
</pre>

insert photo: run_Reveal.png

####What are you going to talk about? 
Title
####What version should we put in the package.json file? 
version

Insert photo: job_Compelte.png

View the presentation:
<pre>
grunt
</pre>

## How to make this work on github pages
Bower is the front end dependency manager, but the bower files are
ignored by github by default. So we need to remove `bower_components` from the
.gitignore file.

####gh-pages
<pre>
git commit -am 'starting the presentation'
git push
git checkout -b gh-pages
git push origin gh-pages
</pre>

Then visit [userName.git.io/repoName](userName.git.io/repoName)
replacing userName and repoName with the appropriate values.

##Editing the presentation
###slides directory
Contains two types of files:
- list.json - this file is the order of the slides.
- .md files - these files are the slides.  

###customization
The index.html file is built by grunt from the template/\_index.html 

Many options exist for changing things such as the theme:
- Go to `bower_components/reveal.js/css/theme/` and look at the options.
  The starting theme is default.css.



