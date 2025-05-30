---
title: Compatibilidad con vídeo dinámico en Brand Portal
description: Compatibilidad con vídeo dinámico en Brand Portal
contentOwner: mgulati
products: SG_EXPERIENCEMANAGER/Brand_Portal
content-type: reference
topic-tags: download-install
exl-id: 08d6a0fb-061e-4bef-b8e2-bb8522e7482e
source-git-commit: e2e007550b557e790533204d49271c90b3b8647d
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 1%

---

# Compatibilidad con vídeo dinámico en Brand Portal {#dynamic-video-support-on-brand-portal}

Vista previa y reproducción de vídeos de forma adaptativa en Brand Portal compatible con Dynamic Media. Descargue también las representaciones dinámicas desde el portal y los vínculos compartidos.
Los usuarios de Brand Portal pueden:

* Obtenga una vista previa de los vídeos en la página Detalles del recurso, Vista de tarjeta y vista previa del recurso compartido de vínculos.
* Reproducir codificaciones de vídeo en la página Detalles del recurso.
* Vea las representaciones dinámicas en la pestaña Representaciones de la página Detalles del recurso.
* Descargue las codificaciones de vídeo y las carpetas que contengan vídeos.

>[!NOTE]
>
>Para trabajar con vídeos y publicarlos en Brand Portal, asegúrese de que la instancia de autor de Experience Manager esté configurada en el modo híbrido de Dynamic Media o en el modo de Dynamic Media **[!DNL Scene7]**.

Para obtener una vista previa, reproducir y descargar vídeos, Brand Portal expone las dos configuraciones siguientes a los administradores:

