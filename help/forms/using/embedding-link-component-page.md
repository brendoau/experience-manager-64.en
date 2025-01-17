---
title: Embedding link component in a page
seo-title: Embedding link component in a page
description: You can use the link component to link an adaptive document or an adaptive form from any page.  
seo-description: You can use the link component to link an adaptive document or an adaptive form from any page.  
uuid: fde56b5f-634c-406f-a026-875f972f7c8f
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: a4a36e73-3f7a-4173-8807-931f26daa35a
exl-id: eb816a35-0773-4eda-95b2-1d351c71be8b
---
# Embedding link component in a page{#embedding-link-component-in-a-page}

## Prerequisites {#prerequisites}

The link component is a member of the Document Services category. Ensure that the Document Services category is visible in the AEM components browser. If the category is not listed, follow the steps listed at [Enabling forms portal components](/help/forms/using/enabling-forms-portal-components.md).

## Link Component {#link-component}

The Link component allows form portal authors to create a link to an adaptive form from anywhere on a page. The Link component is available in the Document Services section in the component browser.

Perform the following steps to add a Link component to the page:

1. Drag the **Link** component on the page. Select the component and tap ![cmppr](assets/cmppr.png). The Edit Link Component dialog opens.

   ![edit-link-component](assets/edit-link-component.png)

1. In the **Display** tab, specify the following:

    * **Link Caption**: Link text or caption for the link.
    * **Link Tooltip**: Tool tip for the link.
    * **Layout Template**: Template for the layout of Link component.

1. Open the **Asset Info** tab and specify the type of the asset. An asset can be a **form**. Depending upon the type of asset selected, the options listed below are displayed:

    * **Asset Path**: Repository path where the asset is stored.
    * **Render Type**: The render format--PDF, HTML, or Auto. The Auto render type detects the user environment and accordingly renders the form as HTML or as PDF. For example, if the form is accessed from a mobile device, the Auto render type render the form in HTML.
    * **Submit URL:**  URL to the servlet where the form data is submitted.
    * **HTML Profile**: Profile for rendering the form as HTML.
    * **PDF Profile**: Profile for rendering the form as PDF document.

1. Open the **Advanced** tab. You can specify the additional parameters in the key-value pair format. When the link is clicked, these additional parameters and passed along with the form.

   Tap **Done** to save the configuration.

## Best practices for using Link component {#best-practices-for-using-link-component-br}

* Ensure that you select PDF as the render type if the path specified in Form Path points to a document which has PDF as its allowed render format.
* Submit URL for a form can be specified at several places and its order of precedence is as follows:

    1. Submit URL embedded in the form (in submit button) has the highest priority.
    1. Submit URL mentioned in Forms Manager has the medium priority.
    1. Submit URL mentioned in forms portal has the lowest priority.
