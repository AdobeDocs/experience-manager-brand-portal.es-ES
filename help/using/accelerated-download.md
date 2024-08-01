---
title: Acelerar las descargas de Brand Portal
description: Mejora del rendimiento de descarga desde Brand Portal y los vínculos compartidos.
contentOwner: Vishabh Gupta
topic-tags: download-install, download assets
content-type: reference
products: SG_EXPERIENCEMANAGER/Brand_Portal
exl-id: cf28df58-c6dd-4b12-8279-01351892009f
source-git-commit: f931f6576c05d82cea61bda00322425abc9e8d43
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 3%

---

# Acelerar las descargas de Brand Portal {#guide-to-accelerate-downloads-from-brand-portal}

<!-- This topic is woefully out of date. It talks at length about using a third party application whose URLs have a variety of problems. Topic should either be deleted or updated entirely to not talk about a specific third party application that Adobe has no control over. It also appears that the third party app is NOT free anymore. -->

Adobe Experience Manager Assets Brand Portal permite mejorar el rendimiento de descarga de archivos de recursos grandes mediante la integración con IBM® Aspera Connect, una aplicación de instalación bajo demanda. La aplicación utiliza tecnología patentada para eliminar los gastos generales de TCP y ayuda a mejorar la velocidad de transferencia de los archivos de recursos. Esta integración garantiza una experiencia de descarga mejorada.

>[!NOTE]
>
>La velocidad de descarga varía según el usuario, ya que depende de factores como el ancho de banda de la red, la latencia del servidor y la ubicación geográfica de los clientes.

La configuración de **[!UICONTROL Descarga rápida]** está habilitada de manera predeterminada, lo que reduce significativamente el tiempo necesario para descargar los archivos de recursos deseados de Brand Portal.

![](assets/download-settings-new.png)

## Requisitos previos para acelerar la descarga de archivos {#prerequisites-to-accelerate-file-download}

Para descargar los archivos más rápido, asegúrese de lo siguiente:

