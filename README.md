# Virtualbox Box for socialpy

**Vagrant** and **Virtualbox** were so valuable during my development of Django [socialpy](https://github.com/kevin-chen-15/socialpy) project. Python virtualenv helps a lots in dealing various versions of Python packages, but Vagrant and Virtualbox truely allow me to control what I have at the OS level (global libraries and packages). When things went bad, and it did in coutless times, I could build another VM so quickly to try it again. Short turnaround time is just so valueable in terms of software development.

# Instructions

## Create Ubuntu Server 14.04 LTS VM, then SSH into this VM
This is just standard **Vagrant** usage.
1. *vagrant up*
2. *vagrant ssh*

## Install Global Software Packages
1. *sudo apt-get install git*
2. *sudo apt-get install python-setuptools*
3. *sudo apt-get install python-pip*
4. *sudo apt-get install python-virtualenv*
5. *sudo apt-get install python-dev*
6. *sudo apt-get install libjpeg-dev libfreetype6-dev*
## Build Python Virtualenv
7. *virtualenv env/django*
8. *source env/django/bin/activate*
9. *cd /vagrant*
10. *git clone https://github.com/kevin-chen-15/socialpy*
11. *cd /vagrant/socialpy*
12. *pip install -r requirements.txt*
## Run Django Lightweight Web Server
13. *python manage.py runserver 0.0.0.0:8000*

# Notes
+ Step 6: install the necessary libraries for Python Pillow - libjpeg-dev, libfreetype6-dev, zlib1g-dev and libpng12-dev.
+ Step 7: build a Python virtualenv at env/django directory.
+ Step 8: activate the Python virtualenv.
+ Step 9: changed to the home of the shared directory between host and guess OS. Typically, within guess OS, it is at /vagrant directory.
+ Step 10: clone socialpy project.
+ Step 11: change to the working directory of socialpy project.
+ Step 12: install all the Python package requirements of [socialpy](https://github.com/kevin-chen-15/socialpy) application.
+ Step 13: the default IP (localhost:8000) won't work in a VM environment since the browser is run at the host OS. The IP needs to be all interfaces (0.0.0.0), and the port **8000** has to be forwarded in **Vagrantfile** too, so the browser can reach this web server within the guess OS.
# socialpybox
