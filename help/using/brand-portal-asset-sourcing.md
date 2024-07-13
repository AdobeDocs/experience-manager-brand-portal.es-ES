---
title: Abastecimiento de recursos en Brand Portal
seo-title: Asset Sourcing in Brand Portal
description: Obtenga información sobre la función de abastecimiento de recursos lanzada en Adobe Experience Manager Assets Brand Portal.
seo-description: Get an insight into the asset sourcing feature released in the Adobe Experience Manager Assets Brand Portal.
uuid: null
content-type: reference
contentOwner: Vishabh Gupta
topic-tags: brand-portal
products: SG_EXPERIENCEMANAGER/Brand_Portal
discoiquuid: null
sub-product: assets
topics: collaboration, content-velocity, sharing
doc-type: feature-video
activity: use
audience: author, marketer
version: 6.5
kt: 3838
exl-id: 2c132a7a-ed10-4856-8378-67939167ea60
source-git-commit: 955cd8afe939ff47e9f08f312505e230e2f38495
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 1%

---

# Resumen de obtención de recursos {#overview-asset-sourcing-in-bp}

**Abastecimiento de recursos** permite a los usuarios de Experience Manager Assets (administradores/usuarios no administradores) crear nuevas carpetas con una propiedad adicional de **Contribución de recursos**, lo que garantiza que la nueva carpeta creada esté abierta al envío de recursos por parte de los usuarios de Brand Portal. Esto almacena en déclencheur automáticamente un flujo de trabajo que crea dos subcarpetas adicionales, llamadas **SHARED** y **NEW**, dentro de la carpeta **Contribution** recién creada. A continuación, el administrador define el requisito cargando un resumen sobre los tipos de recursos que se deben agregar a la carpeta Contribution, así como un conjunto de recursos de línea de base, en la carpeta **SHARED** para garantizar que los usuarios de BP tengan la información de referencia que necesitan. El administrador puede otorgar a los usuarios activos de Brand Portal acceso a la carpeta de contribuciones antes de publicar la carpeta **Contribution** recién creada en Brand Portal. Una vez que el usuario haya terminado de agregar contenido en la carpeta **NEW**, podrá volver a publicar la carpeta Contribution en el entorno de creación de Experience Manager. Tenga en cuenta que puede tardar unos minutos en completar la importación y reflejar el contenido recién publicado en Experience Manager Assets.

Además, todas las funciones existentes permanecen sin cambios. Los usuarios de Brand Portal pueden ver, buscar y descargar recursos desde la carpeta de contribuciones y desde otras carpetas permitidas. Además, los administradores pueden compartir la carpeta de contribución, modificar las propiedades y añadir recursos a las colecciones.

![Abastecimiento de recursos Brand Portal](assets/asset-sourcing.png)

