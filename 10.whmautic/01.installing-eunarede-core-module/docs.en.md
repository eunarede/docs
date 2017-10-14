---
title: 'Installing EunaRede Core Module'
published: true
date: '21-09-2017 04:03'
publish_date: '21-09-2017 04:04'
taxonomy:
    category:
        - docs
    tag:
        - whmcs
external_links:
    process: true
    no_follow: true
    target: _blank
visible: true
---

The modules developed by EunaRede require the installation and activation of the base module called **EunaRede Core**. The EunaRede Core module enables the management and maintenance of the modules offered to be carried out in a standardized and planned way, following a software life cycle.

!! ensure that the EunaRede Core module is enabled **before** activating the acquired module.

## Upload to FTP

Download the module in the downloads area in your control panel, unzip and upload to the respective directory `modules/addons`.
![](Screenshot%20from%202017-09-23%2004-22-32.png)

## Activating the module

After you submit the directory, go to your WHMCS admin panel and go to **Setup > Addon Modules**. Activate the EunaRede Core module.

![](eunaredecore-activate.png)

## Configuring Access Permissions

Configure the access permissions for the groups you want. You must configure at least the administrator group to be able to access the module.
![](WHMCS%20%20%20Addons.jpg)

After activation, you can access the module through the **Addons > EunaRede Core** menu. By activating a EunaRede module, you can confirm your license through this support module. If there are no active modules, a message will be displayed as in the image below.

!!!! Now you can install and activate any of EunaRede Modules. 

![](eunaredecore-acvite.png)

From this point, follow the settings specified in each active module.