---
title: Preguntas frecuentes
description: Obtenga información sobre las preguntas más frecuentes de Adobe Experience Manager Assets Brand Portal.
content-type: reference
contentOwner: Vishabh Gupta
topic-tags: frequently-asked-questions
products: SG_EXPERIENCEMANAGER/Brand_Portal
discoiquuid: null
exl-id: 4a8f7fbd-7485-421d-a8db-755324d2dbef
source-git-commit: 60104481e8f0b883fbf2cf25c1562e8376882e54
workflow-type: tm+mt
source-wordcount: '1495'
ht-degree: 0%

---

# Preguntas frecuentes {#frequently-asked-questions}

Las preguntas más frecuentes de Brand Portal se centran en las consultas y problemas que pueden encontrar los usuarios finales al trabajar con la última versión de Experience Manager Assets Brand Portal 6.4.6 o versiones anteriores.


## Preguntas frecuentes sobre Brand Portal 6.4.6 {#faqs-bp646}

**Pregunta: el extremo OAuth heredado existente (`https://legacy-oauth.cloud.adobe.io/login`) no funciona. ¿Cuál podría ser la posible razón?**

**Respuesta:** La configuración heredada de OAuth está obsoleta. Actualice las instancias de autor de Experience Manager Assets al Service Pack más reciente y configúrelo mediante Adobe Developer Console. Consulte [Configuración de Experience Manager Assets con Brand Portal](configure-aem-assets-with-brand-portal.md) para obtener más información. Sin embargo, para que la configuración de OAuth heredada funcione hasta que actualice, actualice el punto final de OAuth heredado a `https://hypnosisprod.ethos11-prod-or1.ethos.adobe.net/`.

**Pregunta: no puedo publicar los recursos de la carpeta Contribution de Brand Portal en Experience Manager Assets después de actualizar a Adobe Developer Console. Mi instancia de autor se encuentra en Experience Manager Assets 6.5.4. ¿Cuál podría ser la posible razón?**

**Respuesta:** Sí, hay un problema conocido al publicar los recursos de la carpeta Contribution en Experience Manager Assets 6.5.4 mediante Adobe Developer Console.

