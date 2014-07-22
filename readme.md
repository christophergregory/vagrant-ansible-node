# Vagrant / Ansible / Node.js

## Dependencies

First, [download and install Vagrant](https://www.vagrantup.com/downloads).

After installation, ensure vagrant is installed using 

~~~
vagrant -v
~~~

I am also using the vagrant-hostsupdater and vagrant-vbguest plugins

~~~
vagrant plugin install vagrant-vbguest
vagrant plugin install vagrant-hostsupdater
~~~


Then, install Ansible using pip:

~~~
pip install ansible
~~~



## Vagrant Up

Clone this repo into your directory of choice, navigate to the directory containing the Vagrantfile and run the vagrant up command:

~~~
vagrant up
~~~


That's it! Vagrant will automatically setup a new virtual machine and ansible will provision it.