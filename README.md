
# LinuxServerUdacity5

Public IP: 54.190.198.158
SSH port : 2200

Complete URL to the hosted web application : http://ec2-54-190-198-158.us-west-2.compute.amazonaws.com

Third paty installations:
PostgreSQL
Apache 2 
Mod_WSGI 

Steps:
Created Amazon LightSail instance -- ssh into the server per instructions.

ssh port change : 22 to 2200

Add custom TCP rule to allow 2200 under Networking Tab in the lightsail instance

Create user grader, sudo permissions and add grader ALL=(ALL:ALL) NOPASSWD:ALL
sudo nano /etc/sudoers : Change permission RootLogin to no
Test if you can get to the server 2200 and then disable 22
Create keypair using ssh-keygen and save it in ~/.ssh
mkdir .ssh in home/grader, update permissions and copy the create key pair's publick key(.pub contents) into authorized keys in home/grader/.ssh
Then ssh -i ~/.ssh/privateKeyFileName grader@publicIPofLightSailInstance
Start apache2 server and test if the server page responds
Then install postgresql and the other dependencies mentioned above 
Enable mod_wsgi
Create a database, replace db info in the files
Update client_secrets in Google console
Download new client_secrets.json and place it in the file

Locate ssh key for grader user
$ cat ~/.ssh/grader
