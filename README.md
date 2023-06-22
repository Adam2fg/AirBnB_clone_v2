<<<<<<< HEAD
<center> <h1>HBNB - The Console</h1> </center>

This repository contains the initial stage of a student project to build a clone of the AirBnB website. This stage implements a backend interface, or console, to manage program data. Console commands allow the user to create, update, and destroy objects, as well as manage file storage. Using a system of JSON serialization/deserialization, storage is persistent between sessions.

---

<center><h3>Repository Contents by Project Task</h3> </center>

| Tasks | Files | Description |
| ----- | ----- | ------ |
| 0: Authors/README File | [AUTHORS](https://github.com/justinmajetich/AirBnB_clone/blob/dev/AUTHORS) | Project authors |
| 1: Pep8 | N/A | All code is pep8 compliant|
| 2: Unit Testing | [/tests](https://github.com/justinmajetich/AirBnB_clone/tree/dev/tests) | All class-defining modules are unittested |
| 3. Make BaseModel | [/models/base_model.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/base_model.py) | Defines a parent class to be inherited by all model classes|
| 4. Update BaseModel w/ kwargs | [/models/base_model.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/base_model.py) | Add functionality to recreate an instance of a class from a dictionary representation|
| 5. Create FileStorage class | [/models/engine/file_storage.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/_ _init_ _.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/__init__.py) [/models/base_model.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/base_model.py) | Defines a class to manage persistent file storage system|
| 6. Console 0.0.1 | [console.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/console.py) | Add basic functionality to console program, allowing it to quit, handle empty lines and ^D |
| 7. Console 0.1 | [console.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/console.py) | Update the console with methods allowing the user to create, destroy, show, and update stored data |
| 8. Create User class | [console.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/user.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/user.py) | Dynamically implements a user class |
| 9. More Classes | [/models/user.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/user.py) [/models/place.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/place.py) [/models/city.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/city.py) [/models/amenity.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/amenity.py) [/models/state.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/state.py) [/models/review.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/review.py) | Dynamically implements more classes |
| 10. Console 1.0 | [console.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/justinmajetich/AirBnB_clone/blob/dev/models/engine/file_storage.py) | Update the console and file storage system to work dynamically with all  classes update file storage |
<br>
<br>
<center> <h2>General Use</h2> </center>

1. First clone this repository.

3. Once the repository is cloned locate the "console.py" file and run it as follows:
```
/AirBnB_clone$ ./console.py
```
4. When this command is run the following prompt should appear:
```
(hbnb)
```
5. This prompt designates you are in the "HBnB" console. There are a variety of commands available within the console program.

##### Commands
    * create - Creates an instance based on given class

    * destroy - Destroys an object based on class and UUID

    * show - Shows an object based on class and UUID

    * all - Shows all objects the program has access to, or all objects of a given class

    * update - Updates existing attributes an object based on class name and UUID

    * quit - Exits the program (EOF will as well)


##### Alternative Syntax
Users are able to issue a number of console command using an alternative syntax:

	Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])
Advanced syntax is implemented for the following commands: 

    * all - Shows all objects the program has access to, or all objects of a given class

	* count - Return number of object instances by class

    * show - Shows an object based on class and UUID

	* destroy - Destroys an object based on class and UUID

    * update - Updates existing attributes an object based on class name and UUID

<br>
<br>
<center> <h2>Examples</h2> </center>
<h3>Primary Command Syntax</h3>

###### Example 0: Create an object
Usage: create <class_name>
```
(hbnb) create BaseModel
```
```
(hbnb) create BaseModel
3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb)                   
```
###### Example 1: Show an object
Usage: show <class_name> <_id>

```
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
[BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
(hbnb)  
```
###### Example 2: Destroy an object
Usage: destroy <class_name> <_id>
```
(hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
** no instance found **
(hbnb)   
```
###### Example 3: Update an object
Usage: update <class_name> <_id>
```
(hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
(hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
[BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729889), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
(hbnb)
```
<h3>Alternative Syntax</h3>

