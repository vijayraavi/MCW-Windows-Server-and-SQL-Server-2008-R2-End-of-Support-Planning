![Microsoft Cloud Workshop](https://github.com/Microsoft/MCW-Template-Cloud-Workshop/raw/master/Media/ms-cloud-workshop.png "Microsoft Cloud Workshops")

<div class="MCWHeader1">
Windows Server and SQL Server 2008/R2 end of support planning
</div>

<div class="MCWHeader2">
Whiteboard design session student guide
</div>

<div class="MCWHeader3">
February 2019
</div>


Information in this document, including URL and other Internet Web site references, is subject to change without notice. Unless otherwise noted, the example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, e-mail address, logo, person, place or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.

Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.

The names of manufacturers, products, or URLs are provided for informational purposes only and Microsoft makes no representations and warranties, either expressed, implied, or statutory, regarding these manufacturers or the use of the products with any Microsoft technologies. The inclusion of a manufacturer or product does not imply endorsement of Microsoft of the manufacturer or product. Links may be provided to third party sites. Such sites are not under the control of Microsoft and Microsoft is not responsible for the contents of any linked site or any link contained in a linked site, or any changes or updates to such sites. Microsoft is not responsible for webcasting or any other form of transmission received from any linked site. Microsoft is providing these links to you only as a convenience, and the inclusion of any link does not imply endorsement of Microsoft of the site or the products contained therein.

© 2019 Microsoft Corporation. All rights reserved.

Microsoft and the trademarks listed at <https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/Usage/General.aspx> are trademarks of the Microsoft group of companies. All other trademarks are property of their respective owners.

**Contents**

<!-- TOC -->

- [Windows Server 2008 and SQL Server 2008 end of support planning whiteboard design session student guide](#windows-server-2008-and-sql-server-2008-end-of-support-planning-whiteboard-design-session-student-guide)
  - [Abstract and learning objectives](#abstract-and-learning-objectives)
  - [Step 1: Review the customer case study](#step-1-review-the-customer-case-study)
    - [Customer situation](#customer-situation)
    - [Customer needs](#customer-needs)
    - [Customer objections](#customer-objections)
    - [Infographic for common scenarios](#infographic-for-common-scenarios)
  - [Step 2: Design a proof of concept solution](#step-2-design-a-proof-of-concept-solution)
  - [Step 3: Present the solution](#step-3-present-the-solution)
  - [Wrap-up](#wrap-up)
  - [Additional references](#additional-references)

<!-- /TOC -->

# Windows Server 2008 and SQL Server 2008 end of support planning whiteboard design session student guide

## Abstract and learning objectives

Many customers have huge on-premises footprints of Windows Server and SQL Server 2008 and 2008 R2, but these products are rapidly approaching End of Support. This session is designed to help customers understand the risks of running unsupported software and presents great options for using EOS to modernize in Azure or on-premises.

In this whiteboard design session, you will work with a group to look at the process of migrating workloads to Azure.

At the end of this whiteboard design session, you will leave with the information needed to develop a solid migration plan to keep mission-critical apps and data protected as they are transitioned and modernized. Topics covered will include how to get an inventory of a 2008 server environment, how to categorize 2008 workloads and evaluate the best option for each category, migration and upgrade tools available, TCO analysis tools, offers available from Microsoft to leverage existing licenses and innovations of recent product updates, licensing and technologies.     

## Step 1: Review the customer case study 

**Outcome** 

Analyze your customer’s needs.

Timeframe: 15 minutes

Directions: With all participants in the session, the facilitator/SME presents an overview of the customer case study along with technical tips.

1.  Meet your table participants and trainer.

2.  Read all of the directions for steps 1-3 in the student guide.

3.  As a table team, review the following customer case study.

### Customer situation

Fabrikam is an automotive parts manufacturer based in the United States. They are an OEM manufacturer of parts for commercial vehicles. They have manufacturing plants throughout the US and Mexico. Fabrikam competes globally with other manufacturers for contracts, this highly competitive environment makes Fabrikam very price sensitive.

"We are preparing for Windows and SQL Server 2008/R2 end of support and would like to better understand our options for upgrade and migration." Sloane Peterson, Fabrikam CIO

Fabrikam does not have a complete company-wide inventory of the number of servers and applications running on legacy software and many of the systems are undocumented and not well understood by IT staff. They want to understand their current workloads and they would like to take advantage of the cloud where appropriate.

Fabrikam currently has many legacy applications that are running on Windows Server 2008 including a line of business inventory management system that also leverages SQL Server 2008. The inventory management system is considered a mission critical application. It is highly complex and is leveraged by various parts of the business with many upstream and downstream dependencies. Some of these dependencies are Linux systems. Because many of these systems are critical to the business, they need to understand the business continuity and disaster recovery options when upgrading in place or migrating to the cloud.

The Inventory Management system is one of the most critical systems at Fabrikam. It was originally architected when the company was much smaller. It currently runs on Windows Server 2008 R2 with a separate SQL Server 2008 backend. The application team that supports it would ultimately like to rearchitect the system for better scalability and to take better advantage of new innovations in inventory tracking. They see cloud technologies as a good fit for this type of application, but they lack the experience, expertise and time to rebuild the application right now.

They would like a short-term plan to maintain support of the system while the application team reskills and gains experience in Azure.
They would also like a long-term plan to take advantage of the new advancements in SQL Server while still getting the most out of their Azure investment by minimizing the administrative overhead.

"We would love to take advantage of the cloud to minimize the administrative overhead of the Inventory Management System, we simply cannot get all of the dependencies sorted out before the official end of support." Frances Bradley, Manager Inventory Applications

### Customer needs 

1.  Identify migration and upgrade tools to help in assessing, migrating and optimizing the current environment.

2.  Fabrikam needs to build an inventory of their current systems and provide some organization around the various systems they have in place. The inventory should include dependencies and tiering of the applications to help in prioritizing application upgrades and migrations.

3.  Fabrikam has a large mix of applications including Microsoft, third-party and custom applications. They need to evaluate the upgrade options for each workload.

4.  They would like to modernize applications and take advantage of the cloud where it makes sense. How should they go about identifying suitable applications and the costs of running them in Azure?

5.  Applications that are not moving to Azure will need to be optimized on-premises.

6.  As part of the analysis, Fabrikam would like to better understand how to analyze cost of a solution that is slated to be migrated to Azure. They have chosen an application solution that represents a fairly common pattern in their environment and would like you to provide total cost of ownership analysis of this solution in Azure. 

### Customer objections 

1.  We have some third-party applications where we do not have complete control of the code or schema. We will not be able to upgrade these applications before the end of support. What options do we have for these applications?

2.  We have hundreds of applications that are running on servers that are nearing end of support. Some are virtual machines running on VMWare, some are older physical machines. Does Microsoft have any tools to help us identify these applications?

3.  We need to minimize the amount of downtime during migration. How will we do this? What kind of downtime are we looking at?

4.  When migrating workloads into Azure, how do we handle security and authentication? Will my workloads continue to use the same authentication that was used on-premises?

5.  Some of our data has very strict regulatory constraints and cannot leave the country/region of origin, how do we handle this type of data in Azure? Will data be replicated or located in other countries or regions? 

6.  How will migrating from SQL Server to Azure SQL Database impact the role of our database administration team?


## Step 2: Design and present the solution

**Outcome**

Present a part of the solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 3 parts, 15 minutes each

**Presentation**

Directions:

1.  Pair with another table.

2.  One table is the Microsoft team and the other table is the customer.

3.  The Microsoft team presents part of the proposed solution to the customer.

4.  The customer makes one of the objections from the list of objections.

5.  The Microsoft team responds to the objection.

6.  The customer team gives feedback to the Microsoft team.

7.  Tables switch roles and repeat Steps 2-6.

_Part 1 - Assess - Plan for end of support_

- **Inventory**: Fabrikam needs to build an inventory of their current systems. Determine what needs to be tracked in this inventory. What information would you track in your inventory to help Fabrikam organize and prioritize systems for their end of support planning? How would you prioritize systems?

- **Tools:** Identify any tools that Fabrikam might use to help with assessments, migrations and optimizations of their Windows Server and SQL Server systems. You should identify which stage of the process you would leverage these tools and what value they provide.

- **Cost Analysis:** Fabrikam currently has Software Assurance. Provide a cost analysis of the following options available to Fabrikam:

    a. Maintain current version

    b. Rehost - Migrate to cloud

    Additionally, provide a one-year total cost of ownership analysis for migrating the following example solution to Azure. The details below represent a common pattern seen in Fabrikam's environment. Provide analysis for migrating this solution from Fabrikam's Michigan datacenter to the North Central US region of Azure. You can use state averages for utility rates, you may accept the defaults for information that is not provided below.

    |    |            |            |
    |----------|-------------|-------------|
    | Web Farm |  |
    |  | Workload: | Windows Server |
    |  | Environment: | Virtual |
    |  | Operating System: | Windows Server 2008 R2 |
    |  | VMs: | 4 |
    |  | Virtualization: | VMWare |
    |  | Cores (per VM): | 4 |
    |  | RAM (GB): | 16 |
    |  | Optimize by: | CPU |
    | Process Server |  |
    |  | Workload: | Windows Server |
    |  | Environment: | Virtual |
    |  | Operating System: | Windows Server 2008 R2 |
    |  | VMs: | 1 |
    |  | Virtualization: | VMWare |
    |  | Cores (per VM): | 4 |
    |  | RAM (GB): | 16 |
    |  | Optimize by: | CPU |
    | Database Server |  |
    |  | *Source server specs* |  |
    |  | Database: | Microsoft SQL Server |
    |  | License: | Enterprise |
    |  | Environment: | Physical server |
    |  | Operating System: | Windows Server 2008 R2 |
    |  | Servers: | 1 |
    |  | Procs per server: | 2 |
    |  | Cores (per proc): | 8 |
    |  | RAM (GB): | 128 |
    |  | Optimize by: | CPU |
    |  | *Destination server* |  |
    |  | Service: | SQL Database Managed Instance |
    |  | Managed instance tier: | General purpose |
    |  | Managed instance cores: | 8 |
    |  | SQL Server storage: | 500 GB |
    |  | SQL Server backup: | 1 TB |
    | Adjust assumptions |  |
    |  | Azure Hybrid Benefit: | On |
    |  | Software Assurance coverage: | On |
    |  | Geo-redundant storage: | Off |
    |  | Virtual Machine costs: | On |

_Part 2 - Migrate - Upgrade in place or migrate to Azure_

-  **Migration strategy:** Fabrikam would like to take full advantage of the cloud. They would like to create a multifaceted application strategy to determine how applications will be migrated to Azure. You need to identify the various paths to moving applications to the cloud and when each path provides the highest value.

-  **Windows Server Upgrades and Migrations**: Detailed migration steps:

    a. How will physical machines be migrated to Azure?

    b. How will machines hosted in VMWare be migrated to Azure?

    c. Some IIS based web sites will be migrated to Azure Web Apps. Document the requirements and the process for migrating to Azure Web Apps. 

-  **SQL Server Upgrades and Migrations**: Provide Fabrikam with detailed migration steps. At a minimum, your steps should cover the following scenarios:

    a. How SQL Servers that will be migrated to Azure virtual machines be migrated?

    b. How SQL databases that will be migrated to Azure SQL Database and Azure SQL Database Managed Instances be migrated? 

-  **Diagram the solution**

_Part 3 - Optimize_

-  **Security and Authentication:** How will Active Directory be managed in the cloud? Will we continue to do things the way we have in the past?

-  **Cost management:** With the ease of deploying and scaling services in the cloud we are concerned about cost management. What tools can we leverage to help us with cost management?

-  **Compliance:** We want to make sure that our cloud resources are properly secured so that we can maintain compliance. How do we monitor security and maintain compliance in the cloud? What about systems that remain on-premises?

-  **SQL Database Management:** What type of database administration tasks can we automate in Azure SQL Database? We are looking to minimize the amount of administrative tasks our DBAs are doing and focus them on higher value tasks.

##  Step 3: Wrap-up 

Timeframe: 20 minutes

Directions: Tables reconvene with the larger group to hear the facilitator/SME share the preferred solution for the case study.

##  Additional references
|    |            |
|----------|:-------------:|
| **Description** | **Links** |
| Azure Migration Center  | <https://azure.microsoft.com/en-us/migration/>  |
| Azure Hybrid Benefit  | <https://azure.microsoft.com/en-us/pricing/hybrid-benefit/>  |
| Azure Migrate  | <https://docs.microsoft.com/en-us/azure/migrate/migrate-overview>   |
| Azure Pricing Calculator  | <https://azure.microsoft.com/en-us/pricing/calculator/>  |
| Azure TCO Calculator  | <https://azure.microsoft.com/en-us/pricing/tco/calculator/>  |
| Azure Site Recovery | <https://docs.microsoft.com/en-us/azure/site-recovery/>    |
| Database Migration Guide   | <https://datamigration.microsoft.com/>      |
| Windows Server Migration Guide   | <https://go.microsoft.com/fwlink/?linkid=872689>      |
| Azure Database Migration Service   | <https://docs.microsoft.com/en-us/azure/dms/dms-overview>      |
| Data Migration Assistant   | <https://docs.microsoft.com/en-us/sql/dma/dma-overview?view=sql-server-2017>      |
| Database Experimentation Assistant   | https://blogs.msdn.microsoft.com/datamigration/2018/08/06/release-database-experimentation-assistant-dea-v2-6/      |
| Azure Cost Management   | <https://docs.microsoft.com/en-us/azure/cost-management/overview>   |
