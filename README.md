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

Table of Contents
1 INTRODUCING THE NEW STANDARD	1
2 WHO SHOULD READ THIS DOCUMENT	1
3 APPLICATION OVERVIEW	3
3.1 Flow Diagram/Schematic	3
3.2 Overview	3
4 INFORMATION SECURITY	4
4.1 Overview	4
4.2 Issues & Concerns	4
4.3 Monitoring	4
4.4 Information Security Approval (ISA)	4
5 ACCESS CONTROL	5
5.1 Systems Understanding/Background	5
5.2 Key Roles & Responsibilities	5
5.3 System Security Parameters	5
5.4 Identity / Access Management	6
5.5 Access Certifications	7
6 APPLICATION STARTUP	8
6.1 Pre Startup Requirements	8
6.2 Routine Application Startup	8
6.3 Non-Routine Application/Process Startup	8
7 APPLICATION SHUTDOWN	9
7.1 Normal Application Shutdown	9
7.2 Emergency Application Shutdown	9
8 SCHEDULING REQUIREMENTS	10
8.1 Job Specifications	10
8.2 Special Considerations	10
9 BACKUP REQUIREMENTS	11
10 FILE TRANSFER	12
10.1 Incoming Transmissions	12
10.2 Outgoing Transmissions	12
11 APPLICATION RECOVERY PROCEDURES	13
11.1 File System Restores	13
11.2 Database Restores	13
11.3 Application Restores	13
12 MAINTENANCE MANAGEMENT	14
12.1 Maintenance Window	14
12.2 Scheduled Maintenance Process	14
12.3 Unscheduled Maintenance Procedures	14
12.4 Failover During Maintenance	14
12.5 Mainframe Capacity Planning	14
12.6 Distributed Capacity Planning	14
13 APPLICATION MONITORING	15
13.1 Application Monitoring	15
13.2 Application Transaction Performance and Availability Monitoring	15
13.3 Application Infrastructure Availability Monitoring	15
13.4 Business Monitoring	15
13.5 Alert/Error Message Matrix	15
14 OPERATIONS SUPPORT REQUIREMENTS	16
14.1 Global Service Desk	16
14.2 Global Operations	16
15 REQUESTING COMPONENTS FOR A NEW APPLICATION	17
15.1 Applying for a Mnemonic	17
15.2 Implementing a New Application or Component	17
15.3 New Database Instance / Database / Tables	17
15.4 New MQ Instance	18
15.5 New WebLogic Instance	18
15.6 Data Center Acceptance Testing	19
15.7 User Acceptance Testing	19
16 CHANGE CONTROL PROCESS	20
16.1 UNIX / Windows Application Changes	20
16.2 Change Control Review	23
17 PRODUCTION OPERATING ENVIRONMENT & DESCRIPTION	24
17.1 Production Hardware	24
17.2 Infrastructure Software	24
17.3 Application Software	24
17.4 Firewall	25
17.5 Additional Requirements	25
18 CONTINGENCY PROCEDURES	26
18.1 Recovery Methodology	26
18.2 Unique Considerations for Application Recovery	27
18.3 Application Follow-Up Procedures	27
18.4 External Considerations	27
18.5 Application Validation – Wellness Check	28
 






Revision History

VERSION	DATE	NAME	DEPARTMENT	ACTION
1	03/15/2012			ORIGINAL DRAFT
2				REVISED, FORMAT
3				REVISED
4				REVISED

 
1 INTRODUCING THE NEW STANDARD 
The BNYMellon Application Runbook Standards Manual represents the combined efforts and expertise of subject matter experts across the corporation. Each section was reviewed and/or edited to define the current procedures and meet the needs of the integrated organization. 
This manual is designed to serve both as a guide for application developers bringing new applications into the corporation and for editing existing BNY Mellon application runbooks. Please remove any section(s) that do not apply to your application.
This section is informational and may be omitted from the final version of the runbook.
2 WHO SHOULD READ THIS DOCUMENT
This document provides application support personnel with the information needed to complete and submit an application runbook to the data center. All applications are required to submit a runbook when preparing to implement an application, and to maintain that runbook as changes are made to the application. The approved application runbook will then be published on the Documentation Services website.
The subsequent sections of this document correspond to the content that applications are required to provide in their runbooks. Sections 1 and 2 of this document template, which contain general directions for creating and submitting the runbook, should not be included.
The Application Runbook familiarizes readers with the infrastructure architecture and contingency functions required to support applications within BNY Mellon. It enables readers to efficiently manage and recover applications. 
The audience for the runbook includes system administrators, operators, architects, integrators, and other support personnel responsible for application development and deployment. Authors of the runbook should follow the guidelines listed below.
Note: The final version of the runbook should include all of the server names and infrastructure components related to the application. Preliminary and draft copies of the runbook need not include actual server hostnames, database instance names, etc., if they are not yet available. Preliminary drafts should include, for example, the number and type of servers (Solaris, AIX, Windows, Linux) and databases (Oracle, Sybase, UDB, SQL Server) and what they are to be used for.
Policy for New and Existing Applications
Any application being supported by the Technology Services Group (TSG) requires an application runbook.
Any application making a change must provide an updated runbook in compliance with the current standards.
All application runbooks are required to have a completed Contingency Procedures section. Any submission received without this section will be rejected and returned to the owner for further development.
 
Procedure for submitting runbooks to Documentation Services
All new applications to be supported by TSG are required to go through Production Readiness (part of Release Management and Support).  Application owners are required to provide a completed application runbook to Documentation Services for publication at least one week (5 business days) prior to the go-live production date.
Existing applications making a change that does not require Production Readiness must provide an updated runbook to Documentation Services at least 2 business days prior to the go-live production date.
Note 1: The application runbook should not include application contact names.  Contact information should be maintained in the Remedy 7 On-Call Console.
Note 2: All publications require a data classification according to Corporate Policy IN.230
Note 3: All publications require a Publication Request Form
Note 4: All application runbooks are required to have a completed Contingency Procedures section. Any submission received without this section will be rejected and returned to the owner for further development.
Application Teams should prepare the following documents:
•	Runbook text in Microsoft Word 
•	Publication Request Form
Attach both documents to an email message addressed to: Standards - STD
Application owners will be required to review runbook documentation on an annual basis; this review requires management approval.
This section is informational and may be omitted from the final version of the runbook.
 
APPLICATION OVERVIEW
2.1 Flow Diagram/Schematic
 
2.2 Overview
Please include any application dependencies such as traffic flow, settlement dates, etc. If applicable, please include information regarding the following:
•	Normal volume load 
•	Transaction load 
•	Peak load
 
3 INFORMATION SECURITY
3.1 Overview
Users must have the Comit Id and LDAP access for corpapps2.bnymellon.net.

