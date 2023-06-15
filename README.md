# At-Home Purple Team Lab#
The goal of this guide is to provide users with a step-by-step process to create an easily accessible at-home lab. This lab will enable users to perform both simple and advanced attacks, as well as develop effective defense strategies. By utilizing the Docker image provided by MITRE's Caldera framework on one virtual machine (referred to as the Red Team machine), users can simulate attacks based on the MITRE ATT&CK framework against a second virtual machine. This setup allows for hands-on experience with attack techniques and the opportunity to develop effective defense mechanisms.

## Preparing the Lab Environment
Offensive Machine Setup

1. Install Virtualbox and set up a virtual machine running Kali Linux. You can find installation instructions here.

2. Install Docker Compose on the Kali Linux virtual machine. Follow the instructions provided by Digital Ocean's guide on how to install Docker Compose on Debian 10, which can be found here.

3. Install Caldera by following the instructions provided in the Caldera GitHub repository: https://github.com/mitre/caldera.

## Defensive Machine Setup
1. Install Virtualbox and set up another virtual machine running Kali Linux Purple (referred to as the Blue Team machine).

2. Install Docker Compose on the Blue Team machine using the instructions provided in the Digital Ocean guide mentioned earlier.
Install Wazuh, an open-source endpoint protection system and log aggregator, to act as a SIEM on the Blue Team machine. Use the Wazuh Docker GitHub repository for installation: https://github.com/wazuh/wazuh-docker.git.

3. Enroll the agent to aggregate logs in Wazuh by following the provided instructions (usually two commands that you copy and paste).

Note: To avoid potential issues with the elastic stack, run the following command before executing the docker-compose up command: sysctl -w vm.max_map_count=262144.


## Recommended Tools
Offensive Machine:
Virtualbox running Kali Linux
Docker Compose
Docker container or install of Caldera (https://github.com/mitre/caldera)
Defensive Machine:
Virtualbox running Kali Linux Purple (Blue Team machine)
Docker Compose
Docker container running Wazuh (SIEM) (https://github.com/wazuh/wazuh-docker.git)
Access the SIEM at http://youripaddress (default password: admin SecretPassword)
Enroll the agent to aggregate logs by executing the provided enrollment commands.
Note: You can explore alternatives such as using Kali's built-in Armitage tool (GUI for Metasploit) as the offensive machine or Security Onion as the Blue Team machine. Additionally, running a Docker container with the ELK stack is another option for log aggregation.

## Running the Tools
1. Ensure that both the offensive and defensive virtual machines are properly set up and running. (I recommend using the Bridged Adaptor network setting, this way both virtual machines have different IP addresses) 
2. Install Docker Compose on both machines using the instructions mentioned earlier.
3.Follow the Caldera installation guide provided in the Caldera GitHub repository (https://github.com/mitre/caldera) to install Caldera on the offensive machine.
4. Use the Wazuh Docker GitHub repository (https://github.com/wazuh/wazuh-docker.git) to install the log aggregator or SIEM on the defensive machine.
5.Important: Run the command sysctl -w vm.max_map_count=262144 before executing the docker-compose up command to ensure the proper functioning of the elastic stack.
Your at-home Purple Team lab should now be up and running. You can proceed with launching attacks, analyzing results, and preparing detections and mitigations based on the MITRE ATT&CK framework. Utilize Caldera as the offensive tool to mimic the tactics, techniques, and procedures (TTPs) of APT groups. As Threat Intelligence becomes available for different APT groups, you can enrich these TTPs even further.

To ensure realistic simulations, aim to use TTPs that closely resemble those employed by actual threat groups.

Remember, this lab provides an excellent opportunity for both basic detection engineering and progressively advanced defense techniques. By practicing attacks and developing corresponding defenses based on the MITRE ATT&CK framework, you can gain valuable insights and enhance your cybersecurity skills.

Please feel free to customize and expand upon the guide based on your specific needs and preferences.
