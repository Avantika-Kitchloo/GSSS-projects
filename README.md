GSSS-projects
=============

details of the projects

  Introduction
The Configuration Management Database (CMDB) is the central repository for the configuration information gathered by HP Universal CMDB and other third-party applications and tools.         
Using this web application user can view the information gathered in CMDB repository.
1.1.	Tools and Technologies
The main technology used for developing this application is ColdFusion. It comprises of
1.1.1.	UI
·	CFML
·	HTML
·	Java Script
·	Eclipse
1.1.2.	DB

·	Oracle 10g
·	SQL Developer

1.	CMDB Enterprise Host-Level Discovery
1.1.	Purpose
This document describes the scope of the current CMDB Enterprise Host-Level Discovery project for 2010 / 2011. 


1.2.	2010 / 2011 detailed Scope:
	
The purpose of the Enterprise Host Level discovery project is to build a foundation into the CMDB by providing an infrastructure repository based specifically on server configuration information
(i.e.: Unix, Windows, and their associated virtual technologies).

The server information is gathered by using the HP DDM (Discovery and Dependency Mapping) software. The DDM software resides on “probes” (VM Ware Servers) throughout the environment which are responsible for running the discovery scripts (or patterns) against the discovered devices. The probes pass the data that they receive back from the discovered devices and pass it to the uCMDB app server, where it is then housed in a SQL database.

For more information on the current and projected infrastructure click here . 

·	Note:  Mainframe discovery via DDMa is currently under development. More information about intended CI’s discovered will be published as the project progresses.


1.3.	What information do we intend to discover in this project?

The links below take you to documents on our SharePoint site that describe the employed discovery jobs for the Enterprise Host-Level discovery project. While there are many out of box scripts that the uCMDB provides, the current list satisfies the commitment to deliver on the foundation that we intend to discover and maintain. This information will then enable users to generate reports, topology views, perform impact analysis, etc.; this will also allow the Configuration Management Technical team perform application mapping for critical applications. 