3.2 Issues & Concerns
3.2.1 User Roles
Roles are created within the application as follows:
•	Security Coordinator – Security coordinator users can create the users and assign the access rights to the users
•	System Administrator – 

•	Business Administrator - 
3.2.2 Data Roles
Confidential
3.3 Monitoring 
Application monitoring is done by frequently checking the Application Server log
3.4 Information Security Approval (ISA) 
Provide information about the security review, including the date it was approved and the engineer who approved it.
 
4 ACCESS CONTROL
4.1 Systems Understanding/Background
User has to logon this application using their Comit ID and LDAP password
URL: https://corpapps2.bnymellon.net/cmdbportal/
 

4.2 Key Roles & Responsibilities
The objective of this section is to ensure that roles and responsibilities for security management have been clearly and appropriately defined and documented.
4.2.1 Data Owner
Identify the Data Owner for the application/system.
4.2.2 Security Administration
Identify the Security Administrators for the application/system. System administrators must perform system administrator functions in compliance with corporate policy.
4.2.3 Segregation of Duties
Are individuals with security administration responsibilities dedicated to security administration on a full-time basis? If security administration is a part-time responsibility, confirm that individuals with security administration responsibilities have no other responsibilities that are incompatible with the security administration functions (e.g., systems administration assignments).
4.2.4 Procedures
Confirm that documented procedures exist to support the security administration function and to facilitate the training process for new employees assigned to this role.
4.3 System Security Parameters
The objective of this section is to ensure that existing system security parameters are configured to secure settings and are in compliance with relevant corporate policies and standards. Refer to Corporate Policy IN.245.
4.3.1 Identity & Password Controls
Duplicate ids not permitted. Passwords must be used for accessing this site
Passwords must be changed every 45 days
Confirm the system prevents an identity from being created that does not require a password.
Confirm that the use of lock-words, scripting, or other means of systemically bypassing authentication routines are prohibited. Passwords will not be stored in any file, program, command list, procedure, or macro where they are susceptible to disclosure. 
Confirm that default userIDs provided by software vendors for system initialization purposes are deleted or disabled. In situations where such userIDs cannot be deleted because of recognized system limitations, passwords associated with these user accounts must be changed in accordance with standards described herein.
Confirm that for all sign-ons, passwords must be entered in protected, non-viewable fields.
Confirm that passwords must be changed every 60 days or less. 
Confirm that a password history facility will exist to prevent the reuse of at least the user's last thirteen passwords. Based on the platform or application, this may be achieved with the current password plus the last twelve historical passwords (e.g., a “password history” setting may display 12) or a setting of thirteen or higher. 
Confirm that information used for authentication (e.g., passwords, challenge questions, randomly-generated numbers) will be stored and transmitted in an encrypted form, using public and widely accepted algorithms or financial services industry standards.  Encryption is especially critical when authentication information is transmitted across a non-secure network (e.g., the Internet). Refer to Corporate Policy IN.231.
Confirm that the passwords for corporate client userIDs have the capability to be changed upon report of loss or theft. 
Confirm that messages appearing on the sign-on screen associated with failure of the identification and authentication process will be non-descriptive to avoid providing any additional information to unauthorized users.
Confirm that the password change process will force re-authentication via the requirement to enter the current password prior to allowing the user to change the current password.
Confirm that whenever a new identifier (e.g., userID) is created, the initial administrator- or system-generated password must be set to expire upon the initial successful logon by the authorized user of that identifier.
Confirm that, where technically feasible, systems display the date and time of the user’s last successful logon and logoff after successful completion of the identification and authentication processes.
4.3.2 Password Complexity
Minimum 8 characters long, one numeric and one alphabetic are must in the password
Confirm the system has been configured to enforce restrictions on password length and syntax (8 characters long, one numeric and one alphabetic). 
4.3.3 Account Lock-out
Account locked out upon 3 unsuccessful attempts
Confirm the system has been configured to lock accounts after 3 invalid logon attempts.
4.3.4 System Banners
System banner in place
Confirm that system banners are displayed on the systems during the login process to provide a warning against unauthorized access.
4.4 Identity / Access Management
The objective of this section is to ensure that appropriate controls are in place over the security administration and identity management process. Refer to Corporate Policy IN.242.
4.4.1 Identity Naming Convention
Seven characters long prefixed with the letter A or X; e.g., XBB1234

Does the naming convention of the identity created for users follow the COMIT ID format (seven characters long prefixed with the letter A or X; e.g., XBB1234)?
If identities are created that do not follow the COMIT format defined above, validate that the Data Owner, DISO, or Security Administrator(s) have instituted a process to establish unambiguous ownership / accountability over identities.
4.4.2 Access Definitions
Have access definitions (model / profile / group) been established by job function or role?
4.4.3 Non-standard Identities
Confirm procedures exist for establishing accountability over identities used for emergency access purposes, or identified as shared, generic, or off the shelf IDs (a common practice is to use a check in/check out procedure for these shared accounts).
4.4.4 Terminations and Dormant Accounts
Document the formal procedures that ensure userIDs are disabled and/or removed promptly for terminated employees or contracted personnel.
Validate a process exists to disable dormant accounts in accordance with information security standards (at least 180 days or less).
4.5 Access Certifications
The objective of this section is to ensure that appropriate controls are in place over the security administration and identity management process. Refer to Corporate Policy IN.242.
4.5.1 Facilitation of Certifications
Certifications must be performed, at a minimum, every six months and comply with corporate policy. Identify who is responsible for facilitating certifications.
Note: Within 90 days after a system is placed into production, an initial certification must be performed to validate appropriate developer/systems administration access has been revoked and access rights are aligned as expected. 
4.5.2 Certification Reporting
Confirm the certification reports display not only the identities assigned to groups (or profiles / models / profiles), but also provide details of the access afforded to the groups. 
Confirm that certification reports encompass not only identities assigned to individuals or users, but all identities with access into the system (including those used for systems processing or emergency access purposes).
 
5 APPLICATION STARTUP
The prerequisite is that the system OS is already launched and is running.
5.1 Pre Startup Requirements

List all dependent infrastructure components that need to be running prior to application startup, such as, Microsoft Message Queuing, Sybase, MQ, etc.
Table 1: Infrastructure Components
REQUIREMENT COMPONENT	LOCATION
IIS 	 
ColdFusion	 
Oracle server	

5.2 Routine Application Startup
Complete the procedure in Table 2 to for routine application startup.
Table 2: Routine Application Startup
STEP	ACTION	EXPECTED OUTPUT	COMMENTS
1	 		
2	 		

