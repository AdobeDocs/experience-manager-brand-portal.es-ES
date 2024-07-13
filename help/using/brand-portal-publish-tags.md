---
title: Etiquetas de Publish a Brand Portal
seo-title: Publish tags to Brand Portal
description: Obtenga información sobre cómo publicar etiquetas de Experience Manager Assets en Brand Portal.
seo-description: Learn how to publish tags from Experience Manager Assets to Brand Portal.
uuid: 4167367e-1af8-476b-97a5-730c43bd0816
topic-tags: publish
products: SG_EXPERIENCEMANAGER/Brand_Portal
content-type: reference
discoiquuid: 3c8e9251-195d-4c56-a9a9-27bc8b2a82a4
exl-id: 842656a6-1a2b-4b64-954d-1e663923a1a1
source-git-commit: 4caa4263bd74b51af7504295161c421524e51f0c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Etiquetas de Publish a Brand Portal {#publish-tags-to-brand-portal}

Obtenga información sobre cómo publicar etiquetas de Experience Manager Assets en Brand Portal.

Las etiquetas son útiles para organizar los recursos y mejorar la capacidad de búsqueda de los recursos a los que están asociados. Las etiquetas se pueden considerar palabras clave o etiquetas (metadatos) que se adjuntan a los recursos y permiten encontrarlos rápidamente como resultado de una búsqueda. Para saber cómo asignar etiquetas a los recursos en Experience Manager Assets, consulte [usar etiquetas para organizar los recursos](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/organize-assets.html).

AEM Las etiquetas (asociadas a recursos y colecciones en la) se publican automáticamente en Brand Portal cuando los recursos (y colecciones) con etiquetas asociadas se publican en Brand Portal. Las etiquetas publicadas son útiles para permitir que las búsquedas encuentren los recursos asociados.

>[!NOTE]
>
>Sin embargo, se recomienda publicar las etiquetas exclusivamente en Brand Portal antes de publicar los recursos (y colecciones) con los que están asociadas. Esto garantiza una publicación más rápida de los recursos (y colecciones) en Brand Portal.

## Administrar etiquetas {#manage-tags}

AEM Puede usar las etiquetas preexistentes para adjuntarlas a un recurso o crear nuevas etiquetas desde la consola Etiquetas (**[!UICONTROL Herramientas | Etiquetado | AEM Etiquetas]**) De La. En ambos casos, primero debe publicar las etiquetas en Brand Portal y, a continuación, asociarlas a los recursos adecuados.

AEM Para crear etiquetas en, publicar las etiquetas en Brand Portal y asociarlas a los recursos (o colecciones) adecuados, siga estos pasos:

1. **Crear etiquetas**
AEM AEM Inicie sesión en la instancia de autor de la aplicación con privilegios administrativos y acceda a la consola de **[!UICONTROL Etiquetas]** desde la navegación global:

   1. Seleccionar **[!UICONTROL herramientas]**

   1. Seleccionar **[!UICONTROL General]**

   1. Seleccionar **[!UICONTROL Etiquetado]**

1. Seleccione **[!UICONTROL Crear]** y luego seleccione la opción **[!UICONTROL Crear etiqueta]**.
1. Especifique:

   * **[!UICONTROL Título]**
     *(obligatorio)* Un título para mostrar para la etiqueta.
   * **[!UICONTROL Nombre]**
     *(obligatorio)* Un nombre para la etiqueta. Si no se especifica, se crea un nombre de nodo válido a partir del Título. Consulte [TagID](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/tagging/framework.html).
   * **Descripción**
     *(opcional)* Una descripción de la etiqueta.
   * **Ruta de la etiqueta**
Ruta JCR de la etiqueta.

1. Seleccione **[!UICONTROL Enviar]** para crear la etiqueta.

   AEM Una vez que haya creado una etiqueta en la instancia de, la etiqueta estará disponible para adjuntarse a un recurso (mediante la sección Propiedades o la sección Administrar etiquetas de ese recurso).

1. **Publish cambió la etiqueta a Brand Portal**.

   AEM Ir a la consola **[!UICONTROL Etiquetas de la]** ([!UICONTROL Herramientas | Etiquetado | AEM Etiquetas ]), seleccione la etiqueta que desee y Publish a Brand Portal.

1. **Adjunte la etiqueta a un recurso (o colección)**.

   Seleccione un recurso (o una colección) y adjunte la etiqueta deseada mediante la sección Propiedades o la sección Administrar etiquetas de ese recurso. Para obtener más información sobre cómo asignar etiquetas a recursos en AEM Assets, consulte [usar etiquetas para organizar los recursos](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/organize-assets.html).

1. **Recursos de Publish (o colecciones) a Brand Portal**.\
   Al publicar un recurso (o una colección) en Brand Portal, la etiqueta adjunta también está disponible en Brand Portal.

   Para ver la etiqueta adjunta en el recurso (o la colección) correspondiente en Brand Portal, inicie sesión en Brand Portal y seleccione el recurso. En la sección Propiedades, verá la etiqueta adjunta.

## Buscar Promocionar {#search-promote}

AEM Assets Brand Portal le permite hacer que recursos específicos aparezcan como los principales resultados de las búsquedas en función de una etiqueta de palabra clave.

Para elevar un recurso para una palabra clave de búsqueda, siga estos pasos:

1. AEM Abra la página **[!UICONTROL Propiedades]** de un recurso en la instancia de autor de la.
1. Vaya a la ficha **[!UICONTROL Avanzadas]**.
1. En **[!UICONTROL Promocionar búsqueda]** dentro de la sección **[!UICONTROL Elevar para las palabras clave de búsqueda]**, seleccione **[!UICONTROL Agregar]** para agregar las palabras clave o etiquetas de búsqueda.

   ![](assets/search-promote.png)

1. Guarde los cambios.
1. Publish el recurso a Brand Portal.
1. Inicie sesión en Brand Portal. Ver la ficha **[!UICONTROL Avanzadas]** en la sección **[!UICONTROL Propiedades]** del recurso.
Tenga en cuenta que la palabra clave **[!UICONTROL Search Promote]** también está visible en las propiedades de ese recurso.
