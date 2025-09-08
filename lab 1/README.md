Packet Tracer - Configure SSH

Addressing Table

Device	Interface	IP Address	Subnet Mask

S1	VLAN 1	10.10.10.2	255.255.255.0

PC1	NIC	10.10.10.10	255.255.255.0

	Objectives

Part 1: Secure Passwords

Part 2: Encrypt Communications

Part 3: Verify SSH Implementation

	Background

SSH should replace Telnet for management connections. Telnet uses insecure plain text communications. SSH provides security for remote connections by providing strong encryption of all transmitted data between devices. In this activity, you will secure a remote switch with password encryption and SSH.

    Instructions

 Step 1

Verify SSH support.

S1# show ip ssh

 Step 2

Configure the IP domain.

S1(config)# ip domain-name cisco.com

 Step 3

Generate RSA key pairs.

S1(config)# crypto key generate rsa

How many bits in the modulus [512]: 1024

 Step 4

Configure user authentication.

S1(config)# username administrator secret cisco

 Step 5

Configure the vty lines.

S1(config)# line vty 0 15

S1(config)# no passsword

S1(config-line)# transport input ssh

S1(config-line)# login local

S1(config-line)# exit