5.3 Non-Routine Application/Process Startup
Crash recovery processes are unique to each situation or environment. Please provide crash recovery procedures for each situation as applicable in table format. Be sure to include the kind of crash recovery steps (database, application, batch process, etc.).
Table 3: Crash Recovery: Type
STEP	ACTION	EXPECTED OUTPUT	COMMENTS
1	 		
2	 		

 
6 APPLICATION SHUTDOWN
Provide procedures required to bring the application down to a zero prompt.
6.1 Normal Application Shutdown
Complete the procedure in Table 4 to conduct a normal application shutdown.
Prerequisites: The system and application are operating as normal
Table 4: Normal Application Shutdown
STEP	ACTION	EXPECTED OUTPUT	COMMENTS
1	 		
2	 		

6.2 Emergency Application Shutdown
Complete the procedure(s) in Table 5 to conduct a safe and orderly emergency application shutdown. If there is no existing procedure, identify an escalation/contact procedure.  
Reason or cause for shutdown
It is important to list the cause or reason for the emergency shutdown, and to include the corresponding restart process to be used, either standard or non-standard startup procedures. Please provide in table format as in Table 5.
Table 5: Emergency Application Shutdown
STEP	ACTION	REASON/CAUSE	RESTART PROCEDURE
1			
2	 		


 
7 SCHEDULING REQUIREMENTS
All scheduled operations of the application should be noted, including those for start-of-day, end-of-day, backup procedures, and maintenance procedures (such as re-orgs and purges). Note all batch jobs (daily, weekly, special runs, etc.).
7.1 Job Specifications
Provide detailed information on all jobs related to the application including any jobs necessary for recovery.
Include the following:
•	Job name
•	Complete job description
•	Information about the type of job
•	Location/pathname
•	Script name and location (path)
•	Names and locations of input/output files
•	Account login required to run the job
•	Related steps
•	Frequency
•	Restart information
•	Rerun information
•	Holiday processing 
•	Job Requirements – include start time, all types of job dependencies, and /or file dependency – if file trigger, give full pathname to the input file 
The information can be presented in a table, for example:
JOBNAME	SCRIPT NAME	LOCATION (SERVER)	USERID	DESCRIPTION	FREQUENCY	HOLIDAY PROCESSING	JOB REQUIREMENTS
PABC90DR	/PROD/ABC/SCHED/PABC90	XSD00544	PABCP01	UPDATE TRANS LOG	MON - FRI	RUN ON ALL DAYS	SUBMIT AT 20:00
PABC95DR	/PROD/ABC/SCHED/PABC95	XSD00544	PABCP01	TRANS REPORT	MON - FRI	RUN ON ALL DAYS	AFTER PABC90DR


Note: Standards for filenames and paths are available in Scheduling Standards for UNIX, Linux, and Windows. Existing paths do not have to be renamed if they do not conform.
7.2 Special Considerations
7.2.1 Job flowchart
Identify scheduled jobs with:
•	Job predecessors (include internal, cross-platform, and interfacing application jobs) 
•	File dependencies 
•	Start times 
See example flowchart
Note: Cron jobs, though not standard policy, should be documented if they are being used.
8 BACKUP REQUIREMENTS
Any special or non-standard backup requirements should be noted.
Determine what adequate backup procedures are for the particular application. Be sure to address these questions:
•	Is there data that is transient in flat files that needs to be backed up during a scheduled batch
•	Are there databases involved that have similar data issues
•	Are the backups for this data scheduled within maintenance/batch jobs appropriately
To paraphrase the Backup Retention Policy:
•	Default Policy: 
	Unix/NT/NW clients will have a 5-version or a 30-day retention
	Domino Notes Mail clients will have a 5-version/5-day policy 
	Domino Notes Application client will get a 12-version/30-day policy
•	Special Policies 
	This is for a few clients that need special retention considerations.  Request for such arrangements need to be justified, submitted and approved.  Terms and arrangements will be different from application to application.  The longest retention term is 15 years. 
 
9 FILE TRANSFER
Provide detailed input and output information for the application.
9.1 Incoming Transmissions

Table 6: Incoming File Transmissions
APPLICATION FILE NAME	< APPLICATION NAME AND/OR DATASET >
TRANSFER PROTOCOL	< NDM | FTP >
TRANSFER PROCESS NAME	< NDM PROCESS NAME |  FTP PROCESS NAME | JOB NAME | SITEID >
MESSAGE TYPE(S)	< INDICATE FORMAT, IF STANDARD; INDICATE PROPRIETARY OTHERWISE >
SOURCE SYSTEM NAME	< SOURCE SYSTEM NAME | NODE NAMES | IP ADDRESS >
SOURCE FILE NAME	< FILE NAME ON THE SOURCE SYSTEM>
INPUT RECORD LAYOUT:
<PROVIDE LAYOUT OF INPUT FILE>
EXCEPTIONS/ALERTS RAISED (IF ANY):
<LIST EXCEPTIONS RAISED/REPORTED TO LOG OR REMEDY BASED ON PROCESSING EVENTS >
OTHER FILE DEPENDENCIES:

COMMENTS:

9.2 Outgoing Transmissions

Table 7: Outgoing File Transmissions
APPLICATION FILE NAME	< APPLICATION NAME AND/OR DATASET >
SOURCE JOB/PROCESS	<NAME PROCESS/JOB WHICH CREATES FILE>
SOURCE FILE NAME	< SOURCE FILE NAME OR DATASET >
TRANSFER PROTOCOL	< NDM | FTP >
TRANSFER PROCESS NAME	< NDM PROCESS NAME |  FTP PROCESS NAME| JOB NAME | SITEID >
DESTINATION SYSTEM	 
DESTINATION FILE NAME	< FILE NAME ON THE DESTINATION SYSTEM>
OUTPUT RECORD LAYOUT:
<PROVIDE LAYOUT OF OUTPUT FILE>
EXCEPTIONS/ALERTS RAISED (IF ANY):
<LIST EXCEPTIONS RAISED/REPORTED TO LOG OR REMEDY BASED ON PROCESSING ACTION >
OTHER FILE DEPENDENCIES:

COMMENTS:


 
10 APPLICATION RECOVERY PROCEDURES
Define the recovery scenarios in the event of a significant local failure. Refer to the backup procedures outlined in the Special Consideration section of the Scheduling chapter (section 9.2) for additional information. 
10.1 File System Restores
A root/administrator ID is required for file system restores.
Additional information and resources for Tivoli Storage Management (TSM) file restores can be found on the Enterprise Storage Services (ESS) website:
http://ess/pages/tivoli_storage_manager.html 
10.2 Database Restores
Applications that use DBM to backup their databases must use the DBM recovery utilities.   DBM provides a recovery utility process whose name depends on the DBMS as follows:
Table 8: DBMS Recovery Utility Process Names
PLATFORM	OPERATING SYSTEM	PROCESS NAME
SOLARIS	SYBASE	PSSY16PP PRE=DBNAME
SOLARIS	DB2 / UDB	PSDB16PP PRE=DBNAME
AIX	ORACLE	PAOR16PP PRE=TSNAME
WINDOWS	ORACLE	PWOR16PP PRE=TSNAME
WINDOWS	SQL SERVER	PWSQ16PP PRE=DBNAME
WHERE:
PP	EQUALS THE 4TH AND 8TH CHARACTER ORACLE, SYBASE, AND SQL SERVER INSTANCE
DBNAME	EQUALS THE NAME OF THE DATABASE TO BE RECOVERED
TSNAME	EQUALS THE NAME OF THE TABLE SPACE TO BE RECOVERED

