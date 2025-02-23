---
description: With Trait Recommendations, when you build or edit a segment in Segment Builder, you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Add the recommended traits to your segment to increase your target audience.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: 
---

# Trait Recommendations

Get live trait recommendations as you build your segments.

## Video Demonstration

Start by watching the Trait Recommendations video, then read on for more information.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

## Overview

[!UICONTROL Trait Recommendations], powered by [!DNL Adobe Sensei], brings data science into your Audience Manager day-to-day workflows.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Add the recommended traits to your segment to increase your target audience.

![Trait Recommendations Overview](assets/trait-recommendations-overview.png)

**In a nutshell:**

* Audience Manager shows first party traits and third party traits from your currently subscribed data feeds as recommended traits.
* Audience Manager shows a maximum of fifty traits similar to the one in the segment rule.
* You can filter out the data sources from which you don't want to see any recommendations.
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* If you see the error message "No similar traits found. Trait(s) may be too new.", this means that either there was no activity for that trait in the last 30 days, or Audience Manager has not yet updated the recommendations for that trait. Please try again in 24 hours.

## Use Cases

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* As a marketer, you can quickly find audiences interested in complementary products with the help of similar traits, so that you can increase your reach.
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## Differences Between Trait Recommendations and Algorithmic Models

### Algorithmic Models

[!UICONTROL Algorithmic Models] not only finds the most influential traits, but also scores users based on those traits and assigns each user an individual score. You then create algorithmic traits to target your users. With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] enables you to select users at different accuracy levels and test in [!UICONTROL Audience Lab] which group of users converts better. See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### Trait Recommendations

[!UICONTROL Trait Recommendations] is a quick way to get insights on other traits which are similar to the ones you are using in a segment.

You should use [!UICONTROL Trait Recommendations] when:

* You need quick insights while building a segment;
* You are using the segments for short campaigns or when you want to quickly suppress audience who converts;
* You are trying to maximize reach.

## Workflow

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. The Segment builder workflow is very similar for new and existing segments:

### New Segments

1. In **Audience Data > Segments**, select **Add New**.
2. In the **Traits** drop-down box, add at least one trait to the segment rule.
3. You can now see recommended traits that are similar to the traits you added to the segment rule. Scroll down to see all recommended traits.
4. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
    > [!NOTE]
    > 
    >The excluded data sources are shown just above the list of recommended traits. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
5. To add recommended traits to the segment rule, click the **+** symbol.

### Existing Segments

1. Go to **[!UICONTROL Audience Data] > [!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. You can see recommended traits, that are similar to the traits already in the segment rule. Scroll down to see all recommended traits.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
    > [!NOTE]
    > 
    >The excluded data sources are shown just above the list of recommended traits. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

When you create or edit a segment and add a trait to the segment rule, you see a maximum of fifty recommended traits,similar to the one you have added. If the segment rule contains more than one trait, Audience Manager uses a round robin method to show the best match for each trait, then the second-best match for each trait, and so on, for the largest fifty traits by population, in the segment rule.

![Three Base Traits](assets/three-base-traits.png)

For example, when there are three traits in the segment rule, as shown below, the recommended traits are:

1. Best match for trait 3 (the trait with the largest population);
2. Best match for trait 1;
3. Best match for trait 2;
4. Second-best match for trait 3;
5. Second-best match for trait 1, and so on until you get to fifty traits.

To get recommendations for a specific trait, you can click on the traits in the segment rule (1) or in the recommended traits view (2).

![](assets/three-base-traits-numbered.png)

Clicking on a trait opens a pop-up window, as shown in the image below. If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>The excluded data sources from the main page are considered while generating recommendations within the trait information pop-up window. And, if you exclude data sources in this view, the exclusions apply to the main page.

> [!NOTE]
>
> Recommended traits can be your first-party traits or third party traits from feeds that you are subscribed to.

## How it Works

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Manager then displays up to fifty traits that have the highest similarity.

## Trait Similarity Score

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. For two traits A and B, the calculation looks like this:

![](assets/jaccard_similarity.png)

See, also, the two examples below.

### Example 1 - Low Trait Similarity Score

Given two traits A and B, let's say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### Example 2 - Trait Similarity Score

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### How to Interpret the Trait Similarity Score

Use the table below as a rough guide to trait similarity. This guide is based on the similarity scores observed across a majority of the traits.

| [!UICONTROL Trait Similarity Score] | Significance |
---------|----------|
 0.1 and above | High similarity between traits |
 0.03 - 0.1 | Medium similarity between traits |
 0.01 - 0.03 | Low similarity between traits |
 0 - 0.01 | Very low similarity between traits |

## Role-Based Access Control ( RBAC)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## Limitations

* Currently, Audience Manager does not show folder traits as recommended traits. Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.