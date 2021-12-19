# GitHub-Fundamentals-and-Project-13-Submission
Week 13 homework assignments
The files in this repository were used to configure the network depicted below.
see diagram folder

This document contains the following details:
Description of the Topology
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build

Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly versatile_, in addition to restricting high traffic___ to the network.

_TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?
-Load balancers are useful for redundancy purposes. For example, if there is a D DOs attack or if there's a lot of traffic another server can substitute or alleviate it.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ system _____.

TODO: What does Filebeat watch for? 
Filebeat watches and monitors the log files or locations that users specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
TODO: What does Metricbeat record? 
Metricbeat Collect metrics from your systems and services. From CPU to memory, Redis to NGINX, and much more, It is a lightweight way to send system and service statistics.

Name	Function	IP Address	Operating System
Jump Box	 Gateway	10.0.0.9	Linux
Web-1	     DVWA	   10.0.0.8 	Linux
Web-2	     DVWA    10.0.0.7	  Linux
Web-3	     DVWA	   10.0.0.10   Linux

Access Policies
The machines on the internal network are not exposed to the public Internet.

Only the Security Group_ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

TODO: Add whitelisted IP addresses 172.125.54.185 10.0.0.9 Machines within the network can only be accessed by Jump box.
_TODO: Which machine did you allow to access your ELK VM? What was its IP address? -Jump box has access to my ELK VM.
A summary of the access policies in place can be found in the table below.

| Name	    |Publicly Accessible	|Allowed IP Addresses
|Jump Box	  |YES	                 |172.125.54.185
|ELK Server	|YES	                 |40.71.64.81

Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

TODO: What is the main advantage of automating configuration with Ansible?
The advantage of automated configuration with Ansible is that it increases efficiency when configuring multiple machines.

TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
• Install Docker.io 
• Install Docker module 
• Increase Virtual Memory 
• Download and launch elk container 
• Enable elk ports 

Target Machines & Beats
This ELK server is configured to monitor the following machines:
TODO: List the IP addresses of the machines you are monitoring
10.0.0.8, 10.0.0.7, 10.0.0.10
We have installed the following Beats on these machines:

TODO: Specify which Beats you successfully installed
Metricbeat & Filebeat 

These Beats allow us to collect the following information from each machine:
TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc.
Filebeat collects log events, and forwards the information to Elasticsearch or Logstash for indexing.
Metricbeat collects system metrics from the operating system as well as system services.
Using the Playbook

Playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

Copy the my-playbook.yml file to playbook__.
Update the _my-playbook.yml file to include the host: webservers
Run the playbook and navigate to curl localhost/setup.php to check that the installation worked as expected.
TODO: Answer the following questions to fill in the blanks: _

Which file is the playbook? Where do you copy it?
/etc/ansible folder
Which file do you update to make Ansible run the playbook on a specific machine? 
Update the [ansible-config].
How do I specify which machine to install the ELK server on versus which to install Filebeat on?
update the hostname in the hosts file and then update the [ansible-config] file and then save.
_Which URL do you navigate to check that the ELK server is running?
http://[YOUR_ELK-Server_Public]:5601