These examples illustrate how to recover databases to the point of failure. For additional parameters and options, consult the DBM website at http://ssg:81/dbm/index.html
DBM recommends that a Maestro process be set up for each individual database.  All scripts can be found in the DBM script file system /shared/dbm/script.  For information on how to build multiple jobs in Maestro, please consult the DBM utilities job names guidelines in the DBM website: http://ssg:81/dbm/html/jobnames.html. For additional assistance or information, consult your local DBA.
10.3 Application Restores
Application recovery processes are unique to each application. Please provide procedures for each situation as applicable in table format. Be sure to include the scenario, which would dictate each type of recovery.
Note: If multiple scenarios are required, please provide a matrix for each, along with guidelines, list dependencies, database and file systems along with any special file restores. 
Table 9: Application Recovery Scenario(s)
STEP	ACTION	RECOVERY VALIDATION PROCEDURE	COMMENTS
1			
2	 		

11 MAINTENANCE MANAGEMENT
11.1 Maintenance Window
Provide the schedule for when maintenance takes place. 
11.2 Scheduled Maintenance Process
List and describe current scheduled maintenance tasks, required completion times, effects upon application availability, and performance and maximum estimated scheduled maintenance durations.  
11.3 Unscheduled Maintenance Procedures
Identify system maintenance points of contact and provide appropriate unscheduled maintenance procedures.   
11.4 Failover During Maintenance
If the application is running in a High-Availability (HA) environment, whether hosted on a cluster or on a virtual server, a temporary manual failover may be periodically required in order to complete application system maintenance and avoid critical data loss or corruption.  Provide a procedure for manual failover and (when and where appropriate) a procedure to return the system to its original operating state.   
11.5 Mainframe Capacity Planning 
A detailed explanation of Mainframe Capacity Planning standards can be found on the Capacity Planning website.
11.6 Distributed Capacity Planning 
A detailed explanation of Distributed Capacity Planning and instructions for completing a capacity forecast can be found on the Capacity Planning website (Lotus Notes login required). 
 
12 APPLICATION MONITORING
12.1 Application Monitoring
Document any application monitoring that takes place in this section where applicable.
12.2 Application Transaction Performance and Availability Monitoring 
The PKI group monitors application transaction performance from the client experience point of view. Work in this area is covered by Kannan Perichiappan (PKI) under Erik Rogers under Pete Johnson. This group works directly with the application to develop testing scripts that are then used in production via a virtual user running on a desktop in the appropriate business area. 
12.3 Application Infrastructure Availability Monitoring 
The Application Availability Services monitors application availability from an infrastructure point of view. Wellness checks are run after application maintenance is completed. The application infrastructure monitors are run on a schedule (default is every 5 minutes). Only exception based alerts (failures) are sent to Remedy to produce an incident ticket. A standard work request is submitted to detail the following monitoring and alerting requirements for the application:

General Group	Monitor Type	Definition
Network Services Monitors	Network Services monitors test networked applications and services by simulating end user actions. These include the following:
	Database  
The Database Monitor connects to database and performs a query that you specify to verify that data can be retrieved. 
	DNS  
The DNS Monitor checks a Domain Name Server via the network. It verifies that the DNS server is accepting requests, and also verifies that the address for a specific domain name can be found. 
	Ping  
The Ping Monitor verifies that specified hosts are available via the network to ensure continuous availability of critical connections. 
	Port  
The Port Monitor determines whether a service on a port can be connected to. 
	URL  
The URL Monitor verifies availability, content, and access time for specified URLs to ensure that your web pages are always available in an acceptable time frame. SiteScope takes advantage of Java's integrated SSL support to monitor secure HTTPS URLs in addition to HTTP URLs (extra set up steps may be required). 
	URL Sequence  
The URL Sequence Monitor simulates a user's session across several pages. An example of this would be entering an account name via a Web form, checking an account status for the page that is returned, and then following a sequence of links through several more pages. 
Server
Monitors	Server monitors measure server resource and operating system attributes. These include the following: 
	Disk Space  
The Disk Space Monitor reports the percentage and amount of disk space currently in use so that you can act before you run out of disk space. 
	Service  
The Service Monitor verifies that specified processes are running, such as Web server, Mail, FTP, News, Gopher, Telnet, and DNS.  AAS - please see "Composite" monitor type.  Review comment under Successfully Deployed column.
Application
Monitors	App monitors designed to query specific network apps & servers. Several of these are specific to MS Windows environments. These include the following:
	WebSphere Application Server  
WebSphere Application Server Monitor lets you watch a wide range of performance counters for IBM WebSphere Application Servers such as MemoryUse, BeanPoolSize, ActiveThreads, ConnectionWaitTime, Timeouts, and ConnectionTime. 
Advanced
Monitors	Advanced Monitors are special purpose monitors to provide specific functionality. These include the following:
	Composite  
The Composite Monitor checks the status of a set of monitors or monitor groups. 
	LDAP  
The LDAP Monitor checks an LDAP server by sending a password authentication request and reports the result. 
	Log File  
The Log File Monitor allows you to generate warnings and errors based upon data in an application's log file. For example, many applications write error messages to a log file. This monitor can scan those log files, looking for error messages and generating alerts when it finds them. 
	URL Content  