* [Configuración híbrida de Dynamic Media](#configure-dm-hybrid-settings)
Si la instancia de autor de Experience Manager se está ejecutando en Dynamic Media (modo híbrido).
* [Dynamic Media [!DNL Scene7] configuración](#configure-dm-scene7-settings)
Si la instancia de autor del Experience Manager se está ejecutando en Dynamic Media: modo **[!DNL Scene7]**.
Establezca cualquiera de estas configuraciones en función de las configuraciones establecidas en la instancia de autor de Experience Manager con la que se replica el inquilino de Brand Portal.

>[!NOTE]
>
>Los vídeos dinámicos no son compatibles con los inquilinos de Brand Portal configurados con Experience Manager Author que se ejecuta en el modo de ejecución **[!UICONTROL Scene7 Connect]**.

## ¿Cómo se reproducen los vídeos dinámicos? {#how-are-dynamic-videos-played}

Se han recuperado ![codificaciones de vídeo de la nube](assets/VideoEncodes.png)

Si las configuraciones de Dynamic Media ([Hybrid](../using/dynamic-video-brand-portal.md#configure-dm-hybrid-settings) o [[!DNL Scene7]](../using/dynamic-video-brand-portal.md#configure-dm-scene7-settings)) están configuradas en Brand Portal, las representaciones dinámicas se recuperan del servidor **[!DNL Scene7]**. Las codificaciones de vídeo se previsualizan y reproducen sin demora y distorsionan la calidad.

El repositorio de Brand Portal no almacena codificaciones de vídeo y las recupera del servidor **[!DNL Scene7]**. Asegúrese de que las configuraciones de Dynamic Media sean las mismas en la instancia de autor de Adobe Experience Manager y en Brand Portal.

>[!NOTE]
>
>Los visores de vídeo y los ajustes preestablecidos de visualizador no son compatibles con Brand Portal. Los vídeos se previsualizan y reproducen en los visores predeterminados de Brand Portal.

## Requisitos previos {#prerequisites}

Para trabajar con vídeos dinámicos en Brand Portal, asegúrese de lo siguiente:

* **Iniciar Experience Manager Author en modo Dynamic Media**

  Inicie la instancia de autor del Experience Manager (con la que está configurado Brand Portal) en [Dynamic Media - [!DNL Scene7] mode](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/dynamic/config-dms7#enabling-dynamic-media-in-scene-mode) o en [Dynamic Media - Modo híbrido](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/dynamic/config-dynamic) o

* **Configuración de Cloud Service de Dynamic Media en la instancia de autor del Experience Manager**

  En función del modo Dynamic Media (modo Scene7 o híbrido) en el que se está ejecutando Experience Manager Author, establezca [Cloud Service Dynamic Media ([!DNL Scene7] modo)](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/dynamic/config-dms7#configuring-dynamic-media-cloud-services) o [Cloud Service Dynamic Media (modo híbrido)](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/dynamic/config-dms7#configuring-dynamic-media-cloud-services) en Experience Manager Author de **Herramientas** | **Cloud Service** | **Dynamic Media**.

* **Configurar Dynamic Media en Brand Portal**

  En función de las configuraciones de Dynamic Media Cloud en Experience Manager Author, configure [Dynamic Media settings](#configure-dm-hybrid-settings) o [[!DNL Scene7] settings](#configure-dm-scene7-settings) desde las herramientas administrativas de Brand Portal.

  Asegúrese de que se usan [inquilinos de Brand Portal](#separate-tenants) independientes para las instancias de autor de Experience Manager que están configuradas en Dynamic Media: modo **[!UICONTROL Scene7]** y Dynamic Media: modo híbrido. Si usa las funcionalidades de Dynamic Media **[!UICONTROL S7]** y Dynamic Media Hybrid, este enfoque es particularmente importante.

* **Carpetas de Publish con codificaciones de vídeo aplicadas a Brand Portal**

  Aplique [codificaciones de vídeo](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/dynamic/video-profiles) y publique en Brand Portal la carpeta que contiene los recursos de medios enriquecidos de la instancia de autor de Experience Manager.

* **IP de salida de Lista de permitidos en SPS si la vista previa segura está habilitada**

  Si usa Dynamic Media-**[!DNL Scene7]** (con [vista previa segura habilitada](https://experienceleague.adobe.com/es/docs/dynamic-media-classic/using/upload-publish/testing-assets-making-them-public) para una empresa), se recomienda que **[!DNL Scene7]** administrador de la empresa [realice la lista de permitidos de las direcciones IP de salida pública](https://experienceleague.adobe.com/es/docs/dynamic-media-classic/using/upload-publish/testing-assets-making-them-public#testing-the-secure-testing-service) para las regiones respectivas mediante la interfaz de usuario de Flash de SPS (**[!UICONTROL Scene7]** Publishing System).

  Las IP de salida son las siguientes:

  | **Región** | **IP de salida** |
  |--- |--- |
  | ND | 130.248.160.68, 20.94.203.130 |
  | EMEA | 185.34.189.3, 51.132.146.75 |
  | APAC | 63 140 44 54 |

  Para realizar la lista de permitidos de cualquiera de estas direcciones IP de salida, consulte [Preparar su cuenta para un servicio de pruebas seguro](https://experienceleague.adobe.com/es/docs/dynamic-media-classic/using/upload-publish/testing-assets-making-them-public#testing-the-secure-testing-service).

## Prácticas recomendadas

Asegúrese de que los recursos de vídeo dinámico se previsualizan, reproducen y descargan correctamente desde Brand Portal (y vínculos compartidos) y siga estas prácticas:

### Inquilinos independientes para Dynamic Media: Scene7 y Dynamic Media: modos híbridos {#separate-tenants}

Si utiliza las funciones de modo Dynamic Media - **[!DNL Scene7]** y Dynamic Media - Modo híbrido, utilice diferentes inquilinos de Brand Portal para las instancias de Experience Manager Author configuradas con los modos Dynamic Media - **[!DNL Scene7]** y Dynamic Media - Híbrido.


![Asignación uno a uno de autor y BP](assets/BPDynamicMedia.png)

### Mismos detalles de configuración en la instancia de autor del Experience Manager y en Brand Portal

Asegúrese de que los detalles de configuración sean los mismos en Brand Portal y **[!UICONTROL Configuración de Experience Manager Cloud]**. Los mismos detalles de configuración incluyen lo siguiente:

* **[!UICONTROL Título]**
* **[!UICONTROL ID de registro]**
* **[!UICONTROL URL del servicio de vídeo]** en **[!UICONTROL Dynamic Media - Modo híbrido]**
* **[!UICONTROL Título]**
* Credenciales (**[!UICONTROL Correo electrónico]** y Contraseña)
* **[!UICONTROL Región]**
* **[!UICONTROL Compañía]** en Dynamic Media - modo **[!DNL Scene7]**

### Lista de permitidos de direcciones IP de salida públicas para el modo Scene7 de Dynamic Media

Si se usa Dynamic Media **[!UICONTROL Scene7]** con [vista previa segura habilitada](https://experienceleague.adobe.com/es/docs/dynamic-media-classic/using/upload-publish/testing-assets-making-them-public) para proporcionar recursos de vídeo a Brand Portal, **[!UICONTROL Scene7]** creará un servidor de imágenes dedicado para entornos de ensayo o aplicaciones internas. Cualquier solicitud a este servidor comprueba la dirección IP de origen. Si la solicitud entrante no se encuentra dentro de la lista aprobada de direcciones IP, se devuelve una respuesta de error.
Por lo tanto, el administrador de la empresa **[!UICONTROL Scene7]** configura una lista aprobada de direcciones IP para el entorno **[!UICONTROL Secure Testing]** de su empresa, a través de la interfaz de usuario flash de **[!UICONTROL SPS]** (Scene7 Publishing System). Asegúrese de que la IP de salida de su región respectiva (de la siguiente lista) se añada a esa lista aprobada.
Para realizar la lista de permitidos de cualquiera de estas direcciones IP de salida, consulte [Preparar su cuenta para un servicio de pruebas seguro](https://experienceleague.adobe.com/es/docs/dynamic-media-classic/using/upload-publish/testing-assets-making-them-public#testing-the-secure-testing-service).
Las direcciones IP de salida son las siguientes:

| **Región** | **IP de salida** |
|--- |--- |
| ND | 130.248.160.68, 20.94.203.130 |
| EMEA | 51.132.146.75, 130.248.244.202, 130.248.244.203, 130.248.244.204, 130.248.244.210, 130.248.244.211, 130 248 244 212 |
| APAC | 63 140 44 54 |

## Configuración de Dynamic Media (híbrido) {#configure-dm-hybrid-settings}

Si la instancia de autor de Experience Manager se está ejecutando en modo híbrido de medios dinámicos, use el mosaico **[!UICONTROL Vídeo]** del panel de herramientas administrativas para configurar la puerta de enlace de Dynamic Media.

>[!NOTE]
>
>Los [perfiles de codificación de vídeo](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/dynamic/video-profiles) no se han publicado en Brand Portal. En su lugar, se recuperan del servidor **[!UICONTROL Scene7]**. Por lo tanto, para que las codificaciones de vídeo se reproduzcan correctamente en Brand Portal, asegúrese de que los detalles de configuración sean los mismos que los [Cloud Service de Dynamic Media ([!DNL Scene7] modo)](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/dynamic/config-dms7#configuring-dynamic-media-cloud-services) de la instancia de autor de Experience Manager.

Para establecer las configuraciones de Dynamic Media en los inquilinos de Brand Portal:

1. Seleccione el logotipo del Experience Manager para poder acceder a las herramientas administrativas desde la barra de herramientas situada en la parte superior de Brand Portal.
1. En el panel de herramientas administrativas, seleccione el mosaico **[!UICONTROL Vídeo]**.

   ![Configuración híbrida de Dynamic Media en Brand Portal](assets/DMHybrid-Video.png)

   Se abre la página **[!UICONTROL Editar configuración de Dynamic Media]**.

   ![Configuración híbrida de Dynamic Media en Brand Portal](assets/edit-dynamic-media-config.png)

1. Especifique **[!UICONTROL ID de registro]** y **[!UICONTROL URL del servicio de vídeo]** (URL de puerta de enlace de DM). Asegúrese de que estos detalles sean los mismos que los de **[!UICONTROL Herramientas > Cloud Service]** en la instancia de autor de Experience Manager.
1. Seleccione **Guardar** para salvar la configuración.

## Configuración de Dynamic Media Scene7 {#configure-dm-scene7-settings}

Si la instancia de autor del Experience Manager se está ejecutando en el modo Dynamic Media- **[!UICONTROL Scene7]**, use el mosaico **[!UICONTROL Configuración de Dynamic Media]** del panel de herramientas administrativas para establecer la configuración del servidor de **[!UICONTROL Scene7]**.

Para establecer las configuraciones de Dynamic Media **[!UICONTROL Scene7]** en los inquilinos de Brand Portal:

1. Seleccione el logotipo del Experience Manager para poder acceder a las herramientas administrativas desde la barra de herramientas situada en la parte superior de Brand Portal.

2. En el panel Herramientas administrativas, seleccione el mosaico **[!UICONTROL Configuración de Dynamic Media]**.

   Configuración de ![DM [!UICONTROL Scene7] en Brand Portal](assets/DMS7-Tile.png)

   Se abre la página **[!UICONTROL Editar configuración de Dynamic Media]**.

   Configuración de ![Scene7 en Brand Portal](assets/S7Config.png)

3. Proporcionar:

   * **[!UICONTROL Título]**
   * Credenciales (**[!UICONTROL ID de correo electrónico]** y **[!UICONTROL Contraseña]**) para acceder al servidor de Scene7
   * **[!UICONTROL Región]**

   Asegúrese de que estos valores sean los mismos que los encontrados en la instancia de autor de Experience Manager.

4. Seleccione **[!UICONTROL Conectarse a Dynamic Media]**.

5. Proporcione **[!UICONTROL Nombre de la compañía]** y **[!UICONTROL guarde]** la configuración.
