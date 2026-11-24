## Ex. No: 7 – Configure Initial Router Settings
# Date: ___________
________________________________________
# Objective
To perform basic router configuration tasks in Cisco Packet Tracer including:<br>
•	Verifying the default router configuration.<br>
•	Configuring initial router settings (hostname, MOTD, passwords).<br>
•	Securing access to the CLI and console port.<br>
•	Encrypting passwords.<br>
•	Verifying and saving the configuration to NVRAM and flash.<br>
________________________________________<br>
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Router (R1 – 2911 or equivalent)<br>
•	1 PC (for console connection)<br>
•	Console cable (RS-232 to Console)<br>
________________________________________<br>
# Network Topology Diagram
(Insert your Packet Tracer screenshot here showing Router R1 and PC with console connection)
<img width="761" height="510" alt="image" src="https://github.com/user-attachments/assets/eea81847-d6de-4c83-b53c-1d17b3301b91" />

________________________________________
# Procedure
# Part 1: Verify the Default Router Configuration
1.	Connect PC → Router R1 using a Console cable.<br>
2.	On PC → Desktop → Terminal → Connect to R1.<br>
3.	Enter privileged EXEC mode:<br>
4.	Router> enable<br>
5.	Router#<br>
6.	Display running configuration:<br>
7.	Router# show running-config<br>
o	Observe hostname, interfaces, vty lines.<br>
8.	Display startup configuration:<br>
9.	Router# show startup-config<br>
o	Router shows: startup-config is not present (because nothing is saved in NVRAM yet).<br>
________________________________________
# Part 2: Configure and Verify Initial Router Configuration
1.	Enter global configuration mode:<br>
2.	Router# configure terminal<br>
3.	Configure hostname:<br>
4.	Router(config)# hostname R1<br>
5.	Configure MOTD banner:<br>
6.	R1(config)# banner motd # Unauthorized access is strictly prohibited #<br>
7.	Configure passwords:<br>
o	Console password:<br>
o	R1(config)# line console 0<br>
o	R1(config-line)# password letmein<br>
o	R1(config-line)# login<br>
o	R1(config-line)# exit<br>
o	Enable password (unencrypted):<br>
o	R1(config)# enable password cisco<br>
o	Enable secret (encrypted):<br>
o	R1(config)# enable secret itsasecret<br>
8.	Encrypt all plain-text passwords:<br>
9.	R1(config)# service password-encryption<br>
10.	Exit and verify login prompts:<br>
o	On exit, router shows MOTD.<br>
o	User is prompted for password.<br>
o	Enter letmein (console) → access User EXEC mode.<br>
o	Enter itsasecret → access Privileged EXEC mode.<br>
________________________________________
# Part 3: Save the Running Configuration
1.	Save running configuration to NVRAM:<br>
2.	R1# copy running-config startup-config<br>
Short version:<br>
R1# wr<br>
3.	Verify NVRAM contents:<br>
4.	R1# show startup-config<br>
o	Confirms saved configuration.<br>
5.	Save startup config to flash (backup):<br>
6.	R1# copy startup-config flash<br>
o	Use show flash to verify file stored in flash.<br>
________________________________________
# Commands Used
•	To enter privileged mode: enable<br>
•	To view config: show running-config, show startup-config<br>
•	To configure hostname: hostname<br>
•	To configure MOTD banner: banner motd<br>
•	To set passwords: enable password, enable secret, line console<br>
•	To encrypt passwords: service password-encryption<br>
•	To save configuration: copy running-config startup-config, wr, copy startup-config flash<br>
________________________________________
# Output (Attach Screenshots)
•	Console connection to router<br>
<img width="1230" height="580" alt="image" src="https://github.com/user-attachments/assets/fb662d9d-ca7a-4972-a479-6e966685db70" />
<img width="1356" height="483" alt="image" src="https://github.com/user-attachments/assets/d3499c80-3343-4311-8e63-6acaceebf54a" />

•	Running configuration before and after<br>
<img width="1917" height="1078" alt="Screenshot 2026-11-24 180954" src="https://github.com/user-attachments/assets/7725267d-3704-485d-bfe2-0e86fcef6762" />
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/4b0330c6-2f0b-4f53-8370-1ff6146a7e7b" />



•	MOTD banner display<br>

<img width="1917" height="1078" alt="Screenshot 2026-11-24 180910" src="https://github.com/user-attachments/assets/0edc9832-04ae-47ec-a530-9e9b366511e7" />



•	Password prompts<br>
<img width="1917" height="1078" alt="Screenshot 2026-11-24 181022" src="https://github.com/user-attachments/assets/ff39781c-2659-4db2-a743-c03df96eafe4" />
•	Saved configuration in NVRAM and flash<br>


<img width="1917" height="1078" alt="Screenshot 2026-11-24 181039" src="https://github.com/user-attachments/assets/d3c8f91f-522f-45ee-a4b5-9beb619850c3" />

________________________________________
# Result
The router was successfully configured with hostname, banner, encrypted passwords, and secure console access. The configuration was verified and saved to NVRAM and flash, ensuring persistence across reboots.

