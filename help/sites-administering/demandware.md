---
title: Demandware
seo-title: Demandware
description: Learn how to use AEM with Demandware.
seo-description: Learn how to use AEM with Demandware.
uuid: 6dd43f40-465c-4250-9eab-4ae23d90e932
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: c019979f-e65c-46b2-ac43-2721d7fc88fc
pagetitle: Administering Demandware
---

# Demandware{#demandware}

## Product Data Import {#product-data-import}

Demandware products can be imported into AEM to be used by product pickers, components, creating product teasers, and so on.

1. Export the catalog and the product data using the Demandware Business Manager or via a scheduled job.
1. In AEM, navigate to Products: [http://localhost:4502/aem/products.html/etc/commerce/products](http://localhost:4502/aem/products.html/etc/commerce/products)
1. Click **Create** button and **Import Products**.

   ![](assets/chlimage_1-59.png)

1. Select **Demandware** as **Importer**.

   ![](assets/chlimage_1-60.png)

1. Select the exported xml as **Source** and enter a store name.

   >[!NOTE]
   >
   >It is recommended to use `demandware` for the **Demandware store name**. Other names can be used as well, but product properties scaffolding is linked to **demandware**. This can be customised within the project.

1. Click **Next**.

   >[!NOTE]
   >
   >Depending on the size of the catalog, the amount of products and associated images, this can take a few minutes. As a reference, the import of the SiteGenesis apparel catalog including product assets takes around 5 minutes.
