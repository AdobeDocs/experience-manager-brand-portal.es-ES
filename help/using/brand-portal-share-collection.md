---
title: Compartir una colección
description: Descubra cómo los administradores de Experience Manager Assets Brand Portal pueden compartir y dejar de compartir una colección o una colección inteligente con usuarios autorizados. Los editores pueden ver y compartir únicamente las colecciones creadas por ellos, compartidas con ellos y públicas.
contentOwner: Vishabh Gupta
content-type: reference
topic-tags: sharing
products: SG_EXPERIENCEMANAGER/Brand_Portal
exl-id: 29b877f6-4200-4299-9b8d-81d88f4e8221
source-git-commit: 32a67abf466dd3bf635b851b02377ed23591915e
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 0%

---

# Compartir colecciones {#share-collections}

Una colección representa un grupo de recursos relacionados almacenados juntos en Adobe Experience Manager Assets Brand Portal. Los usuarios pueden crear colecciones inteligentes al [aplicar la búsqueda omnisearch o de facetas para filtrar los recursos relacionados](brand-portal-searching.md) y almacenarlos juntos para facilitar el acceso y compartirlos con otros usuarios de Brand Portal.

<!--The administrators can share and unshare a collection with the authorized Brand Portal users. Editors and viewers can view and share the collections created by them, shared with them, and public collections.-->

