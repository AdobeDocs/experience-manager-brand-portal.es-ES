---
title: Uso compartido de recursos como vínculo
seo-title: Share assets as a link
description: Los administradores de Adobe Experience Manager Assets Brand Portal pueden compartir vínculos de varios recursos con usuarios internos autorizados y entidades externas, incluidos socios y proveedores. Los editores solo pueden ver y compartir los recursos que han compartido con ellos.
seo-description: Adobe Experience Manager Assets Brand Portal Administrators can share links of multiple assets with authorized internal users and external entities, including partners and vendors. Editors can view and share only the assets shared with them.
uuid: 8889ac24-c56d-4a47-b792-80c34ffb5c3f
contentOwner: bdhar
content-type: reference
topic-tags: sharing
products: SG_EXPERIENCEMANAGER/Brand_Portal
discoiquuid: f3573219-3c58-47ba-90db-62b003d8b9aa
exl-id: 9d254e95-a4fc-468d-ae1f-9690ddd3b4a1
source-git-commit: e3e35ad4be5c082ad7bac7bed8ea20a186d245ad
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 6%

---

# Uso compartido de recursos como vínculo {#share-assets-as-a-link}

Los administradores de Adobe Experience Manager Assets Brand Portal pueden compartir vínculos de varios recursos con usuarios internos autorizados y entidades externas, incluidos socios y proveedores. Los editores solo pueden ver y compartir los recursos que han compartido con ellos.

Compartir recursos a través de un vínculo es una forma cómoda de ponerlos a disposición de terceros, ya que los receptores no tienen que iniciar sesión en Brand Portal para acceder a los recursos.

<!-- Link sharing access is restricted to editors and administrators. 
-->

