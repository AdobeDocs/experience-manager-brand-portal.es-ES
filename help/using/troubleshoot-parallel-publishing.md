---
title: Solución de problemas en la publicación paralela de Brand Portal
seo-title: Troubleshoot issues in parallel publishing to Brand Portal
description: Solucionar problemas de publicación paralela.
seo-description: Troubleshoot parallel publishing.
uuid: 51e45cca-8c96-4c69-84ef-2ef34f3bcde2
products: SG_EXPERIENCEMANAGER/Brand_Portal
content-type: reference
topic-tags: brand-portal
discoiquuid: a4801024-b509-4c51-afd8-e337417e658b
role: Admin
exl-id: 631beabc-b145-49ba-a8e4-f301497be6da
source-git-commit: 72cd0ebbf05067287d94e1dc4e1b68f5fb6c2888
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 1%

---

# Solución de problemas en la publicación paralela de Brand Portal {#troubleshoot-issues-in-parallel-publishing-to-brand-portal}

Brand Portal está configurado con Experience Manager Assets para que los recursos de marca aprobados se introduzcan (o publiquen) sin problemas desde la instancia de autor de Experience Manager Assets. Una vez [configurado](../using/configure-aem-assets-with-brand-portal.md), Autor de Experience Manager utiliza un agente de replicación para replicar los recursos seleccionados en el servicio en la nube de Brand Portal para que los usuarios de Brand Portal los utilicen de forma aprobada. Se utilizan varios agentes de replicación Experience Manager 6.2 SP1-CFP5, Experience Manager CFP 6.3.0.2 y posteriores para permitir la publicación paralela de alta velocidad.

>[!NOTE]
>
>Adobe recomienda actualizar a Experience Manager 6.4.1.0 para garantizar que Experience Manager Assets Brand Portal se configure correctamente con Experience Manager Assets. Una limitación en el Experience Manager 6.4 da un error mientras se configura Experience Manager Assets con Brand Portal y la replicación falla.

Al configurar el servicio en la nube para Brand Portal en **[!UICONTROL /etc/cloudservice]**, todos los usuarios y tokens necesarios se generan automáticamente y se guardan en el repositorio. Se crea la configuración del servicio en la nube, también se crean los usuarios de servicio necesarios para los agentes de replicación y replicación para replicar contenido. Crea cuatro agentes de replicación. Por lo tanto, cuando publica numerosos recursos de Experience Manager a Brand Portal, los recursos se ponen en cola y se distribuyen entre los agentes de replicación a través de Round Robin.

Sin embargo, la publicación puede fallar de forma intermitente debido a los grandes trabajos de Sling, el aumento de la red y **[!UICONTROL E/S de disco]** en la instancia de Autor del Experience Manager o rendimiento lento de la instancia de Autor del Experience Manager. Por lo tanto, se recomienda probar la conexión con los agentes de replicación antes de comenzar a publicar.

![](assets/test-connection.png)

## Solucionar errores en la primera publicación: validación de la configuración de publicación {#troubleshoot-failures-in-first-time-publishing-validating-your-publish-configuration}

Para validar las configuraciones de publicación:

1. Compruebe los registros de errores
1. Compruebe si se ha creado el agente de replicación
1. Probar conexión

**Registros de cola al crear el Cloud Service**

Compruebe los registros de cola. Compruebe si el agente de replicación se ha creado o no. Si la creación del agente de replicación falla, edite el servicio en la nube realizando cambios menores en el servicio en la nube. Valide y vuelva a comprobar si el agente de replicación se ha creado o no. Si no es así, vuelva a editar el servicio.

Si en la edición repetida del servicio en la nube no está configurado correctamente, notifique un vale de Daycare.

**Probar la conexión con agentes de replicación**

Ver registro, si se encuentran errores en el registro de replicación:

1. Póngase en contacto con el servicio de atención al cliente.

