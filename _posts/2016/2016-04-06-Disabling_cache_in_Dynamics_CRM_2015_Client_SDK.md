---
layout: post
title:  Disabling cache in Dynamics CRM 2015 Client SDK
date:   2016-04-06
categories: crm
tags:
  - crm
  - sdk
  - c#
---
When utilizing Dynamics CRM 2015 Client SDK I have encountered a problem where CrmOrganizationServiceContext would always return some old, cached data from given set, until addition of a new item to this set using Client SDK, thus disallowing discovery of changes made by CRM team directly.

For example: Using Client SDK I wanted to download a list of Incidents from IncidentSet. Once downloaded, the following calls to IncidentSet would always return the same data every request, even if some incident details were changed in CRM Portal. After a while of searching the interwebz __it turns out you can disable the cache using .TryAccessCache() extension method.__

```csharp
var connection = CrmConnection.Parse(connectionString);
var org = new CrmOrganizationServiceContext(connection);
org.TryAccessCache(x => x.Mode = OrganizationServiceCacheMode.Disabled);
```