Para obtener más información, vea [Administrar usuarios, grupos y funciones de usuario](../using/brand-portal-adding-users.md#manage-user-roles).


A continuación se indican los pasos para compartir recursos como vínculo:

1. Inicie sesión en su inquilino de Brand Portal. De manera predeterminada, se abre la vista **[!UICONTROL Archivos]** que contiene todos los recursos y carpetas publicados.

1. Seleccione los recursos o las carpetas que desee compartir o vaya a la vista **[!UICONTROL Colecciones]** para compartir las colecciones que ha creado.

   ![select-multiple-assets](assets/select-assets-new.png)

1. En la barra de herramientas de la parte superior, haga clic en el icono **[!UICONTROL Compartir vínculo]**.

   Aparece el cuadro de diálogo **[!UICONTROL Compartir vínculos]**.

   ![](assets/link-sharing.png)

   * En el cuadro Dirección de correo electrónico, escriba el ID de correo electrónico del usuario con el que desea compartir el vínculo. Puede compartir el vínculo con varios usuarios. Si el usuario es miembro de su organización, seleccione su ID de correo electrónico de entre las sugerencias que aparecen en la lista desplegable. Si el usuario es externo, escriba el ID de correo electrónico completo y presione **[!UICONTROL Intro]**; el ID de correo electrónico se agrega a la lista de usuarios.

     ![](assets/link-sharing-text.png)

   * En el cuadro **[!UICONTROL Asunto]**, escriba un asunto para el recurso que desea compartir.
   * En el cuadro **[!UICONTROL Mensaje]**, escriba un mensaje si es necesario.
   * En el campo **[!UICONTROL Caducidad]**, use el selector de fechas para especificar la fecha y hora de caducidad del vínculo. De forma predeterminada, la fecha de caducidad se establece en 7 días a partir de la fecha en que comparta el vínculo.
   * Active la casilla de verificación **[!UICONTROL Permitir la descarga del archivo original]** para permitir que los destinatarios descarguen la representación original.

   Los recursos compartidos a través del vínculo caducan después de cruzar la fecha y la hora especificadas en el campo **[!UICONTROL Caducidad]**. Para obtener información sobre el comportamiento de los recursos caducados y los cambios en las actividades permitidas en función de las funciones de usuario en Brand Portal, consulte [Administrar los derechos digitales de los recursos](../using/manage-digital-rights-of-assets.md#asset-expiration).

   >[!NOTE]
   >
   >El tiempo de caducidad predeterminado para el vínculo es de 7 días. El vínculo debe enviarse por correo electrónico a los usuarios que usen el cuadro de diálogo **[!UICONTROL Uso compartido de vínculos]**; no copie ni comparta el vínculo por separado.

1. Haga clic en **[!UICONTROL Compartir]**. Un mensaje confirma que el vínculo se comparte con los usuarios. Los usuarios reciben un correo electrónico con el vínculo compartido.

   ![](assets/link-share-email.png)

   >[!NOTE]
   >
   >Los administradores pueden personalizar los mensajes de correo electrónico, lo cual incluye personalizar el logotipo, la descripción y el pie de página con la característica [Promoción de marca](../using/brand-portal-branding.md).

## Descarga de recursos desde vínculos compartidos {#download-assets-from-shared-links}

Haga clic en el vínculo del correo electrónico para acceder al recurso compartido. AEM Se abre la página Uso compartido de vínculos.

Para descargar los recursos compartidos:

1. Haga clic en los recursos o carpetas y, a continuación, haga clic en el icono **[!UICONTROL Descargar]** de la barra de herramientas.

   ![](assets/download-share-link.png)

   >[!NOTE]
   >
   >Actualmente, solo se puede generar una vista previa y una miniatura para determinados recursos, según el formato de archivo. Para obtener más información sobre los formatos de archivo admitidos, consulte [Compatibilidad con vista previa y miniaturas para los formatos de recurso](#preview-thumbnail-support).

1. Aparecerá el cuadro de diálogo **[!UICONTROL Descargar]**.

   ![cuadro de diálogo de descarga](assets/download-dialog-box-new.png)

1. De manera predeterminada, la configuración **[!UICONTROL Descarga rápida]** está habilitada en **[!UICONTROL Configuración de descarga]**. Por lo tanto, aparece un cuadro de confirmación para seguir descargando mediante IBM Aspera Connect.

   Para seguir usando **[!UICONTROL Descarga rápida]**, haz clic en **[!UICONTROL Permitir]**.

   Todas las representaciones seleccionadas se descargan en una carpeta zip que contiene una carpeta independiente para cada recurso.

   >[!NOTE]
   >
   >Se crea una carpeta independiente para cada recurso al descargar los recursos desde un vínculo compartido.
   >
   >Si se selecciona una carpeta, una colección o más de 20 recursos para la descarga, se omitirá el cuadro de diálogo **[!UICONTROL Descargar]** y todas las representaciones de recursos accesibles para el usuario, excluidas las representaciones dinámicas, se descargarán en una carpeta zip que contiene una carpeta independiente para cada recurso.

   >[!NOTE]
   >
   >Las representaciones originales no se descargan mediante el vínculo compartido si el administrador no autoriza al usuario que compartió los recursos como vínculo a tener acceso a las representaciones originales](../using/brand-portal-adding-users.md#manage-group-roles-and-privileges).[


>[!NOTE]
>
>Brand Portal restringe la descarga de carpetas o recursos con un tamaño superior a 5 GB mediante el uso compartido de vínculos.

<!--
1. The **[!UICONTROL Download]** dialog box appears.

   ![](assets/download-linkshare.png)

    * To speed up the download of asset files shared as the link, select **[!UICONTROL Enable download acceleration]** option and [follow the wizard](../using/accelerated-download.md#download-workflow-using-file-accelerator). To know more about the fast download of assets on Brand Portal refer [Guide to accelerate downloads from Brand Portal](../using/accelerated-download.md).
    
1. To download the renditions of assets in addition to the assets from the shared link, select **[!UICONTROL Rendition(s)]** option. When you do so, **[!UICONTROL Exclude System Renditions]** option appears that is selected by default. This prevents the download of out-of-the-box renditions along with approved assets or their custom renditions.

   However, to allow auto-generated renditions to download along with custom renditions, deselect the **[!UICONTROL Exclude System Renditions]** option.

   >[!NOTE]
   >
   >Original renditions are not downloaded using the shared link if the user who shared the assets as a link is not [authorized by the administrator to have access to the original renditions](../using/brand-portal-adding-users.md#manage-group-roles-and-privileges).

   ![](assets/download-linkshare-autoren.png)

1. Click **[!UICONTROL Download]**. The assets (and renditions if selected) are downloaded as a ZIP file to your local folder. However, no zip file is created if a single asset is downloaded without any of the renditions, thereby ensuring speedy download.

-->

## Compatibilidad con vista previa y miniaturas para formatos de recursos {#preview-thumbnail-support}

La siguiente matriz enumera los formatos de recurso para los que Brand Portal admite miniaturas y previsualizaciones:

| Formato de recurso | Compatibilidad con miniaturas | Compatibilidad con previsualización |
|--------------|-------------------|-----------------|
| PNG | ✓ | ✓ |
| GIF | ✓ | ✓ |
| TIFF | ✓ | ✕ |
| JPEG | ✓ | ✓ |
| BMP | ✓ | ✕ |
| PNM* | ND | ND |
| PGM* | ND | ND |
| PBM* | ND | ND |
| PPM* | ND | ND |
| PSD | ✓ | ✕ |
| EPS | ND | ✕ |
| DNG | ✓ | ✕ |
| PICT | ✓ | ✕ |
| PSB* | ✓ | ✕ |
| JPG | ✓ | ✓ |
| IA | ✓ | ✕ |
| DOC | ✕ | ✕ |
| DOCX | ✕ | ✕ |
| PUNTO* | ✕ | ✕ |
| PDF | ✓ | ✕ |
| HTML | ✕ | ✕ |
| RTF | ✕ | ✕ |
| TXT | ✓ | ✕ |
| XLS | ✕ | ✕ |
| XLSX | ✕ | ✕ |
| ODS | ✕ | ✕ |
| PPT | ✓ | ✕ |
| PPTX | ✕ | ✕ |
| ODP | ✕ | ✕ |
| INDD | ✓ | ✕ |
| PS | ✕ | ✕ |
| QXP | ✕ | ✕ |
| EPUB | ✓ | ✕ |
| AAC | ✕ | ✕ |
| MIDI | ✕ | ✕ |
| 3GP | ✕ | ✕ |
| MP3 | ✕ | ✕ |
| MP4 | ✕ | ✕ |
| OGA | ✕ | ✕ |
| OGG | ✕ | ✕ |
| RA | ✕ | ✕ |
| WAV | ✕ | ✕ |
| WMA | ✕ | ✕ |
| DVI | ✕ | ✕ |
| FLV | ✕ | ✕ |
| M4V | ✕ | ✕ |
| MPG | ✕ | ✕ |
| OGV | ✕ | ✕ |
| MOV | ✕ | ✕ |
| WMV | ✕ | ✕ |
| SWF | ✕ | ✕ |
| TGZ | ND | ✕ |
| JAR | ✓ | ✕ |
| RAR | ND | ✕ |
| TAR | ND | ✕ |
| ZIP | ✓ | ✕ |

La siguiente leyenda explica los símbolos utilizados en la matriz:

| Símbolo | Significado |
|---|---|
| ✓ | Este formato de archivo admite esta función |
| ✕ | Este formato de archivo no admite esta función |
| ND | Esta función no es aplicable a este formato de archivo |
| &#42; | AEM Esta función requiere la compatibilidad de complementos para este formato de archivo en la instancia de autor, pero no en Brand Portal, una vez publicados los recursos en Brand Portal. |

## Dejar de compartir recursos compartidos como vínculo {#unshare-assets-shared-as-a-link}

Para dejar de compartir recursos compartidos anteriormente como vínculo, haga lo siguiente:

1. Cuando inicia sesión en Brand Portal, la vista **[!UICONTROL Archivo]** se abre de forma predeterminada. Para ver los recursos que compartió como vínculos, vaya a la vista **[!UICONTROL Vínculos compartidos]**.

1. Revise los vínculos que ha compartido desde la lista mostrada.

   ![](assets/shared-links.png)

1. Para dejar de compartir un vínculo de la lista, selecciónelo y haga clic en el icono **[!UICONTROL Dejar de compartir]** de la barra de herramientas de la parte superior.

   ![](assets/unshare-asset.png)

   >[!NOTE]
   >
   >La visualización de los vínculos compartidos es específica del usuario. Esta función no muestra todos los vínculos compartidos por todos los usuarios de un inquilino.

1. En el cuadro de mensaje de advertencia, haga clic en **[!UICONTROL Continuar]** para confirmar que se ha dejado de compartir. La entrada para el vínculo se elimina de la lista de vínculos compartidos.
