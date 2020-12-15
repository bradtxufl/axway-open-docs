---
title: View the details of an API service
linkTitle: View the details of an API service
weight: 30
date: 2020-12-14
description: Understand the details of your API service
---

{{< alert title="Public beta" color="warning" >}}This feature is currently in **public beta** and not yet available for production use.{{< /alert >}}

You can view details of your API service and of current or previous versions of that service.

Select which version of your API service to view by using the searchable dropdown selector at the top of the page.
(The most recent version of your service is displayed when you first navigate to this page)

Below there are three information sections and three tabs containing further details.

![Service Details Page](/Images/central/env_and_gateway_mgmt/ServiceDetailsPage.png)

### Service Information

The service information section contains general information and any tags or attributes that are specific to the service asset. Attributes in this context are key and value pairs used for extending functionality and integrations with third party systems.

### Activity Report

The values in the activity report section represent a holistic view of metrics within the selected version of your service.  These aggregate values can provide quick access to information about the distribution of your service version and the subscriptions associated with it.

* Endpoints: The total count of endpoints associated with this service version
* Catalog Items: The total count of successfully published items in the Unified Catalog
* Subscriptions: The total count of subscribers to all the published catalog items

The number of catalog items listed here may differ from the number of items available in the Catalog Items table below.  This count only recognizes items that are available in the Unified Catalog whereas the table also contains items that were not published or that are in an error state.

### Version Information

This section contains information specific to the version of the service that you have selected from the dropdown menu. It includes the type of specification represented by the service version (OAS2, OAS3, WSDL, Protobuf, etc.).

### Specification Tab

This tab displays the contract or methods for your selected API service version. Some specification types provide a visualization of your API methods and some fields are collapsible. You may be able to see additional information by clicking to open relevant methods or models.

### Endpoints Tab

This tab contains a table listing the URLs pointing to deployed instances of the API service.

### Catalog Items Tab

This tab contains a table listing both successfully published and unpublished items in the Unified Catalog. Each entry contains the item's state (PUBLISHED, UNPUBLISHED, or IN ERROR).

### Deleting endpoints and catalog items

You can delete any item in the endpoints or catalog items tabs by selecting the ellipsis in it's row, then selecting delete.
