---
title: Configurar y validar las conexiones de red del Antivirus de Windows Defender
description: Configure y pruebe la conexión al servicio de protección en la nube Antivirus de Microsoft Defender.
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
ms.openlocfilehash: 8da099332ffbe2cc3d860faef504e4c5d9663614
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418640"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurar y validar las conexiones de red del Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Para asegurarse de que Antivirus de Microsoft Defender protección entregada en la nube funciona correctamente, el equipo de seguridad debe configurar la red para permitir conexiones entre los puntos de conexión y determinados servidores de Microsoft. En este artículo se enumeran las conexiones que se deben permitir para usar las reglas de firewall. También proporciona instrucciones para validar la conexión. La configuración correcta de la protección garantizará que recibe el mejor valor de los servicios de protección entregados en la nube.

> [!IMPORTANT]
> Este artículo contiene información sobre la configuración de conexiones de red solo para Antivirus de Microsoft Defender. Si usa Microsoft Defender para punto de conexión (que incluye Antivirus de Microsoft Defender), consulte [Configuración del proxy de dispositivo y la conectividad a Internet para Defender para punto de conexión](configure-proxy-internet.md).


> [!NOTE]
> El sitio de demostración de Defender para punto de conexión en demo.wd.microsoft.com está en desuso y se eliminará en el futuro.

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Permitir conexiones al servicio en la nube Antivirus de Microsoft Defender

El servicio en la nube Antivirus de Microsoft Defender proporciona una protección rápida y segura para los puntos de conexión. Es opcional habilitar el servicio de protección entregado en la nube. se recomienda Antivirus de Microsoft Defender servicio en la nube, ya que proporciona una protección importante contra el malware en los puntos de conexión y la red. Para obtener más información, consulte [Habilitación de la protección entregada](enable-cloud-protection-microsoft-defender-antivirus.md) en la nube para habilitar el servicio con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell o clientes individuales en la aplicación Seguridad de Windows.

Después de habilitar el servicio, debe configurar la red o el firewall para permitir conexiones entre la red y los puntos de conexión. Dado que la protección es un servicio en la nube, los equipos deben tener acceso a Internet y llegar a los servicios en la nube de Microsoft. No excluya la dirección URL `*.blob.core.windows.net` de ningún tipo de inspección de red.

> [!NOTE]
> El servicio en la nube Antivirus de Microsoft Defender ofrece protección actualizada a la red y los puntos de conexión. El servicio en la nube no debe considerarse solo como protección para los archivos almacenados en la nube; en su lugar, el servicio en la nube usa recursos distribuidos y aprendizaje automático para ofrecer protección para los puntos de conexión a una velocidad más rápida que las actualizaciones de inteligencia de seguridad tradicionales.

## <a name="services-and-urls"></a>Servicios y direcciones URL

En la tabla de esta sección se enumeran los servicios y sus direcciones url de sitio web asociadas.

Asegúrese de que no haya reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL. De lo contrario, debe crear una regla de permiso específicamente para esas direcciones URL (excepto la dirección URL `*.blob.core.windows.net`). Las direcciones URL de la tabla siguiente usan el puerto 443 para la comunicación.

<br/><br/>

|Servicio y descripción|URL|
|---|---|
|Antivirus de Microsoft Defender servicio de protección entregado en la nube se conoce como Microsoft Active Protection Service (MAPS).<p> El Antivirus de Microsoft Defender usa el servicio MAPS para proporcionar protección proporcionada en la nube.|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
|Microsoft Update Service (MU) y Windows Update Service (WU) <p>Estos servicios permitirán la inteligencia de seguridad y las actualizaciones de productos.|`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Para obtener más información, consulte [Puntos de conexión para Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Actualizaciones de inteligencia de seguridad Ubicación de descarga alternativa (ADL)<p>Esta es una ubicación alternativa para Antivirus de Microsoft Defender actualizaciones de inteligencia de seguridad, si la inteligencia de seguridad instalada está obsoleta (siete o más días de retraso).|`*.download.microsoft.com` <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
|Almacenamiento de envío de malware <p>Se trata de una ubicación de carga para los archivos enviados a Microsoft mediante el formulario de envío o el envío automático de ejemplo.|`ussus1eastprod.blob.core.windows.net` <p> `ussus2eastprod.blob.core.windows.net` <p> `ussus3eastprod.blob.core.windows.net` <p> `ussus4eastprod.blob.core.windows.net` <p> `wsus1eastprod.blob.core.windows.net` <p> `wsus2eastprod.blob.core.windows.net` <p> `ussus1westprod.blob.core.windows.net` <p> `ussus2westprod.blob.core.windows.net` <p> `ussus3westprod.blob.core.windows.net` <p> `ussus4westprod.blob.core.windows.net` <p> `wsus1westprod.blob.core.windows.net` <p> `wsus2westprod.blob.core.windows.net` <p> `usseu1northprod.blob.core.windows.net` <p> `wseu1northprod.blob.core.windows.net` <p> `usseu1westprod.blob.core.windows.net` <p> `wseu1westprod.blob.core.windows.net` <p> `ussuk1southprod.blob.core.windows.net` <p> `wsuk1southprod.blob.core.windows.net` <p> `ussuk1westprod.blob.core.windows.net` <p> `wsuk1westprod.blob.core.windows.net`|
|Lista de revocación de certificados (CRL) <p> Windows usar esta lista al crear la conexión SSL a MAPS para actualizar la CRL.|`http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p> `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs`|
|Almacén de símbolos <p>Antivirus de Microsoft Defender usar el Almacén de símbolos para restaurar determinados archivos críticos durante los flujos de corrección.|`https://msdl.microsoft.com/download/symbols`|
|Cliente de RGPD universal <p> Windows usar este cliente para enviar los datos de diagnóstico del cliente. <p> Antivirus de Microsoft Defender usa el Reglamento general de protección de datos con fines de calidad y supervisión del producto.|La actualización usa SSL (puerto TCP 443) para descargar manifiestos y cargar datos de diagnóstico en Microsoft que usa los siguientes puntos de conexión DNS: <p> `vortex-win.data.microsoft.com` <p> `settings-win.data.microsoft.com`|