This monitor retrieves a web page and compares and saves multiple matching values from the content. 
12.4 Business Monitoring
Please document any separate business monitoring that takes place in this section where applicable. Also include any additional monitoring done by the business unit for the application.
12.5 Alert/Error Message Matrix
Please document all alerts and error messages (include specific alert syntax and error numbers where possible) that are automatically generated for Remedy. Priority is specified as Severe (1), High (2), Medium (3), or Low (4). Resolution should correspond to the KnowledgeBase solution number in RightAnswers. The matrix may be provided in a separate document as needed.
Table 10: Alert/Error Message Matrix
ERROR NUMBER
(IF AVAILABLE)	DESCRIPTION	PRIORITY	RESOLUTION
 	 	 	 
 	 	 	 
Additional information concerning the design and implementation of application and infrastructure monitoring can be found at the Enterprise Automation website.
13 OPERATIONS SUPPORT REQUIREMENTS
This section is informational and may be omitted from the final version of the runbook.
13.1 Global Service Desk
The primary function of the Global Service Desk (GSD) is the management of the TSG Customer Service Desk. CSD’s vision is to create a world-class Service Desk as the foundation of a Global Service Support Infrastructure and to deliver superior support services to both customers and employees. 
To achieve this vision, CSD provides: 
•	End-to-end ownership of the Incident Management process for Production Services 
•	Perform critical first contact call handling, triage, and escalation for TSG Service Support model 
•	Knowledge collection and management across all Production Services elements 
•	Management escalation through programmatic administration of the TSG Major Incident Process 
•	Partner with geographically disperse teams within the Global Service Support model 
13.1.1 New Application Support
New applications which require operational support must complete the CSD on-boarding process. To initiate the on-boarding process, please contact CSD Customer Engagement Team.
13.2 Global Operations
Global Operations is comprised of Global Distributed Services (GDS), Global Network Services (GNS), Global Mainframe Operations (GMO), and Distributed Operations (DPSU). These teams are responsible for pro-active/re-active monitoring and tier 1/2/3 support of the distributed, mainframe, and enterprise network environments. Services provided by these teams include support, maintenance, health checks, and monitoring of critical infrastructure components and applications, while interfacing with Production Support Engineering, Customer Service Delivery, and Application Support to resolve more complicated incidents.
Global Operations requires the following:
•	Detailed application and infrastructure recovery procedures (KnowledgeBase) 
•	Detailed application and infrastructure maintenance procedures (Application Runbook) 
•	Functional testing of the support documentation prior to production turnover 
•	Access and permissions to the necessary application components and infrastructure required to recover from an interruption in service or availability 
Additional information concerning the creation of KnowledgeBase can be found at RightAnswers KnowledgeBase or by contacting KnowledgeBase Management.
Functional testing requirements and access/permissions information and questions can be directed to PDS-CCS-GDS.
 
14 REQUESTING COMPONENTS FOR A NEW APPLICATION
This section is informational and may be omitted from the final version of the runbook.
14.1 Applying for a Mnemonic
Table 11: Mnemonic Application Procedure
STEP	ACTION
1	NEED AN APPLICATION MNEMONIC?
IF YES	AT THE ADDRESS BAR OF AN IE BROWSER, TYPE: BNYIREQ 
AN I.REQ SIGN-IN WINDOW IS DISPLAYED
 	ENTER YOUR RACF USERID AND PASSWORD
THE I.REQ REQUESTOR WINDOW IS DISPLAYED
 	CLICK ON THE SCROLL BUTTON UNDER THE FORMS GROUP AND SELECT THE NEW
APPLICATION FORMS OPTION
THE SYSTEM DISPLAYS ALL THE FORMS THAT NEED TO BE COMPLETED IN APPLYING FOR
A NEW APPLICATION AND THEIR RECIPIENT AREAS
 	SELECT THE NEW APPLICATION MNEMONIC 
THE SYSTEM DISPLAYS THE NEW ACCOUNT MNEMONIC WINDOW
 	ENTER A THREE CHARACTER NEW ACCOUNT MNEMONIC 
THE SYSTEM CHECKS THE LIST OF MNEMONICS ALREADY RESERVED: SEE
HTTP://MVSGSYS/MVSDS/'XTFD01.ACCOUNT.MNEMONIC

2	NEED A RACF USERID TO GET AUTHORITY TO SUBMIT A BNYIREQ?
IF YES	ASK YOUR MANAGER TO SUBMIT A DEVELOPMENT USERID REQUEST IN THE
BNYIREQ SYSTEM 
 	CLICK ON THE SCROLL BUTTON UNDER REQUEST FORMS AND SELECT THE
DEVELOPMENT USERID OPTION

3	IS APPLICATION MNEMONIC ALREADY CREATED BUT NOT REGISTERED IN THE 4.REQ SYSTEM?
IF YES 	SEND AN EMAIL TO: DSC@BANKOFNY.COM SPECIFYING MNEMONIC TO BE ADDED

14.2 Implementing a New Application or Component
Table 12: New Application/Component Procedures
STEP	ACTION
1	NEED UNIX USERID?
 	DO YOU ALREADY HAVE A RACF USERID?       
IF NO	ACCESS THE BNYIREQ AS EXPLAINED ABOVE AND SELECT THE DEVELOPMENT USERID
OPTION. THEN PROCEED TO THE NEXT OPTION.
IF YES	ACCESS THE BNYIREQ AND SELECT THE UNIX – EMPLOYEE USERID OPTION

2	NEED APPLICATION USERID?
IF YES	ACCESS THE BNYIREQ AND SELECT THE UNIX – NON-EMPLOYEE USERID OPTION
(FOR BOTH PRODUCTION AND DEVELOPMENT)
NOTE: ENTER: PAAAP01 OR PAAAD01 WHERE AAA IS THE APPLICATION MNEMONIC

3	NEED NON-DATABASE FILE SYSTEMS?
IF YES 	ACCESS BNYIREQ AND SELECT THE DISK - UNIX NON-DATABASE SPACE OPTION

14.3 New Database Instance / Database / Tables
Table 13: New Database Procedures
STEP	ACTION
1	NEED DBA ASSIGNED TO YOUR APPLICATION AND YOUR PLATFORM / DBMS TYPE?
NOT SURE	LOOK UP YOUR APPLICATION ON 4.REQ.A ON TSO/ISPF
NOTE: THIS OCCURS AUTOMATICALLY IF YOU INDICATE YOU NEED A DBA WHEN YOU REQUEST A MNEMONIC
IF YES	SEND AN EMAIL REQUEST TO: EDLIPSON@BANKOFNY.COM

2	NEED DA ASSIGNED TO YOUR APPLICATION AND YOUR PLATFORM / DBMS TYPE?
DA (DATA ARCHITECTURE) GROUP PERFORMS DATABASE DESIGN FOR ALL INTERNALLY ENGINEERED APPLICATIONS, AND REVIEWS ALL DATABASE DESIGNS BY SUBCONTRACTORS. THEN DA PROVIDES THE DDL TO DBA FOR IMPLEMENTATION. 
IF YES	SEND AN EMAIL REQUEST TO: DAD@BANKOFNY.COM
NOTE: THIS OCCURS AUTOMATICALLY IF YOU INDICATE YOU NEED A DA WHEN YOU REQUEST A MNEMONIC

3	NEED THE DDL FOR A NEW DATABASE? (NOT FROM A VENDOR)
IF YES	ACCESS BNYIREQ AND SELECT THE DISTRIBUTED DBMS PHYSICAL OBJECT OPTION

4	NEW DATABASE INSTANCE? (ORACLE, SYBASE, DB2/UDB, MS-SQL)
IF YES	ACCESS BNYIREQ AND SELECT THE NEW DISTRIBUTED DBMS DATABASE INSTANCE OPTION

