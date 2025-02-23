---
description: This document covers the technicalities related to the General Data Protection Regulation (GDPR) for Audience Manager and shows you how to submit GDPR requests to Audience Manager.
seo-description: This document covers the technicalities related to the General Data Protection Regulation (GDPR) for Audience Manager and shows you how to submit GDPR requests to Audience Manager.
seo-title: GDPR in Audience Manager
solution: Audience Manager
title: GDPR in Audience Manager
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
---

# GDPR in Audience Manager{#gdpr-in-audience-manager}

This document covers the technicalities related to the General Data Protection Regulation (GDPR) for Audience Manager and shows you how to submit GDPR requests to Audience Manager.

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

Before reading the Audience Manager specifics, we advise you go through the Experience Cloud material for the European General Data Protection Regulation (GDPR), linked below:

* [GDPR and Your Business](https://www.adobe.com/privacy/general-data-protection-regulation.html) 
* [GDPR Whitepaper](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md) 
* [GDPR Terminology](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

The sections below explain what GDPR means for Audience Manager and how you can submit GDPR requests to Audience Manager.

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the **[GDPR Client Services UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** or by calling the **[GDPR API](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). If you have questions, please reach out to Customer Care at gdprsupport@adobe.com.

## Access Data {#access-data}

We understand your commitment to honoring your GDPR customer requests within 30 days of reception. For that reason, we try to process your data access request as soon as possible.

**Request**

You can log data access requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** or by calling the **[GDPR API](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (see `access` action). In either case, you must upload a JSON with the Audience Manager identifiers for which you are submitting the data access request. See what a well-formed JSON looks like in the **[Experience Cloud GDPR documentation](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/access_request.json)**.

**Response**

Responses to access data requests contain a summary of total number of traits and segments, trait type, descriptions of traits and segments along with the respective data source names. The Access response will also include second party and third party data accessible to the Data Controller along with the first party data. When [!UICONTROL declared IDs] such as cross device CRM IDs or customer cookie IDs are sent in GDPR requests, Audience Manager will include the Access response from all the linked devices (up to 100 devices per declared ID).

**Response Status**

If there are any errors from Audience Manager in the response, these are surfaced as error codes in the response. We have a [list of error codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), where you can find more information about the returned errors.

**Example Response**

A sample access response could look like the one below. In this example, the Data Subject's ID is a cookie ID. They qualified for several traits and belong to a few segments. The cookie ID is linked to a mobile ID. The example also contains metadata for the phone they use.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

The table below contains descriptions for all the returned fields in the data access response, in the order that they appear above.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Field </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>The user ID for the data that follows. This is either an id you provided in the GDPR data access request, or an ID that is linked to one of the declared IDs you provided. The ID types are described in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Also referred to as data source. See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>The ID of the namespace/data source. See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>Integration codes are friendly names for your data sources, and help you track your data sources easier than using data source IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name </code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">For first party data, this is the customer's own company name. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">For second party data, this is the name of the partner company. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>The type of ID for which you requested the GDPR data access. Accepted types are listed in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Warnings return further information related to the data access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Brief information about the warning. </p> <p>The two warnings you may receive are: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Device Data </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Incomplete request </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>A more detailed description of the warning you received: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Device Data - Contains data from all users of this device </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Incomplete request - Retrieval of Audience Manager data was not completed. Some information may be missing. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>The traits and segments associated with this user ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Traits associated with the user ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>The name of the trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>The trait type. The possible values are: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>First party</i> for your own traits. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Second party</i> for traits that belong to your partners. Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Third party</i> for traits obtained from data partners, via the <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>A few words to help describe the trait's purpose or function. This is an optional field. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this trait's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source that this trait belongs to. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">For first party data, this is the customer's own company name. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">For second party data, this is the name of the partner company. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this trait. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segments </code> </p> </td> 
   <td colname="col2"> <p>Segments that this user belongs to. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>The name of the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>A few words to help describe this segment. This is an optional field. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this segment's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source that this segment belongs to. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">For first party data, this is the customer's own company name. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">For second party data, this is the name of the partner company. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this segment. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>Indicates whether the Data Subject is currently qualified for this segment. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>Additional ID that this ID has been linked to. Information is returned on: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (data source) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">data provider name </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>All these fields are described in the first rows of this table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>The exact time that an ID sync event made the link between IDs. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>Information about the device. This information includes the fields below. Note that not all fields are returned for all device types. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Hardware information </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Device manufacturer </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>The marketing name of the device </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>The device model </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>The name of the device's Operating System (OS) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>The version of the OS </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>The device vendor </p> </li> 
     </ul> </p> <p> <p>Note: We only return device metadata when you submit either one of: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">Mobile IDs </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager IDs </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud IDs </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delete Data {#delete-data}

We understand your commitment to honoring your GDPR customer requests within 30 days of reception. For that reason, we try to process your data deletion request as soon as possible.

**Request**

You can log data deletion requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** or by calling the **[GDPR API](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (see `delete` action). In either case, you must upload a JSON with the Audience Manager identifiers for which you are submitting the data access request. See what a well-formed JSON looks like in the [Experience Cloud GDPR documentation](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/delete_request.json)**.

**Response**

In response to data deletion requests, we delete traits and segments associated with the respective Audience Manager identifier. In addition, the respective Audience Manager identifiers for the Data Subject will be permanently opted out of further data collection by Audience Manager and the respective Id mappings will be removed. When declared IDs such as cross device CRM Ids or customer cookie ids are sent in GDPR requests, Audience Manager will perform the necessary Delete actions on all the linked devices (up to 100 devices per declared ID).

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager Identifiers (IDs) {#aam-ids}

When submitting GDPR requests to Adobe Audience Manager, you must include one of the identifiers (IDs) listed below. You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

### Adobe Audience Manager Unique User ID

**User ID**: aam_uuid 

**Definition**: Adobe Audience Manager Unique User ID

**Namespace ID**: 0

>[!NOTE]
>
>You can also use the CORE namespace. See the second JSON example.

**Example in JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**User ID**: mid

**Definition**: Adobe Experience Cloud ID, formerly known as Visitor ID or Marketing Cloud ID

**Namespace ID**: 4

>[!NOTE]
>
>You can also use the ECID namespace. See the second JSON example.

**Example in JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**User ID**: cid 

**Definition**: Customer ID, such as a cookie you set for anonymous site visitors or a CRM ID from an offline system or a hashed username

**Namespace ID**: Customer-specific. Please find it from your Audience Manager instance.

**Example in JSON**: 

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
  ```

### Mobile advertising ID

**User ID**: d_cid

**Definition**: Mobile advertising IDs.
>[!IMPORTANT]
>
> If you are using the Mobile SDK, then you should also send the Experience Cloud ID (MID) along with mobile advertising IDs for complete GDPR Access and Delete responses.

**Namespace ID**: 

* IDFA: 20915
* GAID: 20914

**Example in JSON**: 

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### Integration code

**User ID**: d_cid_ic

**Definition**: An integration code for the data source. This can be used instead of data source ID / namespace ID in the API request to Adobe Experience Cloud Privacy Core Service.

**Namespace ID**: Not applicable

Example in JSON: 

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
