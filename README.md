# At-Home-Purple-Team-Lab
The Goal is to create a guide to allow users to create an easy to make at home lab that allows them to preform advanced and simple attacks along with seeing how to better defend against them. 
By utilizing https://github.com/mitre/caldera as a docker image on one virtual machine(red teaming machine) to launch an attack based on the MITRE framework attack against a 2nd virtual machine you can simulate attacks based on the MITRE framework and learn how to defend against them.

I would highly reccomend running a SIEM on the 2nd virtual machines as this will give a more realistic image for seeing what the logs will look like when they are aggregated in an enterprise enviornment. I would highly reccomend using this mostly preconfigured Docker ELK stack https://github.com/sherifabdlnaby/elastdocker
(Authors note: You should use whatever SIEM is most similar to the organization you want to work in, I chose this one because it was open source and more simple to use if you just use Docker-compose. I spent many hours hunting for the perfect one and failing).

Finally after initiating the attack and seeing the results you will also be able to prepare detections for the attacks and proper mitigations. This should allow the oppurtunity for basic detection engineering and progressively more advanced defenses. 

By practicing and perfecting both attacks and TTP's according to the MITRE framework and the defenses to mitigate them you can take many hopefully useful lessons. 

With Caldera as the offensive tool you can also mimic more APT groups TTP's from start to finish of the Mitre Framework. You can enrich these TTP's even more as Threat Intelligence becomes available on different APT groups. 

It is important to remember to make the simulations as real as possible you want to make sure to use TTP's that are as close as possible to the real threat groups. 


**Reccomended tools**
Offensive machine: 
-Virtualbox running Kali Linux
- Docker container or Install of Caldera https://github.com/mitre/caldera 

Defensive Machine:
- Virtualbox Kali Purple
- Docker container running https://github.com/sherifabdlnaby/elastdocker (You don't need a SIEM but to get the most from the Blue Team portions it would be wise to run it for the benefit of seeing the logs aggregated like they should be in a SOC). (As an added bonus if you come across an attack that isn't being logged you can perform detection engineering to engineer a detection for that attack in the future). 

Alternatives: You can also run a kali virtual machine running Armitage https://www.kali.org/tools/armitage/ instead of Caldera, Caldera makes it easier to automate a larger that can mimic an ATP group. However Armitage is essentially a GUI for metasploit and can also be used as the offensive machine
- Kali's built in Armitage tool https://www.kali.org/tools/armitage/ can also be used as the offensive machine. I would reccomend this if you are more interested in individual CVE's that can be exploited as the tool is mostly a GUI for Metasploit
- Security Onion is also a possible choice for the Blue team machine it has a robust amount of security features built in and likely is more deserving of the 'SOC in a BOX' title that Kali Purple has. 


