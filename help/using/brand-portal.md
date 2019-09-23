---
title: Descripción general del portal de marca de AEM Assets
seo-title: Descripción general del portal de marca de AEM Assets
description: AEM Assets Brand Portal puede ayudarle a adquirir, controlar y distribuir de forma segura recursos creativos aprobados a terceros externos y usuarios internos de la empresa entre dispositivos.
seo-description: AEM Assets Brand Portal puede ayudarle a adquirir, controlar y distribuir de forma segura recursos creativos aprobados a terceros externos y usuarios internos de la empresa entre dispositivos.
uuid: b1e54d03-eb2e-488e-af4d-bae817dd135a
content-type: referencia
products: SG_EXPERIENCEMANAGER/Brand_Portal
topic-tags: introducción
discoiquuid: 6aefa298-4728-4b8e-a85b-e419ee37f2f4
translation-type: tm+mt
source-git-commit: d584ccb4d50f62ec70dabc39be2b17acaba47140

---


# Descripción general del portal de marca de AEM Assets {#overview-of-aem-assets-brand-portal}

Como especialista en mercadotecnia, a veces necesita colaborar con los socios de canal y los usuarios internos de la empresa para crear, administrar y entregar rápidamente contenido digital relevante a los clientes. La entrega oportuna de contenido relevante a lo largo de todo el viaje del cliente es fundamental para generar una mayor demanda, conversión, compromiso y lealtad del cliente.

Sin embargo, es un desafío desarrollar soluciones que permitan un uso compartido eficiente y seguro de logotipos de marca, directrices, recursos de campaña o tomas de productos aprobados con equipos internos, socios y distribuidores extendidos.

**Recursos Adobe Experience Manager (AEM) Assets Brand Portal** puede ayudarle a adquirir, controlar y distribuir de forma segura recursos creativos aprobados a terceros externos y usuarios empresariales internos en distintos dispositivos. Ayuda a mejorar la eficiencia del uso compartido de activos, acelera el tiempo de comercialización de los activos y reduce el riesgo de incumplimiento y acceso no autorizado.

El entorno de portal basado en explorador le permite cargar, examinar, buscar, previsualizar y exportar recursos fácilmente en formatos aprobados.

## Personas de usuario en Brand Portal {#Personas}

Brand Portal admite las siguientes funciones de usuario:

* Usuario invitado
* Visor
* Editor
* Administrador

En la tabla siguiente se enumeran las tareas que pueden realizar los usuarios con estas funciones:

|  | **Examinar** | **Buscar** | **Descargar** | **Compartir carpetas** | **Compartir una colección** | **Compartir recursos como vínculo** | **Acceso a las Herramientas de administración** |
|--- |--- |--- |--- |--- |--- |--- |--- |
| **Usuario invitado** | ✓* | ✓* | ✓* | x | x | x | x |
| **Visor** | ✓ | ✓ | ✓ | x | x | x | x |
| **Editor** | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | x |
| **Administrador** | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

* Los usuarios invitados pueden examinar, acceder y buscar recursos solo en carpetas públicas y colecciones.

### Guest user {#guest-user}

Cualquier usuario invitado que tenga acceso limitado a los recursos en Brand Portal sin someterse a autenticación. La sesión de invitado permite a los usuarios acceder a carpetas y colecciones públicas. Como usuario invitado, puede examinar los detalles de los recursos y tener una vista completa de los recursos de los miembros de las carpetas públicas y las colecciones. Puede buscar, descargar y agregar recursos públicos a la colección [!UICONTROL Lightbox] .

Sin embargo, la sesión de invitado le impide crear colecciones y guardar búsquedas, y compartirlas aún más. Los usuarios de una sesión de invitado no pueden acceder a la configuración de carpetas y colecciones, y no pueden compartir recursos como vínculos. Esta es una lista de tareas que un usuario invitado puede realizar:

[Explorar y acceder a los recursos públicos](browse-assets-brand-portal.md)

[Buscar recursos públicos](brand-portal-searching.md)

[Descargar recursos públicos](brand-portal-download-users.md)

