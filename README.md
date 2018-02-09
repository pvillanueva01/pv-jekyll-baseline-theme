# UM Libraries (/kislak-center) Jekyll site

A Jekyll site for the Kislak Center

## To use this theme template in your project

- Start by adding your info in `_config.yml`
- In `_layouts/front.html` reorder or remove section as you prefer.


## To apply updates

- create a hotfix branch off of Master branch.
- create a new directory in your development environment. Something like myhotfix.local
- cd into that directory and add the remote branch. Assuming branch is called hotfix

`cd myhotfix.local`

`git remote add hotfix https://github.com/UMiamiLibraries/jekyll-kislak-center.git`

- Use SorceTree or command line to pull that branch into the directory.
- make changes in local enviroment
- build '_site' with local config
- To test locally

`bundle exec jekyll build`

`bundle exec jekyll serve --incremental`

Go to: http://127.0.0.1:4000/  or http://localhost:4000/ and verify changes.

## Build for production deployment

`bundle exec jekyll build --config=_config_prod.yml`

### Push changes up to git repo
- Add and commit files to git

`git add .`

`git commit -m "details about my changes" `

- push your branch to git

`git push hotfix hotfix`

### Merge branch with Master branch. 

** Make sure there are no conflicts, and there are usually conflicts!**
- Do the merge step on the git website.

## To push to production 

For Jekyll sites we SFTP the _site directory to production.

** Do not move the files to production unless you have built for production. Meaning if you did not complete this step then do it now:

`bundle exec jekyll build --config=_config_prod.yml`

SSH onto the production server and cd into /usr/local/www/jekyll/kislak-center

Copy the _site directory over to production. Do not copy anything else over.

Verify changes online and log out of production.
