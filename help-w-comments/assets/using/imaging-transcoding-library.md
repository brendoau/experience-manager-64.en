---
title: Imaging Transcoding Library
seo-title: Imaging Transcoding Library
description: Learn how to configure and use Adobe's Imaging Transcoding Library, an image processing solution that can perform core image-handling functions, including encoding, transcoding, image resampling, and image resizing.
seo-description: Learn how to configure and use Adobe's Imaging Transcoding Library, an image processing solution that can perform core image-handling functions, including encoding, transcoding, image resampling, and image resizing.
uuid: 1bce4c0f-c5ae-4ec1-9e32-3d0d26117aa5
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 1dbcf900-bb39-4f51-a1dd-26473963aed3
index: y
internal: n
snippet: y
---

# Imaging Transcoding Library{#imaging-transcoding-library}

Adobe's Imaging Transcoding Library is a proprietary image processing solution that can perform core image-handling functions, including:

* Encoding
* Transcoding (converting supported formats)
* Image resampling, using PS and Intel IPP algorithms
* Bit depth and color profile preservation
* JPEG quality compression
* Image resizing

Imaging Transcoding Library provides the following capabilities:

* CMYK support
* Full alpha support (except CMYK -Alpha)

In addition to supporting a wide range of file formats and profiles, Imaging Transcoding Library has significant advantages over other third-party solutions around performance, scalability, and quality. Here are some of the key benefits that Imaging Transcoding Library provides:

* **Scales with increasing file size or resolution**: Scaling is primarily achieved by the patented ability of Imaging Transcoding Library to re-size while decoding files. This ability ensures that runtime memory usage is always optimum and is not a quadratic function of increasing file size or resolution megapixels. Imaging Transcoding Library can process larger and high-resolution (containing higher megapixels) files. Third-party tools, such as ImageMagick is unable to handle large files and crashes while processing such files.
* **Photoshop quality compression and resizing algorithms**: Consistency with industry standard in terms of quality of down sampling (smooth, sharp and automatic bicubic) and compression quality. Imaging Transcoding Library further assesses the quality factor of input image, and intelligently uses optimum tables and quality settings for output image. This ability produces files of optimal size without compromising on visual quality.
* **High throughput:** The response time is lower and throughput is consistently higher than ImageMagick. Therefore, Imaging Transcoding Library should decrease the wait time for users and the cost of hosting.
* **Scale better with concurrent load:** Imaging Transcoding Library performs optimally under concurrent load conditions. It provides high throughput with optimum CPU performance, memory usage, and low response time, which helps reduce the cost of hosting.

## Supported MIME types {#supported-mime-types}

Imaging Transcoding Library supports the following MIME types:

* JPG/JPEG
* PNG (8 and 16 Bit)
* GIF
* BMP
* TIFF/Compressed TIFF (apart from 32 Bit Tiffs and PTiffs)
* ICO
* ICN

## Supported Platforms {#supported-platforms}

Imaging Transcoding Library is currently available for the following operating systems:

* RHEL 7
* CentOS 7

>[!NOTE]
>
>Currently, only RHEL 7 and CentOS 7 are supported for Linux distros. Mac OS and other &#42;nix distributions (for example, Debian and Ubuntu) are not supported.

## Usage {#usage}

The command line arguments for Imaging Transcoding Library can include the following:

```
-destMime PNG/JPEG: Mime type of output rendition
 -BitDepth 8/16: Preserves Bit Depth. Bitdepth ‘4’ is automatically converted to ‘8’
 -preserveBitDepth: Downscales Bit Depth (No upscaling)
 -preserveCMYK: Preserves CMYK color space
 -jpegQuality: Provides jpeg quality parameter (0-12 , corresponding to Photoshop qualities)
 -ResamplingMethod BiCubic/Lanczos/PSBicubic: Provides resampling methods. PSBicubic is a Photoshop quality resampling method.
 -resize
```

: `You can configure the following options for the` `-resize` `parameter:`

* `X`: `Works similar to AEM. For example -resize 319.`

* `WxH`: `Aspect Ratio will not be maintained, For example -resize 319X319.`

* `Wx`: `Fixes the width and calculates the height maintaining the aspect ratio. For example -resize 319x.`

* `xH`: `Fixes the height and calculates the width maintaining the aspect ratio. For example -resize x319.`

```
-AllowUpsampling (Resizes smaller images)
 -input <fileName>
 -output <fileName>
```

## Configuring Imaging Transcoding Library {#configuring-imaging-transcoding-library}

