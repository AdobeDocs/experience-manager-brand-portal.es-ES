---
title: Ajustes preestablecidos, esquemas y facetas de Publish en Brand Portal
description: Obtenga información sobre cómo publicar ajustes preestablecidos, esquemas y facetas en Brand Portal.
topic-tags: publish
products: SG_EXPERIENCEMANAGER/Brand_Portal
content-type: reference
exl-id: 9b585606-6538-459b-87a9-2e68df0087b3
source-git-commit: 4d9d7afa2cd45ea68c2e15338c92aa29ecf09f91
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 0%

---

# Ajustes preestablecidos, esquemas y facetas de Publish en Brand Portal {#publish-presets-schema-and-facets-to-brand-portal}

AEM El artículo profundiza en la publicación de ajustes preestablecidos de imagen, esquemas de metadatos y facetas de búsqueda personalizadas desde la instancia de autor de la publicación hasta la instancia de Brand Portal, desde la instancia de autor de la publicación. AEM La capacidad de publicación permite a las organizaciones reutilizar los ajustes preestablecidos de imagen, los esquemas de metadatos y las facetas de búsqueda creadas o editadas en una instancia de autor de la. Este enfoque reduce los esfuerzos duplicados.

>[!NOTE]
>
>AEM La capacidad de publicar ajustes preestablecidos de imagen, esquemas de metadatos y facetas de búsqueda de la instancia de autor en Brand Portal AEM AEM está disponible a partir de las versiones 6.2 SP1-CFP7 y 6.3 SP 1-CFP1 (6.3.1.1) en adelante, a partir de la versión 6.2 SP1-CFP7 y la versión 6.3 SP 1-CFP1 (6.3.1.1), respectivamente.

## Ajustes preestablecidos de imagen de Publish en Brand Portal {#publish-image-presets-to-brand-portal}

Los ajustes preestablecidos de imagen son un conjunto de comandos de tamaño y formato que se aplican a la imagen en el momento de la entrega de la imagen. Los ajustes preestablecidos de imagen se pueden crear y modificar en Brand Portal. AEM Alternativamente, si una instancia de autor de la se está ejecutando en el modo Dynamic Media AEM, los usuarios pueden crear ajustes preestablecidos en Autor de la y publicarlos en AEM Assets Brand Portal. Este método evita volver a crear los mismos ajustes preestablecidos en Brand Portal.
Una vez creado el ajuste preestablecido, aparece como una representación dinámica en el carril de representaciones de detalles del recurso y en el cuadro de diálogo de descarga.

>[!NOTE]
>
>AEM Si la instancia de autor de la no se está ejecutando en **[!UICONTROL Modo Dynamic Media]** (el cliente no ha comprado Dynamic Media), la representación de los recursos por parte del TIFF de la pirámide **[!UICONTROL 3&rbrace; no se creará en el momento de la carga.]** Los ajustes preestablecidos de imagen o las representaciones dinámicas funcionan en **[!UICONTROL TIFF piramidal]** de un recurso. Por lo tanto, si **[!UICONTROL TIFF AEM piramidal]** no está disponible en la instancia de autor, no estará disponible en la instancia de autor, en la instancia de Brand Portal. Como resultado, no hay representaciones dinámicas presentes en el carril de representaciones de la página de detalles del recurso y el cuadro de diálogo de descarga.

Para publicar ajustes preestablecidos de imagen en Brand Portal:

1. AEM AEM En la instancia de autor de la, haga clic en el logotipo de la misma para acceder a la consola de navegación global, haga clic en el icono Herramientas y vaya a **[!UICONTROL Assets > Ajustes preestablecidos de imagen]**.
1. Seleccione el ajuste preestablecido de imagen o varios ajustes preestablecidos de imagen de la lista de ajustes preestablecidos de imagen y haga clic en **[!UICONTROL Publish to Brand Portal]**.

![](assets/publishpreset.png)

>[!NOTE]
>
>Cuando los usuarios hacen clic en **[!UICONTROL Publish para Brand Portal]**, los ajustes preestablecidos de imagen se ponen en cola para su publicación. Se recomienda a los usuarios monitorizar el registro de los agentes de replicación para confirmar si la publicación se realizó correctamente.

Para cancelar la publicación de un ajuste preestablecido de imagen desde Brand Portal:

1. AEM AEM En la instancia de autor de la, haga clic en el logotipo de la misma para acceder a la consola de navegación global, haga clic en el icono **[!UICONTROL Herramientas]** y vaya a **[!UICONTROL Assets > Ajustes preestablecidos de imagen]**.
1. Seleccione un ajuste preestablecido de imagen y seleccione **[!UICONTROL Quitar de Brand Portal]** de las opciones disponibles en la parte superior.

## Esquema de metadatos de Publish a Brand Portal {#publish-metadata-schema-to-brand-portal}

El esquema de metadatos describe el diseño y las propiedades que se muestran en la página de propiedades de los recursos o las colecciones.

![](assets/metadata-schema-editor.png) ![](assets/asset-properties-1.png)

AEM Si los usuarios editaron el esquema predeterminado en una instancia de autor de la y desean utilizar el mismo esquema que el predeterminado en Brand Portal, publique los formularios del esquema de metadatos en Brand Portal. AEM En este tipo de escenarios, los esquemas predeterminados publicados desde la instancia de autor de anulan el esquema predeterminado en Brand Portal.