1. Reintentar [limpieza](../using/troubleshoot-parallel-publishing.md#clean-up-existing-config) y cree de nuevo la configuración de publicación.

<!--
Comment Type: remark
Last Modified By: Mini Gulati (mgulati)
Last Modified Date: 2018-06-21T22:56:21.256-0400
<p>?? check and compare public key. At times public key is different</p>
<p>?? another thing to check in /useradmin</p>
-->

## Limpiar las configuraciones de publicación de Brand Portal existentes {#clean-up-existing-config}

La mayoría de las veces, cuando la publicación no funciona, el motivo puede ser que el usuario que lo está publicando (por ejemplo: `mac-<tenantid>-replication` no tiene la última clave privada y, por lo tanto, la publicación falla con el error &quot;401 no autorizado&quot; y no se notifica ningún otro error en los registros del agente de replicación. Puede que desee evitar la resolución de problemas y crear una configuración en su lugar. Para que la nueva configuración funcione correctamente, limpie lo siguiente de la configuración del autor del Experience Manager:

1. Vaya a `localhost:4502/crx/de/` (teniendo en cuenta que está ejecutando la instancia de autor en localhost:4502:\
   i. delete `/etc/replication/agents.author/mp_replication`
ii. delete 
`/etc/cloudservices/mediaportal/<config_name>`

1. Vaya a localhost:4502/useradmin:\
   i. buscar usuario `mac-<tenantid>replication`
ii. eliminar este usuario

Ahora todo el sistema está limpio. Ahora puede intentar crear una configuración de servicio en la nube y seguir utilizando la aplicación JWT existente. No es necesario crear una aplicación, sino actualizar la clave pública desde la configuración de nube recién creada.

>[!NOTE]
>
>No modifique ninguna configuración generada automáticamente.


## Problema de visibilidad del inquilino de la aplicación JWT de Developer Connection {#developer-connection-jwt-application-tenant-visibility-issue}

Si está activado `https://legacy-oauth.cloud.adobe.io/`, se enumeran todas las organizaciones (inquilinos) para las que los usuarios actuales tienen administrador del sistema. Si no encuentra el nombre de organización aquí o no puede crear una aplicación para un inquilino requerido aquí, compruebe si tiene suficientes derechos (administrador del sistema).

Hay un problema conocido en esta interfaz de usuario que para cualquier inquilino solo son visibles las diez aplicaciones principales. Cuando cree la aplicación, permanezca en esa página y añada un marcador a la dirección URL. No es necesario que vaya a la página de lista de la aplicación y busque la aplicación que ha creado. Puede pulsar esta URL con marcador directamente y actualizar/eliminar la aplicación cuando sea necesario.

Es posible que la aplicación JWT no aparezca en la lista adecuada. Por lo tanto, se recomienda anotar/marcar la URL al crear la aplicación JWT.

## La ejecución de la configuración deja de funcionar {#running-configuration-stops-working}

<!--
Comment Type: draft

<p>If the running configuration stops working, either of the following two possibilities
<g class="gr_ gr_15 gr-alert gr_gramm gr_inline_cards gr_run_anim Grammar multiReplace" data-gr-id="15" id="15" style="font-size: 12px;">
are
</g> there:</p>
<p>1.
<g class="gr_ gr_14 gr-alert gr_gramm gr_inline_cards gr_run_anim Grammar only-ins doubleReplace replaceWithoutSep" data-gr-id="14" id="14">
Connection
</g> has failed, or</p>
<p>2. Publish has failed with permission to dam-replication-service denied, while connection has passed </p>
<p>If the connection has failed [1], the
<g class="gr_ gr_10 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="10" id="10">
fail safe
</g> way to fix it is to <a href="../using/troubleshoot-parallel-publishing.md#main-pars-header-1664955658">clean up</a> the existing Brand Portal publish configuration and recreate a publish configuration. </p>
<p>However, if the
<g class="gr_ gr_18 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="18" id="18">
publish
</g> has failed with
<g class="gr_ gr_16 gr-alert gr_gramm gr_inline_cards gr_run_anim Grammar only-ins doubleReplace replaceWithoutSep" data-gr-id="16" id="16">
permission
</g> denied to dam-replication-service, raise a support ticket.</p>
-->

Si un agente de replicación (que estaba publicando en Brand Portal correctamente) deja de procesar trabajos de publicación, compruebe los registros de replicación. El Experience Manager tiene integrado un reintento automático, por lo que si falla la publicación de un recurso en particular, se vuelve a intentar automáticamente. Si hay algún problema intermitente, como un error de red, puede que se produzca correctamente durante el reintento.

Si hay errores de publicación continuos y la cola está bloqueada, debe comprobar **[!UICONTROL probar conexión]** e intente resolver los errores que se notifican.

En función de los errores, se le recomienda que registre un ticket de asistencia para que el equipo de ingeniería de Brand Portal pueda ayudarle a resolver los problemas.

## El token de configuración de IMS de Brand Portal expiró {#token-expired}

Si el entorno de Brand Portal se detiene repentinamente, existe la posibilidad de que las configuraciones de IMS no funcionen correctamente. El sistema muestra una configuración de IMS incorrecta y refleja un mensaje de error (similar al siguiente) que indica que el token de acceso ha caducado.

`com.adobe.granite.auth.oauth.AccessTokenProvider failed to get access token from authorization server status: 400 response: Unknown macro: {"error"}`

Para resolver este problema, se recomienda guardar manualmente y cerrar la configuración de IMS y comprobar de nuevo el estado de mantenimiento. Si las configuraciones no funcionan, elimine las configuraciones existentes y cree una nueva.


## Configurar los agentes de replicación para evitar el error de tiempo de espera de conexión {#connection-timeout}

Normalmente, el trabajo de publicación falla con un error de tiempo de espera si hay varias solicitudes pendientes en la cola de replicación. Para resolver este problema, asegúrese de que los agentes de replicación estén configurados para evitar el tiempo de espera.

Para configurar los agentes de replicación:

1. Inicie sesión en la instancia de autor de AEM Assets.
1. En el **Herramientas** , vaya a **[!UICONTROL Implementación]** > **[!UICONTROL Replicación]**.
1. En la página Replicación, haga clic en **[!UICONTROL Agentes en autor]**. Puede ver los cuatro agentes de replicación del inquilino de Brand Portal.
1. Haga clic en la dirección URL del agente de replicación y luego en **[!UICONTROL Editar]**.
1. En Configuración del agente , haga clic en el botón **[!UICONTROL Extendido]** pestaña .
1. Seleccione el **[!UICONTROL Cerrar conexión]** en el Navegador.
1. Repita los pasos del 4 al 7 para configurar los cuatro agentes de replicación.
1. Reinicie el servidor.
