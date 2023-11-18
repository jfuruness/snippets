[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
![Tests](https://github.com/jfuruness/backend/actions/workflows/tests.yml/badge.svg)

# backend

This package creates a FastAPI service to use as a backend for Dr. Herzberg's cybersecurity books with SQL as a database.

* [Description](#package-description)
* [Usage](#usage)
* [Installation](#installation)
* [Testing](#testing)
* [Development/Contributing](#developmentcontributing)
* [Credits](#credits)
* [Licence](#license)
* [TODO](#todo)

## Package Description


This package creates a FastAPI service to use as a backend for Dr. Herzberg's cybersecurity books with SQL as a database.

TODO: Add more docs

## Usage
* [backend](#backend)

After installing the server (please do so in a python environment) run:

```bash
backend
```

This should spin the server up at localhost:8000.
Navigate to localhost:8000/docs, which will load the swagger documentation.

Start with create_user.
Let's create a user called jfuruness@gmail.com with a password of password.
Set the role to student. First and last name don't matter.

Then let's "login".
To do this, go to the swagger docs at localhost:8000 and login with the user we just created.
Logging in will also set the login cookie for this user

Then we can logout simply by calling the logout endpoint, which will remove this cookie.


#### For developers: How to add a lab

Labs are placed within backend/backend/labs.
After seeding the lab, it is given a specific lab_template_id, which is later used in the LabTemplate subclass.
Each lab has a questions folder, a solutions folder, and a lab_template.py file containing a subclass of LabTemplate
LabTemplate must generate a unique lab for each student.
LabTemplate saves the seed used for this, along with the solution, and a few other items, which can then be used for each individual student.



## Installation
* [backend](#backend)

Install python and pip if you have not already.

Then run:

```bash
pip3 install pip --upgrade
pip3 install wheel
```

For production:

```bash
pip3 install git+https://github.com/jfuruness/backend.git
```

This will install the package and all of it's python dependencies.

If you want to install the project for development:
```bash
git clone https://github.com/jfuruness/backend.git
cd backend
pip3 install -e .[test]
```

To test the development package: [Testing](#testing)


## Testing
* [backend](#backend)

To test the package after installation:

```
cd backend
pytest backend
ruff backend
black backend
mypy backend
```

If you want to run it across multiple environments, and have python 3.9 installed:

```
cd backend
tox
```


## Development/Contributing
* [backend](#backend)

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Add an engine test if you've made a change in the simulation_engine, or a system/unit test if the simulation_framework was modified
5. Run tox (for faster iterations: flake8, mypy, and pytest can be helpful)
6. Commit your changes: `git commit -am 'Add some feature'`
7. Push to the branch: `git push origin my-new-feature`
8. Ensure github actions are passing tests
9. Email me at jfuruness@gmail.com

## Credits
* [backend](#backend)


Thanks to Dustin for the original implementation of this and to Amir for assisting in this independent study.

## License
* [backend](#backend)

BSD License (see license file)

## TODO
* [backend](#backend)

See Jira
