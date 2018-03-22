# PDU
PDU
SPM RunBook

Logging Into SPM Web GUI	2
Create a New Cabinet	3
Create A New PDU & Link To A Cabinet	4
How To Set Temperature Thresholds	6
How To Troubleshoot a PDU	7
How to ping a PDU within SPM	8
How to perform an SPM walk	8
How to check PDU network settings via serial cable	9
How to generate support logs from PDU	10
How to generate SPM Support Pack	11
How To Delete a PDU from SPM	13
How To Put A CDU Into Maintenance Mode	15
How To Change E-Mail Alert Recipients in SPM	17
How To Change Active Alert Types in SPM	18
How To Configure a CDU	18
How To Update Firmware	20
SPM Alert Response Workflow	22
How to query an entire SCIF, for PDU firmware versions, using SNMPWalk…	25




Logging Into SPM Web GUI

Browse to https://10.192.242.2
Enter your AD credentials.  If unsuccessful, contact your team lead to be added to the access list.
Once access is granted into the web GUI, you will be able to proceed with any of the following tasks.

Create a New Cabinet




Click on Devices Setup
Click on Cabinets
Click on New Cabinet button on the right
Enter Cabinet Name, such as CAB-###
Select the sector the cabinet is in under Cabinet.
Click on Save.
Create A New PDU & Link To A Cabinet



Click on Devices Setup
Click on CDUs
Click on New CDU button on the right
Enter the IP address of the CDU you are adding.
Under Setup -> Enterprise, select STI CDU
Under Setup -> SNAP Template, select SNMP.
Under SNMP -> Version, select SNMP v2c
Under SNMP -> Get Community, enter the Get string listed in LastPass.
Under SNMP -> Set Community, enter the Set string listed in LastPass.
Under Parent, select the cabinet the CDU is physically installed at.
Click on the Save & Close button.
How To Set Temperature Thresholds



Click on Devices Setup
Click on CDUs
Locate the CDU you want to set the temperature thresholds on.
Double-click the CDU
Click on the Environment tab
Double-click on the sensor under temperature you want to set the temperature thresholds on.
Click on the Setup tab.
Enter the new temperature and humidity thresholds you want to set.
Click on the Save button.
How To Troubleshoot a PDU
Access PDU via serial cable to ensure PDU settings are correct. (see How to check PDU network settings via serial cable)
Ping PDU within SPM (see How to Ping PDU from SPM)
Perform a SPM walk (see How to perform SPM walk)
If all network information is correct, then have a DC network engineer look into it.
Obtain support logs from the PDU (see How to obtain debug support logs)
Obtain SPM Support Pack (see How to generate SPM Support Pack)
Send email to support@servertech.com with a description of the issue and include the PDU support logs and the SPM support pack in the email as well.


How to ping a PDU within SPM
Click on the SPM Setup tab on the left
Click on Support Tools
Click on the Communication Tests tab
Enter the IP address of the PDU
Select SNMP v2c from the drop down menu
Enter the GET community string into the Get Community field
Click on the Ping button at the bottom of the window.



How to perform an SPM walk
Click on the SPM Setup tab on the left
Click on Support Tools
Click on the Communication Tests tab
Enter the IP address of the PDU
Click on the SPM Walk button at the bottom of the window.



How to check PDU network settings via serial cable
Use your favorite terminal software to access the PDU (putty, screen, etc)
Use the following command to check the network settings on the PDU:
show network
Terminal will output the following:

Switched CDU: show network
   Network Settings
      State:           Static IPv4       Network:         IPv4 only
      Link:            Up                Negotiation:     Auto
      Speed:           100 Mbps          Duplex:          Full
      AutoCfg IPv6:    FE80::20A:9CFF:FE54:73AC/64
      IPv4 Address:    10.196.242.31     Subnet Mask:     255.255.254.0
      IPv4 Gateway:    10.196.243.254
      DNS1:            10.193.48.5
      DNS2:            10.193.48.23
   Static IPv4/IPv6 Settings
      IPv6 Address:    ::/64
      IPv6 Gateway:    ::
      IPv4 Address:    10.196.242.31     Subnet Mask:     255.255.254.0
      IPv4 Gateway:    10.196.243.254
      DNS1:            10.193.48.5
      DNS2:            10.193.48.23
   DHCP Settings
      DHCP:            Disabled
      FQDN:            Enabled [pdu-111-002.power.infra.las1.mz-inc.com]
      Boot Delay:      Disabled
      Static Fallback: Enabled
   Network Services
      Telnet:       Enabled     Port:    23
      SSH:          Enabled     Port:    22    Auth:      Password, Kb-Int
      HTTP:         Enabled     Port:    80
      SSL:          Enabled     Port:   443    Installed Cert: Factory
         Access:    Optional                   Stored Files: None
         User Cert: Disabled                   User Passphrase: (none)
      SNMPv1/2:     Enabled     Port:   161    TrapPort:  162
      SNMPv3:       Disabled    Port:   161    TrapPort:  162
      FTP Server:   Enabled     Port:    21
      SPM Access:   Enabled