Las colecciones se comparten como un vínculo por correo electrónico. Todas las personas con acceso al vínculo para compartir pueden abrir la colección. Sin embargo, los correos electrónicos compartidos se pueden reenviar a cualquier persona. Además, [los vínculos compartidos](https://experienceleague.adobe.com/es/docs/experience-manager-brand-portal/using/share/brand-portal-link-share) son temporales y solo se puede obtener acceso a ellos por una duración limitada. Como alternativa, los usuarios pueden ser invitados como miembros permanentes a colecciones. Existen los siguientes tipos de usuarios para las colecciones:

* **Los administradores** pueden compartir o dejar de compartir una colección con usuarios de Brand Portal autorizados. Pueden invitar a otros usuarios a una colección específica y definir su función en esa colección. Además, los administradores pueden crear colecciones públicas.

* **Los editores** tienen permiso para crear y compartir colecciones. Pueden invitar a otros usuarios a una colección específica y definir su función en esa colección. Además, también pueden compartir colecciones si se les ha invitado a la colección como editores o propietarios.

* **Los visualizadores** solo pueden crear colecciones privadas. No pueden compartir una colección aunque se les haya invitado como propietarios.

>[!NOTE]
>
>Los editores no pueden cambiar una colección pública por una colección que no sea pública y, por lo tanto, no tienen disponible la casilla de verificación **[!UICONTROL Colección pública]** en el cuadro de diálogo **[!UICONTROL Configuración de la colección]**.

## Compartir una colección {#share-collection}

A continuación se indican los pasos para compartir una colección con los usuarios de Brand Portal autorizados:

1. Inicie sesión en su inquilino de Brand Portal. De manera predeterminada, se abre la vista **[!UICONTROL Archivos]** que contiene todos los recursos y carpetas publicados.

1. Desde la barra de navegación rápida de la parte superior, haz clic en **[!UICONTROL Colecciones]**.

1. Desde la consola **[!UICONTROL Colecciones]**, realice una de las siguientes acciones:

   * Pase el puntero sobre la colección que desee compartir. En las miniaturas de acciones rápidas disponibles para la colección, haga clic en el icono **[!UICONTROL Configuración]**.

     ![](assets/settings-icon.png)

   * Seleccione la colección que desea compartir. En la barra de herramientas de la parte superior, haga clic en **[!UICONTROL Configuración]**.

     ![](assets/collection-console.png)

1. En el cuadro de diálogo **[!UICONTROL Configuración de la colección]**, seleccione los usuarios con los que desea compartir la colección y seleccione la función para que el usuario coincida con su función global. Por ejemplo, asigne la función Editor a un editor global y la función Visor a un visor global.

   Como alternativa, para que la colección esté disponible para todos los usuarios independientemente de su pertenencia al grupo y de su función, haga que sea pública activando la casilla de verificación **[!UICONTROL Colección pública]**.

   >[!NOTE]
   >
   >Sin embargo, se puede restringir la creación de colecciones públicas a los usuarios no administradores para evitar tener numerosas colecciones públicas y ahorrar espacio en el sistema. Las organizaciones pueden deshabilitar la configuración **[!UICONTROL Permitir la creación de colecciones públicas]** desde la configuración de **[!UICONTROL General]** disponible en el panel de herramientas de administración.

   ![](assets/collection_sharingadduser.png)

   Los editores no pueden cambiar una colección pública por una colección que no sea pública y, por lo tanto, no tienen una casilla de verificación **[!UICONTROL Colección pública]** disponible en el cuadro de diálogo **[!UICONTROL Configuración de la colección]**.

   ![](assets/collection-setting-editor.png)

1. Haga clic en el botón **[!UICONTROL Agregar]** para agregar al usuario y luego haga clic en **[!UICONTROL Guardar]**. La colección se comparte con los usuarios.

   >[!NOTE]
   >
   >La función de un usuario rige el acceso a los recursos y carpetas dentro de una colección. Si un usuario no tiene acceso a los recursos, se comparte una colección vacía con el usuario. Además, la función de un usuario rige las acciones disponibles para las colecciones.

## Dejar de compartir una colección {#unshare-a-collection}

Para dejar de compartir una colección previamente compartida, haga lo siguiente:

1. En la consola **[!UICONTROL Colecciones]**, seleccione la colección que desea dejar de compartir.

   En la barra de herramientas de la parte superior, haga clic en **[!UICONTROL Configuración]**.

   ![](assets/collection_settings.png)

1. En el cuadro de diálogo **[!UICONTROL Configuración de la colección]**, en la sección **[!UICONTROL Miembros]**, haga clic en el símbolo **[!UICONTROL x]** situado junto a los usuarios para quitarlos de la lista de usuarios que tienen acceso a la colección.

   ![](assets/unshare_collection.png)

1. Aparece un mensaje de advertencia. Haga clic en **[!UICONTROL Confirmar]** para dejar de compartir la colección.

1. Haga clic en **[!UICONTROL Guardar]** para aplicar los cambios.

   Una vez que el usuario se elimine de la lista compartida, la colección no compartida se eliminará de la consola **[!UICONTROL Colecciones]** del usuario.

<!--
1. Click the overlay icon on the left, and choose **[!UICONTROL Navigation]**.

   ![](assets/contenttree-1.png)

1. From the siderail on the left, click **[!UICONTROL Collections]**.

   ![](assets/access_collections.png)

1. From the **[!UICONTROL Collections]** console, do one of the following:

    * Hover the pointer over the collection you want to share. From the quick action thumbnails available for the collection, click the **[!UICONTROL Settings]** icon.

   ![](assets/settings_thumbnail.png)

    * Select the collection you want to share. From the toolbar at the top, click **[!UICONTROL Settings]**.
    
   ![](assets/collection-sharing.png)

1. In the [!UICONTROL Collection Settings] dialog box, select the users or groups with whom you want to share the collection and select the role for a user or a group to match their global role. For example, assign the Editor role to a global editor, the Viewer role to a global viewer.

   Alternatively, to make the collection available to all users irrespective of their group membership and role, make it public by selecting the **[!UICONTROL Public Collection]** check-box.

   >[!NOTE]
   >
   >However, non-admin users can be restricted from creating public collections, to avoid having numerous public collections so that system space can be saved. Organizations can disable the **[!UICONTROL Allow public collections creation]** configuration from [!UICONTROL General] settings available in admin tools panel.

   ![](assets/collection_sharingadduser.png)

   Editors cannot change a public collection to a non-public collection and, therefore, do not have **[!UICONTROL Public Collection]** check-box available in **[!UICONTROL Collection Settings]** dialog.

   ![](assets/collection-setting-editor.png)

1. Select **[!UICONTROL Add]**, and then **[!UICONTROL Save]**. The collection is shared with the chosen users.

   >[!NOTE]
   >
   >A user's role governs access to the assets and folders inside a collection. If a user does not have access to assets, an empty collection is shared with the user. Also, a user's role governs the actions available for collections.

## Unshare a collection {#unshare-a-collection}

To unshare a previously shared collection, do the following:

1. From the **[!UICONTROL Collections]** console, select the collection you want to unshare.

   In the toolbar, click **[!UICONTROL Settings]**.

   ![](assets/collection_settings.png)

1. On the **[!UICONTROL Collection Settings]** dialog box, under **[!UICONTROL Members]**, click the **[!UICONTROL x]** symbol next to users or groups to remove them from the list of users you shared the collection with.

   ![](assets/unshare_collection.png)

1. In the warning message box, click **[!UICONTROL Confirm]** to confirm unshare.

   Click **[!UICONTROL Save]**.

1. Log in to Brand Portal with the credentials of the user you removed from the shared list. The collection is removed from the **[!UICONTROL Collections]** console.
-->
