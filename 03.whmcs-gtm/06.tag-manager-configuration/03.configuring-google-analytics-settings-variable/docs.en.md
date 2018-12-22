---
title: 'Configuring Google Analytics Settings variable'
published: true
date: '08-10-2017 21:02'
publish_date: '08-10-2017 21:03'
taxonomy:
    category:
        - docs
external_links:
    process: true
    no_follow: true
    target: _blank
---

Recently Google Tag Manage implemented a global variable for the container with default configuration of Google Analytics settings. Use this variable to pass all necessary informations to your tracking tags.

! If you already have this variable configured, please review the configurations and make the necessary adjustments. **If you can't change the seetings of existing variable, please create a new one**.

Select your container tag, go to _Variables_ option and click in the **new** button on the **User-Defined Variables** section.

![](img-00002.jpg)

On **Variable Configuration** choose the variable type **Google Analytics Settings**

![](img-00003.jpg)

Paste your Google Analytics Tracking ID and click in **More Settings**.

![](img-00005.jpg)

Enable **Enable Display Advertising Features** on _Advertising_ dropdown and **Enable Enhanced Ecommerce Features** under _Ecommerce_ option. Please **don't forget** to check the option **user data layer**.

![](img-00007.jpg)

To anhanced the tag features, we recommend that you:

* Change to **true** the option **Decorate Forms** on _Cross Domain Tracking_
* Change to **true** the option **Enable Enhanced Link Attribution** on _Advanced Configuration_

![](img-00006.jpg)

Now save the changes and go trought the next steps!