---
layout: post
title: Parameters for Share Memory in Linux
categories:
- Linux
tags:
- Linux

---
Recently I learned how to install SAP system. The envirionment for my installation is "SAP on Oracle for Suse Linux". SOo the first thing I have to prepare a Suse Linux System. I installed a Suse linux 12 SP1 Server in Vmware, then i install the oracle database in this linux. After I installed the SAP system in the linux. I can start up the SAP system but can not connect to it. the message is "connection refused". My sap system can startup but I do not know why it refused my connection.

After a lot of problems search work, i notice that the instance configuration check program provided in the sap give an error for the share memory limit and the work process can not start up due to the error when invoke the system method shmget. so I realize that the share memory setting in the kernel may not wrong for the operation system runing oracle instance and sap system.

Here i record this problem and the solution. in the solution, the main work is to set the right value for the three parameters: shmmax,shmall and shmmni(be carefull that not shmmin)

- **shmmax**
	shmmax gives the value of the max value of one share memory segment. this value is counted by byte. So if I want to set the shmmax to be 8G, the value of shmmax will be 8*1024*1024*1024 = 8589934592
    
- **shmall** 
	shmall gives the total share memory segments. this value is counted by page. In linux one page size is usually 4Kb. So the value of shmall will be shmmax/page_size = 8589934592/4096 = 2097152.

- **shmmni** 
	shmmni can be kept to be the default value. this is used to control the count of segements in share memory.

After these parameters are setted and take effect,  then restart the oracel system and sap system, the sap can be connected.