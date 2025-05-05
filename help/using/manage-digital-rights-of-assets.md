---
title: Administración de los derechos digitales de recursos
description: Las licencias de recursos y la configuración de la caducidad de los recursos y los vínculos compartidos garantizan un uso controlado de estos recursos y los salvaguardan.
contentOwner: bdhar
topic-tags: download-install
products: SG_EXPERIENCEMANAGER/Brand_Portal
content-type: reference
role: Admin
exl-id: 86c31891-0627-41ca-b571-8dac3a074d55
source-git-commit: 10f89ded6febb1a024cbe181fa48a290d90223f0
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 3%

---

# Administración de los derechos digitales de recursos {#manage-digital-rights-of-assets}

Garantizar la distribución y el uso seguros de los recursos creativos y del material de la marca es vital para proteger su marca. AEM Este proceso se puede hacer cumplir asociando una fecha de caducidad (y hora) con recursos aprobados publicados desde la publicación en Brand Portal o mediante la licencia de estos recursos para su uso condicional. Además, Brand Portal permite especificar una fecha de caducidad para los vínculos a los recursos compartidos desde Brand Portal.

Siga leyendo para saber cómo están protegidos los recursos en Brand Portal y comprender los permisos de uso asociados.

## Caducidad de recursos {#asset-expiration}

La caducidad de los recursos es una forma eficaz de controlar el uso de los recursos aprobados en Brand Portal en toda la organización. Todos los recursos publicados de AEM Assets en Brand Portal pueden tener una fecha de caducidad que restrinja su uso a diferentes funciones de usuario.

### Permisos de uso relacionados con recursos caducados {#usage-permissions-expired-assets}

En Brand Portal, los administradores pueden ver, descargar y agregar recursos caducados a colecciones. Sin embargo, los editores y los visualizadores solo pueden ver y agregar recursos caducados a las colecciones.

Los administradores pueden publicar recursos caducados de AEM Assets en Brand Portal. Sin embargo, los recursos caducados no se pueden compartir mediante un vínculo de Brand Portal. Si selecciona cualquier recurso caducado de una carpeta que contenga recursos caducados y no caducados, la acción **[!UICONTROL Compartir vínculo]** no estará disponible. Sin embargo, si selecciona una carpeta que contiene recursos caducados y no caducados, las acciones [!UICONTROL Compartir] y **[!UICONTROL Compartir vínculo]** están disponibles.

>[!NOTE]
>
>Las carpetas se pueden compartir como vínculos aunque contengan recursos caducados. En este caso, el vínculo no enumera los recursos caducados y solo se comparten los que no lo han hecho.

La siguiente tabla muestra los permisos de uso de los recursos caducados:

|   | **[!UICONTROL Vínculo compartido]** | **[!UICONTROL Descargar]** | **[!UICONTROL Propiedades]** | **[!UICONTROL Agregar a la colección]** | **[!UICONTROL Eliminar]** |
|---|---|---|---|---|---|
| **[!UICONTROL Administrador]** | No disponible | Disponible | Disponible | Disponible | Disponible |
| **[!UICONTROL Editor]** | No disponible | No disponible | Disponible | Disponible | No disponible |
| **[!UICONTROL Visor]** | No disponible | No disponible | Disponible | Disponible | No disponible |
| **[!UICONTROL Usuario invitado]** | No disponible | No disponible | Disponible | Disponible | No disponible |

>[!NOTE]
>
>Si los visualizadores y editores descargan una carpeta que contiene recursos caducados y no caducados, solo se descargan los recursos no caducados. Si una carpeta solo contiene recursos caducados, se descarga una carpeta vacía.

### Estado de caducidad de los recursos {#expiration-status-of-assets}

Puede ver el estado de caducidad de los recursos en su **[!UICONTROL vista de tarjeta]**. Un indicador rojo en la tarjeta indica que el recurso ha caducado.

![](assets/expired_assets_cardview.png)

>[!NOTE]
>
>Las vistas Lista y Columna no muestran el estado de caducidad de los recursos.

## Caducidad de Asset Link {#asset-link-expiration}

