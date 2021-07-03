---
title: Configurar y validar las conexiones de red del Antivirus de Windows Defender
description: Configure y pruebe la conexión con el servicio Antivirus de Microsoft Defender de protección en la nube.
keywords: antivirus, Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, agresividad, nivel de protección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 5b6ed22b38d0795073fc72f380bcad89683ada9c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286818"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurar y validar las conexiones de red del Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Para garantizar Antivirus de Microsoft Defender protección entregada en la nube funciona correctamente, el equipo de seguridad debe configurar la red para permitir conexiones entre los puntos de conexión y determinados servidores de Microsoft. En este artículo se enumeran las conexiones que se deben permitir, como mediante reglas de firewall, y se proporcionan instrucciones para validar la conexión. La configuración correcta de la protección ayuda a garantizar que recibe el mejor valor de los servicios de protección entregados en la nube.

Consulta la entrada de blog [Cambios importantes en el punto](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) de conexión de Microsoft Active Protection Services para obtener algunos detalles sobre la conectividad de red.

> [!TIP]
> Visite el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que funcionan las siguientes características:
>
> - Protección entregada en la nube
> - Aprendizaje rápido (incluido el bloqueo a primera vista)
> - Bloqueo de aplicaciones potencialmente no deseado

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Permitir conexiones al servicio Antivirus de Microsoft Defender nube

El Antivirus de Microsoft Defender nube proporciona una protección rápida y segura para los puntos de conexión. Habilitar el servicio de protección entregado en la nube es opcional, pero es muy recomendable porque proporciona protección importante contra malware en los puntos de conexión y en toda la red. Consulte [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) para obtener más información sobre cómo habilitar el servicio con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell o en clientes individuales en la Seguridad de Windows aplicación. 

Después de habilitar el servicio, es posible que deba configurar la red o firewall para permitir conexiones entre él y los puntos de conexión. Dado que la protección es un servicio en la nube, los equipos deben tener acceso a Internet y llegar a Microsoft Defender para obtener Office 365 aprendizaje automático. No excluya la dirección URL `*.blob.core.windows.net` de ningún tipo de inspección de red.

> [!NOTE]
> El Antivirus de Microsoft Defender en la nube es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión. Aunque se denomina servicio en la nube, no es simplemente protección para los archivos almacenados en la nube, sino que usa recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a una velocidad mucho más rápida que las actualizaciones de inteligencia de seguridad tradicionales.

## <a name="services-and-urls"></a>Servicios y direcciones URL

En la tabla de esta sección se enumeran los servicios y sus direcciones de sitio web asociadas (DIRECCIONES URL). 

Asegúrese de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL. De lo contrario, es posible que deba crear una regla de permitir específicamente para ellos (excluyendo la dirección `*.blob.core.windows.net` URL). Las direcciones URL de la tabla siguiente usan el puerto 443 para la comunicación.

| Servicio y descripción | URL |
|----|---- |
| Antivirus de Microsoft Defender servicio de protección entregado en la nube, también denominado Microsoft Active Protection Service (MAPS)<p>Este servicio lo usa Antivirus de Microsoft Defender para proporcionar protección entregada en la nube|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) y Windows Update Service (WU) <p>Estos servicios permiten la inteligencia de seguridad y las actualizaciones de productos |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Para obtener más información, consulte [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Actualizaciones de inteligencia de seguridad Ubicación alternativa de descarga (ADL)<p>Esta es una ubicación alternativa para las Antivirus de Microsoft Defender de inteligencia de seguridad si la inteligencia de seguridad instalada está des actualizada (7 o más días después)| `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Almacenamiento de envío de malware <p>Esta es la ubicación de carga de los archivos enviados a Microsoft mediante el formulario de envío o el envío automático de muestra | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| Lista de revocación de certificados (CRL) <p>Esta lista la usa Windows al crear la conexión SSL a MAPS para actualizar la CRL | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| Almacén de símbolos <p>El almacén de símbolos lo usa Antivirus de Microsoft Defender restaurar ciertos archivos críticos durante los flujos de corrección | `https://msdl.microsoft.com/download/symbols` |
| Cliente de telemetría universal <p>Este cliente lo usa Windows para enviar datos de diagnóstico de cliente<p> Antivirus de Microsoft Defender telemetría con fines de supervisión de la calidad del producto | La actualización usa SSL (puerto TCP 443) para descargar manifiestos y cargar datos de diagnóstico en Microsoft que usa los siguientes extremos DNS: <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Validar conexiones entre la red y la nube

Después de permitir las direcciones URL enumeradas anteriormente, puede probar si está conectado al servicio en la nube de Antivirus de Microsoft Defender y está informando y recibiendo información correctamente para asegurarse de que está totalmente protegido.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Usar la herramienta cmdline para validar la protección entregada en la nube

Use el siguiente argumento con la Antivirus de Microsoft Defender de línea de comandos ( ) para comprobar que la red se puede comunicar con el servicio Antivirus de Microsoft Defender `mpcmdrun.exe` nube:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Debe abrir una versión de nivel de administrador del símbolo del sistema. Haga clic con el botón secundario en el elemento de la menú Inicio, haga clic en **Ejecutar como administrador** y haga clic en **Sí** en el símbolo del sistema de permisos. Este comando solo funcionará en Windows 10 versión 1703 o posterior.

Para obtener más información, vea [Manage Antivirus de Microsoft Defender with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Intentar descargar un archivo de malware falso de Microsoft

Puede descargar un archivo de ejemplo que Antivirus de Microsoft Defender detectará y bloqueará si está conectado correctamente a la nube.

Descargue el archivo visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Este archivo no es una parte real de malware. Es un archivo falso que está diseñado para probar si estás conectado correctamente a la nube.

Si está conectado correctamente, verá una notificación de Antivirus de Microsoft Defender advertencia.

Si usas Microsoft Edge, también verás un mensaje de notificación:

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Captura de pantalla de notificación de que se encontró malware en Edge":::

Si usa Internet Explorer, se produce un mensaje similar:

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="Notificación antivirus de Microsoft Defender de que se encontró malware":::

También verás una detección en Amenazas en cuarentena **en** **la** sección Historial de análisis de la Seguridad de Windows aplicación:

1. Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio **seguridad**.

2. Seleccione **Protección contra & virus y,** a continuación, seleccione Historial de **protección**.

3. En la **sección Amenazas en** cuarentena, seleccione Ver historial **completo** para ver el malware falso detectado.

   > [!NOTE]
   > Las versiones Windows 10 versiones anteriores a la 1703 tienen una interfaz de usuario diferente. Consulta [Antivirus de Microsoft Defender en la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).

   El Windows de eventos también mostrará Windows Defender [identificador de evento de cliente 1116](troubleshoot-microsoft-defender-antivirus.md).