###### Example 0: Show all User objects
Usage: <class_name>.all()
```
(hbnb) User.all()
["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571128115b', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

###### Example 1: Destroy a User
Usage: <class_name>.destroy(<_id>)
```
(hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
###### Example 2: Update User (by attribute)
Usage: <class_name>.update(<_id>, <attribute_name>, <attribute_value>)
```
(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", name "Todd the Toad")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'name': 'Todd the Toad', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
###### Example 3: Update User (by dictionary)
Usage: <class_name>.update(<_id>, <dictionary>)
```
(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
<br>
=======
# AirBnB_clone_v2: MySQL, deploy web static, web framework

![hbnb](https://camo.githubusercontent.com/a0c52a69dc410e983b8c63fa4aa57e83cb4157cd/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f696e7472616e65742d70726f6a656374732d66696c65732f686f6c626572746f6e7363686f6f6c2d6869676865722d6c6576656c5f70726f6772616d6d696e672b2f3236332f4842544e2d68626e622d46696e616c2e706e67)

## Table of Contents

* [Description](#description)
* [Purpose](#purpose)
* [Requirements](#requirements)
* [File Descriptions](#file-descriptions)
* [Environmental Variables](#environmental-variables)
* [Usage](#usage)
* [Bugs](#bugs)
* [Authors](#authors)
* [License](#license)

## Description

**hbnb** is a full-stack clone of the web application [AirBnB](https://www.airbnb.com/). This clone was built in four iterative phases. This version includes completion of Phase 1 from [AirBnB_clone_v1: Console and web static](https://github.com/bchen528/AirBnB_clone_v1) plus Phase 2, which has three parts: 1) adding a MySQL database storage system and mapping models to a database table using object relational mapping, 2) deploying web static by creating and configuring a web server using Fabric, and 3) converting static HTML page into a dynamic HTML page using Flask and Jinja2.

### Part 1: Add a MySQL database storage system
![mysql_diagram](https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step2.png)

### Part 2: Deploy web static with Fabric
![web_static_deployment](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/288/aribnb_diagram_0.jpg?cache=off)

### Part 3: Build a web framework with Flask
![webframwork](https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step3.png)

## Purpose
The purpose of Phase 2 is to learn how to:
* create a MySQL database
* use ORM
* map a Python class to a MySQL table
* handle 2 different storage engines in same codebase
* use environmental variables
* deploy code on a server
* use Fabric for executing local or remote shell commands, uploading/downloading files, prompting the running user for input, or aborting execution. Fabric is taking care of all network connections (SSH, SCP etc.): it's an easy tool for transferring files and executing commands from local to a remote server.
* manage Nginx configurations
* build a web framework with Flask
* define routes in Flask
* create HTML response in Flask using a template
* create dynamic template with Jinja2
* display data from MySQL database in HTML

## Requirements
* All files compiled with Ubuntu 14.04 LTS
* Documentation
* Organized files in proper folders (i.e. CSS files should be in `styles` folder)
* Python unit tests for all files
* Use SQLAlchemy 1.2.x and MySQL 5.7
* All files must be pep8 and shellcheck compliant

## File Descriptions
  **Note:** Below highlights only new file additions for Phase 2. For Phase 1 file descriptions, click [here](https://github.com/bchen528/AirBnB_clone_v1).
  * [console.py](console.py) - command interpreter from Phase 1 that includes updated `do_create` function that allows object creation with given arameters with syntax `<key name>=<value>`
  * [setup_mysql_dev.sql](setup_mysql_dev.sql) - script that prepares a MySQL development server for the project
  * [setup_mysql_test.sql](setup_mysql_test.sql) - script that prepares a MySQL test server for the project
  * [0-setup_web_static.sh](0-setup_web_static.sh) - Bash script that sets up web servers for `web_static` deployment
  * [1-pack_web_static.py](1-pack_web_static.py) - a Fabric script that generates a .tgz archive from the contents of the `web_static` folder
    * `do_pack` - generates a .tgz archive from the contents of the `web_static` folder using Fabric
  * [2-do_deploy_web_static.py](2-do_deploy_web_static.py) - a Fabric script (based on 1-pack_web_static.py) that distributes an archive to web servers
    * `do_deploy` - distributes an archive to web servers
    * `do_pack` - generates a .tgz archive from the contents of the `web_static` folder using Fabric
  * [3-deploy_web_static.py](3-deploy_web_static.py) - a Fabric script (based on 2-do_deploy_web_static.py) that creates and distributes an archive to my web servers 
    * `deploy` - creates and distributes an archive to web servers
    * `do_deploy` - distributes an archive to web servers
    * `do_pack` - generates a .tgz archive from the contents of the `web_static` folder using Fabric
  * [models](models) - contains models for relevant AirBnB objects
    * [`__init__.py`](models/__init__.py) - switch to file storage or database storage modes
    * [base_model.py](models/base_model.py) - class BaseModel, parent class that will take care of initialization/serialization/deserialization of future instances
      * `__init__` - initialize instance attributes
      * `__str__` - returns formatted string representation of instance
      * `__repr__` - returns string representation of instance
      * save - updates `updated_at` attribute for new instance
      * to_dict - returns dictionary representation a BaseModel object
    * [user.py](models/user.py) - class User
    * [city.py](models/city.py) - class City
    * [state.py](models/state.py) - class State
    * [place.py](models/place.py) - class Place
      * `reviews` - get list of Review instances with place_id (equals current Place.id)
      * `amenities` getter - returns list of Amenity instances based on the attribute amenity_ids that contains all Amenity.id linked to the Place
      * `amenities` setter - adds an Amenity.id to attribute amenity_ids if obj is an instance of Amenity
    * [review.py](models/review.py) - class Review
    * [amenity.py](models/amenity.py) - class Amenity
  * [tests](/tests/) - unit test files
  * [engine](models/engine) - contains storage engines
    * [`__init__.py`](/models/engine/__init__.py) - empty `__init__.py` file for packages
    * [file_storage.py](/models/engine/file_storage.py) - class FileStorage; serializes instances to JSON file and deserializes from a JSON file
      * `all` - returns the dictionary `__objects`
      * `new` - sets in `__objects` the obj with key `<obj class name>.id`
      * `save` - serializes `__objects` to the JSON file (path: `__file_path`)
      * `reload` - deserializes the JSON file to `__objects`
      * `delete` - delete object from `__objects` if exists
      * `close` - call reload
    * [db_storage.py](/models/engine/db_storage.py) - class DBStorage; 
      * `__init__` - initalize instances
      * `all` - return dictionary of instance attributes
      * `new` - add new object to current database session
      * `save` - commit all changes of the current database session
      * `delete` - delete from the current database session obj if not None
      * `reload` - create all tables in database and current database session
      * `close` - close session
* [web_flask](web_flask) - contains Flask, templates, and static files
  * [`__init__.py`](web_flask/__init__.py) - import Flask and create a Flask instance
  * [0-hello_route.py](web_flask/0-hello_route.py) - script that starts a Flask web application where route `/` displays 'Hello HBNB!'
  * [1-hbnb_route.py](web_flask/1-hbnb_route.py) - script that starts a Flask web application where route `/` displays 'Hello HBNB~' and route `/hbnb` displays 'HBNB'
  * [2-c_route.py](web_flask/2-c_route.py) - script that starts a Flask web application where route `/` displays 'Hello HBNB!', `/hbnb` displays 'HBNB', `/c/<text>` displays 'C' followed by the value of the text variable (replace underscore `_` symbols with a space ` `
  * [3-python_route.py](web_flask/3-python_route.py) - script that starts a Flask web application where route `/` displays 'Hello HBNB!', `/hbnb` displays 'HBNB', `/c/<text>` displays 'C' followed by the value of the text variable (replace underscore `_` symbols with a space ` `, `/python/(<text>)` displays 'Python ', followed by the value of the text variable (replace underscore `_` symbols with a space ` `) where the default value of `text` is 'is cool'
  * [4-number_route.py](web_flask/4-number_route.py) - script that starts a Flask web application where route `/` displays 'Hello HBNB!', `/hbnb` displays 'HBNB', `/c/<text>` displays 'C' followed by the value of the text variable (replace underscore `_` symbols with a space ` `, `/python/(<text>)` displays 'Python ', followed by the value of the text variable (replace underscore `_` symbols with a space ` `) where the default value of `text` is 'is cool', `/number/<n>` displays '`n` is a number' only if n is an integer
  * [5-number_template.py](web_flask/5-number_template.py) - script that starts a Flask web application where route `/` displays 'Hello HBNB!', `/hbnb` displays 'HBNB', `/c/<text>` displays 'C' followed by the value of the text variable (replace underscore `_` symbols with a space ` `, `/python/(<text>)` displays 'Python ', followed by the value of the text variable (replace underscore `_` symbols with a space ` `) where the default value of `text` is 'is cool', `/number/<n>` displays '`n` is a number' only if n is an integer, `/number_template/<n>` displays an HTML page only if `n` is an integer
  * [6-number_odd_or_even.py](web_flask/6-number_odd_or_even.py) - script that starts a Flask web application where route `/` displays 'Hello HBNB!', `/hbnb` displays 'HBNB', `/c/<text>` displays 'C' followed by the value of the text variable (replace underscore `_` symbols with a space ` `, `/python/(<text>)` displays 'Python ', followed by the value of the text variable (replace underscore `_` symbols with a space ` `) where the default value of `text` is 'is cool', `/number/<n>` displays '`n` is a number' only if n is an integer, `/number_template/<n>` displays an HTML page only if `n` is an integer, `/number_odd_or_even/<n>` displays an HTML page only if `n` is an integer where `H1` tag includes 'Number: `n` is `even|odd`' in `BODY` tag
  * [7-states_list.py](web_flask/7-states_list.py) - script that starts a Flask web application where route `/states_list` displays an HTML page with `H1` tag: “States”, `UL` tag: list of all State objects present in DBStorage sorted by name (A->Z), `LI` tag: description of one `State: <state.id>: <B><state.name></B>`
  * [8-cities_by_states.py](web_flask/8-cities_by_states.py) - script that starts a Flask web application where route `/cities_by_states` displays an HTML page with `H1` tag: “States”, `UL` tag: list of all State objects present in DBStorage sorted by name (A->Z), `LI` tag: description of one `State: <state.id>: <B><state.name></B>`, `LI` tag: description of one `City: <city.id>: <B><city.name></B>`
  * [9-states.py](web_flask/9-states.py) - script that starts a Flask web application where route `/states` displays an HTML page with `H1` tag: “States”, `UL` tag: list of all State objects present in DBStorage sorted by name (A->Z), `LI` tag: description of one `State: <state.id>: <B><state.name></B>`; route `/states/<id>`displays an HTML page where if a State object is found with this id: `H1` tag: “State: ”, `H3` tag: “Cities:”, `UL` tag: with the list of City objects linked to the State sorted by name (A->Z), `LI` tag: description of one `City: <city.id>: <B><city.name></B>`; Otherwise: `H1` tag: “Not found!”
  * [10-hbnb_filters.py](web_flask/10-hbnb_filters.py) - script that starts a Flask web application and defines route `/hbnb_filters` to display an HTML page like below:
  ![6-index.html_part0](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/10-hbnb_filters_0.jpg)
  ![6-index.html_part1](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/10-hbnb_filters_1.jpg)
  ![6-index.html_part2](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/10-hbnb_filters_2.jpg)
  ![6-index.html_part3](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/10-hbnb_filters_3.jpg)
  * [100-hbnb.py](web_flask/100-hbnb.py) - script that starts a Flask web application and route `/hbnb` displays an HTML page like below:
  ![8-index.html_part0](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/100-hbnb_0.jpg)
  ![8-index.html_part1](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/100-hbnb_1.jpg)
  ![8-index.html_part2](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/100-hbnb_2.jpg)
  ![8-index.html_part3](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/100-hbnb_3.jpg)
  ![8-index.html_part4](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/100-hbnb_4.jpg)
  * [templates](web_flask/templates) - contains HTML files
    * [5-number.html](web_flask/templates/5-number.html) - number template
    * [6-number_odd_or_even.html](web_flask/templates/6-number_odd_or_even.html) - even/odd template
    * [7-states_list.html](web_flask/templates/7-states_list.html) - list of states template
    * [8-cities_by_states.html](web_flask/templates/8-cities_by_states.html) - list of cities by states template
    * [9-states.html](web_flask/templates/9-states.html) - list of states by id template
    * [10-hbnb_filters.html](web_flask/templates/10-hbnb_filters.html) - filters template
    * [100-hbnb.html](web_flask/templates/100-hbnb.html) - advanced filters template
  * [static](web_flask/static) - contains CSS and image files
    * [styles](web_flask/static/styles) - contains CSS files
      * [3-header.css](web_flask/static/styles/3-header.css) - header styles
      * [3-footer.css](web_flask/static/styles/3-footer.css) - footer styles
      * [4-common.css](web_flask/static/styles/4-common.css) - body styles
      * [6-filters.css](web_flask/static/styles/6-filters.css) - filter styles
      * [8-places.css](web_flask/static/styles/8-places.css) - places styles

## Environmental Variables
```
HBNB_ENV: running environment. It can be “dev” or “test” for the moment (“production” soon!)
HBNB_MYSQL_USER: the username of your MySQL
HBNB_MYSQL_PWD: the password of your MySQL
HBNB_MYSQL_HOST: the hostname of your MySQL
HBNB_MYSQL_DB: the database name of your MySQL
HBNB_TYPE_STORAGE: the type of storage used. It can be “file” (using FileStorage) or db (using DBStorage)
```

## Usage
Run the following in your terminal:
```
user@ubuntu:~/AirBnB_v2$ curl -o 100-dump.sql "https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/100-hbnb.sql"
user@ubuntu:~/AirBnB_v2$ cat 100-dump.sql | mysql -uroot -p
Enter password: 
user@ubuntu:~/AirBnB_v2$ HBNB_MYSQL_USER=hbnb_dev HBNB_MYSQL_PWD=hbnb_dev_pwd HBNB_MYSQL_HOST=localhost HBNB_MYSQL_DB=hbnb_dev_db HBNB_TYPE_STORAGE=db python3 -m web_flask.100-hbnb
* Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
....
```
Open up a web browser and type `0.0.0.0:5000/hbnb`.
Voila! You should see a lovely webpage like below:
  ![8-index.html_part0](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/290/100-hbnb_0.jpg)

## Bugs

At this time, there are no known bugs.

## Authors
* Adam Abah | [GitHub](https://github.com/adam2fg) | [Twitter](https://twitter.com/themainog)

## License

**hbnb** is open source and free to download and use
>>>>>>> 48f0b20d6d6d5d594d64036557baf5fe49afc90b
