---
title: Changing default styles of HTML5 forms
seo-title: Changing default styles of HTML5 forms
description: HTML5 forms styling is based on CSS. You can change the default styles of the form.
seo-description: HTML5 forms styling is based on CSS. You can change the default styles of the form.
uuid: dab888b1-d1a9-4990-ab21-96570beafd26
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: a9ab5a78-2add-46e1-a8f2-444d0f25f43a
feature: Mobile Forms
exl-id: 74e54d96-e418-40aa-9b93-561fbdd6312d
---
# Changing default styles of HTML5 forms {#changing-default-styles-of-html-forms}

HTML5 forms are rendered using HTML5 capabilities and the styling of the rendered form is done using CSS. Default appearance of a HTML5 forms is similar to its PDF rendition. Developers can use custom CSS to change default appearance of HTML5 forms.

This article provides step-by-step information to change style of an HTML5 form and [Introduction to Styles](/help/forms/using/css-styles.md) article contains detailed information about various styling aspects of HTML5 forms. Ensure that you read Introduction to styles article before performing steps mentioned in this article.

The following two images show the difference between the default and customized styles.

![pictures-002-small](assets/pictures-002-small.png) 

## Style your forms {#style-your-forms}

1. **Choose a profile to add custom styles**

   Access the CRX DE interface at the URL: **https://&lt;server&gt;:&lt;port&gt;/crx/de** and create a profile or choose an existing profile. To know how to create a profile, see [Creating a new Profile](/help/forms/using/custom-profile.md)

1. **Create a CSS style sheet for styling the HTML5 forms**

   Navigate to the folder in which you have created the profile renderer and create a CSS style sheet file. The steps to follow are

    1. Right click the folder and select **create** -&gt; **create File** from the menu

   To know which CSS classes to create for a particular component in your HTML5 forms, see [Introduction to Styles](/help/forms/using/css-styles.md).  

1. **Include the style sheet in Profile Renderer**

   Open the Profile Renderer page (jsp file) in CRX DE, and include the CSS file in the page just below the XFA client library. Perform these steps to include the CSS file in profile.

    1. Search in the renderer page for the following line:  
    
       &lt;cq:includeClientLib categories="xfaforms.profile" /&gt;  
    
    1. Insert the following below the line above to include the style sheet:  
    
       &lt;link href="/path/to/stylesheet" rel="stylesheet" type="text/css"/&gt;  
    
    1. Save the file.
