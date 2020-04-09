# A Powershell script for Windows installation and ansible-playbook for Linux machines.

They both are in the archive ```mass_agents_installation.zip``` and available at: [Website](https://hystax-eu-fra.s3.eu-central-1.amazonaws.com/Orange/mass_agents_installation.zip) 

To use mass installation script for Windows machines:

 - Create a csv with the following format - host_ip, agent_url

 - Run the script install_agents.ps1 with the created csv, e.g. install_agents.ps1 hosts.csv

To use mass installation script for Linux machines:

 - Install Ansible (playbook was tested with ansible==2.9.4)  

- Create inventory file for all of your machines

Example:
```centos ansible_ssh_host=172.22.14.148 ansible_ssh_user=centos ubuntu ansible_ssh_host=172.22.24.81 ansible_python_interpreter=/usr/bin/python3 ansible_ssh_user=ubuntu  - Run playbook with acura_host and customer_id fields specified
ansible-playbook -i hlragent-install-inventory -e "acura_host=172.22.20.8" -e "customer_id=ae8fd98e-c436-450a-bf4c-69488efbbdbd" linux_agent_install.yaml
```
