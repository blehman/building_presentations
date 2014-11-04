Building Presentations
======================

Let's create an easily sharable presentation via gh-pages! 

To start, make sure that [node.js](http://nodejs.org/) is installed.
## Build scaffolding: [Yeoman](http://yeoman.io/)
I view Yeoman as an organized makefile of sorts that sets up dependencies in packages.json,
bower.js, ect. When this generator runs, it bascially builds a scaffolding for
the presentation in reveal.js. 

First we need to install Yoeman.
<pre>
npm install -g yo
</pre>

We next need to install [Generator-reveal](https://www.npmjs.org/package/generator-reveal). Reveal allows us to turn markdown into a slide deck.
<pre>
npm install -g generator-reveal
</pre>

Finally, we run a simple command to execute Yeoman:
<pre>
yo
</pre>

Choose reveal in the menu.  
![](https://github.com/blehman/building_presentations/blob/master/imgs/run_Reveal.png?raw=true)

Answer a few questions and eventually you'll see the job finish:   
![](https://github.com/blehman/building_presentations/blob/master/imgs/job_Complete.png?raw=true)

##View presentation locally:
<pre>
grunt
</pre>

##View presentation publicly:
Bower is the front end dependency manager, but the bower files are
ignored by github by default. So we need to remove `bower_components` from the
.gitignore file before preceeding. Hence, my `.gitignore` file only
contains the following lines:
<pre>
node_modules
dist
\*.log
.sass-cache
index.html
</pre>

The following commands will allow you to *view the project on gh-pages*:
<pre>
git commit -am 'starting the presentation'
git push
git checkout -b gh-pages
git push origin gh-pages
</pre>

Then visit [userName.github.io/repoName](userName.github.io/repoName)
replacing *userName* and *repoName* with the appropriate values.

##Editing the presentation
#####slides directory
The `slides` directory contains two types of files:
- `list.json` - this file is the order of the slides.
- `.md` files - these files are the slides.  

#####customization
The index.html file is built by grunt from a template each time bower is
run, which means that you must edit `template/_index.html` to change
the css.

Many options exist for changing the css such as the theme:
- Go to `bower_components/reveal.js/css/theme/` and look at the options.
- The starting theme is `default.css`.
- Edit `template/_index.html` with the desired theme.



