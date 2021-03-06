# A Virtual Machine for Ruby on Rails Application Development

## Introduction

This project automates the setup of a development environment for general Ruby on Rails application development. 

## Requirements

* [VirtualBox](https://www.virtualbox.org)

* [Vagrant](http://vagrantup.com)

* [Librarian Puppet](http://librarian-puppet.com/)



## How To Build The Virtual Machine

Building the virtual machine is this easy:

    host $ git clone https://github.com/pragmaticivan/vagrant_rails.git
    host $ cd vagrant_rails
    host $ librarian-puppet install
    host $ vagrant up

If the base box is not present that command fetches it first. 

    host $ vagrant ssh
    Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic-pae i686)
    ...
    vagrant@vagrantrailsbox:~$

Port 3000 in the host computer is forwarded to port 3000 in the virtual machine. This, applications running in the virtual machine can be accessed via localhost:3000 in the host computer.

## What's In The Box

* MySQL
* PostgreSQL
* RVM
* MongoDB
* Redis
* Elasticsearch

## Recommended Workflow

The recommended workflow is

* edit files in the host computer

* run within the virtual machine

## Database
* For mysql the default user is root: `mysql -u root`
* For postgresql the default user is postgres: `sudo -u postgres psql`



## Virtual Machine Management

When done just log out with and suspend the virtual machine

    host $ vagrant suspend

then, resume to hack again

    host $ vagrant resume

Run

    host $ vagrant halt

to shutdown the virtual machine, and

    host $ vagrant up

to boot it again.

You can find out the state of a virtual machine anytime by invoking

    host $ vagrant status

Finally, to completely wipe the virtual machine from the disk **destroying all its contents**:

    host $ vagrant destroy # DANGER: all is gone

Please check the [Vagrant documentation](http://docs.vagrantup.com/v2/) for more information on Vagrant.