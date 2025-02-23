---
description: Defines and describes standard and serialized key-value pairs.
keywords: integration code
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Key-Value Pairs Explained
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
---

# Key-Value Pairs Explained{#key-value-pairs-explained}

Defines and describes standard and serialized key-value pairs.

<!-- 

c_key_value_explained.xml

 -->

A key-value pair consists of two related data elements: A key, which is a constant that defines the data set (e.g., gender, color, price), and a value, which is a variable that belongs to the set (e.g., male/female, green, 100). Fully formed, a key-value pair could look like these:

* `gender = male` 
* `color = green` 
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. Standard formatting organizes data into separate key-value pairs. Each key is stated explicitly, even when used again to define a different value. By contrast, serialized formatting condenses multiple values into one set defined by a single key. Also, in a serialized pair, a special indicator is used to separate the values within the key-value set. Finally, standard and serialized key-values can contain single or multiple values. The following table provides examples of standard and serial key-value formats.  

|  Formatting  | Single Key  | Key-Value Pairs  |
|---|---|---|
|  **Standard** | `x=1&x=2`  | `x=1&x=2&y=3&y=4`  |
|  **Serialized** | `x=1;2`  | `x=1;2&y=3;4`  |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. Elements in key-value pairs are defined as follows:

* **Key:** A unique identifier in the key-value pair. 
* **Value delimiter:** Separates individual key-value pairs. 
* **Key-value separator:** Separates a key from the values within a key-value pair. 
* **Serial separator:** Separates individual values within serialized key-value pairs.

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Example </th> 
   <th colname="col3" class="entry"> Key </th> 
   <th colname="col4" class="entry"> Key-Value Separator </th> 
   <th colname="col5" class="entry"> Key-Value Delimiter </th> 
   <th colname="col6" class="entry"> Serial Separator </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Single key</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Key-value pairs</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Single key</b> <p>(serial) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/a </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Key-value pairs</b> (serial) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

