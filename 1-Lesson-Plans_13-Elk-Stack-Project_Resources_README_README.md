## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  

![Network Diagram](https://github.com/afzalmirza1/cybersecurity-projects/blob/main/Screen%20Shot%202020-11-25%20at%204.00.40%20PM.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
[ELK Install File ](https://github.com/afzalmirza1/cybersecurity-projects/blob/main/elk-install.yml)
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
- _TODO: What aspect of security do load balancers protect? Availibility What is the advantage of a jump box?Remote Administration

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the resources and system files.
- _TODO: What does Filebeat watch for? Looks for changes to system logs
- _TODO: What does Metricbeat record?_ Monitors for changes in resource utilization

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.1.0.12   | Linux            |
| VM1     |   VM       |  10.1.0.13          |                  |
| VM2    |    VM     |   10.1.0.14         |                  |
| ELK     |   SIEM       |  10.0.0.4          |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 100.1.244.123
- _TODO: Add whitelisted IP addresses 100.1.244.123

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP   address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes              | 100.1.244.123  |
|  VM1         |    No                 |   10.1.0.12                   |
|  VM2        |     No                |    10.1.0.12                  |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? Remote configurations for multiple VMs simultaneously

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker.io
  Use more memory
  download and launch docker elk container
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  


![Docker PS](https://github.com/afzalmirza1/cybersecurity-projects/blob/main/dockerps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ 10.1.0.13 and 10.1.0.14

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ Filebeat and Metric beat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Metricbeat - Monitors for changes in resource utilization
Filebeat - Looks for changes to system logs
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the config file file to roles.
- Update the host file to include IPs
- Run the playbook, and navigate to VM to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? .yml and copy it to playbook directory
- _Which file do you update to make Ansible run the playbook on a specific machine? Host file.  How do I specify which machine to install the ELK server on versus which to install Filebeat on? specify IP under a server or group name
- _Which URL do you navigate to in order to check that the ELK server is running? ELK's public IP address on port 5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
