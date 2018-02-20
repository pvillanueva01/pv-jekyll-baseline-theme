# Baseline Theme for Jekyll sites

## Dependencies

- Homebrew 1.5.3 (https://brew.sh/) | brew update  brew -v
- Ruby 2.5.0 (https://www.ruby-lang.org/en/downloads/) | ruby -v
- Ruby Gems 2.7.5 (https://rubygems.org/pages/download) | gem -v
- Bundler 1.16.0 | bundle update  bundle -v
- NPM 5.6.0 (https://docs.npmjs.com/cli/update) | npm -v   npm update -g
- Node 9.5.0 (https://nodejs.org/) | node -v
- Jekyll 3.7.2 | jekyll --version
- Yarn 1.3.2 (https://yarnpkg.com/lang/en/docs/install/) | yarn --version


## Add Bootstrap source files into project folder

https://simpleit.rocks/how-to-add-bootstrap-4-to-jekyll-the-right-way/

- yarn install
- yarn add bootstrap@4.0.0
- yarn add jquery@>=3.0.0
- yarn add popper.js@^1.12.3

- Adding new SASS load paths in config


### Import Bootstrap SCSS files into main.scss

- include overrides in libs/_vars.scss

### Theme uses autoprefixer support for css

https://github.com/vwochnik/jekyll-autoprefixer


## Add Font-awesome into project

https://fontawesome.com/get-started

- current version: 5.0.6
- Download from site

a. add to list of scripts to be minified (large file size)
b. add path in config, import into main.scss
c. include overrides in libs/_vars.scss 


## Asset Building

https://github.com/tkareine/jekyll-minibundle

- yarn add uglify-js (to include in node_modules)

- For js assets to minify as a bundle, they need to be in same directory


## Theme includes breadcrumbs

https://simpleit.rocks/how-to-create-breadcrumbs-with-hierarchical-categories-in-jekyll/

Use layout "default-breadcrumb", see folder "sub" for example on page/posts usage


## Theme uses responsive-images

https://github.com/wildlyinaccurate/jekyll-responsive-image

- Be sure to include imagemagick first: 

check version:  convert -version

brew install imagemagick@6

brew link imagemagick@6 --force

- Set templates on _includes folder
- Use responsive_image_block tag with front-matter variables
- In order for the image to be resized, start with a larger size asset


## To use this theme template in your project

- Start by adding your info in '_config.yml' for site/social settings
- '_layouts/default.html is the starter layout template, site works with nested layouts 
- Reorder or remove sections in layouts as needed
- DO NOT change these _includes: analytics, breadcrumbs, head, responsive-image


## To apply updates or make changes, use own branch

- create a hotfix branch off of Master branch
- create a new directory in your development environment. Something like myhotfix.local
- cd into that directory and add the remote branch (assuming branch is called hotfix)

`cd myhotfix.local`

- Use SorceTree or command line to pull that branch into the directory.
- make changes in local enviroment
- build '_site' with local config
- To test locally

`bundle exec jekyll build`

`bundle exec jekyll serve --watch`

Go to: http://127.0.0.1:4000/  or http://localhost:4000/ and verify changes


## Build for production deployment

`bundle exec jekyll build --config=_config_prod.yml`


### Push changes up to git repo

- Add and commit files to git using SorceTree or command line


### Merge branch with Master branch. 

** Make sure there are no conflicts, and there are usually conflicts!**
- Do the merge step on the git website.

## To push to production 

For Jekyll sites we SFTP the _site directory to production server.

** Do not move the files to production unless you have built for production. Meaning if you did not complete this step then do it now:

`bundle exec jekyll build --config=_config_prod.yml`

Copy the _site directory over to production. Do not copy anything else over.

Verify changes online and log out of production server
