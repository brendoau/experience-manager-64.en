---
title: Basics of configuring forms
seo-title: Basics of configuring forms
description: Learn about the various forms services that help you create interactive data capture applications.
seo-description: Learn about the various forms services that help you create interactive data capture applications.
uuid: 9efb006a-8a40-4d37-808c-b413df535366
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d0c31205-1503-401c-b249-c35a40315819
index: y
internal: n
snippet: y
---

# Basics of configuring forms{#basics-of-configuring-forms}

The Forms service enables you to create interactive data capture client applications that validate, process, transform, and deliver forms typically created in Designer. Form authors develop a single form design that the Forms service renders in various formats:

* as PDF in Adobe Reader or in a browser
* as HTML in various browser environments including a compliant XHTML 1.0 rendering
* as form Guides in various browser environments that support Adobe Flash Player.

For additional information about the Forms service, see [Services Reference](http://www.adobe.com/go/learn_aemforms_services_63).

Using the Forms page in administration console, you can configure the behavior of the Forms service. These settings apply to all invocations of the service. Any parameters sent through the AEM forms SDK override the settings set in administration console; however, they affect only that particular invocation.

After you change the Forms settings in administration console, click Save. You do not need to restart the server for the changes to take effect. However, you may need to stop and restart the Forms service when configuring cache mode settings. (See [Starting and stopping services](../../../forms/using/admin-help/starting-stopping-services.md#starting-and-stopping-services).)