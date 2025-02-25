---
title: "Programmability and Extensibility - Power Platform API - 2020-10-01 - List tenant settings (preview) | Microsoft Docs"
description: Power Platform API Reference - List tenant settings
author: laneswenka
ms.reviewer: sericks
ms.component: pa-admin
ms.topic: reference
ms.date: 06/14/2023
ms.subservice: admin
ms.author: laswenka
search.audienceType: 
  - admin
contributors:
- bibekTimalsina948 
---

# List tenant settings (preview)

[!INCLUDE [cc-beta-prerelease-disclaimer](../includes/cc-beta-prerelease-disclaimer.md)]

You can list settings applicable to your tenant.

## Authentication

For more information about permissions and how to select them, see [Authentication - legacy](programmability-authentication.md).

## HTTP request

```http
Authorization: Bearer eyJ0eXAiOi...
Host: api.bap.microsoft.com
Accept: application/json
POST https://api.bap.microsoft.com/providers/Microsoft.BusinessAppPlatform/listtenantsettings?api-version=2020-10-01
```

## Request headers

| Header         | Value                     |
|----------------|---------------------------|
| Authorization  | Bearer {token} (required) |
| Content-Type   | application/json          |

## Request body

Don't supply a request body for this method.

## Response

The response is always a **200 OK** response, unless you aren't correctly authenticated. 

## Example

```json
{
    "walkMeOptOut": false,
    "disableNPSCommentsReachout": false,
    "disableNewsletterSendout": false,
    "disableEnvironmentCreationByNonAdminUsers": false,
    "disablePortalsCreationByNonAdminUsers": false,
    "disableSurveyFeedback": false,
    "disableTrialEnvironmentCreationByNonAdminUsers": false,
    "disableCapacityAllocationByEnvironmentAdmins": false,
    "disableSupportTicketsVisibleByAllUsers": false,
    "powerPlatform": {
        "search": {
            "disableDocsSearch": false,
            "disableCommunitySearch": false,
            "disableBingVideoSearch": false
        },
        "teamsIntegration": {
            "shareWithColleaguesUserLimit": 10000
        },
        "powerApps": {
            "disableShareWithEveryone": false,
            "enableGuestsToMake": false
        },
        "modelExperimentation": {
            "enableModelDataSharing": false,
            "disableDataLogging": false
        },
        "catalogSettings": {
            "powerCatalogAudienceSetting": All
        }   
    }
}
```
## Definitions

| Property | Type | Description |
|----------|------|-------------|
|walkMeOptOut| Boolean | Ability to opt out of guided experiences using WalkMe in Power Platform.  Default is false.|
|disableNPSCommentsReachout| Boolean | Ability to disable re-surveying users who left prior feedback via NPS prompts in Power Platform.  Default is false.|
|disableNewsletterSendout | Boolean | Ability to disable the newsletter sendout feature.|
|disableEnvironmentCreationByNonAdminusers | Boolean | Restrict all environments to be created by Tenant Admins, Power Platform Admins, or Dynamics365 Service Admins.  Default is false.|
|disablePortalsCreationByNonAdminusers | Boolean | Restrict all portals to be created by Tenant Admins, Power Platform Admins, or Dynamics365 Service Admins.  Default is false.|
|disableSurveyFeedback | Boolean | Ability to disable all NPS survey feedback prompts in Power Platform.  Default is false.|
|disableTrialEnvironmentCreationByNonAdminusers | Boolean | Restrict all trial environments to be created by Tenant Admins, Power Platform Admins, or Dynamics365 Service Admins.  Default is false.|
|disableCapacityAllocationByEnvironmentAdmins | Boolean | Ability to disable capacity allocation by environment administrators.|
|disableSupportTicketsVisibleByAllUsers | Boolean | Ability to disable support ticket creation by non-admin users in the tenant.|
|powerPlatform.search.disableDocsSearch | Boolean | When this setting is true, users in the environment will see a message that Microsoft Learn and Documentation search categories have been turned off by the administrator in the search results page.  Default is false.|
|powerPlatform.search.disableCommunitySearch | Boolean | When this setting is true, users in the environment will see a message that Community and Blog search categories have been turned off by the administrator in the search results page.  Default is false.|
|powerPlatform.search.disableBingVideoSearch | Boolean | When this setting is true, users in the environment will see a message that Video search categories have been turned off by the administrator in the search results page.  Default is false.|
|powerPlatform.teamsIntegration.shareWithColleaguesUserLimit | Integer | Maximum value setting for the number of users in a security group used to share an app built using Power Apps on Microsoft Teams.  Default is 10000 but can be increased or decreased as required.|
|powerPlatform.powerApps.disableShareWithEveryone | Boolean | Ability to disable the Share With Everyone capability in all Power Apps.  Default is false.|
|powerPlatform.powerApps.enableGuestsToMake | Boolean | Ability to allow guest users in your tenant to create Power Apps.  Default is false.|
|powerPlatform.modelExperimentation.enableModelDataSharing | Boolean | Ability to allow Microsoft to read Power Automate Copilot AI feature customer data (inputs and outputs) and provide improved models.  Default is false.|
|powerPlatform.modelExperimentation.disableDataLogging | Boolean | Ability to disable data logging and remove all data logged for Power Automate Copilot AI feature customer data (inputs and outputs).  Default is false.|
|powerPlatform.catalogSettings.powerCatalogAudienceSetting | Enum |This setting is reserved for future use. No enforcement is driven by this setting at the current time.|
|powerPlatform.licensing.disableUseOfUnassignedAIBuilderCredits| Boolean | Ability to use unallocated AI Builder credits in environments without allocated credits. Default is true. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
