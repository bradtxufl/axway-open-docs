---
title: View the details of an API service
linkTitle: View the details of an API service
weight: 30
date: 2020-12-14
description: Understand the details of your API service
---

{{< alert title="Public beta" color="warning" >}}This feature is currently in **public beta** and not yet available for production use.{{< /alert >}}

You can view details of your API service and of current or previous versions of that service.

The service title and a searchable dropdown selector of which version you would like to view are available at the top of the page.
(The most recent version of your service is displayed when you first navigate to this page)

Below there are three information sections and three tabs containing further details.

![Service Details Page](/Images/central/env_and_gateway_mgmt/ServiceDetailsPage.png)

### Service Information

The service information section contains the service's icon, title, logical name, description and any tags or attributes that are specific to the service asset. Attributes in this context are key and value pairs used for extending functionality and integrations with third party systems.

### Activity Report

The values in the activity report section represent a holistic view of metrics within the selected version of your service.

* Endpoints: The total count of endpoints associated with this service version
* Catalog Items: The total count of successfully published items in the Unified Catalog
* Subscriptions: The total count of subscribers to all the published catalog items

### Version Information

This section contains the name of the version that is selected, the user who created the version and who last modified it. You can also view the date and time that the service was created and last modified. It lists the type of specification represented by the service version (OAS2, OAS3, WSDL, Protobuf, etc.).

### Specification Tab

This tab displays the contract or methods for your selected API service version. You can download your specification file and review it in this tab. Some specification types provide a visualization of your API methods and some fields are collapsible. You may be able to see additional information by clicking to open relevant methods or models.

### Endpoints Tab

This tab contains a table listing the URLs pointing to deployed instances of the API service. For each result in the table you can view the URL and an indicator of who last modifed the endpoint and when. You can delete endpoints from their line in the table.

### Catalog Items Tab

This tab contains a table listing both successfully published and unpublished items in the Unified Catalog. Each entry contains the name of the catalog item, its state (PUBLISHED, UNPUBLISHED, IN ERROR), and the endpoint associated with it. There is an indicator of which user last modifed the catalog item and when. You can delete catalog items from their line in the table.
