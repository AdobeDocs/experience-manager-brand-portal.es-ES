---
title: Abastecimiento de recursos en Brand Portal
description: Obtenga información sobre la función de abastecimiento de recursos lanzada en Adobe Experience Manager Assets Brand Portal.
content-type: reference
contentOwner: Vishabh Gupta
topic-tags: brand-portal
products: SG_EXPERIENCEMANAGER/Brand_Portal
sub-product: assets
topics: collaboration, content-velocity, sharing
doc-type: feature-video
activity: use
audience: author, marketer
version: Experience Manager 6.5
kt: 3838
exl-id: 2c132a7a-ed10-4856-8378-67939167ea60
source-git-commit: aea8becdf9493b1d465f1b1cb818c85f8943bedb
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 1%

---

# Resumen de obtención de recursos {#overview-asset-sourcing-in-bp}

**Abastecimiento de recursos** permite a los usuarios de Experience Manager Assets (administradores/usuarios no administradores) crear nuevas carpetas con una propiedad adicional de **Contribución de recursos**, lo que garantiza que la nueva carpeta creada esté abierta al envío de recursos por parte de los usuarios de Brand Portal. Esto almacena en déclencheur un flujo de trabajo automáticamente, lo que crea dos subcarpetas adicionales, denominadas **COMPARTIDO** y **NUEVO**, dentro de la carpeta **Contribución** recién creada. El administrador define el requisito cargando una breve descripción sobre los tipos de recursos que se deben añadir a la carpeta Contribution. Cargan un conjunto de recursos de línea de base en la carpeta **SHARED**, lo que proporciona a los usuarios de Brand Portal la información de referencia necesaria. El administrador puede otorgar a los usuarios activos de Brand Portal acceso a la carpeta de contribuciones antes de publicar la carpeta **Contribution** recién creada en Brand Portal. Cuando el usuario haya terminado de agregar contenido en la carpeta **NEW**, podrá volver a publicar la carpeta Contribution en el entorno de creación de Experience Manager. Tenga en cuenta que puede tardar unos minutos en completar la importación y reflejar el contenido recién publicado en Experience Manager Assets.

Además, todas las funciones existentes permanecen sin cambios. Los usuarios de Brand Portal pueden ver, buscar y descargar recursos desde la carpeta de contribuciones y desde otras carpetas permitidas. Además, los administradores pueden compartir la carpeta de contribución, modificar las propiedades y añadir recursos a las colecciones.

![Abastecimiento de recursos Brand Portal](assets/asset-sourcing.png)

>[!VIDEO](https://video.tv.adobe.com/v/32891/?quality=12&captions=spa)

## Requisitos previos {#prerequisites}

* Instancia de Experience Manager Assets as a Cloud Service, Experience Manager Assets 6.5.2 o superior.
* Asegúrese de que la instancia de Experience Manager Assets esté configurada con Brand Portal. [Configurar Experience Manager Assets con Brand Portal](../using/configure-aem-assets-with-brand-portal.md).

<!--
* Ensure that your Brand Portal tenant is configured with one AEM Assets author instance.
-->

>[!NOTE]
>
>La función de obtención de recursos está habilitada de forma predeterminada en Experience Manager Assets as a Cloud Service, Experience Manager Assets 6.5.9 y versiones posteriores.
>
>Las configuraciones existentes siguen funcionando en las versiones anteriores.

>[!NOTE]
>
>Hay un problema conocido en Experience Manager Assets 6.5.4. Los usuarios de Brand Portal no pueden publicar los recursos de la carpeta Contribution en Experience Manager Assets al actualizar a Adobe Developer Console.
>
>El problema se corrige en Experience Manager Assets 6.5.5. Puede actualizar su instancia de Experience Manager Assets al Service Pack más reciente y [actualizar sus configuraciones](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/brandportal/configure-aem-assets-with-brand-portal#upgrade-integration-65) en Adobe Developer Console.

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


### Cargar la lista de usuarios de Brand Portal {#upload-bp-user-list}

Los administradores de Experience Manager Assets pueden cargar el archivo de configuración de usuario (.csv) de Brand Portal que contiene la lista de usuarios activos de Brand Portal en Experience Manager Assets para permitirles acceder a la función de obtención de recursos.

Una carpeta de contribución solo se puede compartir con los usuarios activos de Brand Portal definidos en la lista de usuarios. El administrador también puede agregar nuevos usuarios al archivo de configuración y cargar la lista de usuarios modificada.

>[!NOTE]
>
>Asegúrese de que la instancia de Experience Manager Assets esté configurada con Brand Portal. [Configurar Experience Manager Assets con Brand Portal](../using/configure-aem-assets-with-brand-portal.md).

>[!NOTE]
>
>El formato del archivo CSV es el mismo que se admite en Admin Console para la importación masiva de usuarios. El correo electrónico, el nombre y los apellidos son obligatorios.

Los administradores pueden agregar nuevos usuarios en Admin Console. Ve a [Administrar usuarios](brand-portal-adding-users.md) para obtener información detallada. Después de agregar usuarios en Admin Console, estos usuarios pueden agregarse al archivo de configuración de usuario de Brand Portal y, a continuación, se les asigna un permiso para acceder a la carpeta Contribution.

**Para cargar la lista de usuarios de Brand Portal:**

1. Inicie sesión en la instancia de Experience Manager Assets.
1. En el panel [!UICONTROL Herramientas], vaya a **[!UICONTROL Assets]** > **[!UICONTROL Usuarios de Brand Portal]**.

1. Se abre la ventana Cargar colaboradores de Brand Portal.
Examine desde su equipo local y cargue un **archivo de configuración (.csv)** que contenga la lista de usuarios activos de Brand Portal.
1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/upload-user-list2.png)

Los administradores pueden proporcionar acceso a usuarios específicos desde esta lista de usuarios mientras configuran una carpeta de contribución. Solo los usuarios asignados a una carpeta de contribución tienen acceso a la carpeta de contribución y publican recursos de Brand Portal en Experience Manager Assets.

## Vea también {#reference-articles}

* [Configuración y publicación de una carpeta de contribución en Brand Portal](brand-portal-publish-contribution-folder-to-brand-portal.md)

* [Publicar carpeta de contribución en Experience Manager Assets](brand-portal-publish-contribution-folder-to-aem-assets.md)
