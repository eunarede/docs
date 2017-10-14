---
title: 'Enabling API and Authentication on Mautic'
published: true
date: '23-09-2017 02:04'
publish_date: '23-09-2017 02:28'
taxonomy:
    category:
        - docs
external_links:
    process: true
    no_follow: true
visible: true
---

## Enabling API and Authentication on Mautic

This module uses the Mautic API to perform its operations, it is necessary for your Mautic installation to have the API and HTTP authentication enabled.

To enable the API, go to Mautic and select the settings option by clicking on the wheel in the upper right corner.
![Mautic Dashboard](Dashboard%20%20%20Mautic.png)

In the side menu go to **"API Settings"**, check **yes** for **"API enabled?"** And **"Enable HTTP basic auth?"**.
![](Configuration%20%20%20Mautic.png)

## Creating a role

For security reasons, we suggest you create a user access rule to be configured in WHMCS. This user needs full access to the permissions in order to be able to manipulate information correctly through the API. To create a new role, access the wheel in the upper right corner and go to "**Role**". Click the **"New"** button, in the field **"Name"** set to `whmcs`. Check **yes** under **Has full system access?** so that this set of functions would have full access to Mautic.
![](Roles%20%20%20Edit%20whmcs%20%20%20Mautic%20%281%29.png)

## Creating a user for WHMCS

![](Users%20%20%20New%20User%20%20%20Mautic.png)

For security and control purposes, create a user that will only be used by WHMCS. Click on the wheel in the upper right corner and go to the **"Users"** option. Click **"New"** and add a user with information to help identify in the logs if needed.

We suggest the following:
* **First Name:** Mautic
* **Last Name:** for WHMCS
* **Role:** whmcs (if you did not create the permissions and roles, review the previous step)
* **Username:** whmcs

! Save this user and password securely.

!!!! always use a strong password