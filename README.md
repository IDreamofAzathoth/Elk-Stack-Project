## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Topolology of the Red_Team pentesting environment](https://github.com/IDreamofAzathoth/Elk-Stack-Project/blob/master/images/Red_Team_Network_Topology.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the [/etc/ansible/filebeat-playbook.yml](https://github.com/IDreamofAzathoth/Elk-Stack-Project/blob/master/etc/ansible/filebeat-playbook.yml) file may be used to install only certain pieces of it, such as Filebeat.

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box? Load balancers offer an organization added defense against DDoS attacks by directing attack traffic. The advantage of a jump box is that it allows a user access from a single access point that can be monitored and secured._

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for? Filebeat monitors information in the file system for instances where it has been changed and when that was._
- _TODO: What does Metricbeat record? Metricbeat takes metrics and statistics that have been collected and sends them to a predefined output._

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump-Box-Provisioner | Gateway  | 10.0.0.4   | Linux (ubuntu 20.04)            |
| Web-1    | Server   | 10.0.0.5   | Linux (ubuntu 20.04)            |
| Web-2    | Server   | 10.0.0.7   | Linux (ubuntu 20.04)            |
| Elk-Server    | Server   | 10.0.0.8   | Linux (ubuntu 20.04)            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses. Home Public IP Address_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address? The Jump-Box-Provisioner VNet IP 10.0.0.4_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | Home IP    |
| Web-1 | No                     | 10.0.0.4    |
| Web-2 | No                     | 10.0.0.4    |
| Elk-Server | No                     | 10.0.0.4    |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? The advantage with using Ansible for automating configuration is that you can put multiple commands into multiple servers from a single playbook._

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ... Install:docker.io 
- ... Install:python-pip
- ... Install:docker 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](https://github.com/IDreamofAzathoth/Elk-Stack-Project/blob/master/images/Docker_PS_Output.jpg)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring. Web-1 10.0.0.5 Web-2 10.0.0.7._

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed. Filebeats._

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see._
- Filebeats logs the authentication traffice to Web-1. [Web-1 Graphic](https://github.com/IDreamofAzathoth/Elk-Stack-Project/blob/master/images/Kibana_Agent_Hostname_Fileset.Name.jpg)
- Filebeats logs the successfull authentication attempts on Web-2. [Web-2 Graphic](https://github.com/IDreamofAzathoth/Elk-Stack-Project/blob/master/images/Kibana_Agent_Hostname_Event_Type.jpg)

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_/etc/ansible/filebeat-playbook.yml_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? /etc/ansible/host file to add webserver/elkserver ip addresses_
- _Which URL do you navigate to in order to check that the ELK server is running? http://20.119.71.132:5601/app/kibana_

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
