## Ansible works:
* In ansible we are calling desired state in _yaml_ format. which is called _ playbook_
[preview]   (D:\Notes\AnsibleZone\images\images1.png)

* SSH connection should be running and python as well on both control server and  node.

* for every task need to do in automation first we need to know how to do it in manual process.

 * Ansible instalation steps:

 sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
ansible --version

* check connection from control serve to node

## ansible -i <inventory> --private-key jpmc.pem -u ubuntu -m ping all

* if we have different flavor of server ,, then we need to  add in inventory like _ ansible_user= centos_ 

## how to make ansible towards our deployment 

  * _ playbook -> play -> task -> one module_  for does the work..

* Ansible has lot of modules..which it will help us automate the deployment 

ansible has bunch of modules to work..

## create apache server on ununtu mechine 

* First we need to check with manual 
'''
  sudo apt update 
  sudo apt install apcahe -y

  ###apache.yaml

  ---
- name: apache
  hosts: all
  become: yes
  tasks: 
    - name: update ubuntu packages and install apache server
      apt: 
        name: apache2
        update_cache: yes
        state: present
#####        

* to make this execution we need to give inventory, private key and   yaml file name.

*  When you can playbook many times ..it wont change any thing ..only first  time it will be change ,, next time onwards it wont show any thing ... The is _ idempotant_













