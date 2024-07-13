---
title: Descarga de recursos
seo-title: Download assets
description: Todos los usuarios pueden descargar simultáneamente recursos y carpetas accesibles para ellos. De este modo, los recursos de marca aprobados se pueden distribuir de forma segura para su uso sin conexión.
seo-description: All users can simultaneously download assets and folders accessible to them. This way, approved brand assets can be securely distributed for offline use.
uuid: 4b57118e-a76e-4d8a-992a-cb3c3097bc03
content-type: reference
contentOwner: Vishabh Gupta
products: SG_EXPERIENCEMANAGER/Brand_Portal
topic-tags: download, download-install, download assets
discoiquuid: f90c2214-beea-4695-9102-8b952bc9fd17
exl-id: be264b1c-38d9-4075-b56a-113f34a2c6bf
source-git-commit: fe6677df928a4125185051d80ae3055afb479369
workflow-type: tm+mt
source-wordcount: '1932'
ht-degree: 5%

---

# Descarga de recursos {#download-assets-from-bp}

Adobe Experience Manager Assets Brand Portal mejora la experiencia de descarga al permitir a los usuarios descargar simultáneamente recursos y carpetas accesibles desde Brand Portal. De este modo, los recursos de marca aprobados se pueden distribuir de forma segura para su uso sin conexión. Siga leyendo para saber cómo descargar recursos (recursos aprobados) de Brand Portal y qué esperar del [rendimiento de descarga](#expected-download-performance).


>[!NOTE]
>
>En Brand Portal 2020.10.0 (y versiones posteriores), la configuración de **[!UICONTROL Descarga rápida]** está habilitada de forma predeterminada, que utiliza IBM Aspera Connect para la descarga acelerada de los recursos. Instale IBM Aspera Connect 3.9.9 (`https://www.ibm.com/docs/en/aspera-connect/3.9.9`) en la extensión del explorador antes de descargar los recursos de Brand Portal. Para obtener más información, consulte la [guía para acelerar las descargas desde Brand Portal](../using/accelerated-download.md).
>
>Si no desea usar IBM Aspera Connect y continuar con el proceso de descarga normal, póngase en contacto con el administrador de Brand Portal para desactivar la configuración de **[!UICONTROL descarga rápida]**.

## Configurar la descarga de recursos {#configure-download}

Los administradores de Brand Portal pueden configurar las opciones de descarga de recursos y grupo de usuarios para los usuarios de Brand Portal, lo que les permite acceder y descargar representaciones de recursos desde la interfaz de Brand Portal.

>[!NOTE]
>
>La configuración de descarga aplicada en la interfaz de usuario facilita una experiencia de autoservicio a los usuarios de Brand Portal para configurar y descargar fácilmente representaciones de recursos. No restringe la descarga de recursos en la capa de aplicación; por ejemplo, los usuarios pueden seguir accediendo y descargando representaciones de recursos con la ruta de URL completa.

El acceso y la descarga de las representaciones de recursos desde la interfaz de Brand Portal se definen mediante las siguientes configuraciones:

* Habilitar configuración de descarga
* Configurar grupos de usuarios

### Habilitar configuración de descarga {#enable-download-settings}

Los administradores pueden habilitar el recurso **[!UICONTROL Configuración de descarga]** para definir el conjunto de representaciones accesibles para los usuarios de Brand Portal para su descarga.

Los ajustes disponibles son:

* **[!UICONTROL Descarga rápida]**

  Proporciona una descarga acelerada de los recursos mediante IBM Aspera Connect. De manera predeterminada, la configuración **[!UICONTROL Descarga rápida]** está habilitada en **[!UICONTROL Configuración de descarga]**.

* **[!UICONTROL Representaciones personalizadas]**

  Permite descargar representaciones personalizadas y (o) dinámicas de los recursos.

  Todas las representaciones de recursos que no sean el recurso original y las generadas por el sistema se denominan representaciones personalizadas. Incluye representaciones estáticas y dinámicas disponibles para el recurso. Cualquier usuario puede crear una representación estática personalizada en Experience Manager Assets, mientras que solo el administrador puede crear representaciones dinámicas personalizadas. Para obtener más información, consulte [cómo aplicar ajustes preestablecidos de imagen o representaciones dinámicas](../using/brand-portal-image-presets.md).

* **[!UICONTROL Representaciones del sistema]**

  Permite descargar representaciones generadas por el sistema de los recursos.

  Estas son las miniaturas que se generan automáticamente en Experience Manager Assets en función del flujo de trabajo &quot;Recurso de actualización DAM&quot;.

* **[!UICONTROL Descarga de recursos]**

  Permite descargar las representaciones en una carpeta independiente para cada recurso. La configuración se aplica a carpetas, colecciones y descargas masivas de recursos (más de 20 recursos).


Inicie sesión en su inquilino de Brand Portal como administrador y vaya a **[!UICONTROL Herramientas]** > **[!UICONTROL Descargar]**.

Los administradores pueden habilitar cualquier combinación de configuraciones para que los usuarios de Brand Portal accedan y descarguen representaciones de recursos.

![](assets/download-settings-new.png)


>[!NOTE]
>
>Solo los administradores pueden descargar los recursos caducados. Para obtener más información sobre los recursos caducados, consulte [administrar derechos digitales de recursos](../using/manage-digital-rights-of-assets.md).

### Configurar grupos de usuarios {#configure-user-group-settings}

Además de la **[!UICONTROL Configuración de descarga]**, los administradores de Brand Portal pueden definir más opciones para que diferentes grupos de usuarios vean y (o) descarguen los recursos originales y sus representaciones.

Inicie sesión en su inquilino de Brand Portal como administrador y vaya a **[!UICONTROL Herramientas]** > **[!UICONTROL Usuarios]**. En la página **[!UICONTROL Funciones de usuario]**, vaya a la pestaña **[!UICONTROL Grupos]** para configurar la configuración de vista y (o) descarga de los grupos de usuarios.

![permiso de visualización/descarga](assets/download-permissions.png)

>[!NOTE]
>
>Si se agrega un usuario a varios grupos y si uno de esos grupos tiene restricciones, estas se aplicarán al usuario.

En función de la configuración, el flujo de trabajo de descarga permanece constante para los recursos independientes, varios recursos, carpetas que contienen recursos, recursos con o sin licencia y descarga de recursos mediante un vínculo compartido.

La siguiente matriz define si un usuario tendría acceso a las representaciones según las [configuraciones de descarga](#configure-download):

| **Configuración de descarga: representaciones personalizadas** | **Configuración de descarga: representaciones del sistema** | **Configuración del grupo de usuarios: descargar original** | **Configuración de grupo de usuarios: descargar representaciones** | **Resultado** |
|---|---|---|---|---|
| ACTIVADO | ACTIVADO | ACTIVADO | ACTIVADO | Ver y descargar todas las representaciones |
| ACTIVADO | ACTIVADO | DESACTIVADO | DESACTIVADO | Ver recurso original |
| DESACTIVADO | DESACTIVADO | ACTIVADO | ACTIVADO | Ver y descargar el recurso original |
| ACTIVADO | DESACTIVADO | ACTIVADO | ACTIVADO | Ver y descargar recursos originales y representaciones personalizadas |
| DESACTIVADO | ACTIVADO | ACTIVADO | ACTIVADO | Ver y descargar representaciones originales de recursos y sistemas |
| ACTIVADO | DESACTIVADO | DESACTIVADO | DESACTIVADO | Ver recurso original |
| DESACTIVADO | ACTIVADO | DESACTIVADO | DESACTIVADO | Ver recurso original |
| DESACTIVADO | DESACTIVADO | DESACTIVADO | ACTIVADO | Ver recurso original |
| DESACTIVADO | DESACTIVADO | ACTIVADO | DESACTIVADO | Ver y descargar el recurso original |
| DESACTIVADO | DESACTIVADO | DESACTIVADO | DESACTIVADO | Ver recurso original |



## Descarga de recursos {#download-assets}

Los usuarios de Brand Portal pueden descargar varios recursos, carpetas que contengan recursos y colecciones desde la interfaz de Brand Portal.

>[!NOTE]
>
>Póngase en contacto con el administrador de Brand Portal si no tiene permiso para acceder o descargar las representaciones de recursos.

Si el usuario tiene acceso a las representaciones, se le proporcionará el cuadro de diálogo **[!UICONTROL Descargar]** mejorado con las siguientes capacidades:

* Vea todas las representaciones disponibles de cualquier recurso en la lista de descarga.
* Excluya las representaciones de los recursos que no sean necesarios para la descarga.
* Aplique el mismo conjunto de representaciones a todos los tipos de recursos similares con un solo clic.
* Aplique un conjunto diferente de representaciones para diferentes tipos de recursos.
* Cree una carpeta independiente para cada recurso.
* Descargar los recursos seleccionados y sus representaciones.

![cuadro de diálogo de descarga](assets/download-dialog-box.png)

>[!NOTE]
>
>El cuadro de diálogo **[!UICONTROL Descargar]** solo aparece si **[!UICONTROL Representaciones personalizadas]** y (o) **[!UICONTROL Representaciones del sistema]** están habilitadas en **[!UICONTROL Configuración de descarga]**.


### Pasos para descargar recursos {#bulk-download}

A continuación se indican los pasos para descargar recursos o carpetas que contengan recursos de la interfaz de Brand Portal:

1. Inicie sesión en su inquilino de Brand Portal. De manera predeterminada, se abre la vista **[!UICONTROL Archivos]** que contiene todos los recursos y carpetas publicados.

   Realice una de las siguientes acciones:

   * Seleccione los recursos o carpetas que desee descargar. En la barra de herramientas de la parte superior, haz clic en el icono **[!UICONTROL Descargar]**.

     ![select-multiple-assets](assets/select-assets-new.png)

   * Para descargar representaciones de recursos específicas de un recurso, pase el puntero sobre el recurso y haga clic en el icono **[!UICONTROL Descargar]** disponible en las miniaturas de acciones rápidas.

     ![select-asset](assets/select-asset.png)


     >[!NOTE]
     >
     >Si descarga los recursos por primera vez y no tiene IBM Aspera Connect instalado en el explorador, se le pedirá que instale el acelerador de descargas de Aspera (`https://www.ibm.com/docs/en/aspera-connect/3.9.9`).


     >[!NOTE]
     >
     >Si los recursos que está descargando también incluyen recursos con licencia, se le redirigirá a la página **[!UICONTROL Administración de copyright]**. En esta página, seleccione los recursos, haga clic en **[!UICONTROL Aceptar]** y, a continuación, haga clic en **[!UICONTROL Descargar]**. Si decide no estar de acuerdo, los recursos con licencia no se descargan.
     > 
     >Los recursos protegidos por licencias tienen [acuerdo de licencia adjunto](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/drm.html), lo cual se lleva a cabo estableciendo la [propiedad de metadatos](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/drm.html) del recurso en Experience Manager Assets.


     ![recurso con licencia](assets/licensed-asset-new.png)

1. Se abre el cuadro de diálogo **[!UICONTROL Descargar]** que enumera todos los recursos seleccionados.

   Haga clic en cualquier recurso para ver las representaciones disponibles y active las casillas de verificación correspondientes a las representaciones que desee descargar.

   Puede seleccionar o excluir manualmente las representaciones de recursos individuales, o hacer clic en el icono **Aplicar** para seleccionar el mismo conjunto de representaciones que se descargarán para tipos de recursos similares (todos los archivos de imagen en este ejemplo). En el cuadro de diálogo **[!UICONTROL Aplicar todo]**, haga clic en **[!UICONTROL Listo]** para aplicar la regla a todos los recursos similares.

   ![aplicar todo](assets/apply.png)

   También puede quitar un recurso de la lista de descarga (si es necesario) haciendo clic en el icono **Quitar**.

   ![quitar](assets/remove.png)

   Para conservar la jerarquía de carpetas de Brand Portal al descargar recursos, active la casilla de verificación **[!UICONTROL Crear una carpeta independiente para cada recurso]**.

   El botón de descarga refleja el recuento de los elementos seleccionados. Una vez que haya terminado de aplicar las reglas, haga clic en **[!UICONTROL Descargar elementos]**.

   ![cuadro de diálogo de descarga](assets/download-dialog-box-new.png)

1. De manera predeterminada, la configuración **[!UICONTROL Descarga rápida]** está habilitada en **[!UICONTROL Configuración de descarga]**. Por lo tanto, aparece un cuadro de confirmación para permitir la descarga acelerada mediante IBM Aspera Connect.

   Para seguir usando **[!UICONTROL Descarga rápida]**, haz clic en **[!UICONTROL Permitir]**. Todas las representaciones seleccionadas se descargan en una carpeta zip con IBM Aspera Connect.

   Si no desea usar IBM Aspera Connect, haga clic en **[!UICONTROL Denegar]**. Si se deniega la descarga rápida **[!UICONTROL 1} o se produce un error, el sistema rellena un mensaje de error.]** Haga clic en el botón **[!UICONTROL Descarga normal]** para continuar descargando los recursos.

<!-- removed the known issue from step 2 as it is fixed in 2022.02.0 release.
   >[!CAUTION]
   >
   >(**Experience Manager Assets as a Cloud Service** only) The following known issue will be fixed in the upcoming release:
   >
   >The download dialog lists the smart crop renditions of the selected asset, however, the user cannot download the smart crop renditions.
-->

>[!NOTE]
>
>Si el administrador desactiva la configuración **[!UICONTROL Descarga rápida]**, las representaciones seleccionadas se descargan directamente en una carpeta zip sin usar IBM Aspera Connect.

>[!NOTE]
>
>Si la configuración **[!UICONTROL Descarga de recursos]** está habilitada en **[!UICONTROL Configuración de descarga]**, las representaciones de recursos se descargan en una carpeta independiente para cada recurso dentro de la carpeta zip.
>  
>Si los recursos se descargan desde un vínculo compartido, las representaciones de recursos se descargan en una carpeta independiente para cada recurso dentro de la carpeta zip.
>
>Si se selecciona una carpeta, una colección o más de 20 recursos para la descarga, se omitirá el cuadro de diálogo **[!UICONTROL Descargar]** y todas las representaciones de recursos accesibles para el usuario, excluidas las representaciones dinámicas, se descargarán en una carpeta zip.

>[!NOTE]
>
>Brand Portal admite la configuración de Dynamic Media en modo híbrido y en modo Scene7.
>
>(*Si la instancia de autor de Experience Manager Assets se está ejecutando en **Modo híbrido de Dynamic Media***)
>
>Para obtener una vista previa o descargar las representaciones dinámicas de un recurso, asegúrese de que el medio dinámico esté habilitado y de que la representación tiff piramidal del recurso exista en la instancia de autor de Experience Manager Assets desde la que se publicaron los recursos. Cuando se publica un recurso desde Experience Manager Assets en Brand Portal, también se publica su representación tiff piramidal.



Si el administrador no le ha autorizado a [tener acceso a las representaciones originales](../using/brand-portal-adding-users.md#main-pars-procedure-202029708), las representaciones originales de los recursos seleccionados no se descargarán.

![mensaje-sin-acceso](assets/no-access-message.png)

<!-- This issue has been resolved, check with engineering.
>[!NOTE]
>
>Once you have downloaded the asset renditions, the **[!UICONTROL Download]** button is disabled to avoid creating duplicate copies of the renditions. To download more (missing or another copy of renditions), refresh the browser to re-enable the download button.
-->

### Descargar recursos desde la página de detalles del recurso {#download-assets-from-asset-details-page}

Además del flujo de trabajo de descarga, existe otro método para descargar las representaciones de recursos individuales directamente desde la página de detalles del recurso.

Los usuarios pueden obtener una vista previa de diferentes representaciones de recursos, seleccionar representaciones específicas y descargar directamente representaciones de recursos desde el panel **[!UICONTROL Representaciones]** de la página de detalles del recurso sin tener que abrir el cuadro de diálogo **[!UICONTROL Descargar]**.


A continuación se indican los pasos para descargar representaciones de recursos desde la página de detalles de recursos:

1. Inicie sesión en el inquilino de Brand Portal y haga clic en el recurso para abrir la página de detalles del recurso.
1. Haga clic en el icono de superposición de la izquierda y, a continuación, haga clic en **[!UICONTROL Representaciones]**.

   ![representación-navegación](assets/rendition-navigation.png)

1. El panel **[!UICONTROL Representaciones]** enumera todas las representaciones de recursos accesibles en función de las [configuraciones de descarga](#configure-download) del recurso.

   Seleccione las representaciones específicas que desee descargar y haga clic en **[!UICONTROL Descargar elementos]**.

   ![representaciones-panel](assets/renditions-panel.png)


1. De manera predeterminada, la configuración **[!UICONTROL Descarga rápida]** está habilitada en **[!UICONTROL Configuración de descarga]**. Por lo tanto, aparece un cuadro de confirmación para permitir la descarga acelerada mediante IBM Aspera Connect.

   Para seguir usando **[!UICONTROL Descarga rápida]**, haz clic en **[!UICONTROL Permitir]**. Todas las representaciones seleccionadas se descargan en una carpeta zip con IBM Aspera Connect.

   Si deniega el uso de **[!UICONTROL Descarga rápida]**, el sistema rellenará un mensaje de error. Haga clic en el botón **[!UICONTROL Descarga normal]** para continuar descargando los recursos.

<!-- removed the known issue from step 3 as it is fixed in 2022.02.0 release.
   >[!CAUTION]
   >
   >(**Experience Manager Assets as a Cloud Service** only) The following known issues will be fixed in the upcoming release:
   >
   >The **[!UICONTROL Renditions]** panel does not list all the static renditions of the assets that are published to Brand Portal after December 16, 2021.
   >
   >The **[!UICONTROL Renditions]** panel lists the smart crop renditions of the asset, however, the user cannot preview or download the smart crop renditions.
-->

>[!NOTE]
>
>Si el administrador desactiva la configuración **[!UICONTROL Descarga rápida]**, las representaciones seleccionadas se descargan directamente en una carpeta zip sin usar IBM Aspera Connect.


>[!NOTE]
>
>Los Assets que se descargan individualmente se pueden ver en el informe de descarga de recursos. Sin embargo, si se descarga una carpeta que contiene recursos, la carpeta y los recursos no se muestran en el informe de descarga de recursos.

<!--
>[!NOTE]
>
>Assets that are individually downloaded are visible in the assets download report. However, if a folder containing assets is downloaded, the folder and assets are not displayed in the assets download report.
-->

<!-- Backup of content before updating the new feature docs.
## Configure asset download {#configure-download}

The download configuration allows the Brand Portal administrators to define the set of renditions available to the Brand Portal users for downloading the assets. The administrator can configure the asset **[!UICONTROL Download]** settings from the Brand Portal interface. 

The available configurations are:

* **[!UICONTROL Fast Download]** 

  Enables high-speed download of the assets. To know more, see [guide to accelerate downloads from Brand Portal](../using/accelerated-download.md).

* **[!UICONTROL Custom Renditions]** 
  
  Download custom and (or) dynamic renditions of the assets. 
  All the asset renditions other than the original asset and system-generated renditions are called as custom renditions. It includes static as well as dynamic renditions available for the asset. Any user can create a custom static rendition in AEM Assets, whereas, only the AEM administrator can create custom dynamic renditions. To know more, see [how to apply image presets or dynamic renditions](../using/brand-portal-image-presets.md)

* **[!UICONTROL System Renditions]** 

  Download system-generated renditions of the assets. These are the thumbnails which are automatically generated in AEM Assets based on the "DAM update asset" workflow. 

Log in to your Brand Portal tenant as an administrator and navigate to **[!UICONTROL Tools]** > **[!UICONTROL Download]**. By default, the **[!UICONTROL Fast Download]** configuration is enabled in the **[!UICONTROL Download Settings]**. 

The administrators can enable any combination to configure the asset download process.

![](assets/download-configuration.png)


Based on the configuration, the download workflow remains constant for stand-alone assets, multiple assets, folders containing assets, licensed or unlicensed assets, and downloading assets using share link. 


* If both **[!UICONTROL Custom Renditions]** and **[!UICONTROL System Renditions]** configurations are turned-off, the original renditions of the assets are downloaded without any additional dialog being presented to the users.    


* If any of the **[!UICONTROL Custom Renditions]** or **[!UICONTROL System Renditions]** configuration is enabled, an additional **[!UICONTROL Download]** dialog box appears wherein you can choose whether to download the original asset along with its renditions, or download only specific renditions. 

>[!NOTE]
>
>Only the administrators can download the expired assets. For more information about expired assets, see [manage digital rights of assets](../using/manage-digital-rights-of-assets.md).

## Steps to download assets {#steps-to-download-assets}

Following are the steps to download assets or folders containing assets from Brand Portal:

1. From the Brand Portal interface, do one of the following:

   * Select the folders or assets you want to download. From the toolbar at the top, click the **[!UICONTROL Download]** icon.

     ![](assets/downloadassets-1.png)

   * To download a specific asset or folder, hover the pointer over the asset or folder and click the **[!UICONTROL Download]** icon available in the quick action thumbnails.

     ![](assets/downloadsingleasset-1.png)


     >[!NOTE]
     >
     >If you are downloading the assets for the first time and do not have IBM Aspera Connect installed in your browser, it will prompt you to install the Aspera download accelerator. 


     >[!NOTE]
     >
     >If the assets you are downloading also include licensed assets, you are redirected to the **[!UICONTROL Copyright Management]** page. In this page, select the assets, click **[!UICONTROL Agree]**, and then click **[!UICONTROL Download]**. If you choose to disagree, licensed assets are not downloaded. 
     > 
     >License-protected assets have [license agreement attached]() to them, which is done by setting asset's [metadata property]() in Experience Manager Assets.


     ![](assets/licensed-asset-download-1.png)

     
     >[!NOTE]
     >
     >Ensure to select all the required asset renditions while downloading them from the asset details page, and click **[!UICONTROL Download]**. The selected renditions are downloaded to your local machine.
     > 
     >Once you download, the **[!UICONTROL Download]** button is disabled to avoid creating duplicate copies of the downloaded renditions. To download more (missing or another copy of renditions), refresh the browser to re-enable the download button.

     If any of the **[!UICONTROL Custom Renditions]** or **[!UICONTROL System Renditions]** configuration is enabled in the **[!UICONTROL Download Settings]**, the **[!UICONTROL Download]** dialog appears with the **[!UICONTROL Asset(s)]** check box selected by default. If the **[!UICONTROL Fast Download]** configuration is enabled, the **[!UICONTROL Enable download acceleration]** check box is selected by default.

     ![](assets/download-dialog.png)

     >[!NOTE]
     >
     >If the downloading assets are image files, and you select only the **[!UICONTROL Asset(s)]** check box in the **[!UICONTROL Download]** dialog but are not [authorized by the administrator to have access to the original renditions of image files](../using/brand-portal-adding-users.md#main-pars-procedure-202029708) then no image files are downloaded and a notification appears, stating that you have been restricted by the administrator to access original renditions.

     ![](assets/restrictaccess-note.png)

1. To download the renditions in addition to the original assets, select the **[!UICONTROL Rendition(s)]** check box. However, if you want to download the system-generated renditions along with the custom renditions, clear the **[!UICONTROL Exclude System Renditions]** check box.

   ![](assets/download-system-rendition.png)

   * To download only the renditions, clear the **[!UICONTROL Asset(s)]** check box.

     >[!NOTE]
     >
     >By default, only the assets are downloaded. However, original renditions of image files are not downloaded if you are not [authorized by the administrator to have access to the original renditions of image files](../using/brand-portal-adding-users.md#main-pars-procedure-202029708).

    * To share the selected assets with other users through a link, select the **[!UICONTROL Email]** check box. An email notification is sent to the users with the download link. To know how to download assets from shared links, see [downloading assets from shared links](../using/brand-portal-link-share.md#main-pars-header-1703469193).  

      ![](assets/download-link.png)

      >[!NOTE]
      >
      >The download link on email notification expires after 45 days.
      >
      >The administrators can customize email messages, that is, logo, description, and footer, using the [Branding](../using/brand-portal-branding.md) feature.


    * You can select a predefined image preset or create a custom dynamic rendition from the **[!UICONTROL Download]** dialog box. 

      To apply a [custom image preset to the asset and its renditions](../using/brand-portal-image-presets.md#applyimagepresetswhendownloadingimages), select the **[!UICONTROL Dynamic Rendition(s)]** check box. Specify the image preset properties (such as size, format, color space, resolution, and image modifier) to apply the custom image preset while downloading the asset and its renditions. To download only the dynamic renditions, clear the **[!UICONTROL Asset(s)]** check box.

      ![](assets/dynamic-rendition.png)

      >[!NOTE]
      >
      >Brand Portal supports configuring Dynamic Media in both - Hybird and Scene 7 mode. 
      >
      >(*If AEM author instance is running on **Dynamic Media Hybrid mode***)
      >
      >To preview or download dynamic renditions of an asset, ensure that the dynamic media is enabled and the asset's Pyramid tiff rendition exists at the AEM Assets author instance from where the assets have been published. When an asset is published to Brand Portal, its Pyramid tiff rendition is also published.
      
  
    * To preserve the Brand Portal folder hierarchy while downloading assets, select the **[!UICONTROL Create separate folder for each asset]** check box. By default, the Brand Portal folder hierarchy is ignored and all the assets are downloaded in one folder in your local system.

1. Click **[!UICONTROL Download]**.

   The assets (and renditions if selected) are downloaded as a zip file to your local folder. However, no zip file is created if a single asset is downloaded without any of the renditions. 

   If you are not [authorized by the administrator to have access to the original renditions](../using/brand-portal-adding-users.md#main-pars-procedure-202029708), the original renditions of the selected assets are not downloaded. 

   >[!NOTE]
   >
   >Assets that are individually downloaded are visible in the assets download report. However, if a folder containing assets is downloaded, the folder and assets are not displayed in the assets download report.
-->

## Rendimiento de descarga esperado {#expected-download-performance}

La experiencia de descarga de archivos puede variar para los usuarios en diferentes ubicaciones de clientes, según factores como la conectividad local a Internet y la latencia del servidor. El rendimiento de descarga esperado para archivos de 2 GB observado en diferentes ubicaciones de clientes es el siguiente, con el servidor de Brand Portal en Oregón, Estados Unidos:

| Ubicación del cliente | Latencia entre cliente y servidor | Velocidad de descarga esperada | Tiempo necesario para descargar un archivo de 2 GB |
|-------------------------|-----------------------------------|-------------------------|------------------------------------|
| Zona occidental de Estados Unidos (Norte de California) | 18 milisegundos | 7,68 MB/s | 4 minutos |
| Zona occidental de EE. UU. (Oregón) | 42 milisegundos | 3,84 MB/s | 9 minutos |
| Zona oriental de EE. UU. (Norte de Virginia ) | 85 milisegundos | 1,61 MB/s | 21 minutos |
| APAC (Tokio) | 124 milisegundos | 1,13 MB/s | 30 minutos |
| Noida | 275 milisegundos | 0,5 MB/s | 68 minutos |
| Sídney | 175 milisegundos | 0,49 MB/s | 69 minutos |
| Londres | 179 milisegundos | 0,32 MB/s | 106 minutos |
| Singapur | 196 milisegundos | 0,5 MB/s | 68 minutos |


>[!NOTE]
>
>Los datos citados se observan en condiciones de prueba, que pueden variar para los usuarios en diferentes ubicaciones que presencian una latencia y un ancho de banda variados.
