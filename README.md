dev-env-provisioned
===================

A virtual developer environment to ease the development of the studentenportal project for Windows and MAC users.

The VirtualBox image that will be installed with Vagrant has everything preeinstalled so you can start developing in no time.

If you want to build your own vagrant machine from scratch follow the instructions of https://github.com/studentenportal/dev-env

Requirements
------------

Required programs:
- Virtualization software (VirtualBox or VMWare)
- Vagrant to setup the virtual machine

Installation instructions:

1. Install VirtualBox: https://www.virtualbox.org/wiki/Downloads
2. Install Vagrant: https://docs.vagrantup.com/v2/installation/

Setup Machine
-------------

1.  Setup the following folder structure by cloning the github repos:

    ```
    `-- <studentenportal project root>
        |-- web (https://github.com/studentenportal/web.git)
        `-- dev-env-provisioned (https://github.com/studentenportal/dev-env-provisioned.git)
    ```
2.  Switch to the dev-env-provisioned directory and start the machine:

    ```bash
    vagrant up
    ```
    Vagrant will automatically download the image and sync the `web` folder with `/srv/www`

3.  Connect to the VM via SSH and setup the environment:

    ```bash
    vagrant ssh
    ```

Setup Environment
-----------------

1.  Switch to the folder `/srv/www/studentenportal`
2.  Run the server inside the VM and allow external connections:

    ```
    python manage.py runserver 0.0.0.0:8000
    ```
    
3. Access the site via `localhost:8000`
4. Install missing SASS packages `sudo apt-get install ruby ruby-dev` and `sudo gem install compass`
5. Update packages `sudo pip install -r requirements.txt`

Install Test Data
-----------------
You can create test data manually with the django-admin (`localhost:8000/admin`).
There is more information to test data on the [main repo](https://github.com/studentenportal/web).

It is however far easier to install provided test data (fixtures).
Because the data of the registered users is confidential, we cannot provide the real data publicly. If you want to mirror the real data of the `studentenportal` simply contact us.

Loading fixtures into the database is pretty simple:

```
python manage.py loaddata /path/to/fixture.json
```

More information
----------------
https://github.com/studentenportal/web

