---
title: Solución de problemas en la publicación paralela de Brand Portal
description: Solucionar problemas de publicación paralela.
products: SG_EXPERIENCEMANAGER/Brand_Portal
content-type: reference
topic-tags: brand-portal
role: Admin
exl-id: 631beabc-b145-49ba-a8e4-f301497be6da
source-git-commit: ce3a7a5232f32c86b4930f9079bed5f04d001d8f
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 0%

---

# Solución de problemas en la publicación paralela de Brand Portal {#troubleshoot-issues-in-parallel-publishing-to-brand-portal}

Brand Portal se configura con Experience Manager Assets para que los recursos de marca aprobados se ingieran (o publiquen) sin problemas desde la instancia de autor de Experience Manager Assets. Una vez [configurado](../using/configure-aem-assets-with-brand-portal.md), Experience Manager Author usa un agente de replicación para replicar uno o más recursos seleccionados en el servicio en la nube de Brand Portal para que los usuarios de Brand Portal los usen de forma aprobada. Se utilizan varios agentes de replicación en el Experience Manager 6.2 SP1-CFP5, el Experience Manager CFP 6.3.0.2 y versiones posteriores para permitir la publicación paralela de alta velocidad.

>[!NOTE]
>
>Para garantizar el éxito de la configuración de Experience Manager Assets Brand Portal con Experience Manager Assets, Adobe recomienda actualizar al Experience Manager 6.4.1.0. Una limitación del Experience Manager 6.4 genera un error al configurar Experience Manager Assets con Brand Portal y se produce un error en la replicación.

Al configurar un servicio en la nube para Brand Portal en **[!UICONTROL /etc/cloudservice]**, todos los usuarios y el token necesarios se generan automáticamente y se guardan en el repositorio. Cuando se crea la configuración de Cloud Service, también se crean los usuarios de servicio necesarios para los agentes de replicación y replicación para replicar contenido. Crea cuatro agentes de replicación. Por lo tanto, cuando publica numerosos recursos de Experience Manager a Brand Portal, estos se ponen en cola y se distribuyen entre los agentes de replicación a través de Round Robin.

Sin embargo, la publicación puede fallar intermitentemente debido a: grandes trabajos de Sling, aumento de la red y **[!UICONTROL E/S del disco]** en la instancia de autor del Experience Manager o rendimiento lento de la instancia de autor del Experience Manager. Adobe recomienda probar la conexión con uno o más agentes de replicación antes de comenzar la publicación.

![](assets/test-connection.png)

## Solucionar errores en la publicación por primera vez: validación de la configuración de publicación {#troubleshoot-failures-in-first-time-publishing-validating-your-publish-configuration}

Para validar las configuraciones de publicación:

1. Comprobación de los registros de errores
1. Compruebe si se ha creado el agente de replicación
1. Probar conexión

**Registros de cola al crear el Cloud Service**

Compruebe los registros de cola. Compruebe si el agente de replicación se ha creado o no. Si la creación del agente de replicación falla, edite el servicio en la nube realizando cambios menores en él. Valide y vuelva a comprobar si el agente de replicación se ha creado o no. Si no es así, vuelva a editar el servicio.

Si al editar repetidamente el servicio en la nube no está configurado correctamente, notifique un ticket de Daycare.

**Probar conexión con agentes de replicación**

Ver registro, si se encuentran errores en el registro de replicación:

1. Póngase en contacto con Atención al cliente.

