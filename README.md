This project specifically sets up a virtual machine with the distro ubuntu on GCS. It also creates backups of the machines so that if something were to happen you could always roll back to a previous state to avoid data loss.
it also uses github actions to make it possible and the project also sets up a few programs automatically to secure the VM, I will talk more about it later
---------------------------------------
First things first you have to download terraform in order to run this yourself

First you need to run "terraform init" to start the terraform process to get things going which essentially starts up the process and you also have to have the tf files ready.

Second with "terraform plan" it will list changes that will happen to the files and it shows each change automatically so you can review and see what will happen

Third you need to now type "terraform apply" in order to essentially apply the changes to the infrastructure of the project.
--------------------------------------

Here is a screenshot of how the pipeline looks like https://gyazo.com/31269e506591d09459a6aa7d3d0c3ba1
--------------------------------------
Here is a screenshot of how the VM looks like in google cloud https://gyazo.com/84ca01d791de161fd1b1b489207390dbs
--------------------------------------
Now back to security. the project will install ufw, fail2ban, unattended-upgradeds,

First off we are gonna talk about ufw. It is a simple firewall that will on default deny all traffic in but allow all traffic out to enhance security. SSH is enabled so that people can remote in on the machine.

fail2ban will automatically  ban people from trying to ssh into the machine after a certain amount of tries so for example if someone tries to brute force into the machine after 3 attempts for example the vm will straight up block them from doing any more attempts for a certain period of time which will
make brute force attacks alot harder

unattended-upgrades, just as it sounds it automatically upgrades software on the VM when new patches comes out, it will make sure that as fast as possible to upgrade the program that get a new patch to avoid having them exploited
