---
title: Configure the Rich Text Editor
seo-title: Configure the Rich Text Editor
description: Learn to configure the AEM Rich Text Editor.
seo-description: Learn to configure the AEM Rich Text Editor.
uuid: e471a0fd-c5a9-4028-b914-ae0e101e205f
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 94e023eb-ae69-4856-b8e3-52d4eb5d1a18
index: y
internal: n
snippet: y
---

# Configure the Rich Text Editor{#configure-the-rich-text-editor}

The Rich Text Editor (RTE) provides authors with a wide range of functionality for editing their text content. Icons, selection boxes, toolbar, and menus are provided for a WYSIWYG text-editing experience.

RTE can be configured to enable, disable, and extend the features available in the authoring components. To know how to use RTE features for authoring, see [Use Rich Text Editor for authoring](../../../sites/authoring/using/rich-text-editor.md).

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-09-13T06:05:17.813-0400
Talk about a OOTB implementation. Example can be tried in the We.Retail site. Link to https://helpx.adobe.com/experience-manager/core-components/using/text.html
-->

The following workflow illustrates a recommended order of completing the RTE configuration tasks.

![Typical workflow to configure Rich Text Editor](assets/rte_workflow_v1.png)

Typical workflow to configure Rich Text Editor

## Understand Touch-enabled UI and Classic UI {#understand-touch-enabled-ui-and-classic-ui}

<!--
Comment Type: remark
Last Modified By: Ashish Gupta . (asgupta)
Last Modified Date: 2018-07-18T08:24:51.706-0400
<p>Describe RTE UX in different UIs.</p>
<p>Backlink to descriptions of both and to RNs about deprecation of Classic.<br /> </p>
<p>Call out specific config steps at the end.</p>
-->

The Touch-enabled UI is the standard UI for AEM. Adobe introduced Touch UI with [responsive design](../../../sites/authoring/using/responsive-layout.md) for authoring environment, in version 5.6. The Touch UI is designed for touch and desktop devices. The UI differs considerably from the original classic UI.

![Rich Text Editor toolbar in Touch-enabled UI](assets/chlimage_1-296.png)

Rich Text Editor toolbar in Touch-enabled UI

![Rich Text Editor toolbar in Classic UI](assets/rtedefault.png)

Rich Text Editor toolbar in Classic UI

**See also**:

* [UI recommendations](../../../sites/deploying/using/ui-recommendations.md)
* About deprecating the Classic UI, see [AEM 6.4 Release Notes](../../../release-notes/deprecated-removed-features.md)
* For difference between the UIs, see [Touch UI and Classic UI](https://aemcq5pedia.wordpress.com/2018/01/05/touch-enabled-ui-aem6-3/)
* To understand the Touch-enabled UI in detail, see [Concepts of AEM Touch UI](../../../sites/developing/using/touch-ui-concepts.md)

## Various modes of editing {#editingmodes}

Authors can create and edit textual content in AEM using the different modes of components. The toolbar options for authoring and formatting content and the user experience of RTE-enabled components in different editing mode varies based on RTE configurations.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th style="text-align: center;" valign="middle">Editing mode</th> 
   <th>Editing area</th> 
   <th>Recommended features to be enabled<br /> </th> 
   <th style="text-align: center;" valign="middle">Touch UI</th> 
   <th style="text-align: center;" valign="middle">Classic UI</th> 
  </tr> 
  <tr> 
   <td style="text-align: center;">Inline</td> 
   <td>In-place editing for quick, minor edits; Format without opening a dialog box</td> 
   <td>Minimal RTE features</td> 
   <td style="text-align: center;">Y</td> 
   <td style="text-align: center;">Y</td> 
  </tr> 
  <tr> 
   <td style="text-align: center;">RTE full screen</td> 
   <td>Covers entire page<br /> </td> 
   <td>All the required RTE features<br /> </td> 
   <td style="text-align: center;">Y</td> 
   <td style="text-align: center;">N<br /> </td> 
  </tr> 
  <tr> 
   <td style="text-align: center;">Dialog</td> 
   <td>Dialog box on top of the page content but does not cover the entire page</td> 
   <td>All the required RTE features in Classic UI; judiciously enable features in Touch UI<br /> </td> 
   <td style="text-align: center;">Y</td> 
   <td style="text-align: center;">Y</td> 
  </tr> 
  <tr> 
   <td style="text-align: center;">Dialog full screen<br /> </td> 
   <td>Same as Full screen mode; contains fields of the dialog alongside RTE<br /> </td> 
   <td>All the required RTE features</td> 
   <td style="text-align: center;">Y</td> 
   <td style="text-align: center;">N</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The source-edit feature is not available in inline editing mode in Touch-enabled UI. You cannot drag images in the full screen mode. All other features work in all the modes.

### Inline editing {#inline-editing}

When opened (with a slow double-tap/click) the content can be edited within the page. A compact toolbar with very basic options is presented.

![Inline editing with basic toolbar in Touch-enabled UI](assets/chlimage_1-297.png)

Inline editing with basic toolbar in Touch-enabled UI

In Classic UI, a slow double-click on the component allows inline editing and an orange outline highlights the content. If the Content Finder is open, a toolbar with the available RTE formatting options is displayed at the top of the window. If the Content Finder is not open, the formatting options are not displayed and you can do basic text edits only.

### Full screen editing {#full-screen-editing}

AEM components can be opened in full screen view that hides the page content and occupies the available screen. Consider full screen editing a detailed version of the inline editing as it offers the most editing options. It can be opened by clicking ![](assets/rte_fullscreen.png), from the compact toolbar when using the inline editing mode.

In the dialog full screen mode, along with a detailed RTE toolbar, the options and components available in a dialog are also available. It is applicable only for a dialog that contains RTE alongside other components.

![The detailed RTE toolbar when editing in full screen mode in Touch-enabled UI](assets/chlimage_1-298.png)

The detailed RTE toolbar when editing in full screen mode in Touch-enabled UI

### Dialog editing {#dialog-editing}

When a component is double-clicked a dialog box opens for editing the contents. The dialog box opens on top of the existing page. In some specific scenarios, the dialog opens as a pop-up window. For example, when a Text component is part of a column in a multicolumn page layout and the area available for the dialog is less.

![Dialog editing mode in Touch-enabled UI](assets/dialog_editing_modetouchui.png)

Dialog editing mode in Touch-enabled UI

![Dialog box in Classic UI that contains detailed toolbar for editing](assets/chlimage_1-299.png)

Dialog box in Classic UI that contains detailed toolbar for editing

## About RTE plug-ins and the associated features {#aboutplugins}

The functionality is made available via a series of plug-ins, each with:

* A `features` property:

    * Used to activate, or deactivate, basic functionality for that plug-in
    * That can be configured using a standardized procedure

* Where appropriate, additional properties and options requiring specialized configuration

Basic features of the RTE are activated, or deactivated, by the value of the `features` property on a node specific to the appropriate plug-in.

The following table lists the current plug-ins, showing:

* Plug-in IDs with a link to API documentation. ID is used as the node name when [activating a plug-in](../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#activateplugin).
* Permitted values for the `features` property.
* A description of the functionality provided by the plug-in.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="100"><p>Plug-in ID<br /> <br /> </p> </td> 
   <td valign="top" width="100"><p>features<br /> <br /> </p> </td> 
   <td valign="top" width="200"><p>Description<br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p>edit</p> </td> 
   <td valign="top" width="100"><p>cut<br /> copy<br /> paste-default<br /> paste-plaintext<br /> paste-wordhtml</p> </td> 
   <td valign="top" width="200"><p><a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#textstyles" target="_blank">Cut, copy and, the three paste modes</a>.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FindReplacePlugin">findreplace</a></p> </td> 
   <td valign="top" width="100"><p>find<br /> replace</p> </td> 
   <td valign="top" width="200"><p>Find and replace.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FormatPlugin">format</a></p> </td> 
   <td valign="top" width="100"><p>bold<br /> italic<br /> underline</p> </td> 
   <td valign="top" width="200"><p><a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#textstyles" target="_blank">Basic text formatting</a>.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ImagePlugin">image</a></p> </td> 
   <td valign="top" width="100"><p>image</p> </td> 
   <td valign="top" width="200">Basic image support (drag from content or Content Finder). Depending on the browser, the support has different behaviors for authors.</td> 
  </tr> 
  <tr> 
   <td valign="top"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.KeyPlugin">keys</a></p> </td> 
   <td valign="top"><p> </p> </td> 
   <td valign="top"><p>To define this value, see <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#tabsize" target="_blank">tab size</a>.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.JustifyPlugin">justify</a></p> </td> 
   <td valign="top" width="100"><p>justifyleft<br /> justifycenter<br /> justifyright</p> </td> 
   <td valign="top" width="200"><p>Paragraph alignment.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.LinkPlugin">links</a></p> </td> 
   <td valign="top" width="100"><p>modifylink<br /> unlink<br /> anchor</p> </td> 
   <td valign="top" width="200"><p><a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#linkstyles" target="_blank">Hyperlinks and anchors</a>.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ListPlugin">lists</a></p> </td> 
   <td valign="top"><p>ordered<br /> unordered<br /> indent<br /> outdent</p> </td> 
   <td valign="top"><p>This plug-in controls both <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#indentmargin" target="_blank">indentation and lists</a>; including nested lists.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p><a href="/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.MiscToolsPlugin">misctools</a></p> </td> 
   <td valign="top" width="100"><p>specialchars<br /> sourceedit</p> </td> 
   <td valign="top" width="200">Miscellaneous tools allow authors to enter <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#spchar" target="_blank">special characters</a> or edit the HTML source. Also, you can add a whole <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#definerangechar" target="_blank">range of special characters</a> if you want to define your own list.</td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p>Paraformat</p> </td> 
   <td valign="top" width="100"><p>paraformat</p> </td> 
   <td valign="top" width="200">The default paragraph formats are Paragraph, Heading 1, Heading 2, and Heading 3 (&lt;p&gt;, &lt;h1&gt;, &lt;h2&gt;, and &lt;h3&gt;). You can <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#paraformats" target="_blank">add more paragraph formats</a> or extend the list.</td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p>spellcheck</p> </td> 
   <td valign="top" width="100"><p>checktext</p> </td> 
   <td valign="top" width="200"><p><a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#adddict" target="_blank">Language aware spell checker</a>.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p>styles</p> </td> 
   <td valign="top" width="100"><p>styles</p> </td> 
   <td valign="top" width="200">Support for styling using a CSS class. <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#textstyles" target="_blank">Add new text styles</a> if you want to add (or extend) your own range of styles for use with text.</td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p>subsuperscript</p> </td> 
   <td valign="top" width="100"><p>subscript<br /> superscript</p> </td> 
   <td valign="top" width="200"><p>Extensions to the basic formats, adding sub- and super-script.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p>table</p> </td> 
   <td valign="top" width="100"><p>table<br /> removetable<br /> insertrow<br /> removerow<br /> insertcolumn<br /> removecolumn<br /> cellprops<br /> mergecells<br /> splitcell<br /> selectrow<br /> selectcolumns</p> </td> 
   <td valign="top" width="200">See <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#tablestyles" target="_blank">configure table styles</a>, if you want to add your own styles for either entire tables or individual cells.</td> 
  </tr> 
  <tr> 
   <td valign="top" width="100"><p>undo</p> </td> 
   <td valign="top" width="100"><p>undo<br /> redo</p> </td> 
   <td valign="top" width="200">History size of <a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#undohistory" target="_blank">undo and redo</a> operations.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The full screen plug-in is not supported in dialog mode. Use of the `dialogFullScreen` setting to configure the toolbar for full screen mode.

<!--
Comment Type: remark
Last Modified By: Ashish Gupta . (asgupta)
Last Modified Date: 2018-08-08T11:01:00.769-0400
<p>This topic should describe the happy path that an average developer would follow to configure RTE. The workflow steps should address only mainstream configuration and not edge cases. Add a very top-level overview of generic configurations.</p>
<p> </p>
<p>Possibly give a sample or two.</p>
<p>Consider this as a reference image of the jigsaw and individual sub-topics below as pieces of the jigsaw.<br /> </p>
<p>This is what I believe will be a good fit for this topic is:</p>
<ol>
<li>What all can be enabled using plug-ins?</li>
<li>Where to enable for a generic AEM component?</li>
<li>How to configure a specific plug-in, for various modes?</li>
<li>Touch upon the extended use case of customizations.</li>
</ol>
-->

## Understand the configuration paths and locations {#understand-the-configuration-paths-and-locations}

The [mode of RTE editing (and the UI)](#editingmodes) that you provide for your authors decide the location for the configuration details when you are [activating the RTE plug-ins](../../../sites/administering/using/configure-rich-text-editor-plug-ins.md#activateplugin):

| Editing mode |Location for Touch UI |Location for Classic UI |
|---|---|---|
| Inline |

```
cq:editConfig/cq:inplaceEditing

```

|
| Full screen | `cq:editConfig/cq:inplaceEditing` |Not applicable

```

```

|
| Dialog | `cq:dialog` | `dialog` |
| Full screen dialog | `cq:dialog` |Not applicable |

>[!NOTE]
>
>Do not name the node under `cq:inplaceEditing` as `config`. On `cq:inplaceEditing` node, define the following properties:
>
>* **Name**: `configPath`
>
>* **Type**: `String`  
>
>* **Value**: path of the node containing the actual configuration
>
>Do not name the RTE configuration node as `config`. Otherwise, the RTE configurations take effect for only the administrators and not for the users in the group `content-author`.

Configure the following properties that apply in Dialog editing mode in Touch UI only:

* `useFixedInlineToolbar`: Set this Boolean property defined on the RTE node (one with sling:resourceType= `cq/gui/components/authoring/dialog/richtext`) to `True`, to make RTE toolbar fixed instead of floating.  
  When this property is true, Richtext editing is, by default, started on the "foundation-contentloaded" event.  
  To prevent this, set the property `customStart` to `True`and trigger the 'rte-start' event to start RTE editing. When this property is 'true', the default behavior, rte start on click, does not work.

* `customStart`: Set this Boolean property defined on the RTE node to `True`, to control when to start RTE by triggering the event `rte-start`.

* `rte-start`: Trigger this event on the `contenteditable-div` of RTE, when to start editing RTE. This works only if `customStart` has been set to true.

When RTE is used in the touch-enabled dialog, setting the property `useFixedInlineToolbar` to true is mandatory to avoid issues.

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-09-26T06:45:17.213-0400
Re-purpose the FixedInlineToolbar content in the config RTE toolbar.
-->

## Enable RTE functionalities by activating plug-ins {#enable-rte-functionalities-by-activating-plug-ins}

RTE functionalities are made available via a series of plug-ins, each with features property. You can configure the features property to enable or disable the various features of each plug-in.

For detailed configurations of the RTE plug-ins, see [how to activate and configure the RTE plug-ins](../../../sites/administering/using/configure-rich-text-editor-plug-ins.md).

>[!NOTE]
>
>The [Core Components text component](/content/help/en/experience-manager/core-components/using/text) allows template editors to configure many RTE plugins in a GUI, eliminating the need for technical configuration.
>
>For more information, see [Creating Page Templates](../../../sites/authoring/using/templates.md) and the [Core Components developer documentation](/content/help/en/experience-manager/core-components/using/developing).

>[!NOTE]
>
>For reference purposes, the default Text components (delivered as part of a standard installation) can be found at:
>
>* `/libs/wcm/foundation/components/text`
>* `/libs/foundation/components/text`
>
>To create your own text component, copy the above component instead of editing these components.

## Configure RTE toolbar {#dialogfullscreen}

AEM allows you to configure the UI for the RichText Editor differently for the different editing modes. The default settings are provided below. You can override these defaults based on your requirements.

For best authoring experience, enable only the plug-ins without pop-up for a floating dialog as it is smaller in size. Configure the plug-ins with larger pop-up, such as the Paste plug-in, to be enabled only in full screen dialog.

```java
<uiSettings jcr:primaryType="nt:unstructured">
  <cui jcr:primaryType="nt:unstructured">
    <inline
      jcr:primaryType="nt:unstructured"
      toolbar="[format#bold,format#italic,format#underline,#justify,#lists,links#modifylink,links#unlink,#paraformat]">
      <popovers jcr:primaryType="nt:unstructured">
        <justify
          jcr:primaryType="nt:unstructured"
          items="[justify#justifyleft,justify#justifycenter,justify#justifyright]"
          ref="justify"/>
        <lists
          jcr:primaryType="nt:unstructured"
          items="[lists#unordered,lists#ordered,lists#outdent,lists#indent]"
          ref="lists"/>
        <paraformat
          jcr:primaryType="nt:unstructured"
          items="paraformat:getFormats:paraformat-pulldown"
          ref="paraformat"/>
      </popovers>
    </inline>
    <dialogFullScreen
      jcr:primaryType="nt:unstructured"
      toolbar="[format#bold,format#italic,format#underline,justify#justifyleft,justify#justifycenter,justify#justifyright,lists#unordered,lists#ordered,lists#outdent,lists#indent,links#modifylink,links#unlink,table#createoredit,#paraformat,image#imageProps]">
      <popovers jcr:primaryType="nt:unstructured">
        <paraformat
          jcr:primaryType="nt:unstructured"
          items="paraformat:getFormats:paraformat-pulldown"
          ref="paraformat"/>
      </popovers>
    </dialogFullScreen>
    <tableEditOptions
      jcr:primaryType="nt:unstructured"
      toolbar="[table#insertcolumn-before,table#insertcolumn-after,table#removecolumn,-,table#insertrow-before,table#insertrow-after,table#removerow,-,table#mergecells-right,table#mergecells-down,table#mergecells,table#splitcell-horizontal,table#splitcell-vertical,-,table#selectrow,table#selectcolumn,-,table#ensureparagraph,-,table#modifytableandcell,table#removetable,-,undo#undo,undo#redo,-,table#exitTableEditing,-]">
    </tableEditOptions>
  </cui>
</uiSettings>
```

Different UI settings are used for the inline mode and full screen mode. The toolbar property is used to specify the buttons of the toolbar.

For example, if the button is itself a feature (for example, Bold), it is specified as 'PluginName#FeatureName' (for example, links#modifylink).

If the button is a popover (containing some features of a plug-in), it is specified as '#PluginName' (for example, #format).

Separators ( | ) between a group of buttons can be specified with '-'.

The pop-up node under inline or full-screen mode contains a list of the popovers being used. Each child node under the 'popovers' node is named after the plug-in (for example, format). It has a property 'items' containing a list of features of the plug-in (for example, format#bold).

## Customize mapping between toolbar icons and commands {#iconstoolbar}

You can customize the mapping between Coral icons displayed on the RTE toolbar and the available commands. You cannot use any other icons besides Coral icons.

1. Create a node named `icons` under `uiSettings/cui`.

1. Create nodes for individual icons under it.
1. On each of the individual icon nodes, specify a Coral icon and a command to map to the icon.

Below is a sample snippet to map the command Bold to the Coral icon named `textItalic`.

```java
<text jcr:primaryType="nt:unstructured" sling:resourceType="cq/gui/components/authoring/dialog/richtext" name="./text" useFixedInlineToolbar="{Boolean}true"> 
    <rtePlugins jcr:primaryType="nt:unstructured"> 
        <format jcr:primaryType="nt:unstructured" features="bold,italic"/> 
    </rtePlugins> 
    <uiSettings jcr:primaryType="nt:unstructured"> 
        <cui jcr:primaryType="nt:unstructured"> 
            <inline jcr:primaryType="nt:unstructured" 
                toolbar="[format#bold,format#italic,format#underline,links#modifylink,links#unlink]"> 
            </inline> 
            <icons jcr:primaryType="nt:unstructured"> 
                <bold jcr:primaryType="nt:unstructured" 
                    command="format#bold" 
                    icon="textItalic"/> 
            </icons> 
        </cui> 
    </uiSettings> 
</text>

```

## Switch to CoralUI 2 Rich Text Editor {#switch-to-coralui-rich-text-editor}

On a page, you can either include CoralUI 2 RTE clientlib or the CoralUI 3 RTE clientlib. By default, Rich Text Editor includes the CoralUI 3 RTE clientlib. To switch to CoralUI 2 RTE, perform the following steps.

>[!NOTE]
>
>Adobe does not recommend it as a best practice. Switch to CoralUI 2 RTE as a last resort. Custom plugins for CoralUI 2 RTE work with CoralUI 3 RTE if the plugins do not depend on RTE internals, such as classes.
>
>If you are using custom plugins for CoralUI3 RTE, use `rte.coralui3` library.

1. Overlay the node `/libs/cq/gui/components/authoring/editors/clientlibs/core` under `/apps`, and do the following:

    * Replace `rte.coralui3` with `rte.coralui2` for the dependencies property.
    
    * Replace `cq.authoring.editor.core.inlineediting.rte.coralui3` with `cq.authoring.editor.core.inlineediting.rte.coralui2` for the embed property.
    
    * Replace `cq.authoring.rte.coralui3` with `cq.authoring.rte.coralui2` for the embed property.

1. Overlay the nodes `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` and `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2` under `/apps`.

   Remove category `cq.authoring.dialog` from `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` and add it to `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2`.

1. Change any other dependency that is getting included on the page from `rte.coralui3` to `rte.coralui2`. For example, after overlaying the node `/libs/mcm/campaign/components/touch-ui/clientlibs/rte` under `/apps`, change any dependency on it from `rte.coralui3` to `rte.coralui2`.  

1. Overlay the node `cq/ui/widgets` under `/apps`. Replace the dependency `cq.rte` at the node `/apps/cq/ui/widgets` with `cq.coralui2.rte`.

>[!NOTE]
>
>CoralUI 2 RTE uses handlebars templates for plug-in dialogs. Therefore, the CoralUI 2 RTE clientlib had a dependency on the handlebars clientlib. CoralUI 3 RTE does not use handlebars templates and doesn't have any associated dependency. If your custom plug-ins use handlebars templates, include the handlebars clientlib in your web page.

## Further Information {#further-information}

For more information about configuring the RTE, see the [AEM Widget API](/sites/developing/using/reference-materials/widgets-api/index) reference.

In particular, to see the plug-ins and related options available:

* The [CQ.form.RichText](/sites/developing/using/reference-materials/widgets-api/output/CQ.form.RichText) component provides a form field for editing styled text information (rich text). To know all the parameters available for the rich text form, see the Config Options.
* The RichText component provides a wide range of functionality using plug-ins listed under [CQ.form.rte.plugins.Plugin](/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.Plugin). For each plug-in:

    * see the Features for details of functionality that can be enabled (or disabled)  
    * See the Config Options for all parameters available for detailed configuration of the appropriate plug-in

* More information about HTML Rules for links is also available.

These can be used to extend and customize your own RTE, for example:

* To list the anchors available in the page when creating a link you can provide your own implementation of the LinkPlugin.

## Known limitations {#known-limitations}

<details> 
 <summary>Use only in AEM components</summary> 
 <p>RTE capabilities are supported only in AEM component dialogs. RTE is not supported on wizards or Foundation-forms like <a href="../../../sites/developing/using/page-properties-views.md" target="_blank">Page Properties</a> and <a href="../../../sites/authoring/using/scaffolding.md" target="_blank">Scaffolding</a> on Touch-enabled UI.</p> 
</details>

<details> 
 <summary>Does not work with Hybrid devices</summary> 
 <p>AEM does not work on <a href="../../../release-notes/known-issues.md#knownissues" target="_blank">Hybrid devices</a>.</p> 
</details>

<details> 
 <summary>Configuration node cannot be named config</summary> 
 <p>Do not name the RTE configuration node as <span class="code">config</span>. Otherwise, the RTE configurations take effect for only the administrators and not for the users in the group <span class="code">content-author</span>.</p> 
</details>

<!--
<related-links>
<a href="../../../sites/administering/using/configure-rich-text-editor-plug-ins.md">Configure RTE plug-ins</a>
<a href="../../../sites/authoring/using/rich-text-editor.md">Use Rich Text Editor for authoring</a>
<a href="../../../sites/administering/using/rte-accessible-content.md">Configure RTE for accessible sites</a>
<a href="../../../release-notes/touch-ui-features-status.md">Touch UI and Classic UI feature parity</a>
</related-links>
-->
