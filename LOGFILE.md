#GitHub new Repository
2014-04-06

> GitHub Pages are public webpages freely hosted and easily published through 
our site. You can create and publish them online using the Automatic Page Generator. 
If you prefer to work locally, you can use the GitHub for Mac and Windows apps, or the command line.

Pages are served over HTTP, not HTTPS. That doesn't make them inherently less secure, but it does mean that you shouldn't use them for sensitive transactions, like sending passwords or credit card numbers.

For more information, check out the GitHub Pages site, or the related documentation here on Help.  
Refer to https://github.com/legallj/legallj.github.io

##Create a new repository on the command line

	[bash] legallj@mercure : ~
	$ mkdir legallj.github.io

	[bash] legallj@mercure : ~
	$ cd /Users/legallj/legallj.github.io 

	[bash] legallj@mercure : ~/legallj.github.io
	$ git init
	Dépôt Git vide initialisé dans /Users/legallj/legallj.github.io/.git/

	[bash] legallj@mercure : ~/legallj.github.io
	$ git add README.md

	[bash] legallj@mercure : ~/legallj.github.io
	$ git commit -m "first commit"
	[master (commit racine) b9f2c07] first commit
	 1 file changed, 39 insertions(+)
	 create mode 100644 README.md

	[bash] legallj@mercure : ~/legallj.github.io
	$ git remote add origin https://github.com/legallj/legallj.github.io.git

	[bash] legallj@mercure : ~/legallj.github.io
	$ git push -u origin master
	Username for 'https://github.com': legallj
	Password for 'https://legallj@github.com': 
	Counting objects: 3, done.
	Delta compression using up to 4 threads.
	Compressing objects: 100% (2/2), done.
	Writing objects: 100% (3/3), 1.56 KiB | 0 bytes/s, done.
	Total 3 (delta 0), reused 0 (delta 0)
	To https://github.com/legallj/legallj.github.io.git
	 * [new branch]      master -> master
	La branche master est paramétrée pour suivre la branche distante master depuis origin.

##Check Web page

Open [page](https://github.com/legallj/legallj.github.io) --> Ok!

The create a GitHub User Pages [site](https://github.com/legallj/legallj.github.io/generated_pages/new)  
Page generation hangs --> FAILS! Give up

##Retry using Google Chrome web-browser
<span style='color:red;'>The problem comes from <strong>Safari</strong> which is 
no longer supported by GitHub.<br>Use <strong>Chrome</strong> instead and then 
page template is correctly applied to project.</span>

Follow the procedure at [Create Pages](https://help.github.com/articles/creating-pages-with-the-automatic-generator) 
and load the `README.md` file to populate the project Web page.

- After your Page is generated, you can get a local copy of its HTML code. 
If you generated a Project Page, fetch and check out the new `gh-pages` branch.
- Presently you generated a *User Page*, then the code lives in the `master` branch 
instead of the *gh-pages* branch, so just check out *master* and then pull.

There are the executed commands:

	[bash] legallj@mercure : ~/legallj.github.io
	$ git fetch origin
	remote: Counting objects: 15, done.
	remote: Compressing objects: 100% (12/12), done.
	remote: Total 14 (delta 2), reused 0 (delta 0)
	Unpacking objects: 100% (14/14), done.
	Depuis https://github.com/legallj/legallj.github.io
	   b9f2c07..5c9df7b  master     -> origin/master

	[bash] legallj@mercure : ~/legallj.github.io
	$ git checkout master
	Déjà sur 'master'
	Votre branche est en retard sur 'origin/master' de 1 commit, et peut être mise à jour en avance rapide.
	  (utilisez "git pull" pour mettre à jour votre branche locale)

	[bash] legallj@mercure : ~/legallj.github.io
	$ git pull origin master
	Depuis https://github.com/legallj/legallj.github.io
	 * branch            master     -> FETCH_HEAD
	Mise à jour b9f2c07..5c9df7b
	Fast-forward
	 images/bg_hr.png             | Bin 0 -> 943 bytes
	 images/blacktocat.png        | Bin 0 -> 1428 bytes
	 images/icon_download.png     | Bin 0 -> 1162 bytes
	 images/sprite_download.png   | Bin 0 -> 16799 bytes
	 index.html                   |  96 ++++++++++++++++++++++
	 javascripts/main.js          |   1 +
	 params.json                  |   1 +
	 stylesheets/pygment_trac.css |  70 ++++++++++++++++
	 stylesheets/stylesheet.css   | 423 +++++++++++++++++++++++...++++++++
	 9 files changed, 591 insertions(+)
	 create mode 100644 images/bg_hr.png
	 create mode 100644 images/blacktocat.png
	 create mode 100644 images/icon_download.png
	 create mode 100644 images/sprite_download.png
	 create mode 100644 index.html
	 create mode 100644 javascripts/main.js
	 create mode 100644 params.json
	 create mode 100644 stylesheets/pygment_trac.css
	 create mode 100644 stylesheets/stylesheet.css

Now the Web site is loaded into local repos: `~/legallj.github.io`  
And can be visible at [GitHub.io](http://legallj.github.io/) public site.  
Even the *avatar* portrait is now correctly loaded (only use PNG image).

##Update and Sync

Keeping your site up to date is easy so long as you keep both your local and remote code in sync with git. To do so:

Make some change and push to remote:

	$ git add .
	$ git commit -m '<some message>'
	$ git push -u origin master

Then keep local repos in sync:

	$ git pull origin master
