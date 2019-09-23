---
title: Publicación de etiquetas en Brand Portal
seo-title: Publicación de etiquetas en Brand Portal
description: Descubra cómo publicar etiquetas de Recursos AEM en Brand Portal.
seo-description: Descubra cómo publicar etiquetas de Recursos AEM en Brand Portal.
uuid: 4167367e-1af8-476b-97a5-730c43bd0816
topic-tags: publicación
products: SG_EXPERIENCEMANAGER/Brand_Portal
content-type: referencia
discoiquuid: 3c8e9251-195d-4c56-a9a9-27bc8b2a82a4
translation-type: tm+mt
source-git-commit: 068ce845c51de48fb677f7bd09a2f6d20ff6f1a5

---


# Publish tags to Brand Portal {#publish-tags-to-brand-portal}

Descubra cómo publicar etiquetas de Recursos AEM en Brand Portal.

Las etiquetas son útiles para organizar recursos y mejorar la capacidad de búsqueda de los recursos a los que están asociados. Las etiquetas se pueden considerar palabras clave o etiquetas (metadatos) que se adjuntan a los recursos y permiten encontrarlos rápidamente como resultado de una búsqueda. Para saber cómo asignar etiquetas a recursos en Recursos AEM, consulte [Uso de etiquetas para organizar recursos](https://helpx.adobe.com/experience-manager/6-5/assets/using/organize-assets.html#Usetagstoorganizeassets).

Las etiquetas (asociadas con recursos y colecciones en AEM) se publican automáticamente en Brand Portal cuando los recursos (y las colecciones) con etiquetas asociadas se publican en Brand Portal. Las etiquetas publicadas son útiles para permitir que las búsquedas encuentren los recursos asociados.

>[!NOTE]
>
>Sin embargo, se recomienda publicar únicamente etiquetas en Brand Portal antes de publicar los recursos (y colecciones) con los que están asociadas las etiquetas. Esto garantiza una publicación más rápida de los recursos (y las colecciones) en Brand Portal.

## Manage tags {#manage-tags}

Puede utilizar las etiquetas preexistentes para adjuntar a un recurso o crear nuevas etiquetas desde la consola Etiquetas AEM (**[!UICONTROL Herramientas)| Etiquetado| Etiquetas]** AEM). En ambos casos, primero debe publicar las etiquetas en Brand Portal y, a continuación, asociarlas con los recursos adecuados.

Para crear etiquetas en AEM, publique las etiquetas en Brand Portal y asócielas a los recursos (o colecciones) adecuados, siga estos pasos:

1. **Crear etiquetas** Inicie sesión en la instancia de AEM Author con privilegios administrativos y acceda a la consola Etiquetas **[!UICONTROL de]** AEM desde la navegación global:

   1. Seleccionar **[!UICONTROL herramientas]**

   2. Seleccionar **[!UICONTROL general]**

   3. Seleccionar **[!UICONTROL etiquetado]**

2. Seleccione **[!UICONTROL Crear]** y, a continuación, seleccione la opción **[!UICONTROL Crear etiqueta]** .
3. Especifique:

   * **[!UICONTROL Título]**
      *(obligatorio)* Un título de visualización para la etiqueta.
   * **[!UICONTROL Nombre]**
      *(obligatorio)* Un nombre para la etiqueta. Si no se especifica, se crea un nombre de nodo válido desde el Título. Consulte [TagID](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/framework.html#TagID).
   * **Descripción**
      *(opcional)* Descripción de la etiqueta.
   * **Ruta** de etiqueta JCR de la etiqueta.

4. Seleccione **[!UICONTROL Enviar]** para crear la etiqueta.

   Una vez que haya creado una etiqueta en una instancia de AEM, la etiqueta estará disponible para adjuntarse a un recurso (mediante la sección Propiedades o la sección Administrar etiquetas de ese recurso).

5. **Publique la etiqueta en Brand Portal**.

   Vaya a la consola Etiquetas **** AEM ([!UICONTROL Herramientas)| Etiquetado| Etiquetas]AEM), seleccione la etiqueta que desee y Publicar en Brand Portal.

6. **Adjunte la etiqueta a un recurso (o colección)**.

   Seleccione un recurso (o colección) y adjunte la etiqueta deseada mediante la sección Propiedades o la sección Administrar etiquetas de ese recurso. Para obtener más información sobre cómo asignar etiquetas a recursos en Recursos AEM, consulte [Uso de etiquetas para organizar recursos](https://helpx.adobe.com/experience-manager/6-5/assets/using/organize-assets.html#Usetagstoorganizeassets).

7. **Publique recursos (o colecciones) en Brand Portal**.\
   Cuando publica un recurso (o colección) en Brand Portal, la etiqueta adjunta también está disponible en Brand Portal.

   Para ver la etiqueta adjunta en el recurso (o colección) correspondiente en Brand Portal, inicie sesión en Brand Portal y seleccione el recurso. En la sección Propiedades verá la etiqueta adjunta.

## Buscar Promocionar {#search-promote}

AEM Assets Brand Portal le permite incluir recursos específicos como los principales resultados de las búsquedas basadas en una etiqueta de palabra clave.

Para elevar un recurso para una palabra clave de búsqueda, siga estos pasos:

1. Abra la página **[!UICONTROL Propiedades]** de un recurso en una instancia de autor de AEM.
2. Vaya a la ficha **[!UICONTROL Avanzado]** .
3. En la sección **[!UICONTROL Buscar promociones]** dentro de **[!UICONTROL Elevar para palabras clave]** de búsqueda, seleccione **[!UICONTROL Agregar]** para agregar las palabras clave o etiquetas de búsqueda.

   ![](assets/search-promote.png)

4. Guarde los cambios.
5. Publicar el recurso en el portal de marca.
6. Inicie sesión en Brand Portal. Consulte la ficha **[!UICONTROL Avanzadas]** en la sección **[!UICONTROL Propiedades]** del recurso.
Tenga en cuenta que la palabra clave **[!UICONTROL Search Promote]** también está visible en las Propiedades de ese recurso.