Command successful

3. Verify the network information from the “show network” command matches exactly what you see in the PDU verification spreadsheet.
https://docs.google.com/spreadsheets/d/1wNGqXLTWMRz9zaPOf4gVYMPAluBlTv6H3U5-RMFEH0o/edit#gid=1327298115
How to generate support logs from PDU
Use your favorite terminal software to access the PDU (putty, screen, etc)
Use the following command to check the network settings on the PDU
debug support
Terminal will output logs for a few minutes and will end with “Command successful” when the task is complete.
Copy everything from the debug support command to Command successful into TextEdit.
Save the file contents to “debug support” onto your Desktop.






How to generate SPM Support Pack
Click on SPM Setup
Click on Support Tools
Click on the System Info tab
Click on the Generate Support Pack button
Next, click on Reports Menu
Click on Logs
You will see the filename for the Support Pack as soon as SPM completes generating it.
Next, click on Admin Setup
Click on Backup Files
Right-click on the Support Pack file, select Download and place it on your Desktop.






How To Delete a PDU from SPM



Click on Devices Setup
Click on CDUs
Locate the CDU you want to delete.
Double-click the CDU
Click on the “Red X” icon on the far right.
SPM will ask you to confirm the deletion of the PDU so press “OK” to confirm deletion of the PDU.
How To Put A CDU Into Maintenance Mode



Click on Devices Setup
Click on CDUs
Locate the CDU you want to place into maintenance mode.
Double-click the CDU
Click on the purple wrench icon on the right to bring up the Setup Maintenance window.
Highlight the CDU.
Select the Duration area to bring up a drop-down menu with the maintenance duration length.
Select the maintenance duration length.
Click on Save to put that PDU into maintenance mode for the set maintenance duration length.
It is a known issue by ServerTech that PDUs in maintenance mode will not show up in maintenance mode in the CDU status view. It will still show up as Normal (green).
How To Change E-Mail Alert Recipients in SPM
Select Admin Setup.
Select System setup
Click on Email Notification tab
You can change the Mail To 1: email address by replacing it with the new email address you wish to use.
Click on the Save button.
Click on the Send Test Email button to send out a test notification to ensure the email address is setup correctly
How To Change Active Alert Types in SPM

Select Admin Setup.
Select System setup
Click on Email Notification tab
Select or deselect the alerts you wish to have SPM send you.
Click on Save.
Click on the Send Test Email button to send out a test notification to ensure the email address is setup correctly.

How To Configure a CDU
Utilize the following spreadsheet to obtain the network info for the CDU you wish to configure:https://docs.google.com/spreadsheets/d/1wNGqXLTWMRz9zaPOf4gVYMPAluBlTv6H3U5-RMFEH0o/edit#gid=1327298115
Use a serial cable to connect a laptop to the PDU and locally log into the PDU
Use your favorite serial terminal application (putty, screen, etc)
Use the following commands to configure the PDU:
set net ipv4only
Terminal will output “Command successful”
set dhcp disabled
Terminal will output “Command successful”
set ipv4 address [IP ADDRESS]
Terminal will output “Command successful -- restart required”
set ipv4 subnet [SUBNET MASK]
Terminal will output “Command successful -- restart required”
set ipv4 gateway [GATEWAY IP ADDRESS]
Terminal will output “Command successful -- restart required”
set dns1 [DNS IP ADDRESS]
Terminal will output “Command successful”
set dns2 [DNS IP ADDRESS]
Terminal will output “Command successful”
Restart
Browse to the IP address of the CDU that has just been configured and login.
SNTP/syslog setup
Click on Configuration - SNTP/Syslog
In the SNTP section, type in the IP address for the Primary SNTP host and the Secondary SNTP host.
Set GMT Offset to -8.
Set Use DST to “enabled”.
Click apply.
Type in the IP address for the primary syslog host and secondary syslog host.
Port should be set to 514.
Click apply.
SNMP setup
click on Configuration - SNMP/Thresholds
In the SNMPv2Agent section, enter the GET Community string and the SET community string.
TACACs setup
Click on Configuration - TACACS+
Set TACACS+ to “Enabled”
Set Authentication order to “remote->Local”
Set primary host to 10.193.48.24
Set port to 49.
Click apply.
Copy the TACACS encryption key from LastPass and paste it into the New Encryption Key field and the Verify New Encryption key field.
Click apply.
Credentials setup
Click on Tools - Change Password
Enter “admin” in the current password field.
Copy and paste the CDU password from LastPass into the New Password field and the Verify New Password field.
Click apply
How To Update Firmware




