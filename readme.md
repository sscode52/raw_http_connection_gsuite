
# Custom HTTP connector for GSuite Admin in Workflows


## Overview

Our current Workflows connector for G Suite Admin does not include all functions within Google Workspace APIs . The Custom API card is also restricted to the Directory and Licensing APIs. As our product team expands the scopes and permissions for different Workspace APIs, you can use this guide as a workaround to create your own custom HTTP connector to request for specific scopes from different Workspace APIs.


## Before you get Started/Prerequisites

Before you get started you will need:



*   Access to an Okta tenant with Okta Workflows enabled for your org
*   Access to a tenant for Google Workspace

## Workflow Setup Steps



1. Navigate to[ https://console.developers.google.com/](https://console.developers.google.com/) and login with the G Suite Admin login.
2. If you do not already have a project, create a new project, leave the rest to defaults and click on Create:



## Testing this flow



*   Ensure all three flows are turned on.
*   From Okta administration, add a user to the group you have created.
*   The “User added to Group” flow should be triggered. The flow should add the user, group, expiration to the “User Added to Temporary Groups” table.
*   Run the “Scan users for removal” flow to scan the user table to see if users should be removed from groups. If the scan is run after the duration specified, you should see the user removed from the group and removed from the user table as clean up.


## Limitations & Known Issues 



*   Keep in mind the [Okta Workflows System Limits](https://help.okta.com/en/prod/Content/Topics/Workflows/workflows-system-limits.htm).
*   When invoking HTTP endpoints consider any applicable rate limits of the SaaS application (or http endpoint) that you are invoking. You should almost always set up error handling on the card to retry periodically.
