---
description: Describes the components of an Audience Manager segment, the expressions used to set audience qualification criteria, and how data is transmitted in an event call.
seo-description: Describes the components of an Audience Manager segment, the expressions used to set audience qualification criteria, and how data is transmitted in an event call.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Signals, Traits, and Segments
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
---

# Signals, Traits, and Segments{#signals-traits-and-segments}

Describes the components of an Audience Manager segment, the expressions used to set audience qualification criteria, and how data is transmitted in an event call.

<!-- 

c_signal_trait_segment.xml

 -->

**Composition and Purpose**

[!DNL Audience Manager] data consists of signals, traits, segments, and related qualification rules. The data elements and rules combine to create segments. Segments organize site visitors into related groups. The following table defines the three principal components in an [!DNL Audience Manager] segment.  

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Consists of </th> 
   <th colname="col3" class="entry"> Example </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Signal</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">The key is a constant that defines a data set (e.g., gender, color, price). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">The value is a variable related to the constant (e.g., male/female, green, 100). </li> 
    </ul> <p>Comparison operators join the key-value pair and set the relationship between them. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trait</b> </td> 
   <td colname="col2"> <p>Combinations of one or more signals. </p> <p>Boolean expressions and comparison operators let you create trait qualification rules. </p> <p>Create precise qualification requirements with combinations of traits and trait groups. </p> </td> 
   <td colname="col3"> <p>From the available signals, you could create a "High End Camera Browser" rule expressed as: </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segment</b> </td> 
   <td colname="col2"> <p>Users who share a set of common attributes and qualify for related traits. </p> <p>Boolean expressions, along with recency/frequency requirements, let you create segment qualification rules. </p> <p>Create precise qualification requirements with combinations of trait and segment rules. </p> </td> 
   <td colname="col3"> <p>From the available traits and signals, you could create a segment rule expressed as: </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Use the diagram below to keep a mental note of the relationship between signals, traits, and segments.

![](assets/signals-traits-segments.png)

**Build Traits and Segment Rules With Visual Tools and Code Editors**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. The visual tools let you create rules using search features, pop-up options, drop-down menus, and drag and drop functionality. The code editors provide advanced users with a way to programmatically develop audience segmentation criteria.

**Event Calls Send Data to Audience Manager**

An event call sends data from your website to [!DNL Audience Manager]. The call contains signal, trait, and segment data in an HTTP request. The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager]. 

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_LIKE_THIS]
>
>* [Segments: Purpose, Composition, and Rules](../features/segments/segments-purpose.md)