AEM Si los usuarios han creado un esquema personalizado en instancia de autor, pueden publicar el esquema personalizado en Brand Portal en lugar de volver a crear el mismo esquema personalizado allí. A continuación, los usuarios pueden aplicar este esquema personalizado a cualquier carpeta o colección de Brand Portal.

>[!NOTE]
>
>Los esquemas predeterminados no se pueden publicar en Brand Portal AEM si estaban bloqueados en la instancia de la. Es decir, no se editan.

![](assets/default-schema-form.png)

>[!NOTE]
>
>AEM Si una carpeta tiene un esquema aplicado en instancia de autor, también debe existir el mismo esquema en Brand Portal. AEM Al hacerlo, se ayuda a mantener la coherencia en la página de propiedades del recurso en Autor de recursos y Brand Portal de la.

AEM Para publicar un esquema de metadatos de la instancia de autor de la en Brand Portal:

1. AEM AEM En la instancia de autor de la, haga clic en el logotipo de la aplicación para acceder a la consola de navegación global, haga clic en el icono Herramientas y vaya a **[!UICONTROL Assets > Esquemas de metadatos]**.
1. Seleccione un esquema de metadatos y seleccione **[!UICONTROL Publish to Brand Portal]** de las opciones disponibles en la parte superior.

>[!NOTE]
>
>Cuando los usuarios hacen clic en **[!UICONTROL Publish para Brand Portal]**, los esquemas de metadatos se ponen en cola para su publicación. Se recomienda a los usuarios monitorizar el registro de los agentes de replicación para confirmar si la publicación se realizó correctamente.

Para cancelar la publicación de un esquema de metadatos desde Brand Portal:

1. AEM AEM En la instancia de autor de la, haga clic en el logotipo de la aplicación para acceder a la consola de navegación global, haga clic en el icono Herramientas y vaya a **[!UICONTROL Assets > Esquemas de metadatos]**.
1. Seleccione un esquema de metadatos y seleccione **[!UICONTROL Quitar de Brand Portal]** de las opciones disponibles en la parte superior.

## Facetas de búsqueda de Publish a Brand Portal {#publish-search-facets-to-brand-portal}

Los formularios de búsqueda proporcionan la capacidad de [búsqueda con facetas](../using/brand-portal-search-facets.md) a los usuarios de Brand Portal. Las facetas de búsqueda proporcionan una mayor granularidad a las búsquedas en Brand Portal. Todos los [predicados agregados](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/administer/search-facets) en el formulario de búsqueda están disponibles para los usuarios como facetas de búsqueda en los filtros de búsqueda.

![](assets/property-predicate-removed.png)
![](assets/search-form.png)

Para usar un formulario de búsqueda personalizada en **[!UICONTROL Carril de búsqueda de administración de Assets AEM]** desde la instancia de autor de la búsqueda, publíquelo directamente en Brand Portal en lugar de volver a crearlo.

>[!NOTE]
>
>Para publicar un formulario de búsqueda bloqueado en **[!UICONTROL Carril de búsqueda de administración de Assets]** de AEM Assets a Brand Portal, primero debe editarlo. Una vez editado y publicado, este formulario de búsqueda anula el formulario de búsqueda existente en Brand Portal.

AEM Para publicar la faceta de búsqueda editada de la instancia de autor de la publicación en Brand Portal, haga lo siguiente:

1. AEM Haga clic en el logotipo de la y, a continuación, vaya a **[!UICONTROL Herramientas > General > Buscar Forms]**.
1. Seleccione el formulario de búsqueda editado y seleccione **[!UICONTROL Publish to Brand Portal]**.

   >[!NOTE]
   >
   >Cuando los usuarios hacen clic en **[!UICONTROL Publish para Brand Portal]**, las facetas de búsqueda se ponen en cola para la publicación. Se recomienda a los usuarios monitorizar el registro de los agentes de replicación para confirmar si la publicación se realizó correctamente.

Para cancelar la publicación de formularios de búsqueda desde Brand Portal:

1. AEM AEM En la instancia de autor de la, haga clic en el logotipo de la aplicación para acceder a la consola de navegación global, haga clic en el icono Herramientas y vaya a **[!UICONTROL General > Buscar Forms]**.
1. Seleccione el formulario de búsqueda y seleccione **[!UICONTROL Quitar de Brand Portal]** de las opciones disponibles en la parte superior.

>[!NOTE]
>
>La acción **[!UICONTROL Cancelar la publicación de Brand Portal]** deja el formulario de búsqueda predeterminado en Brand Portal y no restaura al último formulario de búsqueda utilizado antes de la publicación.

### Limitaciones {#limitations}

1. Pocos predicados de búsqueda no son aplicables a los filtros de búsqueda en Brand Portal. AEM Cuando estos predicados de búsqueda se publican como parte del formulario de búsqueda de la instancia de autor a Brand Portal, se filtran hacia fuera. Por lo tanto, los usuarios ven menos número de predicados en el formulario publicado en Brand Portal. Vea [predicados de búsqueda aplicables a los filtros en Brand Portal](../using/brand-portal-search-facets.md#list-of-search-predicates).

1. AEM Para [!UICONTROL Predicado de opciones], si un usuario está usando una ruta personalizada para leer opciones en una instancia de autor de, no funciona en Brand Portal. Estas rutas y opciones adicionales no se publican en Brand Portal con el formulario de búsqueda. En este caso, los usuarios pueden seleccionar la opción **[!UICONTROL Manual]** en **[!UICONTROL Agregar opciones]** en **[!UICONTROL Predicado de opciones]** para agregar estas opciones manualmente en Brand Portal.

![](assets/options-predicate-manual.png)
