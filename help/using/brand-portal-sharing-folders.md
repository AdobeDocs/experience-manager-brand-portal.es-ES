---
title: Compartir carpetas
seo-title: Share folders
description: Brand Portal no admite la ingesta de recursos, por lo que estos deben publicarse en Brand Portal desde una instancia preconfigurada de Experience Manager Assets Author. Los recursos publicados no son accesibles para los usuarios no administradores de Brand Portal, a menos que se configuren al configurar la replicación con la instancia de Experience Manager y deban compartirse con ellos.
seo-description: Brand Portal does not support asset ingestion so assets must be published to Brand Portal from a pre-configured Experience Manager Assets Author instance. Published assets are not accessible to non-admin users of Brand Portal, unless configured while configuring replication with Experience Manager instance, and need to be shared with them.
uuid: 340d0a49-b708-4f0e-9fb8-99c824942f34
content-type: reference
topic-tags: sharing
products: SG_EXPERIENCEMANAGER/Brand_Portal
discoiquuid: 2332c16f-40be-4673-8cc6-2360d5b74116
exl-id: d28cf927-60e8-437e-9cba-92f7e19020e7
source-git-commit: 4caa4263bd74b51af7504295161c421524e51f0c
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%

---

# Compartir carpetas en Brand Portal {#share-folders}

Assets debe publicarse en Brand Portal desde una instancia preconfigurada de autor de Experience Manager, ya que Brand Portal no admite la ingesta de recursos.

## Flujo de trabajo de uso compartido de carpetas en Brand Portal {#folder-sharing-workflow-in-brand-portal}

A continuación se describe el flujo de trabajo del recurso compartido de carpetas y el acceso de los usuarios:

* De forma predeterminada, todas las carpetas publicadas desde Experience Manager Assets en Brand Portal solo son visibles para el administrador de Brand Portal, a menos que se marquen como públicas al configurar la replicación.
* El administrador usa la consola **[!UICONTROL Propiedades de carpeta]** para compartir una carpeta con determinados usuarios o grupos. Solo los usuarios o grupos con los que se comparte la carpeta pueden verla después de iniciar sesión en Brand Portal. La carpeta no es visible para otros usuarios.
* El administrador también puede optar por hacer pública una carpeta mediante la casilla de verificación **[!UICONTROL Carpeta pública]** en la consola **[!UICONTROL Propiedades de carpeta]**. Una carpeta pública es visible para todos los usuarios.

* Independientemente de las funciones y los privilegios de los usuarios, cuando estos inician sesión en Brand Portal, ven todas las carpetas públicas y las que se comparten directamente con ellos o con un grupo al que pertenecen. Las carpetas privadas o las carpetas compartidas con otros usuarios no son visibles para todos los usuarios.

### Compartir carpetas con grupos de usuarios en Brand Portal {#sharing-folders-with-user-groups-on-brand-portal}

Los derechos de acceso a los recursos de una carpeta dependen de los derechos de acceso de su carpeta principal, independientemente de la configuración de las carpetas secundarias. AEM Este comportamiento está regido por [ACL](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html?lang=es) en la, ya que las carpetas secundarias heredan ACL de sus carpetas principales. Por ejemplo, si una carpeta A contiene la carpeta B, que contiene la carpeta C, un grupo de usuarios (o usuarios) con derechos de acceso en la carpeta A también tienen los mismos derechos de acceso en la carpeta B y la carpeta C. La carpeta B, que es la carpeta secundaria de A, hereda sus ACL, y la carpeta C, que es la carpeta secundaria de B, hereda sus ACL.

Del mismo modo, los grupos de usuarios (o usuarios) que tienen permisos para acceder solo a la carpeta B tienen los mismos permisos de acceso en la carpeta C, pero no en la carpeta A. Por lo tanto, se recomienda que las organizaciones organicen su contenido de modo que la mayoría de los recursos expuestos se coloquen en la carpeta secundaria y que se pueda restringir el acceso desde los elementos secundarios a la carpeta raíz.

### Publicación de carpeta pública {#public-folder-publish}

A menos que se seleccione la opción **[!UICONTROL Publish de carpeta pública]** al configurar la replicación de Brand Portal, los usuarios que no son administradores (como editores y visores) no tendrán acceso a los recursos publicados de AEM Assets en Brand Portal.

![](assets/assetbpreplication.png)

Si la opción **[!UICONTROL Publish de carpeta pública]** está deshabilitada, los administradores deben compartir específicamente estos recursos con usuarios que no sean administradores mediante la capacidad de uso compartido.

>[!NOTE]
>
>La opción para habilitar **[!UICONTROL Publish AEM de carpeta pública]** está disponible a partir de la versión 6.3.2.1 de la versión en adelante de la versión 6.3.1.

## Acceso a carpetas compartidas {#access-to-shared-folders}

La siguiente matriz analiza los derechos de acceso y los derechos para compartir o dejar de compartir recursos para varias funciones de usuario:

|               | Acceso a todas las carpetas publicadas desde AEM Assets en Brand Portal | Acceso a carpetas compartidas | Compartir/dejar de compartir derechos de carpeta |
|---------------|-----------|-----------|------------|
| Administrador | Sí | Sí | Sí |
| Editor | No* | Sí, solo si se comparte con ellos o con el grupo al que pertenecen | Sí, solo para las carpetas compartidas con ellos o con el grupo al que pertenecen |
| Visor | No* | Sí, solo si se comparte con ellos o con el grupo al que pertenecen | No |
| Usuario invitado | No* | Sí, solo si se comparte con ellos o con el grupo al que pertenecen | No |

