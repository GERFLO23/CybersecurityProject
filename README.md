## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

~/Github/CybersecurityProject/Diagrams/Homework_12.drawio

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - ~/Github/CybersecurityProject/Ansible/filebeat-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
- Load balancers can defend from DDos attacks.
- The benefit of a jumpbox is having stronger security and also manage other VM's. Its so closed the "gateway" with a strong door.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _Filebeat monitors the log files._
- _Metricbeat records the metrics and statistics from the operation system and from services running on the server._

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Elk-VM   |  VM      | 10.1.0.4   | Linux            |
| Web-1    |  VM      | 10.0.0.5   | Linux            |
| Web-2    |  VM      | 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 40.122.32.10

Machines within the network can only be accessed by __IP___.
- My Jumpbox has access to my ELK-VM, its IP is 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |      No             |     40.122.32.10     |
| Web-1    |      No             |     10.0.0.4         |
| Web-2    |      No             |     10.0.0.4         |
| Elk-VM   |      No             |     10.0.0.4         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _Ansible helps save time for IT administrators by automate configuration_

The playbook implements the following tasks:
- Install Docker
- Install python3-pip
- Install Docker python module

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
~/Github/CybersecurityProject/Images

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1
- Web-2

We have installed the following Beats on these machines:
- Filbeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat monitors the log files which we use to see what changes or messages the log files have received. 
- Metricbeat records the metrics and statistics from the OS, which helps us see the CPU or RAM usage 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ansible.cfg file to /etc/ansible.
- Update the host file to include the IPs addresses of the Web-servers
- Run the playbook, and navigate to azure to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- Copy the install-elk.yml and filebeat-playbook.yml file to /etc/ansible.
- Update the install-elk.yml and filebeat-playbook.yml file to include the machine you want use the playbooks on by changing the hosts name.
- Run the playbook, and navigate to http://[your.VM.IP]:5601/app/kibana to check that the installation worked as expected.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
