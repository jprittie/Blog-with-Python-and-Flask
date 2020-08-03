## Blog CRUD Application with Flask
### Built with Python, the Flask microframework, a MYSQL database, flask-mysqldb and the Jinja 2 templating engine.

### Project description:
* A user will be able to register an account and log in
* Registered users will be allowed to create, edit and delete a blog post
* Any visitor to the site will be able to view the blog posts written by all registered users

### Implementation:
* Database interactions are handled by flask-mysqldb
* Passwords are hashed with werkzeug.security
* Sessions are tracked with Flask's sessions package
* The front-end code is built with the Jinja 2 templating engine, and flask-bootstrap for styling

### To build this project:
* Run `git clone https://github.com/jprittie/flask-blog-app`.
* Have MySQL installed and running, and create a database and tables:
    * `CREATE DATABASE blog_db`
    * `USE blog_db`
    * `CREATE TABLE user(user_id int auto_increment, first_name varchar(20), last_name varchar(20), username varchar(20) unique, email varchar(30) unique, password varchar(100), primary key(user_id));`
    * `CREATE TABLE blog(blog_id int auto_increment, title varchar(100), author_id int, body varchar(1000), primary key (blog_id), foreign key (author_id) references user (user_id));`
* Update `db.yaml` with your MySQL password
* Install pipenv via `pip3 install pipenv`
* Create a virtual environment with `pipenv shell`
* Install dependencies from the Pipfile with `pipenv install`
* Navigate to the project root and run `python3 app.py`.

### To use this project:
* Open a browser tab and go to `localhost:5001`.

### Planned improvements:
* Create database models with Flask-SQLAlchemy
* Seed initial data