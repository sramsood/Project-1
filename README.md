## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Project-1/Project 1 Network Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the elk.yml file may be used to install only certain pieces of it, such as Filebeat.

  - _https://github.com/sramsood/Project-1/blob/master/Elk.yml_

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- _Load balancing offers the offloading function that defends and organization against distributed denial-of-service (DDoS) attacks. The advantage of an Azure jump box is to prevent Azure VM's from exposure to the public.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _Filebeat monitors syslog hostnames and processes_
- _Metricbeat takes the metrics and statistics that it collects and ships them to the Elasticsearch_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.2.0.7   | Linux            |
| Web-1    | Webserver| 10.2.0.5   | Linux            |
| Web-2    | Webserver| 10.2.0.6   | Linux            |
| Web-Elk  | Webserver| 10.10.4    | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump-box-provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _216.49.48.114_

Machines within the network can only be accessed by _____.
- _The jump-box-provisioner is allowed to connect to my VM. Its IP address is 52.188.153.161_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.2.0.5  10.2.0.6   |
| Elk      | No                  |  52.188.153.161      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _The main advantage of ansible is that it can be run from the command line without the use of configurationfiles or simple taks, such as making sure a service is running_

The playbook implements the following tasks:
- ... 1. The first step is to install docker onto the machine, install python3, and install python docker module
- ... 2. The second step is to download more memory and launch the docker elk container
- ... 3. The third step is to attach to the elk container and make sure the playbook ran properly

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/sramsood/Project-1/blob/master/docker%20ps.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _10.2.0.5
- _10.2.0.6

We have installed the following Beats on these machines:
- _Filebeat and metricbeat__

These Beats allow us to collect the following information from each machine:
- _Filebeat monitors logs that you specify such as syslog hostnames and processes. Metricbeat takes the metrics and statistics that it collects and ships them to the Elasticsearch_

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_/etc/ansible/filebeat-config.yml | /etc/filebeat/filebeat.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_/etc/ansible/hosts  | /etc/ansible/roles
- _Which URL do you navigate to in order to check that the ELK server is running? http://104.40.2.186:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._ ansible-playbook <instert playbook name>