El problema se corrige en Experience Manager Assets 6.5.5. Puede actualizar su instancia de Experience Manager Assets al Service Pack más reciente y [actualizar sus configuraciones](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/brandportal/configure-aem-assets-with-brand-portal#upgrade-integration-65) en Adobe Developer Console.


**Pregunta: no veo el contenido de la carpeta Contribution publicado desde Brand Portal en Experience Manager Assets. ¿Cuál podría ser la posible razón?**

**Respuesta:** Póngase en contacto con el administrador de Experience Manager Assets para comprobar las configuraciones y asegurarse de que el inquilino de Brand Portal solo esté configurado con una instancia de autor de Experience Manager Assets.

Este problema posiblemente se produzca cuando haya configurado un inquilino de Brand Portal en varias instancias de autor de Experience Manager Assets. Por ejemplo, el administrador configura el mismo inquilino de Brand Portal en la instancia de autor de Experience Manager Assets de un entorno de ensayo y producción. En este caso, la publicación de recursos déclencheur en Brand Portal, pero la instancia de autor de Experience Manager Assets no importa el recurso porque el agente de replicación no recibe el token de solicitud.


**Pregunta: no puedo publicar recursos de Experience Manager Assets en Brand Portal. El registro de replicación indica que se agotó el tiempo de espera de la conexión. ¿Hay alguna solución rápida?**

**Respuesta:** Normalmente la publicación falla con un error de tiempo de espera si hay varias solicitudes pendientes en la cola de replicación. Para resolver este problema, asegúrese de que los agentes de replicación estén configurados para evitar el tiempo de espera.

Realice los siguientes pasos para configurar el agente de replicación:

1. Inicie sesión en la instancia de autor de Experience Manager Assets.
1. En el panel **Herramientas**, vaya a **[!UICONTROL Implementación]** > **[!UICONTROL Replicación]**.
1. En la página Replicación, haga clic en **[!UICONTROL `Agents on author`]**. Puede ver los cuatro agentes de replicación para su inquilino de Brand Portal.
1. Haga clic en la URL del agente de replicación para abrir los detalles del agente.
1. Haga clic en **[!UICONTROL Editar]** para editar la configuración del agente de replicación.
1. En la configuración del agente, haga clic en la ficha **[!UICONTROL Ampliado]**.
1. Active la casilla de verificación **[!UICONTROL Cerrar conexión]**.
1. Repita los pasos del 4 al 7 para configurar los cuatro agentes de replicación.
1. Reinicie el servidor y compruebe la conexión.


## Preguntas frecuentes sobre Brand Portal 6.4.5 {#faqs-bp645}

**Pregunta: ¿Cuál es el cambio más importante en la versión 6.4.5 de Brand Portal?**

**Respuesta:** Experience Manager Assets Brand Portal 6.4.5 permite a los usuarios cargar contenido y volver a publicar la carpeta Contribution en Experience Manager Assets directamente desde Brand Portal, sin necesidad de derechos de administrador. Para obtener más información, consulte [Abastecimiento de recursos en Brand Portal](brand-portal-asset-sourcing.md).



**Pregunta: ¿He perdido el acceso a algún recurso, característica o configuración existente que haya creado?**

**Respuesta:** Todas las características y configuraciones existentes permanecen intactas. Los usuarios finales no se verán afectados y el contenido permanecerá intacto.



**Pregunta: ¿Cuándo me mudo a la nueva versión de Brand Portal?**

**Respuesta:** Brand Portal 6.4.5 se publicó en producción en octubre de 2019. Y la próxima versión de Brand Portal está prevista para marzo de 2020.
Para actualizaciones y cambios de versión, el Adobe recomienda que realice un seguimiento de [Notas de la versión](brand-portal-release-notes.md) y [Novedades de Brand Portal](whats-new.md).



**Pregunta: ¿se ven afectados mis usuarios?**

**Respuesta:** La versión de Brand Portal 6.4.5 se encuentra exclusivamente en Brand Portal, por lo que no afecta a los usuarios finales.



**Pregunta: ¿se requiere alguna acción por mi parte como usuario de Brand Portal?**

**Respuesta:** La versión 6.4.5 de Brand Portal viene con una nueva característica denominada Abastecimiento de recursos. El administrador debe configurar la función de obtención de recursos en Experience Manager Assets para habilitar dicha función para los usuarios de Brand Portal. Para obtener más información, consulte [Habilitar el abastecimiento de recursos](brand-portal-asset-sourcing.md).



**Pregunta: ¿quién puede crear una carpeta Contribution?**

**Respuesta:** Cualquier usuario de Experience Manager Assets que tenga permisos para crear una carpeta en Experience Manager Assets puede crear una carpeta **Contribution**. Para crear una carpeta **Contribution**, cree una carpeta de tipo **Contribution de recursos**.
Esta carpeta se comparte con los usuarios activos de Brand Portal para que contribuyan.



**Pregunta: ¿Qué contiene una carpeta Contribution?**

**Respuesta:** La carpeta **Contribution** contiene dos subcarpetas **NEW** y **SHARED**. Inicialmente, la carpeta NUEVA está en blanco y la carpeta COMPARTIDA contiene el contenido de referencia (recursos reutilizables) para los usuarios de Brand Portal.
Los usuarios de Brand Portal acceden a la carpeta **Contribution** y cargan contenido en la carpeta **NEW**.



**Pregunta: ¿puedo modificar el nombre de una carpeta Contribution existente?**

**Respuesta:** **No**, no puede modificar el nombre de una carpeta de **Contribution** existente.



**Pregunta: ¿cuáles son los requisitos de recursos con contribución de r.t?**

**Respuesta:** El documento **Brief** de la carpeta **Contribution** y el contenido de referencia de la carpeta **SHARED** ayudan a los usuarios de Brand Portal a comprender las necesidades y expectativas de contribución. En conjunto, se conocen como requisitos de recursos.

**Pregunta: ¿Puedo cargar recursos en cualquier carpeta permitida?**

**Respuesta:** No todas las carpetas permitidas. Un usuario de Brand Portal solo puede cargar contenido en la carpeta **Contribution** que compartan los administradores de Experience Manager Assets o Brand Portal.



**Pregunta: ¿Cómo obtengo acceso a una carpeta Contribution?**

**Respuesta:** Solo puede tener acceso a una carpeta de **Contribution** si se ha compartido con usted. Recibirá una notificación por correo electrónico/pulso cada vez que se comparta una carpeta Contribution con usted. Puede acceder a la carpeta Contribution a través del vínculo compartido en el correo electrónico. O bien, puede iniciar sesión en la instancia de Brand Portal y navegar hasta el icono de campana para recibir las notificaciones y acceder a la carpeta Contribution.

>[!NOTE]
>
>Si no es usuario de Brand Portal, solicite al administrador de Experience Manager Assets que cree su usuario en el Admin Console. A continuación, añada su perfil al archivo de configuración de usuario en la lista de usuarios de Brand Portal.


**Pregunta: ¿Cuál es el formato del archivo CSV para la importación de usuarios?**

**Respuesta:** El formato coincide con lo que admite el Admin Console para la importación masiva de usuarios. El correo electrónico, el nombre y los apellidos son obligatorios.



**Pregunta: ¿Qué rellena la lista de usuarios (colaboradores de Brand Portal) en la lista desplegable de usuarios de contribución de recursos?**

**Respuesta:** Los usuarios de la lista desplegable se rellenan desde el archivo de configuración de usuario de Brand Portal (.csv) cargado en Experience Manager Assets.



**Pregunta: ¿Dónde puedo ver el estado de los trabajos de importación y publicación?**

**Respuesta:** En Experience Manager Assets, puede ver el estado de una importación en la página de trabajo **async**. En Brand Portal, puede ver el estado de un trabajo de publicación en **[!UICONTROL Herramientas > Estado de contribución de recursos]**.



**Pregunta: ¿Cuál es la frecuencia de un trabajo de importación que se ejecuta periódicamente en Experience Manager?**

**Respuesta:** En Experience Manager Assets, el sondeo se ejecuta cada 5 minutos.



**Pregunta: ¿Hay un umbral en la cantidad de veces que una carpeta se puede publicar de Brand Portal a Experience Manager Assets?**

**Respuesta:** No, todos los recursos de la carpeta **NEW** se publican en Experience Manager Assets, independientemente de si se publicaron anteriormente. Cada vez que se publica una carpeta **Contribution** de Brand Portal en Experience Manager Assets, reemplaza el contenido de la carpeta **NEW**.



**Pregunta: ¿Cómo cargar nuevos recursos en una carpeta Contribution?**

**Respuesta:** Consulte la documentación detallada de [Carga de recursos en la carpeta Contribution](brand-portal-publish-contribution-folder-to-brand-portal.md).



**Pregunta: no puedo ver miniaturas ni vistas previas de los recursos cargados en la NUEVA carpeta.**

**Respuesta:** Es como está diseñado, porque no hay ningún flujo de trabajo ejecutado al final de Brand Portal.



**Pregunta: ¿Qué sucede si se publica una carpeta de Experience Manager Assets a Brand Portal que está en proceso de cambio?**

**Respuesta:** En Experience Manager Assets, los registros se mantienen cada vez que se publica una carpeta en Brand Portal. En el momento de la publicación, todos los recursos que no se publican en Brand Portal se agregan a una cola de replicación. Los recursos agregados a la carpeta después de activarse el trabajo de publicación no se publican en Brand Portal. Cuando un usuario de Experience Manager Assets vuelve a publicar la carpeta, solo los recursos que no se publicaron anteriormente (existentes en la cola de replicación) se publican en Brand Portal. Este proceso se aplica a todas las carpetas publicadas desde Experience Manager Assets a Brand Portal y a las carpetas COMPARTIDAS dentro de una carpeta Contribution.

**Pregunta: ¿Con quién debo contactar para hacer preguntas?**

**Respuesta:** Póngase en contacto con el administrador de cuentas de Adobe o con la atención al cliente.

>[!NOTE]
>
>La programación de versiones es provisional y está sujeta a cambios. Póngase en contacto con el administrador de cuentas de Adobe o con la asistencia al cliente para obtener la programación de versiones actualizada.


## Acceso y asistencia de productos (sitios restringidos) {#product-access-and-support-restricted-sites}

Estos sitios solo están disponibles para los clientes de. Si es cliente y necesita acceso, póngase en contacto con el administrador de cuentas de Adobe.

<!--
* [](https://daycare.day.com) [Product Access](https://login.marketing.adobe.com)

* [Adobe Customer Support]()
-->
