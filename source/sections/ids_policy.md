# IDS Policy

In order to preserve the integrity of data that 1healthy.world stores, processes, or transmits for Customers, 1healthy.world implements strong intrusion detection tools and policies to proactively track and retroactively investigate unauthorized access. 1healthy.world currently utilizes built-in Azure tools to track file system integrity, monitor log data, and detect rootkit access.

## Applicable Standards from the HITRUST Common Security Framework

*  09.ab - Monitoring System Use
*  06.e - Prevention of Misuse of Information
*  10.h - Control of Operational Software

## Applicable Standards from the HIPAA Security Rule

* 164.312(b) - Audit Controls

## Intrusion Detection Policy

* Azure tools are used to monitor and correlate log data from different systems on an ongoing basis. Reports generated by Azure are reviewed by the Security Officer on a monthly basis.
* Azure generates alerts to analyze and investigate suspicious activity or suspected violations.
* Azure monitors file system integrity and sends real time alerts when suspicious changes are made to the file system.
* Automatic monitoring is done to identify patterns that might signify the lack of availability of certain services and systems (DOS attacks).
* 1healthy.world firewalls monitor all incoming traffic to detect potential denial of service attacks. Suspected attack sources are blocked automatically. Additionally, our hosting provider actively monitors its network to detect denial of services attacks.
* All new firewall rules and configuration changes are tested before being pushed into production. All firewall and router rules are reviewed every quarter.
* 1healthy.world utilizes redundant firewall on network perimeters.
* Static IP addresses are used for 1healthy.world servers.
