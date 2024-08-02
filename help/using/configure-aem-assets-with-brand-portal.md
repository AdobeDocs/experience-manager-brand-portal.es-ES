---
title: Configurar Experience Manager Assets con Brand Portal
description: Obtenga información sobre la configuración de Experience Manager Assets con Brand Portal.
content-type: reference
contentOwner: Vishabh Gupta
topic-tags: brand-portal
products: SG_EXPERIENCEMANAGER/Brand_Portal
role: Admin
exl-id: 261c0e84-6b3d-459c-b6b9-a9af106d6943
source-git-commit: 32a67abf466dd3bf635b851b02377ed23591915e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 6%

---

# Configurar Experience Manager Assets con Brand Portal {#configure-integration}

La configuración de Adobe Experience Manager Assets con Brand Portal habilita las funciones de publicación, distribución y contribución de recursos para los usuarios de Brand Portal. Permite a los usuarios de Experience Manager Assets publicar y distribuir recursos con los usuarios de Brand Portal. Los usuarios de Brand Portal pueden acceder a los recursos compartidos y contribuir cargando nuevos recursos en las carpetas de contribución de recursos y publicándolos de nuevo en Experience Manager Assets.

La configuración de Experience Manager Assets con Brand Portal se admite en:

* Experience Manager Assets as a Cloud Service
* Experience Manager Assets (local y servicio administrado) 6.5 y versiones posteriores

Experience Manager Assets as a Cloud Service se configura automáticamente con Brand Portal activando Brand Portal desde Cloud Manager. El flujo de trabajo de activación crea las configuraciones necesarias en el back-end de y activa Brand Portal en la misma organización de IMS que la instancia as a Cloud Service de Experience Manager Assets.

Por su parte, Experience Manager Assets (local y servicio administrado) se configura manualmente con Brand Portal mediante Adobe Developer Console, que obtiene un token de Adobe de Identity Management Services (IMS) para la autorización del inquilino de Brand Portal.

>[!NOTE]
>
>***Para Experience Manager Assets, 6.5 y versiones posteriores***
>
>Anteriormente, la interfaz clásica configuraba Brand Portal mediante la puerta de enlace OAuth heredada, que emplea el intercambio de token web JSON (JWT) para obtener un token IMS para la autorización.
>
>La configuración mediante OAuth heredado ya no es compatible a partir del 6 de abril de 2020 y se cambia a mediante Adobe Developer Console.


>[!TIP]
>
>***Solo para clientes existentes (servicio local y administrado)***
>
>La configuración heredada de OAuth Gateway sigue funcionando para los clientes existentes.
>
>Si tiene problemas con la configuración heredada de OAuth Gateway, elimine la configuración existente y cree una nueva mediante Adobe Developer Console.

Los pasos para configurar AEM Assets con Brand Portal AEM varían en función de la versión de la aplicación, y de si está configurando por primera vez o actualizando las configuraciones existentes:

| AEM **Versión de la** | **Nueva configuración** | **Actualizar configuración** |
|---|---|---|
| **AEM Assets as a Cloud Service** | [Activar Brand Portal](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/assets/brand-portal/configure-aem-assets-with-brand-portal) | - |
| AEM **6.5 (6.5.4.0 y superior)** | [Crear configuración](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/brandportal/configure-aem-assets-with-brand-portal) | [Actualizar configuración](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/brandportal/configure-aem-assets-with-brand-portal#upgrade-integration-65) |
