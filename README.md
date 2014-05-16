#Vagrant *lemp + node + mongodb* Development setup

#Using Ansible

>**Linux - Nginx - MySQL - PHP - MongoDB - Nodejs**

============================================

THIS IS A COMBINATION OF VAGRANT + ANSIBLE

You can also use the ansible playbooks only.

Full Web Stack for deploying PHP and Nodejs Applications

============================================


## Requirements

- Vagrant (with Virtual Box)
- Ansible


## Installed Components
- Nginx
- Varnish
- Nodejs
	- Yo
	- Express
- PHP-FPM-55
	- Composer
- MySQL
	- phpMyAdmin
- MongoDB
	- RockMongo
- Redis
- Ruby


## Installation
####This setup is based and tested with Cent OS 6 x64 base box, with Vagrant 1.5.2 version

* Install Vagrant using using the [installation instructions](http://docs.vagrantup.com/v2/installation/index.html)

* Clone this repository
	    $ https://github.com/guillermojmc/vagrant-lnmmnp.git

* Add the box to vagrant. ( [direct link](https://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.5-x86_64-v20140504.box) )
		vagrant box add https://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.5-x86_64-v20140504.box --name centos64

* run vagrant (for the first time it should take up to 15-30 min)
	    $ vagrant up

* Setup Local Domain
	* Modify your host files for
			sudo vi /etc/hosts
	* Add the new record (IP)
			33.33.33.100 local.dev

* Web server is accessible with http://33.33.33.100 and http://local.dev (IP address can be changed in Vagrantfile)


## Ansible Configuration

- Note: If you encounter this error

		ERROR: problem running path_to/ansible/hosts --list ([Errno 8] Exec format error)

	do this:

		chmod -x path_to/ansible/hosts

- If you have run swap module, remember to comment # it if you need to do other provison module later


## Access
* Ports
	* 8080: nginx
	* 3306: mysql
	* 27017: mongodb
	* 6379: redis


* PhpMyAdmin is accessible with http://local.dev/phpmyadmin
	* Username: root
	* Password: root


* RockMongo is accessible with http://local.dev/rockmongo
	* Username: admin
	* Password: admin


* Shared folders
	* **host:** ```/nginx``` **guest:** ```/var/nginx/``` *easy config to nginx*
	* **host:** ```/web``` **guest:** ```/var/www/```


## Hints
####Startup speed
To speed up the startup process use ```$ vagrant up --no-provision```