5	NEW DATABASE/TABLE?  (THIS WILL GET THE DISK SPACE - BUT YOU NEED TO TALK TO DBA ABOUT DDL AND LOADING DATA)
IF YES	ACCESS BNYIREQ AND SELECT THE DISTRIBUTED DBMS DATABASE SPACE OPTION

6	APPLICATION NEEDS TO ACCESS DATABASE? (IF THE ANSWER IS YES - REMEMBER THAT USERIDS NEED TO BE DEFINED FIRST)
IF YES	ACCESS BNYIREQ AND SELECT THE DISTRIBUTED DBMS OBJECT PRIVILEGES OPTION

14.4 New MQ Instance
Setting up a new MQ instance is generally a five step process, as follows;
1.	Request the new MQ instance 
2.	Request the channel to connect it to the 'other' MQ (assuming you need to connect to another MQ) 
3.	Request the MQ queues 
4.	Request the BMW queues 
5.	Request authorization by your application group (UNIX group-id) to access MQ (to allow programs to read and write from MQ)

Table 14: New MQ Request Procedures
STEP	ACTION
1	NEW MQSERIES INSTANCE?
IF YES	ACCESS BNYIREQ AND SELECT THE BLANK FORM FOR SERVICE REQUESTS TO MQS AREA OPTION

2	NEED TO CONNECT MQ TO ANOTHER MQ? 
IF YES	ACCESS BNYIREQ AND SELECT THE MQSERIES: CHANNELS OPTION

3	NEW QUEUES?  
IF YES	ACCESS BNYIREQ AND SELECT THE MQSERIES: BNY QUEUES AND PROCESSES OPTION

4	NEED BMW QUEUES? 
IF YES	ACCESS BNYIREQ AND SELECT THE MQSERIES: BNY SESSION DEFINITION OPTION

5	NEED TO READ/WRITE TO THE NEW QUEUES? (IF NOT, WHY ARE THEY BEING CREATED?)
IF YES	ACCESS BNYIREQ AND SELECT THE MQSERIES: QUEUE MANAGER AUTHORIZATIONS OPTION

14.5 New WebLogic Instance
There are a large number of possible WebLogic configurations; WebLogic can run load balanced within a machine, load balanced across machines and can support failover options. Applications are encouraged to contact the WebLogic support team to understand the number and placement of WebLogic servers they will use. At a minimum setting up a single WebLogic instance will require an application file system on the server running WebLogic before submitting the WebLogic request and the application UNIX userID.
For an application new to WLS or one that needs more ports, specify 0000 in the ports and explain the need in the special instructions (ie/ New WLS app, or Need more ports).
Table 15: New WebLogic Request Procedures
STEP	ACTION
1	DO YOU HAVE AN APPLICATION USERID (A PRODUCTION USERID FOR PRODUCTION, DEVELOPMENT FOR DEVELOPMENT)?
IF NO	SEE IMPLEMENTING A NEW APPLICATION OR COMPONENT SECTION ABOUT REQUESTING AN APPLICATION USERID

2	DO YOU HAVE AN APPLICATION FILE SYSTEM FOR WEBLOGIC?
IF NO	SEE IMPLEMENTING A NEW APPLICATION OR COMPONENT SECTION ABOUT REQUESTING A NON-DATABASE FILE SYSTEM

3	NEED A NEW WEBLOGIC INSTANCE? 
IF YES	ACCESS BNYIREQ AND SELECT THE WEBLOGIC SERVER REGISTRATION OPTION.
NOTE: THIS CANNOT BE PROCESSED UNTIL STEPS 1 AND 2 ARE COMPLETED

14.6 Data Center Acceptance Testing
For information on Data Center Acceptance Testing for UNIX, see the following sections of the UNIX Standards Manual: 
•	Change Management 
•	Testing 
Additional documentation about the DCAT Process is available in:
•	Project Reviews/Checkpoints 
14.7 User Acceptance Testing
User acceptance testing is performed by the users with support of the Project Team. It verifies that the new system produces the results expected by the user. 
14.7.1 Testing Methods 
User acceptance testing uses the same methods as systems testing. 
14.7.2 Related Functions 
Related functions include: 
•	Verifying that the Functional Specifications and the new system correspond 
•	Reviewing user training plans and handling of new equipment, forms, policies, etc. 
•	Verifying error identification and correction procedures 
•	Monitoring, reviewing, and approving all input and output 
•	Validating workflows and procedures to ensure compatibility with automated functions 
•	Volume testing 
•	Obtaining signoffs 
 