>[!VIDEO](https://video.tv.adobe.com/v/29365/?quality=12)

## Requisitos previos {#prerequisites}

* Experience Manager Assets as a Cloud Service instance, Experience Manager Assets 6.5.2 o superior.
* Asegúrese de que la instancia de Experience Manager Assets esté configurada con Brand Portal. [Configurar Experience Manager Assets con Brand Portal](../using/configure-aem-assets-with-brand-portal.md).

<!--
* Ensure that your Brand Portal tenant is configured with one AEM Assets author instance.
-->

>[!NOTE]
>
>La función de obtención de recursos está habilitada de forma predeterminada en Experience Manager Assets as a Cloud Service, Experience Manager Assets 6.5.9 y versiones posteriores.
>
>Las configuraciones existentes seguirán funcionando en las versiones anteriores.

>[!NOTE]
>
>Hay un problema conocido en Experience Manager Assets 6.5.4. Los usuarios de Brand Portal no pueden publicar en Experience Manager Assets los recursos de la carpeta Contribution al actualizar a Adobe Developer Console.
>
>El problema se corrige en Experience Manager Assets 6.5.5. Puede actualizar su instancia de Experience Manager Assets al Service Pack más reciente y [actualizar sus configuraciones](https://experienceleague.adobe.com/docs/experience-manager-65/assets/brandportal/configure-aem-assets-with-brand-portal.html?lang=es#upgrade-integration-65) en Adobe Developer Console.

<!--

>For immediate fix on AEM 6.5.4, it is recommended to [download the hotfix](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/hotfix/cq-6.5.0-hotfix-33041) and install on your author instance.
-->

<!--
## Configure Asset Sourcing {#configure-asset-sourcing}

**Asset Sourcing** is configured from within the AEM Assets author instance. The administrators can enable the Asset Sourcing feature flag configuration from the **AEM Web Console Configuration** and upload the active Brand Portal users list in **AEM Assets**.

>[!NOTE]
>
>Asset Sourcing is by default enabled on AEM Assets as a Cloud Service. The AEM administrator can directly upload the active Brand Portal users to allow them access to the Asset Sourcing feature.

>[!NOTE]
>
>Before you begin with the configuration, ensure that your AEM Assets instance is configured with Brand Portal. See, [Configure AEM Assets with Brand Portal](../using/configure-aem-assets-with-brand-portal.md). 

The following video demonstrates, how to configure Asset Sourcing on your AEM Assets author instance:

>[!VIDEO](https://video.tv.adobe.com/v/29771)
-->

<!--
### Enable Asset Sourcing {#enable-asset-sourcing}

AEM administrators can enable the Asset Sourcing feature flag from within the AEM Web Console Configuration (a.k.a Configuration Manager).

>[!NOTE]
>
>This step is not applicable for AEM Assets as a Cloud Service.


**To enable Asset Sourcing:**
1. Log in to your AEM Assets author instance and open Configuration Manager. 
Default URL: http:// localhost:4502/system/console/configMgr.
1. Search using the keyword **Asset Sourcing** to locate **[!UICONTROL Asset Sourcing Feature Flag Config]**.
1. Click **[!UICONTROL Asset Sourcing Feature Flag Config]** to open the configuration window.
1. Select the **[!UICONTROL feature.flag.active.status]** check box.
1. Click **[!UICONTROL Save]**.

![](assets/enable-asset-sourcing.png)
-->


### Cargar lista de usuarios de Brand Portal {#upload-bp-user-list}

Los administradores de Experience Manager Assets pueden cargar el archivo de configuración de usuario (.csv) de Brand Portal que contiene la lista de usuarios activos de Brand Portal en Experience Manager Assets para permitirles acceder a la función de obtención de recursos.

Una carpeta de contribución solo se puede compartir con los usuarios activos de Brand Portal definidos en la lista de usuarios. El administrador también puede agregar nuevos usuarios al archivo de configuración y cargar la lista de usuarios modificada.

>[!NOTE]
>
>Asegúrese de que la instancia de Experience Manager Assets esté configurada con Brand Portal. [Configurar Experience Manager Assets con Brand Portal](../using/configure-aem-assets-with-brand-portal.md).

>[!NOTE]
>
>El formato del archivo CSV es el mismo que se admite en el Admin Console para la importación masiva de usuarios. El correo electrónico, el nombre y los apellidos son obligatorios.

Los administradores pueden agregar nuevos usuarios en Admin Console; consulte [Administrar usuarios](brand-portal-adding-users.md) para obtener información detallada. Después de agregar usuarios en Admin Console, estos usuarios pueden agregarse al archivo de configuración de usuarios de Brand Portal y, a continuación, se les asigna un permiso para acceder a la carpeta Contribution.

**Para cargar la lista de usuarios de Brand Portal:**

1. Inicie sesión en la instancia de Experience Manager Assets.
1. En el panel **Herramientas**, vaya a **[!UICONTROL Assets]** > **[!UICONTROL Usuarios de Brand Portal]**.

1. Se abre la ventana Cargar colaboradores de Brand Portal.
Examine desde su equipo local y cargue **archivo de configuración (.csv)** que contenga la lista de usuarios activos de Brand Portal.
1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/upload-user-list2.png)


Los administradores pueden proporcionar acceso a usuarios específicos desde esta lista de usuarios mientras configuran una carpeta de contribución. Solo los usuarios asignados a una carpeta de contribución tendrán acceso a la carpeta de contribución y publicarán recursos de Brand Portal en Experience Manager Assets.

## Ver también {#reference-articles}

* [Configuración y publicación de la carpeta Contribution en Brand Portal](brand-portal-publish-contribution-folder-to-brand-portal.md)

* [Carpeta de contribución de Publish a Experience Manager Assets](brand-portal-publish-contribution-folder-to-aem-assets.md)
