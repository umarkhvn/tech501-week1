# DevOps Day 3

- [DevOps Day 3](#devops-day-3)
  - [Creating a Virtual Machine on Azure](#creating-a-virtual-machine-on-azure)
    - [Create SSH Key](#create-ssh-key)
    - [Create VNET](#create-vnet)
    - [Create VM](#create-vm)
    - [Run VM on Bash](#run-vm-on-bash)
    - [Create a Bash Script for nginx](#create-a-bash-script-for-nginx)


## Creating a Virtual Machine on Azure

### Create SSH Key

* Go onto Git Bash and use command:  cat tech501-umar-az-key.pub to access SSH key
* Go on to Azure portal and SSH Keys.
* Chose Use Existing Key and paste key gen code into prompt.
* Use standard naming convention
  * E.g: tech501-umar-az-key
* Location should always be UK South
* Go on to Tags
  * First field is always: Owner
  * Second field is your name: Umar

### Create VNET

* Go on to Azure Portal and Virtual Networks
* Follow default configuration
* Create 2 subnets
  * Public with .pub extension and IP 10.0.2.0
  * Private without any extensions and IP 10.0.3.0
* Use standard naming convention
  * E.g: tech501-umar-subnet-vnet
* Follow same Tag protocol 

### Create VM

* Our virtual machine:
* Name: tech501-your_name-first-vm
* Region: UK South
* Security: standard
* Image (i.e. the OS that will go onto the machine): Ubuntu Pro 18.04 LTS Gen 2 [LTS means long term support for ~7 years]
* Size: Standard_B1s — 1 vcpu, 1 GiB [very important to set correctly because this impacts pricing]
* Administrator account: adminuser
* Use existing key pair stored in Azure (use the one with your name)
* Select inbound ports: allow HTTP and SSH traffic
* Disks tab:
* OS disk type: Standard SSD
* Networking tab:
* Virtual network: your named version
* Subnet: public-subnet
* Choose Delete public IP and NIC when VM is deleted option

### Run VM on Bash

* Connect VM via Portal and Connect
* Select Native SSH
* Copy and execute SSH command. 
  * Provide a path to your SSH private key file on your local machine: 
  * This will be our SSH key name we created earlier:
    * tech501-umar-az-key
    * We can then SSH to VM with the below command and copy to Bash: 
    * ssh -i tech501-umar-az-key adminuser@172.187.170.82
* If you have a passphrase, you will be prompted to enter it before entering your VM. 

### Create a Bash Script for nginx

* Once in your VM. We can create a script to run nginx:
* Run the command 'nano' followed by what you'd like to name your file with a .sh extension.
  * E.g: nano provision.sh
* Write a script in nano:
    *  To update:
        * sudo apt update
    * To upgrade:
        * sudo apt upgrade -y
    * To install nginx:
        * sudo apt install nginx -y
    * To restart nginx:
        * sudo systemctl restart nginx
    * To enable nginx:
        * sudo systemctl is-enabled nginx
* Ctrl + S to save the script
* Ctrl + X to exit nano
* Execute the script with ./ followed by the script name. In this example:
  * ./provision.sh
  * NOTE: You may need to change permissions before the script runs by executing chmod+x followed by the script name. 
    * E.g: chmod +x provision.sh
    * then you can run the script 
* To check if nginx is running on a browser, you can copy copy and paste HTTP://[your IP address]
  * Your IP address can be found anywhere on the Overview sections on Azure Portal