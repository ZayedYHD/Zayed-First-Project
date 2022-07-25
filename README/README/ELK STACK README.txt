## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly functional, in addition to restricting high traffic to the network.
-: What aspect of security do load balancers protect? What is the advantage of a jump box? An aspect of security that load balancers protect is that it is able to prevent the server from being overloaded which is optimizes producitivity. One advantage of a jump box is that it is highly secure and is able to prevent the Azure VMs from being exposed

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs.
-: What does Filebeat watch for? Filebeat is able to collect data about a file system.
-: What does Metricbeat record? Metricbeat is able to machines statistics data.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  |20.211.4.167| Linux            |
|  VM1     | Server   |20.211.4.167| Linux            |
|  VM2     | Server   |10.2.0.7    | Linux            |
|  ELK     | Server   |10.3.0.5    | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
-: Add whitelisted IP addresses 20.211.4.167

Machines within the network can only be accessed by .
-: Which machine did you allow to access your ELK VM? What was its IP address? The Jump Box is the machine allowed to acess the ELK VM the IP is 10.3.0.5.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |   20.211.4.167       |
| VM1      | NO                  |   10.0.0.4           |
| VM1      | NO                  |   10.0.0.4           |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-: What is the main advantage of automating configuration with Ansible? The advantage of this is that it is very simple to set up and use

The playbook implements the following tasks:
- SSH into the Jumpbox
- Attach to a anisble docker
- Created a ELK playbook
- Ran the playbook 
- SSH into the ELK VM to confirm if the server is up and running 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-
VM1 10.2.0.7
VM2 10.3.0.5

We have installed the following Beats on these machines:
-: Specify which Beats you successfully installed_  Metricbeat and Filebeat were successfully installed

These Beats allow us to collect the following information from each machine:
-: Filebeat will be used to collect log files. Also Metricbeat will be used to monitor machine statistics.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the file to filebeat-configuration.yml file to /etc/ansible/roles/files.
- Update the filebeat-configuration.yml file to include...
- Run the playbook, and navigate to http://20.78.18.251:5601 to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:
- _Which file is the playbook? Where do you copy it? filebeat-playbook.yml and copy it to /etc/ansible/roles
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?  /etc/ansible/hosts file
- _Which URL do you navigate to in order to check that the ELK server is running? http://20.78.18.251:5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._