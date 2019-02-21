---
title: Convert PDF Service Java API QuickStart(SOAP)
seo-title: Convert PDF Service Java API QuickStart(SOAP)
description: null
seo-description: null
uuid: 1c5ad25c-25e8-41da-b9ab-282e047b0e83
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 18c69fa3-5201-4867-8327-82fadfd6f7d5
index: y
internal: n
snippet: y
---

# Convert PDF Service Java API QuickStart(SOAP){#convert-pdf-service-java-api-quickstart-soap}

The following Quick Starts are available for the Convert PDF service API.

[Quick Start (SOAP mode): Converting a PDF document to PostScript using the Java API](convert-pdf-service-java-api#quick_start_soap_mode_converting_a_pdf_document_to_postscript_using_the_java_api)

[Quick Start (SOAP mode): Converting a PDF document to JPEG files using the Java API](convert-pdf-service-java-api#quick_start_soap_mode_converting_a_pdf_document_to_jpeg_files_using_the_java_api)

AEM Forms operations can be performed using the AEM Forms strongly-typed API and the connection mode should be set to SOAP.

***Note**: Quick Start located in Programming with AEM forms are based on the Forms Server being deployed on JBoss Application Server and the Microsoft Windows operating system. However, if you are using another operating system, such as UNIX, replace Windows-specific paths with paths that are supported by the applicable operating system. Likewise, if you are using another J2EE application server, ensure that you specify valid connection properties. (See [Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties).)*

## Quick Start (SOAP mode): Converting a PDF document to PostScript using the Java API {#quick-start-soap-mode-converting-a-pdf-document-to-postscript-using-the-java-api}

The following code example converts a PDF document called *Loan.pdf* to a PostScript document called *Loan.ps*. (See [Converting PDF Documents to PostScript](/programming-with-aem-forms/converting-pdf-postscript-image-files#converting_pdf_documents_to_postscript).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-convertpdf-client.jar 
     * 2. adobe-livecycle-client.jar 
     * 3. adobe-usermanager-client.jar 
     * 4. activation.jar (required for SOAP mode) 
     * 5. axis.jar (required for SOAP mode) 
     * 6. commons-codec-1.3.jar (required for SOAP mode) 
     * 7.  commons-collections-3.1.jar  (required for SOAP mode) 
     * 8. commons-discovery.jar (required for SOAP mode) 
     * 9. commons-logging.jar (required for SOAP mode) 
     * 10. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
     * 11. jaxen-1.1-beta-9.jar (required for SOAP mode) 
     * 12. jaxrpc.jar (required for SOAP mode) 
     * 13. log4j.jar (required for SOAP mode) 
     * 14. mail.jar (required for SOAP mode) 
     * 15. saaj.jar (required for SOAP mode) 
     * 16. wsdl4j.jar (required for SOAP mode) 
     * 17. xalan.jar (required for SOAP mode) 
     * 18. xbean.jar (required for SOAP mode) 
     * 19. xercesImpl.jar (required for SOAP mode) 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * The adobe-utilities.jar file is located in the following path: 
     * <install directory>/sdk/client-libs/jboss 
     * 
     * The jboss-client.jar file is located in the following path: 
     * <install directory>/jboss/bin/client 
     * 
     * SOAP required JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/thirdparty 
     * 
     * If you want to invoke a remote forms server instance and there is a 
     * firewall between the client application and the server, then it is  
     * recommended that you use the SOAP mode. When using the SOAP mode,  
     * you have to include these additional JAR files 
     * 
     * For information about the SOAP  
     * mode, see "Setting connection properties" in Programming  
     * with AEM Forms 
     */ 
 import java.io.File; 
 import java.io.FileInputStream; 
 import java.util.Properties; 
 import com.adobe.idp.Document; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.convertpdfservice.client.ConvertPdfServiceClient; 
 import com.adobe.livecycle.convertpdfservice.client.ToPSOptionsSpec; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.Color; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.LineWeight; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.PSLevel; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.PageSize; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.Color; 
  
 public class JavaAPIConvertPDFtoPSSOAP 
 { 
     public static void main(String[] args) 
     { 
     try 
         { 
         //Set connection properties required to invoke AEM Forms using SOAP mode                                 
         Properties connectionProps = new Properties(); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "http://[server]:[port]"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
                          
         //Create a ServiceClientFactory object 
         ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
          
         //Create a ConvertPdfServiceClient object 
         ConvertPdfServiceClient convertPDFClient= new ConvertPdfServiceClient(myFactory); 
  
         //Get a PDF file document to convert to a PS document  
         //and populate a com.adobe.idp.Document object 
         String inputFileName = "C:\\Adobe\Loan.pdf"; 
         FileInputStream fileInputStream = new FileInputStream(inputFileName); 
         Document inDoc = new Document(fileInputStream); 
          
         //Create a ToPSOptionsSpec object that defines run-time options 
         ToPSOptionsSpec psSpec = new ToPSOptionsSpec();  
         psSpec.setPsLevel(PSLevel.LEVEL_3); 
         psSpec.setShrinkToFit(true); 
         psSpec.setPageSize(PageSize.A4); 
         psSpec.setRotateAndCenter(true); 
         psSpec.setColor(Color.compositeGray); 
         psSpec.setLineWeight(LineWeight.point25); 
          
         //Convert the PDF document to a PostScript file 
         Document createdDocument =convertPDFClient.toPS2( 
             inDoc, 
             psSpec 
             ); 
  
         //Save the PostScript file 
         createdDocument.copyToFile(new File("C:\\Adobe\Loan.ps")); 
         } 
     catch (Exception e) 
         { 
             e.printStackTrace(); 
         } 
     } 
 }
```

## Quick Start (SOAP mode): Converting a PDF document to JPEG files using the Java API {#quick-start-soap-mode-converting-a-pdf-document-to-jpeg-files-using-the-java-api}

The following Java code example converts a PDF document called *Loan.pdf* to a set of JPEG files and stores them in the C:\Adobe directory. Each file is named *tempFile[index].jpg*, where the first image file is named *tempFile0.jpg*. (See [Converting PDF Documents to Image Formats](/programming-with-aem-forms/converting-pdf-postscript-image-files#converting_pdf_documents_to_image_formats).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-convertpdf-client.jar 
     * 2. adobe-livecycle-client.jar 
     * 3. adobe-usermanager-client.jar 
    * 4. activation.jar (required for SOAP mode) 
     * 5. axis.jar (required for SOAP mode) 
     * 6. commons-codec-1.3.jar (required for SOAP mode) 
     * 7.  commons-collections-3.1.jar  (required for SOAP mode) 
     * 8. commons-discovery.jar (required for SOAP mode) 
     * 9. commons-logging.jar (required for SOAP mode) 
     * 10. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
     * 11. jaxen-1.1-beta-9.jar (required for SOAP mode) 
     * 12. jaxrpc.jar (required for SOAP mode) 
     * 13. log4j.jar (required for SOAP mode) 
     * 14. mail.jar (required for SOAP mode) 
     * 15. saaj.jar (required for SOAP mode) 
     * 16. wsdl4j.jar (required for SOAP mode) 
     * 17. xalan.jar (required for SOAP mode) 
     * 18. xbean.jar (required for SOAP mode) 
     * 19. xercesImpl.jar (required for SOAP mode) 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * The adobe-utilities.jar file is located in the following path: 
     * <install directory>/sdk/client-libs/jboss 
     * 
     * The jboss-client.jar file is located in the following path: 
     * <install directory>/jboss/bin/client 
     * 
     * SOAP required JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/thirdparty 
     * 
     * If you want to invoke a remote forms server instance and there is a 
     * firewall between the client application and the server, then it is  
     * recommended that you use the SOAP mode. When using the SOAP mode,  
     * you have to include these additional JAR files 
     * 
     * For information about the SOAP  
     * mode, see "Setting connection properties" in Programming  
     * with AEM Forms 
     */ 
 import java.io.File; 
 import java.io.FileInputStream; 
 import java.util.Iterator; 
 import java.util.List; 
 import java.util.Properties; 
 import com.adobe.idp.Document; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.convertpdfservice.client.ConvertPdfServiceClient; 
 import com.adobe.livecycle.convertpdfservice.client.ToImageOptionsSpec; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.CMYKPolicy; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.ColorCompression; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.ColorSpace; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.GrayScaleCompression; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.GrayScalePolicy; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.ImageConvertFormat; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.Interlace; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.JPEGFormat; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.MonochromeCompression; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.PNGFilter; 
 import com.adobe.livecycle.convertpdfservice.client.enumeration.RGBPolicy; 
  
 public class JavaAPIConvertPDFtoImageSOAP { 
  
     public static void main(String[] args) 
     { 
     try 
     { 
         //Set connection properties required to invoke AEM Forms using SOAP mode                                 
         Properties connectionProps = new Properties(); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "http://[server]:[port]"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
                          
         //Create a ServiceClientFactory object 
         ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
  
         //Create the ConvertPDF service client 
         ConvertPdfServiceClient serviceClient = new ConvertPdfServiceClient(myFactory); 
          
         //Get a PDF file document to convert to a JPEG document and populate a com.adobe.idp.Document object 
         String inputFileName = "C:\\Adobe\Loan.pdf"; 
         FileInputStream fileInputStream = new FileInputStream(inputFileName); 
         Document inDoc = new Document(fileInputStream); 
  
         // Set up the runtime options for the new JPEG file to be created 
         ToImageOptionsSpec spec = new ToImageOptionsSpec(); 
         spec.setImageConvertFormat(ImageConvertFormat.JPEG); 
         spec.setGrayScaleCompression(GrayScaleCompression.Low); 
         spec.setColorCompression(ColorCompression.Low); 
         spec.setFormat(JPEGFormat.BaselineOptimized); 
         spec.setRgbPolicy(RGBPolicy.Off); 
         spec.setCmykPolicy(CMYKPolicy.Off); 
         spec.setColorSpace(ColorSpace.RGB); 
         spec.setResolution("72"); 
         spec.setMonochrome(MonochromeCompression.None); 
         spec.setFilter(PNGFilter.Sub); 
         spec.setInterlace(Interlace.Adam7); 
         spec.setTileSize(180); 
         spec.setGrayScalePolicy(GrayScalePolicy.Off); 
          
         //Perform the conversion and get the containing the newly created JPEG files 
         List allImages = serviceClient.toImage2( 
             inDoc, 
             spec 
         ); 
          
         //Create an Iterator object and iterate through  
         //the List object to get all images 
         Iterator iter = allImages.iterator();  
         int i = 0 ;  
         while (iter.hasNext()) {  
             Document file = (Document)iter.next();  
             file.copyToFile(new File("C:\\Adobe\tempFile"+i+".jpg")); 
             i++;  
         } 
     } 
     catch (Exception e) { 
         e.printStackTrace(); 
         } 
     } 
 }
```
