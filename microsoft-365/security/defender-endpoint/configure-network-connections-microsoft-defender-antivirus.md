---
title: Configurar y validar las conexiones de red del Antivirus de Windows Defender
description: Configure y pruebe la conexión con el servicio Antivirus de Microsoft Defender de protección en la nube.
keywords: antivirus, Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, agresividad, nivel de protección
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/03/2022
ms.reviewer: mkaminska; pahuijbr
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: f29cf5f77acd52a4ff3ccc8384f3c64861e48b64
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806041"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurar y validar las conexiones de red del Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Para garantizar Antivirus de Microsoft Defender protección entregada en la nube funciona correctamente, el equipo de seguridad debe configurar la red para permitir conexiones entre los puntos de conexión y determinados servidores de Microsoft. En este artículo se enumeran las conexiones que deben permitirse para usar las reglas de firewall. También proporciona instrucciones para validar la conexión. Configurar correctamente la protección garantizará que reciba el mejor valor de los servicios de protección entregados en la nube.

> [!IMPORTANT]
> Este artículo contiene información sobre cómo configurar las conexiones de red solo para Antivirus de Microsoft Defender. Si usa Microsoft Defender para Endpoint (que incluye Antivirus de Microsoft Defender), consulte [Configure device proxy and Internet connectivity settings for Defender for Endpoint](configure-proxy-internet.md).


> [!NOTE]
> El sitio de demostración defender para el punto de conexión en demo.wd.microsoft.com está en desuso y se quitará en el futuro.

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Permitir conexiones al servicio Antivirus de Microsoft Defender nube

