# Profiles REST API

Profile rest api course code.


# cmd for vagrant initialization
vagrant init ubuntu/bionic64

# cmd for starting vagrant everytime
vagrant up
vagrant ssh
cd /vagrant --> this is where all files are present

Vagrant configuration are available online. We are using ubuntu virtual machine to run our python
becuase python dependencies and stored in a differnet way and windows environment is not best place to develop python code.

For each python project we can start a vagrant config which is stored within the prject.
This way python projects are managed.

https://medium.com/cleverprogrammer/the-ultimate-guide-to-getting-started-with-vagrant-and-why-you-shouldve-been-using-it-like-a8116e18fdca

Vagrant will sync files from your windows folder into its virtual machine folder. To and fro.

RSA is a very simple mechanism for communication. You give out a public key for encryption and it can be decrypted by a key only you hold. This is a private key and never meant to be shared.


Before we can create a Django app we neet to create a python virtual environment for installing our dependencies on our vagrant machine. 

# cmd to create virtual env in the home directory of vagrant server. this way this environment will not be synced in our code and we can destroy and create it again whenever we want.
python -m venv ~/env

# cmd to activate virtual environment
source ~/env/bin/activate

if everything works fine then u will see (env) in terminal next to current folder name.
# cmd to deactivate virtual environment simply
deactivate

# save the required packages in requirements.txt and run cmd
pip install -r requirements.txt

# Now we can run django commands
# syntax django-admin.py startproject project_name directory(optional, but put dot for current directory or else it will create a subfolder.)
django-admin.py startproject profiles_project .

# Now we have a djaongo project, we need to create a django app. A single project can consist of multiple apps.
python manage.py startapp profiles_api


# cmd to run python dev server
python manage.py runserver 0.0.0.0:8000


# cmd for creating migration everytime you change your models
python manage.py makemigrations profiles_api

# run migration to create db

# create admin user from admin.py
python manage.py createsuperuser

http://localhost:8000/admin