[Agregar recursos a [!UICONTROL Lightbox]](brand-portal-light-box.md#add-assets-to-lightbox)

### Visor {#viewer}

Un usuario estándar de Brand Portal suele ser un usuario con la función de visor. Un usuario con esta función puede acceder a las carpetas, colecciones y recursos permitidos. El usuario también puede examinar, previsualizar, descargar y exportar recursos (representaciones originales o específicas), configurar la cuenta y buscar recursos. Esta es una lista de tareas que un visor puede realizar:

[Examinar recursos](browse-assets-brand-portal.md)

[Buscar recursos](brand-portal-searching.md)

[Descargar recursos](brand-portal-download-users.md)

### Editor {#editor}

Un usuario con la función de editor puede realizar todas las tareas que pueda realizar un visor. Además, y Editor pueden ver los archivos y carpetas que un administrador comparte. El usuario con la función de editor también puede compartir contenido (archivos, carpetas, colecciones) con otros usuarios.

Aparte de las tareas que puede realizar un visor, un editor puede realizar las siguientes tareas adicionales:

[Compartir carpetas](brand-portal-sharing-folders.md)

[Compartir una colección](brand-portal-share-collection.md)

[Compartir recursos como vínculo](brand-portal-link-share.md)

### Administrador {#administrator}

Un administrador incluye un usuario marcado como administrador del sistema o administrador del producto Brand Portal en la Consola [!UICONTROL de administración]. Un administrador puede agregar y quitar administradores y usuarios del sistema, definir ajustes preestablecidos, enviar correos electrónicos a los usuarios y ver informes de almacenamiento y uso del portal.

Un administrador puede realizar todas las tareas que un editor puede realizar con las siguientes tareas adicionales:

[Administrar usuarios, grupos y funciones de usuario](brand-portal-adding-users.md)

[Personalización de papel tapiz, encabezados de página y correos electrónicos](brand-portal-branding.md)

[Utilizar facetas de búsqueda personalizadas](brand-portal-search-facets.md)

[Utilizar el formulario de esquema de metadatos](brand-portal-metadata-schemas.md)

[Aplicación de ajustes preestablecidos de imagen o representaciones dinámicas](brand-portal-image-presets.md)

[Trabajar con informes](brand-portal-reports.md)

Además de las tareas anteriores, un autor de Recursos AEM puede realizar las siguientes tareas:

[Configuración de la integración de AEM Assets con Brand Portal](https://helpx.adobe.com/experience-manager/6-5/assets/using/brand-portal-configuring-integration.html)

[Publicar carpetas en Brand Portal](https://helpx.adobe.com/experience-manager/6-5/assets/using/brand-portal-publish-folder.html)

[Publicar colecciones en Brand Portal](https://helpx.adobe.com/experience-manager/6-5/assets/using/brand-portal-publish-collection.html)

## Alias alternativo para la dirección URL de Brand Portal {#tenant-alias-for-portal-url}

A partir de Brand Portal 6.4.3, las organizaciones pueden tener una URL alternativa (alias) para la URL existente de su inquilino de Brand Portal. La dirección URL del alias se puede crear con un prefijo alternativo en la dirección URL.\
Tenga en cuenta que solo se puede personalizar el prefijo de la dirección URL de Brand Portal y no toda la dirección URL. Por ejemplo, una organización con un dominio existente **[!UICONTROL geometSymmetrix.brand-portal.adobe.com]** puede obtener **[!UICONTROL geomettrixinc.brand-portal.adobe.com]** creada a petición.

Sin embargo, la instancia de AEM Author solo se puede [configurar](https://helpx.adobe.com/experience-manager/6-5/assets/using/brand-portal-configuring-integration.html) con la dirección URL de identificación del inquilino y no con la URL de alias del inquilino (alternativa).

>[!NOTE]
>
>Para obtener un alias para el nombre del inquilino en la URL del portal existente, las organizaciones deben ponerse en contacto con el servicio de asistencia de Adobe con una nueva solicitud de creación de alias del inquilino. Esta solicitud se procesa comprobando primero si el alias está disponible y, a continuación, creando el alias.
>
>Para reemplazar el alias antiguo o eliminarlo, debe seguirse el mismo proceso.

## Solicitar acceso a Brand Portal {#request-access-to-brand-portal}

Los usuarios pueden solicitar acceso a Brand Portal desde la pantalla de inicio de sesión. Estas solicitudes se envían a los administradores de Brand Portal, quienes otorgan acceso a los usuarios a través de Adobe [!UICONTROL Admin Console]. Una vez concedido el acceso, los usuarios reciben un correo electrónico de notificación.

Para solicitar acceso, haga lo siguiente:

1. En la página de inicio de sesión de Brand Portal, seleccione **[!UICONTROL ¿Hacer clic aquí]** correspondiente a **[!UICONTROL Necesita acceso?]**. Sin embargo, para entrar en la sesión de invitados, seleccione **[!UICONTROL Haga clic aquí]** correspondiente a Acceso de **[!UICONTROL invitados?]**.

   ![Pantalla de inicio de sesión de Brand Portal](assets/bp-login-requestaccess.png)

   Se abre la página [!UICONTROL Solicitar acceso] .

2. Para solicitar acceso al portal de marca de una organización, debe tener un ID [!UICONTROL de]Adobe válido, un ID [!UICONTROL de]empresa o un ID [!UICONTROL federado].

   En la página [!UICONTROL Solicitar acceso] , inicie sesión con su ID (escenario 1) o cree un ID de [!UICONTROL Adobe] (escenario 2):
   ![[!UICONTROL Solicitar acceso]](assets/bplogin_request_access_2.png)

   **Escenario 1**
   1. Si tiene un [!UICONTROL Adobe ID], un [!UICONTROL Enterprise ID]o un [!UICONTROL Federated ID], haga clic en **[!UICONTROL Iniciar sesión]**.
Se abre la página [!UICONTROL Iniciar sesión] .
   2. Proporcione sus credenciales de [!UICONTROL Adobe ID] y haga clic en **[!UICONTROL Iniciar sesión]**.<br />
   ![Inicio de sesión de Adobe](assets/bplogin_request_access_3.png)

   Se le redirige a la página [!UICONTROL Solicitar acceso] .
   **Escenario 2**
   1. Si no dispone de un ID [!UICONTROL de]Adobe, para crear uno, haga clic en **[!UICONTROL Obtener un ID]** de Adobe en la página [!UICONTROL Solicitar acceso] .
Se abre la página [!UICONTROL Iniciar sesión] .
   2. Click **[!UICONTROL Get an Adobe ID]**.
Se abre la página [!UICONTROL Registro] .
   3. Escriba su nombre y apellidos, ID de correo electrónico y contraseña.
   4. Seleccione **[!UICONTROL Registrarse]**.<br />
   ![](assets/bplogin_request_access_5.png)

   Se le redirige a la página [!UICONTROL Solicitar acceso] .

3. La página siguiente muestra su nombre e ID de correo electrónico utilizados para solicitar acceso. Deje un comentario para el administrador y haga clic en **[!UICONTROL Enviar]**.

   ![](assets/bplogin-request-access.png)

## Los administradores de productos otorgan acceso {#grant-access-to-brand-portal}

Los administradores de productos de Brand Portal reciben solicitudes de acceso en el área de notificación de Brand Portal y a través de correos electrónicos en su bandeja de entrada.

![Notificación de acceso solicitada](assets/bplogin_request_access_7.png)

Para conceder acceso, los administradores de productos deben hacer clic en la notificación correspondiente en el área de notificación de Brand Portal y, a continuación, hacer clic en **[!UICONTROL Otorgar acceso]**.
Como alternativa, los administradores de productos pueden seguir el vínculo proporcionado en el correo electrónico de solicitud de acceso para visitar Adobe [!UICONTROL Admin Console] y agregar el usuario a la configuración de producto relevante.
![](assets/bplogin_request_access_8.png)

Se le redirige a la página principal de [Adobe [!UICONTROL Admin Console]](https://adminconsole.adobe.com/enterprise/overview) . Utilice Adobe [!UICONTROL Admin Console] para crear usuarios y asignarlos a perfiles de producto (anteriormente conocidos como configuraciones de producto), que se muestran como grupos en Brand Portal. Para obtener más información sobre cómo agregar usuarios en [!UICONTROL Admin Console], consulte [Agregar un usuario](brand-portal-adding-users.md#add-a-user) (siga los pasos 4 a 7 del procedimiento para agregar un usuario).

## Notificación de mantenimiento de Brand Portal {#brand-portal-maintenance-notification}

Antes de que el portal de marcas esté programado para su mantenimiento, se muestra una notificación como pancarta después de iniciar sesión en Brand Portal. Una notificación de muestra:

![](assets/bp_maintenance_notification.png)

Puede rechazar esta notificación y continuar usando Brand Portal. Esta notificación aparece en cada nueva sesión.

## Información de la versión y del sistema {#release-and-system-information}

<!--* [What's new](../using/whats-new.md)-->
* [Notas de versión](brand-portal-release-notes.md)
* [Formatos de archivo admitidos](brand-portal-supported-formats.md)

## Related resources {#related-resources}

* [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/marketing-cloud/contact-support.html)
* [Foros de AEM](https://www.adobe.com/go/aod_forums_en)