* Vaya a **[!UICONTROL Herramientas]** > **[!UICONTROL Descargar]** y compruebe que la configuración de **[!UICONTROL Descarga rápida]** esté habilitada en **[!UICONTROL Configuración de descarga]**.
* Asegúrese de que el puerto 33001 (TCP y UDP) esté abierto en el firewall.
* **Instale IBM® Aspera Connect 3.9.9** en la extensión de su explorador con privilegios de administrador ([Descargas de IBM® Aspera Connect](https://www.ibm.com/support/fixcentral/swg/selectFixes?parent=ibm%7EOther%20software&amp;product=ibm/Other+software/IBM+Aspera+Connect&amp;release=3.9.9&amp;platform=All&amp;function=all)).

>[!NOTE]
>
>Hay un problema conocido con IBM® Aspera Connect. La descarga rápida no funciona con IBM® Aspera Connect versión 3.10 o posterior.

## Descargar dominios {#download-domains}

A continuación se muestran los dominios de descarga para diferentes regiones geográficas:

| Código de región | Dominio |
|---|---|
| NA O1 | downloads-na1.brand-portal.adobe.com |
| NA VA5 | downloads-na2.brand-portal.adobe.com |
| EMEA LON5 | downloads-emea1.brand-portal.adobe.com |
| SIN2 APAC | downloads-apac1.brand-portal.adobe.com |

## Rendimiento de descarga de muestra mediante el acelerador de archivos {#expected-download-performance-using-file-accelerator}

La siguiente tabla muestra el rendimiento de descarga de un archivo de 2 GB mediante el acelerador de descargas de archivos de Aspera Connect:

*Los resultados observados varían debido a factores como el ancho de banda de la red, la latencia del servidor y la ubicación del cliente, considerando que el servidor de Brand Portal se encuentra en Oregón (Estados Unidos).*

| Ubicación del cliente | Latencia entre cliente y servidor (milisegundos) | Velocidad con el acelerador de transferencia de archivos Aspera Connect (MBps) | Tiempo necesario para descargar un archivo de 2 GB con Aspera File Transfer Accelerator (segundos) |
|---------------------------|-----------------------------------|---------------------------------------------|-------------------------------------------------------------------------|
| Zona occidental de Estados Unidos (Norte de California) | 18 | 36 | 57 |
| Zona occidental de Estados Unidos (Oregón) | 42 | 36 | 57 |
| Este de EE. UU. (Virginia del Norte) | 85 | 35 | 58 |
| APAC (Tokio) | 124 | 36 | 57 |
| Noida (India) | 275 | 13,36 | 153 |
| Sídney | 175 | 29 | 70 |
| Londres | 179 | 35 | 58 |
| Singapur | 196 | 34 | 60 |

## Descarga de recursos {#download-assets}

Para descargar recursos más rápido desde Brand Portal:

1. Inicie sesión en su inquilino de Brand Portal. De manera predeterminada, se abre la vista **[!UICONTROL Archivos]** que contiene todos los recursos y carpetas publicados.

   Realice una de las siguientes acciones:

   * Seleccione los recursos o carpetas que desee descargar. En la barra de herramientas de la parte superior, haz clic en el icono **[!UICONTROL Descargar]**.

     ![select-multiple-assets](assets/select-assets-new.png)

   * Para descargar representaciones de recursos específicas de un recurso, pase el puntero sobre el recurso y haga clic en el icono **[!UICONTROL Descargar]** disponible en las miniaturas de acciones rápidas.

     ![select-asset](assets/select-asset.png)

1. Se abre el cuadro de diálogo **[!UICONTROL Descargar]** que enumera todos los recursos seleccionados.

   Para conservar la jerarquía de carpetas de Brand Portal al descargar recursos, active la casilla de verificación **[!UICONTROL `Create separate folder for each asset`]**.

   El botón de descarga refleja el recuento de los elementos seleccionados. Una vez que haya terminado de aplicar las reglas, haga clic en **[!UICONTROL Descargar elementos]**. Para obtener más información sobre cómo aplicar las reglas, consulte [descargar recursos](../using/brand-portal-download-assets.md#download-assets).

   ![cuadro de diálogo de descarga](assets/download-dialog-box-new.png)

1. De manera predeterminada, la configuración **[!UICONTROL Descarga rápida]** está habilitada en **[!UICONTROL Configuración de descarga]**. Por lo tanto, aparece un cuadro de confirmación para descargar recursos mediante IBM® Aspera Connect.

   Si ha descargado recursos por primera vez y no tiene IBM® Aspera Connect instalado en el explorador, se le pedirá que lo instale. Si la versión existente no está actualizada, también se le pedirá que instale el [acelerador de descargas de Aspera](https://www.ibm.com/support/fixcentral/swg/selectFixes?parent=ibm%7EOther%20software&amp;product=ibm/Other+software/IBM+Aspera+Connect&amp;release=3.9.9&amp;platform=All&amp;function=all).

   ![](assets/aspera-not-launched.png)

1. **Instalar el cliente de Aspera Connect**

   Para instalar el programa de instalación del cliente de IBM® Aspera Connect, ejecute el programa de instalación desde el archivo .msi de la aplicación cliente de IBM® Aspera Connect y siga el asistente de instalación.

   ![](assets/aspera-download-1.png)

1. Una vez que el cliente se haya instalado correctamente, actualice la página del explorador e inicie de nuevo los pasos de descarga.

1. Para seguir usando **[!UICONTROL Descarga rápida]**, haz clic en **[!UICONTROL Permitir]**. Todas las representaciones seleccionadas se descargan en una carpeta zip mediante IBM® Aspera Connect.

   Al finalizar correctamente la descarga, un cuadro de diálogo muestra la ubicación en la que se descargan los recursos en el sistema del usuario.

   ![](assets/aspera-download-2.png)

   Si no quieres usar IBM® Aspera Connect, haz clic en **[!UICONTROL Denegar]**. Si se deniega la descarga rápida **[!UICONTROL 1} o se produce un error, el sistema rellena un mensaje de error.]** Haga clic en el botón **[!UICONTROL Descarga normal]** para continuar descargando los recursos.

>[!NOTE]
>
>Si el administrador desactiva la configuración **[!UICONTROL Descarga rápida]**, las representaciones seleccionadas se descargan directamente en una carpeta zip sin usar IBM® Aspera Connect.

<!-- 
On successful completion of the download, a dialog box shows the location where assets are downloaded onto the user's system. If there is a failure, it shows error.

   >[!NOTE]
   >
   >There is a known limitation in Aspera Connect client application that no prompt to select download location appears if **[!UICONTROL Always ask me where to save downloaded files]** is enabled under the tab **[!UICONTROL Transfers]** within **[!UICONTROL Preferences]**. Before any download begins, provide the location in the text box **[!UICONTROL Save downloaded files to]**.


1. Log in to Brand Portal using a supported browser.
1. Browse and select the folders or assets you want to download. From the toolbar at the top, click the **[!UICONTROL Download]** icon. the **[!UICONTROL Download]** dialog appears with the **[!UICONTROL Asset(s)]** and **[!UICONTROL Enable download acceleration]** check boxes selected by default. 

   ![](assets/download-assetsbp.png)

   >[!NOTE]
   >
   >The functionality to send email notification with the link to download assets is presently not supported while faster downloads are enabled.

   ![](assets/fast-download-emailchk.png)

1. Click **[!UICONTROL Download]**.

   To speed up the download experience on your Brand Portal tenant account, you need to have Aspera Connect client application installed in your browser's extension.

1. **Download Aspera Connect Client**

   If Aspera Connect client is not installed on your system or the existing Aspera Connect client is out of date, a prompt is displayed on the browser page from where you can download the system-specific Aspera Connect client by selecting **[!UICONTROL Download Latest Version]**.

   ![](assets/aspera-not-launched.png)

   To download the latest version of Aspera Connect from [https://downloads.asperasoft.com/connect2/](https://downloads.asperasoft.com/connect2/), select **[!UICONTROL Download Now]** and follow the instructions.

1. **Install Aspera Connect Client**

   To install IBM Aspera Connect client setup, run the setup from  .msi  file of IBM Aspera Connect client application and follow the installation wizard.

1. Once the client is successfully installed, refresh the browser page and initiate the download steps again.

   When using Aspera Connect for the first time, the browser prompts to open the link using **[!UICONTROL IBM Aspera Connect]**. To skip this dialog in future, enable **[!UICONTROL Remember my choice for FASP links]**.

   >[!NOTE]
   >
   >This message is different on the different browsers.

1. A dialog box confirms whether to proceed the transfer or not. Select **[!UICONTROL Allow]** to begin.
To skip this dialog in future, enable **[!UICONTROL Use my choice for all connections with this host]**.
Download begins. A dialog box shows the progress of the download. Use the dialog box to **[!UICONTROL pause]**, **[!UICONTROL resume]**, or **[!UICONTROL cancel]** the download.
Aspera Connect application provides an Activity Window on the system where user can view and manage all transfer sessions. For more information, refer [Aspera Connect Client documentation](https://downloads.asperasoft.com/en/documentation/8).

![](assets/aspera-activity-window.png)

On successful completion of the download, a dialog box shows the location where assets are downloaded onto the user's system. If there is a failure, it shows error.

   >[!NOTE]
   >
   >There is a known limitation in Aspera Connect client application that no prompt to select download location appears if **[!UICONTROL Always ask me where to save downloaded files]** is enabled under the tab **[!UICONTROL Transfers]** within **[!UICONTROL Preferences]**. Before any download begins, provide the location in the text box **[!UICONTROL Save downloaded files to]**.
-->

## Uso del acelerador de archivos en el explorador Microsoft® Edge {#using-file-accelerator-on-microsoft-edge-browser}

Microsoft® Edge se ejecuta en modo protegido mejorado (EPM), lo que impide la comunicación con el servidor de Aspera Connect, mientras se encuentra en la misma red privada o con un sitio de confianza. Por lo tanto, aparece una ventana emergente cada vez que se establece una conexión con el servidor.

![](assets/switchapps-msedge.png)

Para utilizar la funcionalidad de descarga acelerada en Microsoft® Edge, elimine el sitio de Brand Portal de la lista Sitio de confianza.

1. Abra el Panel de control de Campaign (**[!UICONTROL Tecla de ventana + X]** y seleccione **[!UICONTROL Panel de control de Campaign]**).
1. Vaya a **[!UICONTROL Red e Internet]** > **[!UICONTROL Opciones de Internet]**. Haga clic en la ficha **[!UICONTROL Seguridad]**.
1. Haga clic en la zona de **[!UICONTROL sitios de confianza]** y, a continuación, haga clic en **[!UICONTROL Sitios]**.
1. Elimine el sitio de Brand Portal de la lista.

## Preferencias del cliente de Aspera Connect {#aspera-connect-client-preferences}

Hay algunas preferencias útiles que se pueden establecer en la preferencia del cliente de IBM® Aspera Connect haciendo clic con el botón derecho en el icono y seleccionando **[!UICONTROL Preferencias]**.

![](assets/download_assets_frombrandportalimg19.png)

Puede establecer la ubicación de descarga predeterminada.

![](assets/aspera-preferences.png)

Además, el cliente de Aspera Connect puede marcarse para que se inicie automáticamente al iniciar el sistema. Además, el cliente de Connect se ejecuta y está disponible para que la descarga empiece más rápido.

![](assets/aspera-automaticallylaunch.png)

## Solucionar problemas con la aceleración de descargas {#troubleshoot-issues-with-download-acceleration}

Si la aceleración de descarga no funciona para usted, pruebe las siguientes sugerencias:

1. Compruebe que los puertos no estén bloqueados. Utilice la búsqueda de Google para buscar opciones que le permitan comprobar si los puertos están bloqueados, en función del sistema operativo que se utilice.  <!-- THIS URL IS 404 AND DOES NOT REDIRECT [https://test-connect.asperasoft.com](https://test-connect.asperasoft.com/) from your computer. -->

   Si los puertos no son correctos, póngase en contacto con el equipo de red y asegúrese de que los puertos 33001 (TCP y UDP) no están bloqueados en el firewall.

1. Si los puertos están correctos, compruebe si la red no es lenta midiendo el ancho de banda disponible con [https://www.speedtest.net/](https://www.speedtest.net/).

   Si el ancho de banda es de unos pocos (1-10 Mbps) o en Kbps, utilice las Preferencias de Aspera y trate de limitar el ancho de banda igual al ancho de banda disponible.

   <!-- The URL in this step is giving a 404 error. 1. To confirm whether the downloads from Aspera demo server are working, use [https://demo.asperasoft.com/aspera/user](https://demo.asperasoft.com/aspera/user).  
   (login:  asperaweb , password:  demoaspera ) -->

1. Si ninguno de los pasos anteriores para solucionar problemas funciona, anule la selección de la opción Habilitar la aceleración de descarga y utilice la descarga normal.
