.. title: Blogging with the  Nikola, IPython and Github
.. slug: blogging-with-the-nikola-ipython-and-github
.. date: 2016-08-06 16:25:45 UTC-04:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text


https://shankarmsy.github.io/posts/blogging-with-the-awesome-nikola-ipython-and-github.html

Problem 1: conda, virtual env doesn't work for me.

https://conda.io/docs/using/envs.html#create-an-environment

conda create -n blog python

jakehku blog $ conda create -n blog
Fetching package metadata ...........
Solving package specifications: 
Package plan for installation in environment /anaconda/envs/blog:

Proceed ([y]/n)? y

#
# To activate this environment, use:
# > source activate blog
#
# To deactivate an active environment, use:
# > source deactivate
#.

Deploying to GitHub

Nikola provides a separate command github_deploy to deploy your site to GitHub Pages. The command builds the site, commits the output to a gh-pages branch and pushes the output to GitHub. Nikola uses the ghp-import command for this.

In order to use this feature, you need to configure a few things first. Make sure you have nikola and git installed on your PATH.

Initialize a Nikola site, if you haven’t already.

Initialize a git repository in your Nikola source directory by running:

git init .
git remote add origin git@github.com:user/repository.git
Setup branches and remotes in conf.py:

GITHUB_DEPLOY_BRANCH is the branch where Nikola-generated HTML files will be deployed. It should be gh-pages for project pages and master for user pages (user.github.io).
GITHUB_SOURCE_BRANCH is the branch where your Nikola site source will be deployed. We recommend and default to src.
GITHUB_REMOTE_NAME is the remote to which changes are pushed.
GITHUB_COMMIT_SOURCE controls whether or not the source branch is automatically committed to and pushed. 
We recommend setting it to True, unless you are automating builds with 
Travis CI.
Create a .gitignore file. We recommend adding at least the following entries:

cache
.doit.db
__pycache__
output
If you set GITHUB_COMMIT_SOURCE to False, you must switch to your source branch and commit to it. Otherwise, this is done for you.

Run nikola 

github_deploy

. This will build the site, commit the output folder to your deploy branch, and push to GitHub. Your website should be up and running within a few minutes.

If you want to use a custom domain, create your CNAME file in files/CNAME on the source branch. Nikola will copy it to the output directory. To add a custom commit message, use the -m option, followed by your message.

git pull origin src --allow-unrelated-histories