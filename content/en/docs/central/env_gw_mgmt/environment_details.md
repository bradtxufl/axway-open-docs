---
title: Viewing the details of your environment
linkTitle: Viewing the details of your environment
weight: 20
date: 2020-12-14
description: Understanding the details of your environment
---

{{< alert title="Public beta" color="warning" >}}This feature is currently in **public beta** and not yet available for production use.{{< /alert >}}

![Environment Details Page](/Images/central/env_and_gateway_mgmt/EnvironmentDetailsPage.png)

For environments created using the API service model, the details page lists the title of the environment along with the status of any connected discovery and traceability agents, and includes three sections below with additional information

### Environment Information

The Environment Information section contains the environment's icon, title, logical name, description and any tags or attributes that are specific to the environment asset. Attributes in this context are key and value pairs used for extending functionality and integrations with third party systems.

The date and time that the environment asset was created is listed in this section.

### Activity Report

The values in the Activity Report section represent a holistic view of metrics within the environment.

* Services: The total count of services represented in the environment
* Catalog Items: The total count of published catalog items
* Subscriptions: The total count of subscribers to all the published catalog items

### Services Table

The table at the bottom of the page is a representation of all of the services that exist within the environment. This table is sortable by title, logical name, and when the service was created or last modified. You can search by title, name, or tag.

Each result in the table contains an icon, description, the tags associated with the service, and the title of the service.

There are indicators that display the number of versions for the service as well as the user who last modified the service and when. There is an option to delete the service from this table.

You can select the title of any service in the table to view additional details.

[View Service Details](/docs/central/env_gw_mgmt/api_service_details/)