## <a name="validate-connections-between-your-network-and-the-cloud"></a>Validación de conexiones entre la red y la nube

Después de permitir las direcciones URL enumeradas, compruebe si está conectado al servicio en la nube de Antivirus de Microsoft Defender. Pruebe que las direcciones URL notifican y reciben información correctamente para asegurarse de que está totalmente protegido.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Uso de la herramienta cmdline para validar la protección entregada en la nube

Use el argumento siguiente con la utilidad de línea de comandos Antivirus de Microsoft Defender (`mpcmdrun.exe`) para comprobar que la red puede comunicarse con el servicio en la nube de Antivirus de Microsoft Defender:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Abra una ventana de Símbolo de sistema como administrador. Haga clic con el botón derecho en el elemento en el menú **Inicio** , haga clic en **Ejecutar como administrador** y haga clic en **Sí** en el símbolo del sistema de permisos. Este comando solo funcionará en Windows 10, versión 1703 o posterior, o Windows 11.

Para obtener más información, vea [Administrar Antivirus de Microsoft Defender con la herramienta de línea de comandos mpcmdrun.exe](command-line-arguments-microsoft-defender-antivirus.md).

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Intento de descargar un archivo de malware falso de Microsoft

Puede descargar un archivo de ejemplo que Antivirus de Microsoft Defender detectará y bloqueará si está conectado correctamente a la nube. Visite [https://aka.ms/ioavtest](https://aka.ms/ioavtest) para descargar el archivo.

> [!NOTE]
> El archivo descargado no es exactamente malware. Es un archivo falso diseñado para probar si está conectado correctamente a la nube.

Si está conectado correctamente, verá una advertencia Antivirus de Microsoft Defender notificación.

Si usa Microsoft Edge, también verá un mensaje de notificación:

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="La notificación de que se encontró malware en Edge" lightbox="../../media/wdav-bafs-edge.png":::

Se produce un mensaje similar si usa Internet Explorer:

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="La notificación del antivirus de Microsoft Defender de que se encontró malware" lightbox="../../media/wdav-bafs-ie.png":::

#### <a name="view-the-fake-malware-detection-in-your-windows-security-app"></a>Visualización de la detección de malware falso en la aplicación Seguridad de Windows

1. En la barra de tareas, seleccione el icono de Escudo y abra la aplicación **Seguridad de Windows**. O bien, busque **en Start** for Security (Iniciar por *seguridad).*

2. Seleccione **Virus & protección contra amenazas** y, a continuación, seleccione **Historial de protección**.

3. En la sección **Amenazas en cuarentena** , seleccione **Ver historial completo** para ver el malware falso detectado.

   > [!NOTE]
   > Las versiones de Windows 10 anteriores a la versión 1703 tienen una interfaz de usuario diferente. Consulte [Antivirus de Microsoft Defender en la aplicación de Seguridad de Windows](microsoft-defender-security-center-antivirus.md).

   El registro de eventos Windows también mostrará [Windows Defender identificador de evento de cliente 1116](troubleshoot-microsoft-defender-antivirus.md).

    > [!TIP]
    > Si busca información relacionada con antivirus para otras plataformas, consulte:
    > - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
    > - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
    > - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
    > - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
    > - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
    > - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
    > - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)


## <a name="see-also"></a>Vea también

- [Configuración del proxy de dispositivo y la conectividad a Internet para Microsoft Defender para punto de conexión](configure-proxy-internet.md)
- [Use directiva de grupo configuración para configurar y administrar Antivirus de Microsoft Defender](use-group-policy-microsoft-defender-antivirus.md)
- [Cambios importantes en el punto de conexión de Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 