El Antivirus de Microsoft Defender en la nube proporciona una protección rápida y segura para los puntos de conexión. Es opcional habilitar el servicio de protección entregado en la nube. Antivirus de Microsoft Defender se recomienda el servicio en la nube, ya que proporciona una protección importante contra malware en los puntos de conexión y la red. Para obtener más información, vea [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for enabling service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or individual clients in the Seguridad de Windows app.

Después de habilitar el servicio, debe configurar la red o firewall para permitir conexiones entre la red y los puntos de conexión. Dado que la protección es un servicio en la nube, los equipos deben tener acceso a Internet y llegar a los servicios en la nube de Microsoft. No excluya la dirección URL `*.blob.core.windows.net` de ningún tipo de inspección de red.

> [!NOTE]
> El Antivirus de Microsoft Defender en la nube proporciona protección actualizada a la red y los puntos de conexión. El servicio en la nube no debe considerarse solo protección para los archivos almacenados en la nube; en su lugar, el servicio en la nube usa recursos distribuidos y aprendizaje automático para ofrecer protección para los puntos de conexión a una velocidad más rápida que las actualizaciones de inteligencia de seguridad tradicionales.

## <a name="services-and-urls"></a>Servicios y direcciones URL

En la tabla de esta sección se enumeran los servicios y sus direcciones de sitio web asociadas (DIRECCIONES URL).

Asegúrese de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL. De lo contrario, debe crear una regla de permitido específicamente para esas direcciones URL (excluyendo la dirección URL `*.blob.core.windows.net`). Las direcciones URL de la tabla siguiente usan el puerto 443 para la comunicación.

<br/><br/>

|Servicio y descripción|URL|
|---|---|
|Antivirus de Microsoft Defender servicio de protección entregado en la nube se conoce como Microsoft Active Protection Service (MAPS).<p> El Antivirus de Microsoft Defender usa el servicio MAPS para proporcionar protección entregada en la nube.|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
|Microsoft Update Service (MU) y Windows Update Service (WU) <p>Estos servicios permitirán la inteligencia de seguridad y las actualizaciones de productos.|`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Para obtener más información, vea [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Actualizaciones de inteligencia de seguridad Ubicación alternativa de descarga (ADL)<p>Esta es una ubicación alternativa para las Antivirus de Microsoft Defender de inteligencia de seguridad, si la inteligencia de seguridad instalada está des actualizada (siete o más días después).|`*.download.microsoft.com` <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
|Almacenamiento de envío de malware <p>Se trata de una ubicación de carga para los archivos enviados a Microsoft mediante el formulario de envío o el envío automático de ejemplo.|`ussus1eastprod.blob.core.windows.net` <p> `ussus2eastprod.blob.core.windows.net` <p> `ussus3eastprod.blob.core.windows.net` <p> `ussus4eastprod.blob.core.windows.net` <p> `wsus1eastprod.blob.core.windows.net` <p> `wsus2eastprod.blob.core.windows.net` <p> `ussus1westprod.blob.core.windows.net` <p> `ussus2westprod.blob.core.windows.net` <p> `ussus3westprod.blob.core.windows.net` <p> `ussus4westprod.blob.core.windows.net` <p> `wsus1westprod.blob.core.windows.net` <p> `wsus2westprod.blob.core.windows.net` <p> `usseu1northprod.blob.core.windows.net` <p> `wseu1northprod.blob.core.windows.net` <p> `usseu1westprod.blob.core.windows.net` <p> `wseu1westprod.blob.core.windows.net` <p> `ussuk1southprod.blob.core.windows.net` <p> `wsuk1southprod.blob.core.windows.net` <p> `ussuk1westprod.blob.core.windows.net` <p> `wsuk1westprod.blob.core.windows.net`|
|Lista de revocación de certificados (CRL) <p> Windows esta lista al crear la conexión SSL a MAPS para actualizar la CRL.|`http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p> `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs`|
|Almacén de símbolos <p>Antivirus de Microsoft Defender el Almacén de símbolos para restaurar determinados archivos críticos durante los flujos de corrección.|`https://msdl.microsoft.com/download/symbols`|
|Cliente de RGPD universal <p> Windows este cliente para enviar los datos de diagnóstico del cliente. <p> Antivirus de Microsoft Defender usa el Reglamento general de protección de datos con fines de supervisión y calidad del producto.|La actualización usa SSL (puerto TCP 443) para descargar manifiestos y cargar datos de diagnóstico en Microsoft que usa los siguientes extremos DNS: <p> `vortex-win.data.microsoft.com` <p> `settings-win.data.microsoft.com`|


## <a name="validate-connections-between-your-network-and-the-cloud"></a>Validar conexiones entre la red y la nube

Después de permitir las direcciones URL enumeradas, compruebe si está conectado al servicio Antivirus de Microsoft Defender nube. Pruebe que las direcciones URL están informando y recibiendo información correctamente para asegurarse de que está totalmente protegido.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Usar la herramienta cmdline para validar la protección entregada en la nube

Use el siguiente argumento con la Antivirus de Microsoft Defender de línea de comandos (`mpcmdrun.exe`) para comprobar que la red se puede comunicar con el servicio Antivirus de Microsoft Defender nube:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Abra el símbolo del sistema como administrador. Haga clic con el botón secundario en el elemento del **menú** Inicio, haga clic **en Ejecutar como administrador** y haga clic en **Sí en** el símbolo del sistema de permisos. Este comando solo funcionará en Windows 10, versión 1703 o posterior, o Windows 11.

Para obtener más información, [vea Manage Antivirus de Microsoft Defender with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Intentar descargar un archivo de malware falso de Microsoft

Puede descargar un archivo de ejemplo que Antivirus de Microsoft Defender detectará y bloqueará si está conectado correctamente a la nube. Visita [https://aka.ms/ioavtest](https://aka.ms/ioavtest) para descargar el archivo.

> [!NOTE]
> El archivo descargado no es exactamente malware. Es un archivo falso diseñado para probar si estás conectado correctamente a la nube.

Si está conectado correctamente, verá una notificación de Antivirus de Microsoft Defender advertencia.

Si usas Microsoft Edge, también verás un mensaje de notificación:

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Captura de pantalla de notificación de que se encontró malware en Azure IoT Edge.":::

Si usa Internet Explorer, se produce un mensaje similar:

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="Notificación antivirus de Microsoft Defender de que se encontró malware.":::

#### <a name="view-the-fake-malware-detection-in-your-windows-security-app"></a>Ver la detección de malware falso en la Seguridad de Windows de correo

1. En la barra de tareas, selecciona el icono Escudo y abre la **Seguridad de Windows** aplicación. O bien, busque **en Inicio** para *seguridad*.

2. Seleccione **Protección contra & virus** y, a continuación, seleccione **Historial de protección**.

3. En la **sección Amenazas en** cuarentena, seleccione **Ver historial completo** para ver el malware falso detectado.

   > [!NOTE]
   > Las versiones Windows 10 versiones anteriores a la 1703 tienen una interfaz de usuario diferente. Consulta [Antivirus de Microsoft Defender en la aplicación Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).

   El Windows de eventos también mostrará Windows Defender [identificador de evento de cliente 1116](troubleshoot-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Vea también

- [Configurar el proxy de dispositivo y la configuración de conectividad a Internet para Microsoft Defender para endpoint](configure-proxy-internet.md)
- [Usar la configuración de directiva de grupo para configurar y administrar Antivirus de Microsoft Defender](use-group-policy-microsoft-defender-antivirus.md)
- [Cambios importantes en el punto de conexión de Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 