15 CHANGE CONTROL PROCESS
This section is informational and may be omitted from the final version of the runbook.
15.1 UNIX / Windows Application Changes
15.1.1 Initiation of an Application Change/Authorization Business Users 
The tool used to submit application change requests is Remedy: Change Management System. After the application change is approved by an authorized approver (2 Approvers in the support group of the requester, DCAB, and CAB approval for Risk 3, 4 & 5). 
15.1.2 Development
The requester of the change assigns the implementation to the appropriate support group within Remedy; the department manager of the support group assigns the change to an Implementer based on the required skills necessary to fulfill the requirements of the change and the availability of resources.
When the change is assigned to the Implementer, meetings are held to discuss business requirements and functionalities of the change, with the application/business owner, requestor, programmer, and any other related member being affected by the change. The business requirements and functionalities are documented in each business line chosen documentation repository (i.e., Remedy: Change Request, hardcopies, etc.).
There are distinct development, test, and production environments for program changes. Auditors observed three distinct UNIX environments. The UNIX servers are listed by the server name and the server environment is noted (i.e., development, test, and production), In the Windows environment, development takes place on development servers in the CNJ data center. 
15.1.3 Harvest
The Harvest application acts as the version control with the repository of software for transmittals. Harvest is used in the change control process for the majority of UNIX and Windows applications. The Windows and UNIX applications that are not Harvest compliant do not use a standard version control repository. Harvest is a repository-based change and configuration management solution that organizes development activities throughout the Software Development Life Cycle (SDLC). 
Access to Harvest is controlled by the Harvest Administrators, within Data Center Change and Release Support Group. This administration results in the creation of application group and the addition of application developers with their respective application. Additionally, each application has a Local Configuration Manager (LCM). The LCM has limited administrator privileges and has the authority to add application developers to their respective application.
The Harvest Administrators have to create a 'Project' for each application team. The Project is where the application's source code resides. For a user to gain access to an application's source code, Administrator or the LCM has to add the user's profile to the Project. A user only has access to the Project(s) that his/her user profile is associated with.
A review of active Harvest users is conducted quarterly. The Administrators compare the list of active userIDs to the list of users in Harvest. If a user exists in Harvest but does not have an active userID, the administrator deletes the user's Harvest ID.
The Enterprise Harvest product tools may be used to version control any code, script, document, etc that needs modification in the production environment.  The application developer will manage the promotion through the development, test and QA (where applicable) environments.  The Online Forms for the Distributed Platform will be used to promote and distribute the code, executables, script, etc to the production Enterprise Harvest state and servers.  The actual process of promoting to the production state and servers is performed by the Production Support Services in TSG Operations and Production Support.  This final step of distribution to production is a required step to comply with corporate standards.
15.1.4 Harvest Systems Development Life Cycle
There are two Harvest Project Lifecycle Models designed to support the Software Development Life Cycle at The Bank of New York Mellon. A Standard Model supports the SDLC (Software Development Life Cycle) leading practices via discrete states for each life cycle milestone. A Streamlined Model also supports SDLC leading practices but consolidates the life cycle milestones into fewer states. The states in Harvest are: 
•	Unit Testing (UT) 
•	Integration Testing (IT) 
•	Build View (Build) 
•	Quality Assurance View (QA) 
•	Production View (Emergency and Production)
The developers are forced to use one model versus the other depending on the type of change.
15.1.5 Testing
15.1.5.1 Unit Testing
The developer will create a Package in the Unit Test state, and will locate the components that need to be changed. These components are checked out to their local workstation (using the Harvest GUI or command line utilities). Unit testing occurs in the development environment and it examines a single function, script, subprogram, or complete program by executing it against controlled test data designed to check the logic path through the code. Error handling is tested by passing invalid data to the code.
15.1.5.2 Integration Testing
During this phase, the interfaces between applications are tested for proper operation and conformity with specifications, and to validate the file recovery function.
Once the change is signed off by the developer, it is ready for User Acceptance Testing (UAT) and possibly Data Center Acceptance Testing (DCAT)
15.1.5.3 User Acceptance Testing (UAT)
The UAT is designed to ensure that results produced by the application system meet user business requirements and needs. Not all changes require User Acceptance Testing. This is because the change may be initiated by a technology group. For example, the technology group may create a change request to fix a job ABEND. Since this change does not impact an end-user, and UAT is not required.
15.1.5.4 Data Center Acceptance Testing (DCAT)
Please refer to DCAT portion of this document.
15.1.5.5 Remedy: Change Management
After the application developer or system software developer finishes testing, the Project Leader or Department Manager will fill out a Change Record. In Remedy 7, the developer enters a brief description of the change, special instructions (for production), location of the change file, and back out instructions; then completes the risk calculator template. The risk calculator template assigns the risk of the change request based on a number of factors relating to the risk of the implementation.
When the developer completes the Remedy Change Record, approvals are electronically submitted by the system in each phase. The change record must be fully approved for Normal and Expedited changes before the change is promoted to production. 
Remedy 7 contains an Approval Role list of managers that are allowed to approve the change based on the Requester Support Group and possibly additional approvals based on the application. Within Remedy 7, the Change Manager reviews the change, and if approved, moves the change from Planning in Progress to Scheduled for Approval. Then the Support Group Managers in Level 1 are notified for approval. Only 1 Change Manager and 1 Group Manager approval is needed per Change request. If the change is Risk 3, then the DCAB is notified for a 3rd approval. 
If Risk 4 or 5, the CAB is notified for the 4th and final review and approval. After this is completed the change is ready for production.
15.1.5.6 Production
The data center technician receives the Remedy Change Request and Accepts the Remedy 7 Change, if there are no problems with the nature of the change. On the scheduled date noted on the Change Request, the data center technician copies the executable files from the production reference library to the production server(s). The copy to production is performed on a weekend or late at night to help to ensure operations are not interrupted.
15.1.5.7 Segregation of Duties
Developers' access to UNIX and Windows production environment is restricted. In the UNIX environment programmers are granted View Only access to the production environment. Only certain data center employees are given Root Access so that they are able to migrate a change to production.
In the Windows environment, only the certain data center employees have system administrator access, which allow them to move changes into production. To restrict remote logon, remote access is disabled; this helps to ensure that the system administrator must be at the console to migrate a change to production.
Application programmers may only have access to production in emergency situations. Those emergency situations must be clearly documented, stating the reason for action and the tasks performed. The documentation is retained with the application documentation for future reference. In the UNIX environment, application developers are given a temporary ID which allows them access to root. The ID expires after a defined period of time. In the Windows environment, the data center technicians will enable remote access so that the developers can access production. Remote access is disabled once the developer(s) have completed their tasks. The Application’s Data Custodian is responsible for reviewing emergency activity and ensuring that programmers are in compliance with corporate policy.
15.1.5.8 Emergency Changes
An emergency change constitutes a change that cannot wait until the next business day to be implemented. Emergency changes will be approved on a case-by-case basis. To qualify as an emergency, the following criteria must be met:
•	An existing production user impact is being addressed 
•	A Remedy 7 Incident ticket has been opened 
•	Application and the appropriate infrastructure groups are aware of what is being moved to production, have approved the move to production and have personnel (on-site is preferred) to validate that this change was executed properly
After the approvals have been received, developers create a package in the Emergency state of Harvest, and make the necessary changes in the Harvest Emergency state.
After the change is completed, the developer calls the Technical Support technician to move the change from the Harvest emergency reference directory to the appropriate production server(s).
15.1.5.9 Follow-up Procedures for an Emergency Change
During the next business day, the application programmers are responsible for moving the change through each state in Harvest so appropriate approvals are obtained. This helps to ensure that the change is retrofitted back into the lifecycle and can undergo unit testing and formal user acceptance testing. The application team must also submit an Emergency change Request in Remedy 7. The Change request states what was done in the emergency change and includes the appropriate approvals. As well as a Remedy Incident ticket is shown in the Relationship tab of the Change request, giving the details of the Incident that caused the Emergency change.
15.2 Change Control Review
Every day, the Change Advisory Board holds a conference call to review for approval, medium and high risk application changes as determined by the risk calculator in Remedy.

The Board addresses the changes that will be going into production that day (or in the next few days) to ensure all required sign offs have occurred. The developers and business owners could be invited to attend the meeting to present the details of the change or other supporting information to the committee. Change submitters should contact the committee if their change is not approved by the day of the scheduled start date on the Remedy change record.

The Change Advisory Board consists of members from various TSG support teams, IRM and stakeholders from critical applications. A member of TSG Operations and Production Services acts as the Change Advisory Board chairman. Other individuals may be invited to the meeting depending on the scope of the change and the areas that the change impacts.
 