Al compartir recursos mediante vínculos, los administradores y editores pueden establecer una fecha y una hora de caducidad mediante el campo **[!UICONTROL Caducidad]** del cuadro de diálogo **[!UICONTROL Uso compartido de vínculos]**. La caducidad predeterminada de un vínculo es de siete días a partir de la fecha en que se comparte.

![](assets/asset-link-sharing.png)

Garantiza que los recursos compartidos como vínculos caduquen en la fecha y la hora establecidas por los administradores y editores de Brand Portal. Además, los recursos ya no se pueden ver ni descargar más allá de la fecha de caducidad. Para proteger los recursos aprobados de los usuarios externos, establezca una fecha de caducidad en los vínculos compartidos para garantizar que no se expongan a entidades desconocidas más allá de un tiempo especificado.

Para obtener más información sobre cómo compartir vínculos, consulte [Compartir recursos como vínculo](../using/brand-portal-link-share.md).

## Assets con licencia {#licensed-assets}

Los activos con licencia están sujetos a la aceptación de un acuerdo de licencia antes de su descarga desde Brand Portal. Este acuerdo para los recursos con licencia se produce cuando se descarga directamente el recurso desde Brand Portal o mediante un vínculo compartido. Ya haya caducado o no, todos los usuarios pueden ver los recursos protegidos por licencias. Sin embargo, la descarga y el uso de los recursos con licencia caducados son limitados. Para obtener información sobre el comportamiento de los recursos con licencia vencidos y las actividades permisibles en función de las funciones de usuario, consulte [permisos de uso de recursos caducados](../using/manage-digital-rights-of-assets.md#usage-permissions-expired-assets).

Los recursos protegidos por licencias tienen un [acuerdo de licencia adjunto](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/administer/drm), para lo cual se establece la propiedad de metadatos del recurso en [!DNL Experience Manager Assets].

Un recurso se considera protegido si contiene una de las siguientes propiedades de metadatos (o ambas):

* `xmpRights:WebStatement`: esta propiedad hace referencia a la ruta de acceso de la página que contiene el contrato de licencia del recurso. `xmpRights:WebStatement` debe ser una ruta de acceso válida en el repositorio.
* `adobe_dam:restrictions`: el valor de esta propiedad es un HTML sin procesar que especifica el acuerdo de licencia.


Si elige descargar recursos protegidos por licencias, se le redirigirá a la página **[!UICONTROL Administración de derechos de autor]** en función de las propiedades de los metadatos.

| `adobe_dam:restrictions` | `xmpRights:WebStatement` | Administración de copyright |
| --- | --- | --- |
| Sí | - | La interfaz aparece en Assets y Brand Portal |
| - | Sí (ruta no válida) | Sin interfaz |
| Sí | Sí (ruta no válida) | Sin interfaz |
| Sí | Sí (ruta válida) | La interfaz aparece en Assets o Brand Portal</br>Dependiendo de si la ruta de acceso es válida para Assets o Brand Portal (o ambos). |

![](assets/asset-copyright-mgmt.png)

Aquí debe seleccionar el recurso que desea descargar y aceptar el acuerdo de licencia asociado. Si no acepta el contrato de licencia, el botón **[!UICONTROL Descargar]** no estará habilitado.

![](assets/licensed-asset-download-2.png)

Si la selección contiene varios recursos protegidos, seleccione un recurso a la vez, acepte el acuerdo de licencia y proceda a descargar el recurso.

## Generar informe sobre recursos caducados {#generate-report-about-expired-assets}

Los administradores pueden generar y descargar un informe que enumere todos los recursos caducados en un lapso de tiempo específico. Este informe incluye información detallada, como tamaño, tipo, ruta que especifica la ubicación del recurso en la jerarquía de recursos, cuándo caducó el recurso y cuándo se publicó, sobre los recursos caducados. Las columnas de este informe se pueden personalizar para mostrar más datos según los requisitos del usuario.

![](assets/assets-expired.png)

Para obtener más información sobre la característica de informes, ve a [Trabajar con informes](../using/brand-portal-reports.md#work-with-reports).
