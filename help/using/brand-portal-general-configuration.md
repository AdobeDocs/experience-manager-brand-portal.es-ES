---
title: Administrar configuraciones de inquilino generales
seo-title: Administer general tenant configurations
description: Configurar la aceleración descargar, la creación de colección inteligente públicas, la creación pública colección y permitir que los usuarios administradores eliminen activos en los inquilinos.
seo-description: Configure download acceleration, public smart collection creation, public collection creation, and enable admin users to delete assets on tenants.
uuid: 3c46cd7c-c38b-4bc7-b566-93f977bc8227
contentOwner: mgulati
topic-tags: administration
content-type: reference
products: SG_EXPERIENCEMANAGER/Brand_Portal
discoiquuid: f4c237bc-f6a4-4bc4-af56-3d9c3027daf4
role: Admin
exl-id: 5607be8e-0a7f-4692-b71b-5f66eb9ac5ee
source-git-commit: 955cd8afe939ff47e9f08f312505e230e2f38495
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---

# Administrar configuraciones de inquilino generales {#administer-general-tenant-configurations}

Experience Manager Assets Brand Portal permite a las organizaciones configurar las siguientes funciones para inquilinos específicos:

* Eliminación de recursos por administradores
* Creación de colección públicas por usuarios que no son administradores
* Creación de colección inteligente públicas por usuarios que no son administradores
* jerarquía principal de carpetas compartidas visibles para usuarios que no son administradores

Estas configuraciones se han proporcionado como **[!UICONTROL configuraciones generales configuración]** en el panel Herramientas administrativas.

![](assets/general-config.png)

**** Configuración para permitir a los administradores eliminar activos de Brand portal. (El valor predeterminado está habilitado)

**B**   para permitir que los usuarios que no son administradores creen colecciones públicas. (El valor predeterminado está habilitado)

**Configuración C**   para permitir que los usuarios que no son administradores creen colecciones inteligentes públicas. (El valor predeterminado está habilitado)

**D**  Configuración para mostrar la jerarquía de carpetas (desde la raíz) de las carpetas compartidas a usuarios no administradores (editores, visualizadores, usuarios invitados). (El valor predeterminado está desactivado)

## Activar/ desactivar configuraciones generales {#enable-disable-general-configurations}

Para habilitar o deshabilitar cada una de estas configuraciones:

1. Inicie sesión con privilegios de administrador.
1. Seleccione el logotipo Experience Manager para acceder a las herramientas administrativas en la barra de herramientas de la parte superior.
1. En el panel Herramientas administrativas, seleccione **[!UICONTROL General]** para abrir el **[!UICONTROL configuración]** General página.
1. Utilice el conmutador de alternancia correspondiente para habilitar o deshabilitar cualquiera de las configuraciones generales.
1. **[!UICONTROL Guarde los cambios.]**
1. Cierre de sesión para que los cambios surtan efecto.

## Permitir que los usuarios administradores eliminen activos de Brand portal {#allow-admin-users-to-delete-assets-from-brand-portal}

**[!UICONTROL Permitir que los usuarios eliminen]** La configuración de permite a las organizaciones permitir (o restringir) a los usuarios con privilegios de administrador eliminar recursos y carpetas de Brand Portal.

## Permitir la creación de colecciones públicas por parte de los no administradores {#allow-public-collections-creation-by-non-admins}

[[!UICONTROL Permitir la creación de colecciones públicas]](../using/brand-portal-share-collection.md#main-pars-text-1915052376) La configuración de controla si los usuarios que no son administradores pueden crear colecciones públicas en Brand Portal. La configuración está habilitada de forma predeterminada. Al deshabilitar las organizaciones de configuración puede evitar tener numerosas colecciones públicas en su portal para que se pueda guardar el espacio del sistema.

## Permitir que los usuarios que no son administradores creen la creación de colecciones inteligentes públicas {#allow-public-smart-collections-creation-by-non-admins}

[[!UICONTROL Permitir la configuración pública de creación ]](../using/brand-portal-searching.md#main-pars-header-500620467) de colecciones inteligentes permite que los usuarios que no sean administradores puedan guardar sus búsquedas como colecciones inteligentes y hacer que sean públicas para ese inquilino. La configuración está habilitada de forma predeterminada. Al deshabilitar las organizaciones de configuración puede evitar tener un gran número de colecciones inteligentes públicas creadas por usuarios que no son administradores en Brand portal de la organización.

<!-- 
## Allow download acceleration {#allow-download-acceleration}

[[!UICONTROL Allow download acceleration]](../using/accelerated-download.md) configuration lets the organizations to allow accelerated downloads of assets from Brand Portal and shared links, by integrating with IBM Aspera Connect that is an install-on-demand application. The application uses proprietary technology to remove TCP overheads.
-->

## Habilitar la jerarquía de carpetas {#enable-folder-hierarchy}

[[!UICONTROL Habilitar la configuración de jerarquía ]](../using/brand-portal-sharing-folders.md#non-admin-user-access-to-shared-folders) de carpeta permite a los administradores controlar la forma en que los usuarios que no son administradores (editores, visores y usuarios invitados) ven las carpetas compartidas después de registro en.
