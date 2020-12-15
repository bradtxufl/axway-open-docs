---
title: Viewing your environments
linkTitle: Viewing your environments
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

### Interacting with the list

This page can be sorted by an environment's logical name, title, or by the time that they were created or last modified. Some environments contain both a logical name and a more customizable title which are both displayed on this page.

You can search the environments by their logical name, title, or any tags that are attached to it.

### Anatomy of the results

Each environment in the list contains some basic information about the environment for quick viewing.

![Environment Results Details](/Images/central/env_and_gateway_mgmt/EnvironmentListResult.png)

Each entry contains:

1. Title
2. Logical name
3. An icon
4. The connection status of agents within the environment (This status will display MANUAL SYNC if an API Service is not connected using an AWS Gateway or API Mangager discovery and traceability agent)
5. Description
6. Tags
7. The number of service assets housed in the environment
8. An indication of which user last modified the environment and when
9. An option to delete the environment

You can select the title or logical name of the environment to view additional details.

[View Environment Details](/docs/central/env_gw_mgmt/environment_details/)
