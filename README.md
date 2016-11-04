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
| JSON      | Data Interchange Format                          | App creates and utilizes JSON datasets      | [More info](http://www.json.org/) |

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
| Library or Module | Purpose                                                        |
| ----------------- | -------------------------------------------------------------- |
| oauth2client      | Python library for accessing resources protected by OAuth 2.0  |
| httplib2          | python library to interact with the web                        |
| flask             | Python framework (see above in [Technologies](#technologies))  |
| sqlalchemy        | allows for SQL queries                                         |
| random            | generates numbers (used in login route)                        |
| string            | allows for use of string functions                             |
| json              | provides tools for working with JSON data                      |
| requests          | allows for getting info from http request                      |

<a id="using-software"></a>
##Using the Software
**To use the software**

1.  Install [Git](https://git-scm.com/downloads) in order to use Git Bash Unix-Style terminal.
2.  Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads). No need for the extension pack or SDK. Do not launch after install.
3.  Install [Vagrant](https://www.vagrantup.com/downloads.html).
4.  Fetch the [GitHub repository](https://github.com/udacity/fullstack-nanodegree-vm) created for the project by first Forking, and then getting the URL from GitHub for cloning (use HTTPS).
5.  Open **Git Bash** and cd to the desired directory for the application.
6.  Run "git clone PASTE_CLONED_PATH_FROM_GITHUB_HERE fullstack". This creates a directory called "fullstack" within your selected folder as well as the vagrant configuration. You'll need to change the ports in the Vagrantfile to match that of the app: 8000.
7.  Add the files from this repository to your project.
8.  In **Git Bash** Switch to the directory containing your **main.py** file.
9.  Launch the Virtual Machine by running "vagrant up" ("vagrant halt" stops the VM).
10.  Run "vagrant ssh" to log into the virtual machine ("exit" will log you off).
11.  cd to /vagrant.
12.  Type "python database_setup.py" to add the database and tables.
13.  Type "python add_states.py" to add the states to the database.
14.  Type "python main.py" to start the server.
15.  You can test the app by running localhost on your web browser.

Refer to [this page](https://udacity.atlassian.net/wiki/display/BENDH/Vagrant+VM+Installation) from Udacity for additional install details and screen shots.

**To customize the files**
Feel free to modify your copy of the template files to customize to a different use. You will need to get your own API key for use of Google and Facebook login and the Maps APIs.

Instructions for this project were provided by [Udacity](http://www.Udacity.com). Additional instruction on Full Stack Application Development is available by signing up for a class on their site. No code was directly copied and pasted, but resources such as [Stack Overflow](http://www.stackoverflow.com) and Udacity's instructional videos were used for guidance.

Images on the app were retrieved from the [NASA Gallery](https://www.nasa.gov/multimedia/imagegallery/).

I welcome any feedback on this project at marija@springmail.com.