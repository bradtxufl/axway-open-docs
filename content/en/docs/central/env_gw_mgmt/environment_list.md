---
title: View your environments
linkTitle: View your environments
weight: 10
date: 2020-12-14
description: All of your environments displayed in one place.
---

{{< alert title="Public beta" color="warning" >}}This feature is currently in **public beta** and not yet available for production use.{{< /alert >}}

The environments page contains all of your environments in a searchable and sortable list. An environment is a logical container for grouping APIs and additional assets. This list contains:

* the Axway Cloud SaaS environment
* Environments using a service mesh gateway
* Environments using the API service model
    * AWS Gateway environments
    * API Manager environments
    * Environments that have been defined manually using the AMPLIFY Central CLI or APIs

You can add a new environment from this page by selecting the **+ Environment** button and customizing it with your environment's information.

![Environment List Page](/Images/central/env_and_gateway_mgmt/EnvironmentListPage.png)

### Interact with the list

This page can be sorted by an environment's logical name, title, or by the time that they were created or last modified. Some environments contain both a logical name and a more customizable title which are both displayed on this page.

You can search the environments by their logical name, title, or any tags that are attached to it.

### Anatomy of the results

Each environment in the list contains some basic information about the environment for quick viewing.

![Environment Results Details](/Images/central/env_and_gateway_mgmt/EnvironmentListResult.png)

Each entry contains:

1. Title
2. Logical name
3. An icon
4. The connection status of agents within the environment (This status will display MANUAL SYNC if an API Service is not connected using an AWS Gateway or API Manager discovery and traceability agent)
5. Description
6. Tags
7. The number of service assets housed in the environment
8. An indication of which user last modified the environment and when
9. An option to delete the environment

You can select the title or logical name of the environment to view additional details.

### View environment details

For environments created using the API service model, the details page lists the title of the environment along with the status of any connected discovery and traceability agents, and includes three sections below with additional information

![Environment Details Page](/Images/central/env_and_gateway_mgmt/EnvironmentDetailsPage.png)

### Environment Information

The environment information section contains general information and any tags or attributes that are specific to the environment asset. Attributes in this context are key and value pairs used for extending functionality and integrations with third party systems.

### Activity Report

The values in the Activity Report section represent a holistic view of metrics within the environment.  Here you can view aggregated values for how your environment assets are distributed and how many subscriptions exist across all of those assets.

* Services: The total count of services represented in the environment
* Catalog Items: The total count of published catalog items
* Subscriptions: The total count of subscribers to all the published catalog items

### Services Table

This table is a representation of all of the services that exist within the environment. It is sortable by title, logical name, and when the service was created or last modified. You can search by title, name, or tag.

There are indicators that display the number of versions for the service as well as the user who last modified the service and when.

### Deleting a service

You can delete a service by selecting the ellipsis in the service's row in the service table and then selecting delete.

You can select the title of any service in the table to view additional details.

[View Service Details](/docs/central/env_gw_mgmt/api_service_details/)
