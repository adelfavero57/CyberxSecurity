# CyberxSecurity
Repository for Cyber Security bootcamp

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

/CyberxSecurity/Diagrams/Azure Diagram.drawio

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - /CyberxSecurity/Anisble/pentest.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system metrics.


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| web-1    |Web server| 10.0.0.6   | Linux            |
| web-2    |Web server| 10.0.0.7   | Linux            |
| web-3    |Web server| 10.0.0.8   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 114.74.243.225

Machines within the network can only be accessed by the jump box.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 114.74.243.225       |
|web server| No                  | 10.0.0.4             |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because system configurations are able to be quickly repeated without risk of error.

The playbook implements the following tasks:
- Install Docker
- Install pip3
- Install docker-python module
- increase memory use
- Launch a docker elk container

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.6
- 10.0.0.7
- 10.0.0.8

We have installed the 
following Beat on these machines:
- Filebeat

These Beats allow us to collect the following information from each machine:
- Filebeat collects log files from the systems it is monitoring and ingests them into Elastic search for analysis.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-playbook.yml file to the host machine.
- Update the hosts file to include the IP addresses of the computers to run on
- Run the playbook, and navigate to http://10.0.0.9/kibana to check that the installation worked as expected.
