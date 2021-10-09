# ELK-Stack-Project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![](Images/Network_Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook files may be used to install only certain pieces of it, such as Filebeat.

  - Elk-Playbook.yml

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
- Load balancers are great because they create availability. If one VM fails, the other serves as a backup for the system.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system stability.
- Filebeats collect logfiles for records and making sure the network is intact.
- Metricbeat will montitor the systems that are configured in the file

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1        VM       10.0.0.5     Linux             
| Web-2        VM       10.0.0.6     Linux              
| ELK          VM       10.1.0.4     Linux                 |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBoxProvisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 97.88.144.63

Machines within the network can only be accessed by 22.
-10.1.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |  Yes              | 97.88.144.63    |
| Web 1&2      NO                   10.0.0.4              
| Elk Stack    NO                 10.1.0.4

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ansible is set to restart without having to boot it up everytime. With the right script, it will configure automatically.

The playbook implements the following tasks:
- Install Docker
- Install Python3-pip
- Install Docker_container module

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![](Images/Ansible_Containter.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- It will allows us to monitor machines and also log data on those machines. The data can be viewed on Kibana as we had configured the filebeat and metricbeat to log and monitor the data so we can analyze. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeatconfig.yml file to the ELK Stack
- Update the hosts file to include the correct IP addressses
- You will want to run the playbook and then go to Kibana using your public IP and port 5601 to make sure it is running and logging data.



_
