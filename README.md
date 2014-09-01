# tutorial-slides

Tutorial Slides for SOEN-422 Fall 2014

## Setting Up the Development Environment

The development environment is based on a Centos 7 environment managed by Vagrant.

### Pre-Requisites

* [Vagrant](http://www.vagrantup.com)
* [ChefDK](http://downloads.getchef.com/chef-dk/)

Once Vagrant and the ChefDK are installed, you must install the vagrant-berkshelf plugin for Vagrant which allows the use of Berkshelf to manage cookbooks for provisioning the virtual machine, and the vagrant-omnibus plugin which installs chef on the vm allowing it to be provisioned.

```bash
vagrant plugin install vagrant-berkshelf
vagrant plugin install vagrant-omnibus
```

### Create the Development Environment

The creation of the development environment is automated by Vagrant. Simply run the following:

```bash
vagrant up
```

from the root directory of this project.

Once the virtual machine is provisioned, login to the vm:

```bash
vagrant ssh
```

Create and activate a virtualenv

```bash
mkvirtualenv soen-422-tutorial-slides
```

Install the dependencies

```bash
pip install -r /vagrant/requirements.txt
```

### Building the Slides

To build the slides run:

```bash
md2remark src
```

This will generate an output directory with html files for each slide.

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.