1. Vuelva a intentar [limpiar](../using/troubleshoot-parallel-publishing.md#clean-up-existing-config) y cree la configuración de publicación.

<!--
Comment Type: remark
Last Modified By: Mini Gulati (mgulati)
Last Modified Date: 2018-06-21T22:56:21.256-0400
<p>?? check and compare public key. At times public key is different</p>
<p>?? another thing to check in /useradmin</p>
-->

## Limpiar las configuraciones de publicación de Brand Portal existentes {#clean-up-existing-config}

La publicación a menudo falla con un error &quot;401 unauthorized&quot; porque el usuario (por ejemplo, `mac-<tenantid>-replication`) carece de la clave privada más reciente y no se informa de ningún otro error en los registros del agente de replicación. Es posible que desee evitar la resolución de problemas y crear una configuración en su lugar. Para que la nueva configuración funcione correctamente, limpie lo siguiente de la configuración del autor del Experience Manager:

1. Ir a `localhost:4502/crx/de/` (teniendo en cuenta que está ejecutando la instancia de autor en `localhost:4502:`)
i. Eliminar `/etc/replication/agents.author/mp_replication`
ii. Eliminar `/etc/cloudservices/mediaportal/<config_name>`

1. Vaya a localhost:4502/useradmin:\
   i. Busque el usuario `mac-<tenantid>replication`
ii. Eliminar este usuario

Ahora, el sistema está todo limpio. Ahora puede intentar crear una configuración de servicio en la nube y seguir utilizando la aplicación JWT existente. No es necesario crear una aplicación, sino actualizar la clave pública desde la configuración en la nube recién creada.

>[!NOTE]
>
>No modifique ninguna configuración generada automáticamente.


## Problema de visibilidad del inquilino de la aplicación JWT de Developer Connection {#developer-connection-jwt-application-tenant-visibility-issue}

Si está en `https://legacy-oauth.cloud.adobe.io/`, se enumerarán todas las organizaciones (inquilinos) para las que los usuarios actuales tienen un administrador del sistema. Si no encuentra aquí el nombre de la organización o no puede crear una solicitud para un inquilino requerido, compruebe si tiene suficientes derechos (de administrador del sistema).

Hay un problema conocido en esta interfaz de usuario que indica que, para cualquier inquilino, solo están visibles las diez aplicaciones principales. Cuando cree la aplicación, permanezca en esa página y marque la dirección URL. No vaya a la página del listado de la aplicación y busque la aplicación que ha creado. Puede acceder a esta dirección URL con marcador directamente y actualizar o eliminar la aplicación cuando sea necesario.

Es posible que la aplicación JWT no aparezca correctamente en la lista. Por lo tanto, se recomienda que anote o marque la dirección URL al crear una aplicación JWT.

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

Si un agente de replicación (que publicaba en Brand Portal correctamente) detiene el procesamiento de los trabajos de publicación, compruebe los registros de replicación. El Experience Manager tiene integrado el reintento automático, por lo que si falla la publicación de un recurso en particular, se vuelve a intentar automáticamente. Si hay algún problema intermitente como un error de red, puede que se realice correctamente durante un reintento.

Si hay errores de publicación continuos y la cola está bloqueada, compruebe la **[!UICONTROL conexión de prueba]**. Intente resolver los errores de los que se informa.

En función de los errores, se le recomienda registrar un ticket de asistencia para que el equipo de ingeniería de Brand Portal pueda ayudarle a resolver los problemas.

## Token de configuración de IMS de Brand Portal caducado {#token-expired}

Si el entorno de Brand Portal se detiene abruptamente, es posible que las configuraciones de IMS no funcionen correctamente. El sistema muestra una configuración de IMS incorrecta y refleja un mensaje de error (similar al siguiente) que indica que el token de acceso ha caducado.

`com.adobe.granite.auth.oauth.AccessTokenProvider failed to get access token from authorization server status: 400 response: Unknown macro: {"error"}`

Para resolver este problema, Adobe recomienda guardar y cerrar manualmente la configuración de IMS y comprobar de nuevo el estado. Si las configuraciones no funcionan, elimine las configuraciones existentes y cree una nueva.


## Configurar agentes de replicación para evitar errores de tiempo de espera de conexión {#connection-timeout}

Normalmente, el trabajo de publicación falla con un error de tiempo de espera si hay varias solicitudes pendientes en la cola de replicación. Para resolver este problema, asegúrese de que los agentes de replicación estén configurados para evitar el tiempo de espera.

Para configurar los agentes de replicación:

1. Inicie sesión en la instancia de autor de AEM Assets.
1. En el panel **Herramientas**, vaya a **[!UICONTROL Implementación]** > **[!UICONTROL Replicación]**.
1. En la página Replicación, haga clic en **[!UICONTROL `Agents on author`]**. Puede ver los cuatro agentes de replicación de su inquilino de Brand Portal.
1. Haga clic en la URL del agente de replicación y luego en **[!UICONTROL Editar]**.
1. En Configuración de agente, haga clic en la ficha **[!UICONTROL Extendido]**.
1. Active la casilla de verificación **[!UICONTROL Cerrar conexión]**.
1. Repita los pasos del 4 al 7 para configurar los cuatro agentes de replicación.
1. Reinicie el servidor.