1. Configure `LD_LIBRARY_PATH`:

    * `vi ~/.bash_profile`
    * Add " `export LD_LIBRARY_PATH`=**.**"
    
    * Save and exit.

1. Fetch the value of `LD_LIBRARY_PATH` using the following command:

   Verify whether the value of `LD_LIBRARY_PATH` is set to "**.**"

   If the value is not set to "." restart the session.

1. Download the Imaging Transcoding Library package and install it using Crx Package Manager.

<table border="1" cellpadding="0" cellspacing="0"> 
 <tbody> 
  <tr> 
   <td valign="top" width="126"><p><strong>Package Version</strong></p> </td> 
   <td valign="top" width="168"><p><strong>Package Share Link</strong></p> </td> 
   <td valign="top" width="330"><p><strong>Supported Platforms</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="126"><p>1.4<br /> </p> </td> 
   <td valign="top" width="168"><a href="https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/aem630/product/assets/aem-assets-imaging-transcoding-library-pkg">Imaging transcoding library package</a></td> 
   <td valign="top" width="330"><p>RHEL 7, CentOS7</p> </td> 
  </tr> 
 </tbody> 
</table>

<table border="1" cellpadding="0" cellspacing="0" style="font-family: tahoma, arial, helvetica, sans-serif;"> 
 <tbody> 
  <tr> 
   <td valign="top" width="168"><p>TBD</p> </td> 
  </tr> 
 </tbody> 
</table>

   <!--
   Comment Type: annotation
   Last Modified By: rbrough
   Last Modified Date: 2018-05-09T13:18:35.258-0400
   Old link to the package was: https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/aem-assets-imaging-transcoding-library-pkg
   -->

1. Tap/click the AEM logo, and go to **Tools** &gt; **Workflow** &gt; **Models**.
1. From the **Workflow Models** page, open the** DAM Update Asset** workflow model in edit mode.
1. Open the **Process Thumbnails** workflow process step. In the **Thumbnails** tab, add the MIME types for which you want to skip the default thumbnail generation process in the **Skip Mime Types **list. For example, if you want to create thumbnails for a JPEG image using Imaging Transcoding Library, specify `skip:image/jpeg` in the Skip Mime Types field.

   ![](assets/skip_mime_types-1.png)

1. In the **Web Enabled Image** tab, add the MIME types for which you want to skip the default web rendition generation process in **Skip List**. For example, if you skipped MIME type `image/jpeg` in step 6, add `image/jpeg` to the skip list.

   ![](assets/skip_web_renditions.png)

1. Open the **EPS thumbnails (powered by ImageMagick)** step navigate to the **Arguments** tab. In the **Mime Types** list, add the MIME types you want Imaging Transcoding Library to process. For example, if you skipped the MIME type `image/jpeg` in step 6, add image/jpeg to the **Mime Types** list.

   ![](assets/process_arguments.jpg)

1. Add commands to SwitchEngine Handler using one of the following ways:

    * Based on custom requirements, tune the parameters of commands that you specify. For example, if you want to preserve the color profile of your JPEG image, add the following commands to the **Commands** list:

    1. `SWitchEngine -input ${file} -destMime PNG -resize 48 -output ${directory}cq5dam.thumbnail.48.48.png`
    1. `SWitchEngine -input ${file} -destMime PNG -resize 140x100 -output ${directory}cq5dam.thumbnail.140.100.png`
    1. `SWitchEngine -input ${file} -destMime PNG -resize 319 -output ${directory}cq5dam.thumbnail.319.319.png`
    1. `SWitchEngine -input ${file} -destMime JPEG -resize 1280 -preserveCMYK -output ${directory}cq5dam.thumbnail.1280.1280.jpg`

   <!--
   Comment Type: annotation
   Last Modified By: rbrough
   Last Modified Date: 2018-05-09T16:46:42.119-0400
   Commands need to be updated to account for the "SWitchEngine Handler" component no longer being used. Get from engineering or tester.
   -->

   ![](assets/chlimage_1-206.png)

    * Generate thumbnails from an intermediate rendition using a single command. The intermediate rendition acts as source to generate static and web renditions. This method is faster than the earlier method. However, you cannot apply custom parameters to thumbnails using this method.

   ![](assets/chlimage_1-207.png)

   To generate web renditions, configure parameters in the** Web-Enabled Image** tab as depicted in the following image.

   ![](assets/web_enabled_imagetab.png)

1. Save the workflow.
