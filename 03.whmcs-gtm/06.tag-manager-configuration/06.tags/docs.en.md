---
title: Tags
published: true
date: '09-10-2017 00:37'
publish_date: '09-10-2017 00:37'
taxonomy:
    category:
        - docs
external_links:
    process: true
    title: false
    no_follow: true
    target: _blank
    mode: active
---

## Add a Tag

A tag is a piece of code that sends information to a third party, such as Google Analytics.

### Deploying Google Analytics Tag for WHMCS

!! On May 2017 Google Tag Manager have been update the Google Analytics Tracking code and variables, now the Ecommerce settings and Datalyer settings have your configuration under the _Google Analytics Settings Variables_, check this update on **[Deploying Google Analytics Variable](/whmcs-gtm/tag-manager-configuration/configuring-google-analytics-settings-variable)**

Google Tag Manager allows you to deploy Google Analytics using the Universal Analytics template. To install a Google Analytics tag for WHMCS, create a new tag and select Google Analytics as the tag type. Select the trigger **checkout** for the tag to fire.

* Tag name: **```WHMCS Enhanced Ecommerce```**;
* Tag type: **Universal Analytics**;
* Track Type: **Event** (_capital E_);
* Category: ** {\{category}} **;
* Action: ** {\{Event}} **;
* Label: ** {\{label}} **;
* Value: ** {\{value}} **
* Google Analytics Settings: **[select the previously created configuration](/whmcs-gtm/tag-manager-configuration/configuring-google-analytics-settings-variable)**
* Triggering: **[select the checkout trigger previously created](/whmcs-gtm/tag-manager-configuration/triggers)**

![](img-00013.jpg)
![](img-00014.jpg)