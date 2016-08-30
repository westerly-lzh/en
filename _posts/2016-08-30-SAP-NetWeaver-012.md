----
layout: post
title: SAP NetWeaver - 1.2 Architecture of an SAP System, AS ABAP and AS Java
categories:
- SAP
tags:
- NetWeaver

------

#### SAP NetWeaver Provides runtime environments for:

* ABAP runtime environment (AS ABAP)
* Java runtime environment (AS JAVA)

#### Client/Server Configuration for SAP Systems

Operating Business Application Processes:

* Presentation processes
* Application processes
* Database processes

System configurations:

* Single-Tier configuration
* Two-Tier configuration
* three-Tier configuration

#### SAP System

> An SAP system is an installed software system that provides a defined set of functions that are part of an SAP system solution. it consists of a database, one or more application server instances(ABAP and/or Java), central services, and other components depending on the system. The system is identified by its SAP system ID, which consists of three letters or digits.

#### SAP Instance

> An instance is an administrative unit that combines the SAP system components together to provide one or more services.  These services are started or stopped together, and each instance has its own buffer



> The installation and operation of the database for an SAP system can be done on a separate physical computer, separated from the instances of the SAP system. There is exactly one database for each SAP system. <u>The database has the same system ID(DB ID) as the SAP system</u>



#### Central Instance

> The central instance provides services that other instance of system do not offer, such as message service and enqueue service. 