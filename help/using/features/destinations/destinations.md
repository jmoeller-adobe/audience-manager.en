---
description: In Audience Manager, a destination is any third-party system (ad server, DSP, ad network, etc.) that you want to share data with. Destination Builder is the tool you used to create and manage cookie, URL, or server-to-server destinations.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: In Audience Manager, a destination is any third-party system (ad server, DSP, ad network, etc.) that you want to share data with. Destination Builder is the tool you used to create and manage cookie, URL, or server-to-server destinations.
seo-title: Destinations
solution: Audience Manager
title: Destinations
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
---

# Destinations Overview {#destinations}

In Audience Manager, a destination is any third-party system (ad server, [!DNL DSP], ad network, etc.) that you want to share data with. [!UICONTROL Destination Builder] is the tool you used to create and manage cookie, [!DNL URL], or server-to-server destinations.

## Purpose and Advantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] and [!UICONTROL Destination Builder] let you create destinations and send information about segmented users to your data partner. This helps you:

* **Protect data value:** Rather than send all user data to a destination, [!UICONTROL Destination Builder] let you share specific information about qualified users only.
* **Take action on your data:** Sending data to a destination partner helps them quickly develop and target qualified audience segments.
* **Reduce technical overhead:** Business users can set up destinations safely in the [!UICONTROL Destination Builder] interface. This helps reduce the time required for pre-deployment testing. With [!UICONTROL Destination Builder], you create, manage, and delete destinations as your business needs change, all without working through a long development cycle.

## Technical Considerations {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Data delivery depends on how your data partner wants to, or can, receive destination information. Technical or engineering constraints may prevent a destination from receiving data via [!DNL URL], cookie, or server-to-server processes. Work with your third-party partner to determine which method they can use.

## Business Considerations {#business-considerations}

Business decisions for selecting one delivery method over another depend on the technical capabilities of your destination partner and what you want to do with qualified user information. For example, technical constraints can limit your options if a destination cannot receive data by a particular delivery method. However, if there are no technical issues, you can send information based on how you want to take action on that data. For example:

* [!DNL URL]s and cookie-based destinations work almost synchronously with user actions on a page.
* Server-to-server methods are good for building deep audience segments over time.

## Destination Types and Typical Uses {#destination-types}

The examples in the following table can help you understand when to use a particular destination and the differences between each type.

| Destination Type | Typically Used When | Example | Considerations |
|--- |--- |--- |--- |
|**URL** or **Cookie**|You need to transfer data immediately so a destination can take action on a qualified user right away.|Sending data from a ticket purchasing site. Use a URL or cookie destination to qualify user and immediately re-target.|<ul><li>Transfers data about new visitors only. </li><li>Visitors must be seen again to qualify for the segment.</li></ul>|
|**Server-to-server**|<ul><li>Immediate data transfer is not required.</li><li>Collecting data to build a large audience pool of qualified users.</li></ul>|Collecting data over time (hours or days) to use it in a campaign set to run at a later date.|<ul><li>Transfers data about new and previous site visitors. </li><li>Visitors don't have to be seen again to qualify for other segments.</li></ul>|
