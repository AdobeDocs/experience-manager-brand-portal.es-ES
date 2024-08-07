---
title: Administrar configuraciones de inquilino generales
description: Configure la aceleración de descargas, la creación de colecciones inteligentes públicas y la creación de colecciones públicas, y habilite a los usuarios administradores para eliminar recursos en los inquilinos.
contentOwner: mgulati
topic-tags: administration
content-type: reference
products: SG_EXPERIENCEMANAGER/Brand_Portal
role: Admin
exl-id: 5607be8e-0a7f-4692-b71b-5f66eb9ac5ee
source-git-commit: 32a67abf466dd3bf635b851b02377ed23591915e
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---

# Administrar configuraciones de inquilino generales {#administer-general-tenant-configurations}

Experience Manager Assets Brand Portal permite a las organizaciones configurar las siguientes funciones para inquilinos específicos:

* Eliminación de recursos por administradores
* Creación de colecciones públicas por usuarios no administradores
* Creación de colecciones inteligentes públicas por usuarios no administradores
* La jerarquía principal de las carpetas compartidas es visible para los usuarios que no son administradores

Estas configuraciones se han proporcionado como **[!UICONTROL configuraciones generales]** en el panel de herramientas administrativas.

![](assets/general-config.png)

**A**: configuración para permitir que los administradores eliminen recursos de Brand Portal. (El valor predeterminado está habilitado)

**B**: configuración para permitir que los usuarios que no son administradores creen colecciones públicas. (El valor predeterminado está habilitado)

**C**: configuración para permitir que los usuarios que no son administradores creen colecciones inteligentes públicas. (El valor predeterminado está habilitado)

**D**: configuración para mostrar la jerarquía de carpetas (desde la raíz) de carpetas compartidas a usuarios no administradores (editores, visores, usuarios invitados). (El valor predeterminado está desactivado)

## Habilitar o deshabilitar las configuraciones generales {#enable-disable-general-configurations}

Para habilitar o deshabilitar cada una de estas configuraciones:

1. Inicie sesión con privilegios de administrador.
1. Seleccione el logotipo del Experience Manager para acceder a las herramientas administrativas desde la barra de herramientas de la parte superior.
1. En el panel de herramientas administrativas, seleccione **[!UICONTROL General]** para abrir la página **[!UICONTROL Configuración general]**.
1. Utilice el conmutador correspondiente para habilitar o deshabilitar cualquiera de las configuraciones generales.
1. **[!UICONTROL Guardar]** los cambios.
1. Cierre la sesión para que los cambios surtan efecto.

## Permitir que los usuarios administradores eliminen recursos de Brand Portal {#allow-admin-users-to-delete-assets-from-brand-portal}

**[!UICONTROL Permitir que los usuarios eliminen]** la configuración permite que las organizaciones permitan (o restrinjan) a los usuarios con privilegios de administrador eliminar recursos y carpetas de Brand Portal.

## Permitir la creación de colecciones públicas por parte de los no administradores {#allow-public-collections-creation-by-non-admins}

[[!UICONTROL Permitir la creación de colecciones públicas]](../using/brand-portal-share-collection.md#main-pars-text-1915052376) la configuración controla si los usuarios que no son administradores pueden crear colecciones públicas en Brand Portal. La configuración está habilitada de forma predeterminada. Al deshabilitar la configuración, las organizaciones pueden evitar tener numerosas colecciones públicas en su portal para poder guardar el espacio del sistema.

## Permitir la creación de colecciones inteligentes públicas por parte de los no administradores {#allow-public-smart-collections-creation-by-non-admins}

[[!UICONTROL Permitir la creación de colecciones inteligentes públicas]](../using/brand-portal-searching.md#main-pars-header-500620467) la configuración controla si los usuarios que no son administradores pueden guardar sus búsquedas como colecciones inteligentes y hacerlas públicas para ese usuario. La configuración está habilitada de forma predeterminada. Al deshabilitar la configuración, las organizaciones pueden evitar que se cree una gran cantidad de colecciones inteligentes públicas por usuarios no administradores en Brand Portal de la organización.

<!-- 
## Allow download acceleration {#allow-download-acceleration}

[[!UICONTROL Allow download acceleration]](../using/accelerated-download.md) configuration lets the organizations to allow accelerated downloads of assets from Brand Portal and shared links, by integrating with IBM Aspera Connect that is an install-on-demand application. The application uses proprietary technology to remove TCP overheads.
-->

## Habilitar la jerarquía de carpetas {#enable-folder-hierarchy}

La configuración de [[!UICONTROL Habilitar jerarquía de carpetas]](../using/brand-portal-sharing-folders.md#non-admin-user-access-to-shared-folders) permite a los administradores controlar cómo ven las carpetas compartidas los usuarios que no son administradores (editores, visualizadores y usuarios invitados) después de iniciar sesión.
