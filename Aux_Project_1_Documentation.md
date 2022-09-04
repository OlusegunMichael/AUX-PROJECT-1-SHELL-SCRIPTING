# AUX PROJECT 1 - SHELL SCRIPTING
___
___
In this project, 20 new Linux users will be onboarded onto a server. A shell script will be created to automate this task. The script will reads a csv file that contains the first name of the users to be onboarded.
### **Project Start**
>### Installing Ubuntu’s package manager ‘apt’

#### To update a list of packages in package manager for Node like apt for Ubuntu the following set of commands are run;
* *`sudo apt update`* - (Updated Ubuntu)
* *`sudo apt upgrade`* - (Upgrades Ubuntu)
>### Create Project Folder and Usernames file
#### The following command were used to create a Project folder, a .csv file that contains the name of the new users.
* *`mkdir Shell && cd Shell`* - (Creates a Directory Shell and opens the directory)
* *`vi names.csv`* -(Creates a .csv file called names where all username will be stored)

![mkdir](./Aux_Project1%20Images/1.PNG)
![names](./Aux_Project1%20Images/Names.PNG)
>### Create a Group for the Users 
#### The following command were used to create and confirm the group has been created
* *`sudo groupadd developers`* - (Creates a group called developers)
* *`sudo grep developers /etc/group`* - (Confirm that the group has been created)

![mkdir](./Aux_Project1%20Images/1.PNG)
>### Create file for both the Public and Private ssh key
#### 2 new files are created to save the Public and the Privat SSH Keys.
* *`vi id_rsa`* - (Creates a file for the private key and the provided key is pasted)
* *`vi id_rsa.pub`* - (Creates a file for the public key and the provided key is pasted)

![id_rsa](./Aux_Project1%20Images/id_rsa.PNG)
![id_rsapub](./Aux_Project1%20Images/id_rsapub.PNG)
>### Create the Shell Script 
The created shell script newusers.sh is opened in vi editor  *`vi newusers.sh`* 

![script](./Aux_Project1%20Images/script1.PNG)
![script](./Aux_Project1%20Images/script2.PNG)

The file is made executable by setting Permission with  *`chmod +x newusers.sh.sh`*

![chmod](./Aux_Project1%20Images/chmod.PNG)

The executable script is ran using  *`sudo ./newusers.sh`*

To View the created user and confirm they have been added to the home directory and assigned to group developers *`ls -la /home`* command is used.

![users](./Aux_Project1%20Images/users%20created.PNG)
 >### Confirming the status of the Users
To check is the new users has .ssh file command *`sudo ls -la /home/Mary`* is used also if it contains the authorized keys  *`sudo ls -la /home/Mary/.ssh`*

![ssh](./Aux_Project1%20Images/ssh.PNG)
![keys](./Aux_Project1%20Images/key.PNG)

>### Access the EC2 Instance form the terminal with one of the newly created users using the **.pem key**
         
On a diferent terminal,**(git bash in vscode)** a .pem file **auxproject.pem** in **C:\Users\USER\Downloads directory** in my local computer, is created and the private ki is copied into it using *`vi auxproject.pem`* 
Access User **Mary & Megan** as and example via the terminal using a split windoe, acces **C:\Users\USER\Downloads** directory where the newly created file **"auxproject.pem key"** is saved. 
To access user Mary via the ssh the following command was used *`ssh -i "auxproject.pem" Mary@ec2-13-40-82-26.eu-west-2.compute.amazonaws.com`*

![Mary](./Aux_Project1%20Images/Mary.PNG)]
![Mary](./Aux_Project1%20Images/Mary1.PNG)
![Megan](./Aux_Project1%20Images/Megan.PNG)
  