Browse to the IP address of the CDU.
Log into the PDU.
Click on Tools.
Click on Firmware.
Click on the “Choose file” button next to Select a System Firmware file.
Select the PDU firmware file you wish to upload to the PDU and click on the “Open” button.
Select the Upload button.
SPM Alert Response Workflow
// No communications message
Enclosure Master (pdu-55-001.power.infra.las1.mz-inc.com) Status (No Communications)
Attempt to ping the PDU.
Open up a ticket with Switch to ensure there are no power fluctuation or outages for that rack and to check for RPP breaker trips.
Physically check the PDU to ensure it is receiving power.
Check power supplies for all devices in the rack to ensure all devices are power redundant.
Check port on the switch to make sure the port is enabled.
Check the cable going from the PDU to the switch to make sure it is connected.
Use a serial cable to connect a laptop to the PDU and locally log into the PDU.
Use “show network” command on the PDU to see what the status field indicates.
If the status fields indicates an IP conflict, then issue the “restart” command on the PDU. This command will cause the network daemon thread on the PDU to restart without powering off any of the power outlets on the PDU.
If PDU network configuration is correct on the PDU itself and the SNMP settings are correct in SPM for this PDU, then delete the PDU from SPM and then add the PDU back into SPM.
If this does not work, have a DC network engineer check to see if there have been any recent network changes.

// Unreachable message
CDU pdu-85-001.power.infra.las1.mz-inc.com Status (Unreachable)
CDU pdu-85-001.power.infra.las1.mz-inc.com Status (Unreachable) has cleared
Attempt to ping the PDU.
Open up a ticket with Switch to ensure there are no power fluctuation or outages for that rack and to check for RPP breaker trips.
Physically check the PDU to ensure it is receiving power.
Check power supplies for all devices in the rack to ensure all devices are power redundant.
Check port on the switch to make sure the port is enabled
Check the cable going from the PDU to the switch to make sure it is connected.
Use a serial cable to connect a laptop to the PDU and locally log into the PDU.
Use “show network” command on the PDU to see what the status field indicates.
If the status fields indicates an IP conflict, then issue the “restart” command on the PDU. This command will cause the network daemon thread on the PDU to restart w/o powering off any of the power outlets on the PDU.
If the PDU has an IP address and the PDU is still not showing with an “OK” status in SPM, then check the SNMP community strings to ensure they are setup correctly on the PDU and in SPM.
If PDU network configuration is correct on the PDU itself and the SNMP settings are correct in SPM for this PDU, then delete the PDU from SPM and then add the PDU back into SPM.
If this does not work, then have a DC network engineer check to see if there have been any recent network changes.
 
// Maintenance message
CDU pdu-162-002.power.infra.las1.mz-inc.com Status (Maintenance)
CDU pdu-162-002.power.infra.las1.mz-inc.com Status (Maintenance) has cleared
This indicates someone logged into the PDU and set the PDU into maintenance mode meaning you won’t see any alerts or temperature readings from this PDU since it has been taken offline for the specified time duration selected.
The cleared message will be sent when the maintenance time duration has elapsed.
The PDU needs to reestablish the handshake with SPM so it will take a few minutes for SPM to receive temperatures and power readings from the PDU that just came out of maintenance. 

// Power factor status low warning 
Phase Unit1_InputCord1_phase (pdu-150-001.power.infra.las1.mz-inc.com) Power Factor Status (Low Warning)
Check power supplies on all the devices in the rack since this alert is usually triggered by a failing or faulty power supply from a device in the rack.
It can also be caused by a power fluctuation from the Switch power feed so a ticket will need to be opened up with Switch to have them investigate for power fluctuations, power outages and RPP break trips based on the email timestamp. 
If Switch doesn’t find any issues, collect debug support logs from the PDU and create a case with ServerTech support.

