This project specifically sets up a virtual machine with the distro ubuntu on GCS. It also creates backups of the machines so that if something were to happen you could always roll back to a previous state to avoid data loss.
it also uses github actions to make it possible and the project also sets up a few programs automatically to secure the VM, I will talk more about it later

First things first you have to download terraform in order to run this yourself

First you need to run "terraform init" to start the terraform process to get things going which essentially starts up the process and you also have to have the tf files ready.

Second with "terraform plan" it will list changes that will happen to the files and it shows each change automatically so you can review and see what will happen

Third you need to now type "terraform apply" in order to essentially apply the changes to the infrastructure of the project.


Here is a screenshot of how the pipeline looks like https://gyazo.com/31269e506591d09459a6aa7d3d0c3ba1
