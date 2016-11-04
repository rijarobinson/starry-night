#Starry Night Site Database (Udacity Item Catalog Project)
###(In fullfillment of Udacity's Full Stack Developer Program)

The Starry Night Database was developed as part of Udacity's Full Stack Developer Nanodegree. It contains the front and back end code for a system designed to share data on great stargazing sites. The purpose of this project was to develop a database and functions that would pass the requirements of the Item Catalog project.

##Table of Contents
 * [Functionality](#functionality)
 * [Structure Overview](#structure-overview)
 * [Technologies](#technologies)
 * [Folders & Files](#folders-files)
 * [Libraries & Modules](#libraries-modules)
 * [Using the Software](#using-software)

<a id="functionality"></a>
##Functionality
The *Starry Night Database* contains functionality for adding, editing, and deleting sites (as well as states for Administrator privilige) for logged in users (restricted to record creator). The database also contains a State table that is loaded upon initilization, and the administrator is automatically designated with the first user. There is a mapping component that will translate addresses to latitude and longitude and provide a map for each site. Commonly used queries are stored as Python functions. The application has the ability to browse data without being logged in. The site utilizes Google and Facebook login APIs for authorization/authentication.
<a id="structure-overview"></a>
##Structure Overview

| Table         | Description                               | Key(s)                                    |
| ------------- | ----------------------------------------- | ----------------------------------------- |
| User (t)      | User data stored from logins              | id                                        |
| State (t)     | Manually loaded on initialization of app  | id, user_id (foreign)                     |
| Site (t)      | Data on location and description of sites | id, state_id (foreign), user_id (foreign) |
<a id="technologies"></a>
##Technologies

| Tool Used  | Purpose                                         | Notes                                       | About         |
| ---------- | ----------------------------------------------- | ------------------------------------------- | ------------- |
| Windows OS | developer platform                              | Virtual Machine (VM) used to simulate Linux | [More info](http://www.microsoft.com) |
| VirtualBox | software to run virtual machine                 | Configured to run Linux server              | [More info](https://www.virtualbox.org/wiki/VirtualBox) |
| Vagrant    | software to configure/manage VM                 | Shares files between host computer & VM     | [More info](https://www.vagrantup.com/about.html) |
| GitHub     | provide configuration instructions for VM       | Fork & clone Udacity repo (link below)      | [More info](https://en.wikipedia.org/wiki/GitHub) |
| Git Bash   | run commands from VM                            | Provides Unix-Style terminal                | [More info](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) |
| SQLite     | database for persistant data storage            | Runs on Virtual Machine (VM)                | [More info](https://sqlite.org/) |
| SQLAlchemy | allows interaction with the SQLite DB           | Run commands in Python file                 | [More info](http://www.sqlalchemy.org/) |
| Python     | language used to program functions              | Python files detailed below                 | [More info](https://www.python.org/about/) |
| Flask      | Python Microframework                           | Allows use of templates and Jinja2 commands | [More info](http://flask.pocoo.org/) |
| Google Maps API | Interface for utilizing Google Maps        | Translate address to geocode and get maps   | [More info](https://developers.google.com/maps/) |
| Google Oauth API | Interface for utilizing Google Login      | Allows secure Login using G+ account        | [More info](https://developers.google.com/maps/) |
| Facebook Oauth API | Interface for utilizing Facebook Login  | Allows secure Login using FB account        | [More info](https://developers.google.com/maps/) |
| JavaScript | Language for client-side scripts                | See code for script functions               | [More info](https://www.javascript.com/) |
| Bootstrap | Framework for front end                          |                                             | [More info](http://getbootstrap.com/) |
| CSS       | Language for styling web pages                   |                                             | [More info](http://www.w3schools.com/css/css_intro.asp) |
| HTML      | Language for structuring web pages               |                                             | [More info](http://www.w3schools.com/html/html_intro.asp) |
| JSON      | Data Interchange Format                          | App creates and utilizes JSON datasets      | App[More info](http://www.json.org/) |

<a id="folders-files"></a>
##Folders & Files

| File                          | Purpose                                   | Notes                                       |
| ----------------------------- | ----------------------------------------- | ------------------------------------------- |
| database_setup.py             | db schema                                 | Run once to create database objects         |
| add_states.py                 | run to add state data to appliction       | Run once to create state data               |
| client_secrets.json           | file used by G+ login API                 |  |
| fb_client_secrets.py          | file used by FB login API                 |  |
| main.py                       | core code for application                 | Run to start up web server application (local port 8000) |
| templates/addState.html       | add a state (admin only)                  |  |
| templates/deletesite.html     | delete a site (site owner only)           |  |
| templates/deleteState.html    | delete a state (admin only)               |  |
| templates/editsite.html       | edit site (site owner only can edit)      |  |
| templates/editState.html      | edit a state (admin only)                 |  |
| templates/header.html         | displays main screen and log in/out links |  |
| templates/login.html          | login screen                              |  |
| templates/main.html           | main template                             |  |
| templates/newsite.html        | add a site with state already attached    |  |
| templates/newsitenostate.html | add site and assign a state               |  |
| templates/singleSite.html     | displays information on a single site     |  |
| templates/site.html           | shows sites within a state                |  |
| templates/states.html         | main page                                 |  |
| static/green_6in.jpg          | Login screen image                        |  |
| static/styles.css             | CSS file with styles                      |  |
| static/sun_290ppi.jpg         | App header image                          |  |

<a id="libraries-modules"></a>
##Libraries & Modules
| Library or Module | Purpose                                  |
| ----------------- | ---------------------------------------- |
| psycopg2          | API for PostgreSQL db use                |
| bleach            | used to clean input of malicious scripts |
<a id="using-software"></a>
##Using the Software
**To use the software**

1.  Install [Git](https://git-scm.com/downloads) in order to use Git Bash Unix-Style terminal.
2.  Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads). No need for the extension pack or SDK. Do not launch after install.
3.  Install [Vagrant](https://www.vagrantup.com/downloads.html).
4.  Fetch the [GitHub repository](https://github.com/udacity/fullstack-nanodegree-vm) created for the project by first Forking, and then getting the URL from GitHub for cloning (use HTTPS).
5.  Open **Git Bash** and cd to the desired directory for the application.
6.  Run "git clone PASTE_CLONED_PATH_FROM_GITHUB_HERE fullstack". This creates a directory called "fullstack" within your selected folder as well as the vagrant configuration.
7.  Replace the stock *tournament.py* and *tournament.sql* files with the two files in the "vagrant/tournament" folder of the same name from this repository. (The files provided by Udacity are blank, pre-project completion files.)
8.  Launch the Virtual Machine by running "vagrant up" in the vagrant directory ("vagrant halt" stops the VM).
9.  Run "vagrant ssh" to log into the virtual machine ("exit" will log you off).
10.  Run "cd /vagrant/tournament" if necessary to switch to the tournament directory.
11.  Run "psql" to run the querying software.
---ADD SECTION TO RUN DATABASE FILE AND CREATE STATES, FIRST USER LOGGED IN WILL BE OWNER OF STATE LIST

13.  At "vagrant=>", run "\i tournament.sql" to create the database, tables, and views and connect to the tournament database. If you would like to see a list of the tables, run "\dt". For other commands you can use in psql, check [here](http://postgresguide.com/utilities/psql.html). Note that if you are connected to the database, you will see "tournament=>". If you don't see this (after the initial creation of tables), you can connect using "\c tournament".
15.  Quit psql with "\q" and run "tournament_test.py" to see the tests run on the *tournament.py* file.

Refer to [this page](https://udacity.atlassian.net/wiki/display/BENDH/Vagrant+VM+Installation) from Udacity for additional install details and screen shots.

**To customize the files**
Feel free to modify your copy of *tournament.py* and run *tournament_test.py* to see how this affects the outcomes of the test. You can use print statements within *tournament.py* to troubleshoot your code.

Stubs and test file were provided by [Udacity](http://www.Udacity.com). Additional instruction on Back End Development is available by signing up for a class on their site. No code was directly copied and pasted, but resources such as [Stack Overflow](http://www.stackoverflow.com) and were used for guidance. Additional enhancements by Marija Robinson.

I welcome any feedback on this project at marija@springmail.com.