// Temperature lost message
Sensor pdu-145-001-cold (pdu-145-001.power.infra.las1.mz-inc.com) Temperature (Lost)
Sensor pdu-145-001-cold (pdu-145-001.power.infra.las1.mz-inc.com) Temperature (Lost) has cleared
This alert is triggered when the temperature/humidity probe is disconnected from the PDU or when the temperature probe itself fails.
Reconnect the cable from the probe going into the PDU.
Wait 5 minutes to see if the error clears.
If error does not clear, replace the temperature probe sensor. 
If error persists after replacement of sensor, collect debug support logs from the PDU and create a case with ServerTech support.

// Humidity lost message
Sensor pdu-145-001-cold (pdu-145-001.power.infra.las1.mz-inc.com) Humidity (Lost)
Sensor pdu-145-001-cold (pdu-145-001.power.infra.las1.mz-inc.com) Humidity (Lost) has cleared
This alert is triggered when the temperature/humidity probe is disconnected from the PDU or when the temperature probe itself fails.
Reconnect the cable from the probe going into the PDU.
Wait 5 minutes to see if the error clears.
If not, then replace the temperature probe sensor. 
If this doesn’t work, then collect debug support logs from the PDU and create a case with ServerTech support.

// Fuse off message
Outlet Master_ZX_1 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
Outlet Master_ZX_2 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
Outlet Master_ZX_3 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
Outlet Master_ZX_4 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
Outlet Master_ZX_5 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
Outlet Master_ZX_6 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
Outlet Master_ZX_7 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
Outlet Master_ZX_8 (pdu-129-001.power.infra.las1.mz-inc.com) Status (Off Fuse)
This alert is triggered when the fuse goes out on a phase of the PDU.
Open up a ticket with Switch to ensure there are no power fluctuation or outages for that rack and to check for RPP breaker trips.
Physically check the PDU to ensure it is receiving power.
Check the inventory spreadsheet for spare PDU stock in case the PDU needs to be swapped.
The fuses on the ServerTech PDUs are not self-serviceable so a support ticket will need to be created with ServerTech.
Obtain debug support logs to provide to ServerTech Support if needed.

// Breaker tripped message
Branch AA:L2-L3-BR2 (10.200.212.16) Status (Breaker Tripped) 
Outlet Master_Outlet_11 (10.200.212.16) Status (Breaker Tripped) 
Outlet Master_Outlet_14 (10.200.212.16) Status (Breaker Tripped)
Branch AA:L2-L3-BR2 (10.200.212.16) Status (Breaker Tripped) has cleared
Outlet Master_Outlet_11 (10.200.212.16) Status (Breaker Tripped) has cleared
Outlet Master_Outlet_14 (10.200.212.16) Status (Breaker Tripped) has cleared
This alert is triggered when the breaker is tripped on the PDU.
Open up a ticket with Switch to have them investigate power delivery to the rack and to investigate any RPP issues.
Perform a visual check on the rack to look for power redundancy and to check for failed power supplies.
Check inventory for a spare PDU in case we need to swap out the PDU.
Obtain debug support logs and create a case with ServerTech support.




How to query an entire SCIF, for PDU firmware versions, using SNMPWalk


( replace <SNMP_GET_COMM> with the actual Get Community string )
( replace {171..210} with the actual start and end fourth-octets )
( replace 10.201.72 with the first three octets of the PDU’s; for loop assumes that all PDU's share identical first three octets )
( certain PDU's may require this OID instead :  enterprises.1718.4.1.1.1.3.0 ; note 1718.4 vice 1718.3.  Distinguishes Version 3 PDU's vice Version 4. )


from Bastion home directory, run this for loop...

for x in {171..210}; do snmpwalk -Os -c <SNMP_GET_COMM> -v 2c 10.201.72.$x enterprises.1718.3.1.1.0 >> 7D_PDU_IMAGES.txt;done

then cat the 7D_PDU_IMAGES.txt


To send the results directly to the screen, instead of to a text file, just omit the redirection operator & file name.  New command...

for x in {171..210}; do snmpwalk -Os -c <SNMP_GET_COMM> -v 2c 10.201.72.$x enterprises.1718.3.1.1.0;done

To query for PDU model, vice firmware version, use OID = enterprises.1718.3.2.1.1.7.1
Example...

for x in {171..210}; do snmpwalk -Os -c <SNMP_GET_COMM> -v 2c 10.201.72.$x enterprises.1718.3.2.1.1.7.1 >> 7D_PDU_MODELS.txt;done



 

 

