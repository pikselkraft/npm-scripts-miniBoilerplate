# Pikselkraft npm scripts
This portfolio uses the last web standards and focuses on quality, accessibility and workflow optimisation.

## Workflow and technologies

* HTML5 / CSS3
* Use the BEM and Atomic design methodologies
* NPM script

## Installation

> npm init
> npm install --save-dev

## Ressources

### Grid, reset, helpers (KNACSS)
http://www.knacss.com

KNACSS is a simple stylesheet with a reset, perfect to bootstrap a project with accessibility, performance and responsive web design in mind. It uses a grid named grillade.css and contains useful helpers.
It's made by the french web agency [Alsacreations.fr](http://alsacreations.fr)

## NPM script
The core basis of this boilerplate is NPM, the script manages all the workflow to improve quality, manage test and even the deployment.

### List of scripts

		"info": "echo 'npm as a build tool: ¦̵̱ ̵̱ ̵̱ ̵̱ ̵̱(̢ ̡͇̅└͇̅┘͇̅ (▤8כ−◦'",
		"fold:clean": "rm -R -rf dist",
		"fold:assets": "mkdir -p assets/{css,img,fav,js,typo}",
		"fold:dist": "mkdir -p dist/public/{css,img,fav,js,typo}",
		"fold:files": "cp -R -f assets/js assets/img assets/fav assets/typo  assets/*.html  assets/*.xml  assets/*.txt assets/*.json  assets/typo assets/CNAME dist/public/",
		"css:concat": "cat assets/css/*.css > dist/public/css/bundle.css",
		"css:comb": "csscomb dist/public/bundle.css",
		"css:minify": "cleancss dist/public/css/bundle.css -o dist/public/css/bundle.min.css",
		"build:css": "echo '=> build:css' && npm run css:concat && npm run css:comb && npm run css:minify",
		"img:min": "imagemin assets/img/*.jpg dist/public/img/*.jpg -p",
		"svg:clean": "svgo -f assets/img/icons",
		"svg:opt": "svgo -f assets/img",
		"svg:icons": "svgo -f assets/img/icons && svg-sprite-generate -d assets/img/icons -o dist/public/img/icons.svg",
		"js:lint": "jshint assets/scripts/*.js",
		"js:minify": "uglifyjs assets/js/*.js -o dist/public/js/*.js",
		"dist": "npm run fold:clean && npm run fold:assets && npm run fold:dist && npm run cp:files && npm run build:css",
		"watch": "watch 'npm run dist' assets/css/",
		"watch:nodemon": "nodemon -e css -x",
		"livereload": "live-reload --port 9091 dist/public",
		"browsersync": "browser-sync start --server --files 'dist/css/*.css, dist/js/*.js'",
		"server": "http-server dist/public/"

## Details

* Copy tasks
	* manage the creation of folders and copy the files in dist/public
* CSS tasks
  * Concat CSS files
  * Comb -> watch quality of the css
  * Minify -> minify the CSS
  * Combine all the tasks
* Img and svg tasks
  * Optimise of the images
  * Optimise SVG files (clean)
  * Optimise SVG files
  * Generate SVG sprite
* JS tasks
  * Inspect JS files quality
  * Minify JS files
* Dist: Build task, create folder, copy files, build css
* Dev tools
  * Watch
  * Livereload
  * Test server

## Liens utiles

* [**NPM**](https://www.npmjs.com)
* [Atomic css](http://bradfrost.com/blog/post/atomic-web-design/)
* [BEM css](http://getbem.com/introduction/)
* Website of KNACSS : http://knacss.com
  * [**Documentation**](https://github.com/raphaelgoetter/KNACSS/tree/master/doc)
  * [**Documentation**](https://github.com/raphaelgoetter/KNACSS/tree/master/doc)
  * On Alsacreations.com [FR]: ["KNACSS framework"](http://www.alsacreations.com/tuto/lire/1577-decouverte-du-framework-css-KNACSS.html)