16 PRODUCTION OPERATING ENVIRONMENT & DESCRIPTION
16.1 Production Hardware
Include and describe items from the following list for each hardware component where applicable. Cover all applicable specialized or non-standard hardware or peripherals. Create a separate list for each hardware component. If virtual or cloud technology is used, then list and describe the virtual hardware used for this, as well as, providing a link to the corresponding software section as needed.
•	Identify production hardware vendors
•	Identify production hardware models
•	Identify domain or LPAR host names
•	Identify aliases assigned to each hardware instance
•	Identify subsystems running on each machine (WebSphere Server, Oracle Database Server, APP Server, etc.)
•	Identify additional required features above the standard vendor offering
•	See the appropriate vendor-supplied documentation for more detailed hardware information
16.2 Infrastructure Software
Identify and describe the items in the following list where applicable.  Include any specialized or non-standard software, and be sure to describe any grid related software.  
16.2.1 Operating System
•	Identify the operating system vendor.  Note BNYM standard versions and patch levels will be used
•	See the appropriate application vendor-supplied documentation for more detailed operating system information
16.2.2 Production Database
•	Identify production database software vendors
•	Identify production database software
•	Identify BNYM standard database version(s)
•	Identify the approved database and instance names
16.2.3 Production Middleware
•	Identify if BNYM standard WebSphere middleware can be used
•	Identify production-messaging tools (IBM MQ, Microsoft Message Queuing, Java Messaging Service)
•	Identify production middleware configuration data
•	Identify application-to-application and machine-to-machine communication data
•	Identify relevant NDM links
16.3 Application Software
16.3.1 Vendor Components
Identify vendor-supplied application components, individual products and their respective version numbers.  For more detailed software information, see the vendor-supplied documentation.
16.3.2 In-House Components
Identify in-house software components, their revision levels and respective configurations as required.
16.3.3 Change Management Configuration
Please describe application configuration change processes.  
16.4 Firewall
If applicable, document the considerations and resources available to the application regarding firewalls.
16.4.1 Application Considerations
•	Identify the geographic location of the clients using the firewall
•	Identify system components that must have access through the system firewall
•	Identify the actual firewall location
•	For each component or server, list connectivity details through the firewall including the server name, port numbers, network protocol used, and data speed
16.5 Additional Requirements
Identify any additional hardware or software requirements not covered in the previous sections(s).
 
17 CONTINGENCY PROCEDURES 
This section details the application procedures to be followed when a contingency event results in the loss of an application's production systems during the loss of an entire site.
All application runbooks are required to have a completed Contingency Procedures section. Any submission received without this section will be rejected and returned to the owner for further development.  Entering N/A (Not Applicable) is not acceptable for this section.
Note: This section does not cover local recovery or local failover recovery involving a single machine; that should be documented within the infrastructure procedures.
17.1 Recovery Methodology
Detailed infrastructure recovery documents are provided that covers each production platform (UNIX, Wintel, mainframe, etc.). In this section, the application only needs to document the type of infrastructure recovery that is being provided for each server. This is done by summarizing the recovery of the application in a paragraph, describing the data centers supporting the production application and the general method of recovery, followed by a chart, in the following format, listing the recovery for each server running the application.

Table 16: Recovery Methodology Chart
HOSTNAME	FUNCTION	RECOVERY METHOD
HOSTNAME 1	GENERAL DESCRIPTION	TYPE OF RECOVERY
HOSTNAME 2	GENERAL DESCRIPTION	TYPE OF RECOVERY

Table 17: Example of a Recovery Methodology Chart
HOSTNAME	FUNCTION	RECOVERY METHOD
XSD00T99	ORACLE DATABASE SERVER	SYNCHRONOUS DISK RECOVERY 
XSD00X06/Y06	WEBLOGIC APPLICATION SERVERS	NEAR SYNCHRONOUS DISK RECOVERY 
XSD00X05	IPLANET DMZ SERVER	LIVE LIVE SERVER RECOVERY 
WTEAPAPZZZ01	REPORTING SERVER	LIVE LIVE SERVER RECOVERY 
WTEAPAPZZZ11	IMAGING SERVER 01	SAN SERVER, SAN BOOT SERVER RECOVERY 
WTEAPAPZZZ12	IMAGING SERVER 02	STAND ALONE SERVER RECOVERY 

The different types of recovery methods for Solaris / AIX systems are provided in the UNIX Contingency Procedures section of the Documentation Services website. 
The different types of recovery methods for Wintel systems are provided in the Intel Contingency Procedures section of the Documentation Services website. 
Additional recovery methods for these systems are provided in the Infrastructure Deployment Baseline Recovery Methods section of the Documentation Services website.
To determine the specific recovery method for your machines, please contact your Intel and/or UNIX planner.
17.2 Unique Considerations for Application Recovery
In this section document any procedure necessary to license or activate software required for your application, including screenshots of steps to activate a licensed product if it cannot be scripted.
17.3 Application Follow-Up Procedures
In this section applications should document the procedures to be followed once the infrastructure recovery procedures have been completed.  For applications running live-live applications across the production and contingency sites, there may be little or nothing for the application to do at this point; at the other extreme, for applications where the recovery requires shipping a new server and doing TSM restores there may be a great deal of work required.
This section should also include any specific desktop considerations for end users accessing the application, including a list of special desktop components installed on desktops.  
Although desktop recovery is covered in the Business Continuity Plans for each Business Unit, if a contingency event for an application requires or could require desktop reconfiguration (even though the end user area / customer itself does not necessarily require recovery) that should be specifically detailed in this section.
Recoverability - What is the Maximum outage time the application is willing to incur? This does not include the declaration of a disaster.  If this topic has already been covered in the SLA and/or OLA sections of this document, this section can be removed.
LOB Target Availability – What are the timeframes required by the Line of Business for the restoration of service of this application? Availability requires investment in infrastructure and applications that are designed for resiliency and recoverability.  If this topic has already been covered in the SLA and/or OLA sections of this document, this section can be removed.
Include order of recovery for application components. Include any dependencies for recovery of other applications that it may be dependent on (for example, startup order of systems for application, or dependency on another application for access and authentication).
17.4 External Considerations
In the two sections below, supply the mnemonics and components of any other applications that must be recovered to run this application.
17.4.1 On-line Dependencies
Supply the names and components of any other applications that need to be recovered to run this application.  For example, if the application reads another application database, or requires an MQ Series feed, then that should be noted here.  Note that detailed information listed in sections above need not be duplicated here, just a general description.
17.4.2 Batch Dependencies
Supply the names and components of any other applications that need to be recovered to run this application.  For example, if the application is dependent upon files that are transmitted such as a batch cycle, please note that here.  Note that detailed information listed in sections above need not be duplicated here, just a general description.
17.5 Application Validation – Wellness Check
A basic method of validating that the application is functioning should be detailed in this section. It is expected that application personnel would do a more thorough validation followed by internal end users.  If the application validation is covered in a Wellness Check (typically stored in the RightAnswers KnowledgeBase repository), please provide a link to the corresponding health check document.

