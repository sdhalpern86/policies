# Introduction

1healthy.world, Inc. ("1healthy.world") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As developers and deliverers of a compliant, hosted application used by care teams as well as other health technology vendors, 1healthy.world strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by 1healthy.world to maintain compliance and assure the proper protections used to store, process, and transmit ePHI for 1healthy.world's Customers.

1healthy.world provides secure and compliant cloud-based software. This hosted software falls into two broad categories: 1) **Software as a Service (SaaS)** and 2) **Add-ons**. These Categories are cited throughout polices as Customers in each category inherit different policies, procedures, and obligations from 1healthy.world.

## Software as a Service (SaaS)

SaaS Customers utilize hosted software from 1healthy.world to deploy our compliant software to their care team professionals and patients. These customers are deployed into systems secured and managed by Microsoft Corporation. 1healthy.world makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of SaaS Customer data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, port restrictions, etc).

## Add-ons

Add-ons are compliant API-driven services that are offered as part of the 1healthy.world solution suite. These services are in alpha development and are not available to our Customers or the general public at this time. 

In the future there may be 3rd party Add-on services available as part of the 1healthy.io Platform. These 3rd party, or Partner, Services will be fully reviewed by 1healthy.world to assure they do not have a negative impact on 1healthy.world's information security and compliance posture.

## Compliance Inheritance

1healthy.world provides compliant hosted software for its Customers. Currently there is no official certification for HIPAA or HITECH Act compliance. However, 1healthy.world's infrastructure at Microsoft Azure is covered under a BAA amendment provided by Microsoft, and Microsoft Azure's systems have undergone audits conducted by accredited independent auditors for the Microsoft ISO/IEC 27001 certification. Microsoft enterprise cloud services are also covered by FedRAMP assessments.

1healthy.world signs business associate agreements (BAAs) with its Customers, whom in most cases are "covered entities" as defined by HIPAA. These BAAs outline 1healthy.world's obligations and Customer obligations, as well as liability in the case of a breach. In providing online software and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, 1healthy.world manages various aspects of compliance for Customers. The aspects of compliance that 1healthy.world manages for Customers are inherited by Customers, and 1healthy.world assumes the risk associated with those aspects of compliance. In doing so, 1healthy.world helps Customers achieve and maintain compliance, as well as mitigates Customers' risk.

Certain aspects of compliance cannot be inherited. Because of this, 1healthy.world Customers, in order to achieve full compliance or HITRUST Certification, must implement certain organizational policies. These policies and aspects of compliance fall outside of the services and obligations of 1healthy.world.

Below are mappings of HIPAA Rules to 1healthy.world controls and a mapping of what Rules are inherited by Customers, both SaaS Customers and Add-on Customers.

## 1healthy.world Organizational Concepts

The physical infrastructure environment is hosted with [Microsoft Azure](https://www.microsoft.com/en-us/trustcenter/Compliance/HIPAA). The network components and supporting network infrastructure are contained within the Azure infrastructure and managed by Microsoft. 1healthy.world does not have physical access into the network components. The 1healthy.world environment consists of Azure's firewalls, Apache and nginx web servers, Dropwizard Java application servers, Microsoft Enterprise SQL and PostgreSQL database servers, logging servers, Linux Ubuntu monitoring servers, Salt configuration management server, OSSEC IDS services, and developer tools servers running on Linux Ubuntu.

Within the 1healthy.world Application on Azure, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. 1healthy.world assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

In the case of SaaS Customers, it is the responsibility of the Company to restrict, secure, and assure the privacy of ePHI data at the Application Level. In the case of PaaS customers leveraging the 1healthy.io Platform, it is the responsibility of Customer to assure the privacy of ePHI data at the Application Level, as this falls outside the scope of our core mission to serve covered entities and their patients.

The data and network segmentation mechanism differs depending on the primitives offered by the underlying cloud provider infrastructure. Within Azure, hosted load balancers segment data across dedicated Virtual Networks for SaaS Customers and for Add-ons.

The result of segmentation strategies employed by Catalyze effectively create RFC 1918, or dedicated, private segmented and separated networks and IP spaces, for each SaaS Customer and for Add-ons.

Additionally, IPtables is used on each each server for logical segmentation. IPtables is configured to restrict access to only justified ports and protocols. 1healthy.world has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an SSL encrypted session.

In the case of Add-ons, which at this time are not available, once the data is received from the application server, a series of Application Programming Interface (API) calls is made to the database servers where the ePHI resides. The ePHI is separated into PostgreSQL and Percona databases through programming logic built, so that access to one database server will not present you with the full ePHI spectrum.

The bastion host, Apache web server, Dropwizard application servers are externally facing and accessible via the Internet. The database servers, where the ePHI resides, are located on the internal 1healthy.world network and can only be accessed directly over an SSH connection through the bastion host. The access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business justified reason. Remote access to the internal servers is not accessible except through the load balancers and bastion host.

All Platform Add-ons and operating systems are tested end-to-end for usability, security and impact prior to deployment to production.

## Version Control

Policies were last updated November 7th, 2016.