>[!NOTE]
>
>De manera predeterminada, la opción **[!UICONTROL Publish de carpeta pública]** está deshabilitada al configurar la replicación de Brand Portal AEM con Autor de. Si la opción está activada, las carpetas publicadas en Brand Portal serán accesibles para todos los usuarios (usuarios no administradores también) de forma predeterminada.

### Acceso de usuarios no administradores a carpetas compartidas {#non-admin-user-access-to-shared-folders}

Los usuarios no administradores solo pueden acceder a las carpetas compartidas con ellos en Brand Portal. Sin embargo, la forma en que se muestran estas carpetas en el portal cuando inician sesión depende de la configuración de **[!UICONTROL Habilitar jerarquía de carpetas]**.

**Si la configuración está deshabilitada**

Los usuarios no administradores ven todas las carpetas compartidas con ellos en la página de aterrizaje o al iniciar sesión en Brand Portal.

![](assets/disabled-folder-hierarchy1-1.png)

**Si la configuración está habilitada**

Los usuarios no administradores ven el árbol de carpetas (a partir de la carpeta raíz) y las carpetas compartidas organizadas dentro de sus respectivas carpetas principales al iniciar sesión en Brand Portal.

Estas carpetas principales son las carpetas virtuales y no se pueden realizar acciones en ellas. Puede reconocer estas carpetas virtuales con un icono de candado.

No hay tareas de acción visibles al pasar el puntero sobre ellas o seleccionarlas en **[!UICONTROL Vista de tarjeta]**, a diferencia de las carpetas compartidas. El botón **[!UICONTROL Información general]** se muestra al seleccionar una carpeta virtual en **[!UICONTROL Vista de columna]** y **[!UICONTROL Vista de lista]**.

>[!NOTE]
>
>Tenga en cuenta que la miniatura predeterminada de las carpetas virtuales es la imagen en miniatura de la primera carpeta compartida.

![](assets/enabled-hierarchy1-1.png) ![](assets/hierarchy1-nonadmin-1.png) ![](assets/hierarchy-nonadmin-1.png) ![](assets/hierarchy2-nonadmin-1.png)

## Compartir carpetas {#how-to-share-folders}

Para compartir una carpeta con usuarios en Brand Portal, siga estos pasos:

1. Haga clic en el icono de superposición de la izquierda y seleccione **[!UICONTROL Navegación]**.

   ![](assets/selectorrail.png)

1. En el carril lateral izquierdo, seleccione **[!UICONTROL Archivos]**.

   ![](assets/access_files.png)

1. En la interfaz de Brand Portal, seleccione la carpeta que desee compartir.

   ![](assets/share-folders.png)

1. En la barra de herramientas de la parte superior, seleccione **[!UICONTROL Compartir]**.

   ![](assets/share_icon.png)

   Aparecerá la consola [!UICONTROL Propiedades de carpeta].

   ![](assets/folder_properties.png)

1. En la consola **[!UICONTROL Propiedades de carpeta]**, especifique el título de la carpeta en el campo **[!UICONTROL Título de carpeta]** si no desea que se muestre el nombre predeterminado a los usuarios.
1. En la lista **[!UICONTROL Agregar usuario]**, seleccione los usuarios o grupos con los que desea compartir la carpeta y haga clic en **[!UICONTROL Agregar]**.
Para compartir la carpeta únicamente con usuarios invitados y no con otros usuarios, seleccione **[!UICONTROL Usuarios anónimos]** de la lista desplegable **[!UICONTROL Miembros]**.

   ![](assets/only-anonymous.png)

   >[!NOTE]
   >
   >Para que la carpeta esté disponible para todos los usuarios independientemente de su pertenencia al grupo y función, haga que sea pública activando la casilla de verificación **[!UICONTROL Carpeta pública]**.

1. Si es necesario, haga clic en **[!UICONTROL Cambiar miniatura]** para modificar la imagen en miniatura de la carpeta.
1. Haga clic en **[!UICONTROL Guardar]**.

1. Para acceder a la carpeta compartida, inicie sesión en Brand Portal con las credenciales del usuario con el que compartió la carpeta. Revise la carpeta compartida en la interfaz.

## Dejar de compartir carpetas {#unshare-the-folders}

Para dejar de compartir una carpeta previamente compartida, siga estos pasos:

1. En la interfaz de Brand Portal, seleccione la carpeta que desea dejar de compartir.

   ![](assets/share-folders-1.png)

1. En la barra de herramientas de la parte superior, haz clic en **[!UICONTROL Compartir]**.
1. En la consola **[!UICONTROL Propiedades de carpeta]**, en **[!UICONTROL Miembros]**, haga clic en el símbolo **[!UICONTROL x]** que aparece junto a un usuario para quitarlo de la lista de usuarios con los que compartió la carpeta.

   ![](assets/folder_propertiesunshare.png)

1. En el cuadro del mensaje de advertencia, haga clic en **[!UICONTROL Confirmar]** para confirmar que se ha dejado de compartir.
Haga clic en **[!UICONTROL Guardar]**.

1. Inicie sesión en Brand Portal con las credenciales del usuario que eliminó de la lista compartida. La carpeta ya no está disponible en la interfaz de Brand Portal para el usuario.
