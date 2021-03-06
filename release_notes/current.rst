.. _Release Notes:

*************************
|morphver| Release Notes
*************************

.. IMPORTANT:: Review :ref:`compatibility` before installing or upgrading to |morpheus| |morphver|.

|morpheus| UI Updates
*********************

Highlights
==========

**NSX-T Integration** Enhancements

- Create and manage NSX-T load balancers for NSX-T
- Create and manage load balancer monitors
- Create and manage load balancer pools and pool members
- Create and manage virtual servers for NSX-T
- Reserve and release IP addresses NSX-T IP pools when provisioning and decommissioning

.. image:: /images/releases/422/nsxt.png

**NSX-V Integration** Enhancements

- Create, manage and sync load balancers for NSX-V
- Configure nsx-v load balancers in instance/app wizards
- Add or remove load balancers to/from existing Instances
- Edit load balancers on existing Instances
- Create and manage load balancer monitors
- Create and manage pools and pool members
- Create and manage virtual servers for NSX-V
- Scope NSX-V load balancers to Groups such that they are owned by and, by default, only visible to that Group. They are also subject to Group-level policies

**Kubernetes** Enhancements

- Kubernetes version 1.17 support for Morpheus-type (MKS) Kubernetes deployments

Other New Features
==================

- Advanced Search: Enhancements and stability improvements to advanced search and filtering tools released in |morpheus| 4.2.1
- Appliance: Various optimizations resulting in reduced CPU usage and improved performance 
- Azure: Azure China Cloud support added *
- Azure: Azure German Cloud Support added *
- Azure: Azure Stack Integration updated to support latest Azure Stack version & 2019-03-01-hybrid api-profile *
- Azure: Azure US Government support added *
- Azure: Cloud Type selection added to Azure Cloud config for specifying Standard, US Gov, China and German environments *
- Azure: Costing sync updates and enhancements *
- Catalog: openSUSE 15.1 catalog item added for SCVMM Clouds
- Kubernetes: Version 1.17 support for Morpheus-type Kubernetes deployments (MKS)
- NSX-T: Improvements to NSX-T integration including the ability to work with load balancers and virtual servers
- NSX-V: Improvements to NSX-V integration including the ability to work with load balancers and virtual servers
- Nutanix: MAC Address now displayed in the Instance/Server Detail Network tab *
- OCI: Support for Recursive Compartments added *
- Open Telekom Cloud: Added bandwidth option to floating IP selection
- Policies: Policies now apply when Reconfiguring an Instance or Server *
- RabbitMQ: Agent Queue consolidation. ``monitorJobs*`` and ``statCommands*`` agent queues removed, agent messages now use ``morpheusAgentActions`` queue
- RabbitMQ: Stomp Broker removed. A Load Balancer is no longer required for external RabbitMQ clusters.
- vCloud Director: Proxy support added
- VMware: MAC Address now displayed in the Instance/Server Detail Network tab *

Fixes
=====

- Amazon: Fixed issue with Amazon Costing Inventory Reports not handling changing rates from previously processed line items correctly. Totals are also now recalculated on a daily basis *
- Bluecat: Fixed removal of Network Pool record when deleting a Bluecat Integration
- Clusters: Fixed available host check when adding new nodes to Instances in Docker Clusters
- Console: Fixed issue causing Instance and Server Consoles form displaying in Safari browsers *
- Fixed issue we found causing slow Elasticsearch queries on certain indices *
- Hosts: Fixed for bulk convert-to-managed
- Identity Sources: Custom External SSO Identity Source: Fixed AES encryption setting
- Instances: Fixed edit Wiki button displayed on Instances when user has Read Only Instance access.
- Instances: Special Characters can now be used in Instances names, will be stripped from hostname and host names.
- Logs: Removed ``println "Not a master"`` from MorphTagLib service
- Networks: Fixed display error when editing tenant permissions on existing network
- Networks: IP Pools: Fixed conflict when using 169.x.x.x pool address ranges
- Option Types: Fixed Field Name returning instead of Field Value for Custom Options variables when using Typeahead Option Types in Blueprints/Apps *
- Option Types: Fixed LDAP Typeahead search not searching against multiple fields *
- Oracle Cloud: Fix Oracle Cloud Costing sync when using a Proxy *
- SCVMM: Guacd updated to support SCVMM Hypervisor Console
- ServiceNow: Plugin: v2.0.6  Fixed multiple Name fields appear for Instance provisioning form in ServiceNow catalog Item. (Plugin: v > 2.0.6)
- ServiceNow: Plugin: v2.0.6: Fixed snow plugin not including Instance environment data in Blueprint provisioning requests from ServiceNow
- Usage: Fixed Usage record time periods overlapping time periods (milliseconds) for the same object
- Users: Fixed "Disable User if Inactive For" User setting locking non-local user accounts
- vCloud Director: Fixed ``validateResizeContainer error`` in morpheus-ui logs
- vCloud Director: Fixed cloud-sync connection timeouts

|morpheus| API Updates
**********************

API Fixes
=========
- API/CLI: Fixed calls to instances without containers throwing a gasket
- API/CLI: The exportMeta property is now provided for an option type in both the CLI and API. This maps to the "Export As Tag" checkbox setting on the Option Type dialog in the UI.

|morpheus| CLI Updates
**********************

CLI Enhancements
================
- CLI: Improved logs list output, the message output will flex to the width of the terminal and show more than one line, also new option --table is available. This also impacts health logs , instances logs, etc.

CLI Fixes
=========

- CLI: Fixed tasks add add --no-prompt still prompting for Content Ref. This fixes spec-templates add as well.
- CLI: Fixed login -T always resulting in Token not valid error.
- CLI: Fixed remote add --insecure not working.
- CLI: Fixed several issues with invoices.

* Indicates Features and Fixes included in 4.2.2-2 release packages. 
