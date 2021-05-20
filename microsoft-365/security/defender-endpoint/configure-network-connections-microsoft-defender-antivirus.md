---
title: Configurar y validar las conexiones de red del Antivirus de Windows Defender
description: Configure y pruebe la conexión al servicio de protección en la nube Antivirus de Microsoft Defender.
keywords: antivirus, Antivirus de Microsoft Defender, antimalware, seguridad, defensor, nube, agresividad, nivel de protección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572530"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurar y validar las conexiones de red del Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Para asegurarse de que Antivirus de Microsoft Defender protección entregada en la nube funciona correctamente, debe configurar la red para permitir conexiones entre los puntos de conexión y determinados servidores de Microsoft. En este artículo se enumeran las conexiones permitidas, por ejemplo, mediante reglas de firewall y se proporcionan instrucciones para validar la conexión. Configurar la protección correctamente ayuda a garantizar que reciba el mejor valor de sus servicios de protección entregados en la nube.

Consulte la entrada de blog [Cambios importantes en el punto de conexión de Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) para obtener más información sobre la conectividad de red.

> [!TIP]
> También puede visitar el sitio web de demostración de Microsoft Defender for Endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las siguientes características funcionan:
>
> - Protección entregada en la nube
> - Aprendizaje rápido (incluyendo bloqueo a primera vista)
> - Bloqueo de aplicaciones potencialmente no deseados

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Permitir conexiones al servicio en la nube Antivirus de Microsoft Defender

El servicio en la nube de Antivirus de Microsoft Defender proporciona una protección rápida y sólida para los puntos de conexión. Habilitar el servicio de protección entregado en la nube es opcional, sin embargo, es muy recomendable porque proporciona una protección importante contra el malware en los puntos de conexión y en toda la red.

> [!NOTE]
> El servicio en la nube Antivirus de Microsoft Defender es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión. Aunque se llama servicio en la nube, no es simplemente protección para archivos almacenados en la nube, sino que utiliza recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a un ritmo mucho más rápido que las actualizaciones de inteligencia de seguridad tradicionales.

Consulte [Habilitar la protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) para obtener más información sobre cómo habilitar el servicio con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell o en clientes individuales de la aplicación Seguridad de Windows. 

Después de habilitar el servicio, es posible que deba configurar la red o el firewall para permitir conexiones entre él y los puntos de conexión.

Dado que la protección es un servicio en la nube, los equipos deben tener acceso a Internet y llegar a Microsoft Defender para obtener Office 365 servicios de aprendizaje automático. No excluya la dirección URL `*.blob.core.windows.net` de ningún tipo de inspección de red. 

En la tabla siguiente se enumeran los servicios y sus direcciones URL asociadas. Asegúrese de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL, o es posible que deba crear una regla de permiso específicamente para ellas (excluyendo la dirección `*.blob.core.windows.net` URL). A continuación se menciona que las DIRECCIONES URL utilizan el puerto 443 para la comunicación.


| **Servicio**| **Descripción** |**URL** |
| :--: | :-- | :-- |
| Antivirus de Microsoft Defender servicio de protección entregado en la nube, también denominado Microsoft Active Protection Service (MAPS)|Utilizado por Antivirus de Microsoft Defender para proporcionar protección suministrada por la nube|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Servicio microsoft update (MU) <br/> Windows Servicio de actualización (WU)|  Inteligencia de seguridad y actualizaciones de productos   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Para obtener más información, consulte [Puntos de conexión para Windows Actualizar](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Inteligencia de seguridad actualiza la ubicación de descarga alternativa (ADL)|   Ubicación alternativa para Antivirus de Microsoft Defender actualizaciones de inteligencia de seguridad si la inteligencia de seguridad instalada está desactualizada (7 o más días después)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Almacenamiento de envío de malware|Upload ubicación de los archivos enviados a Microsoft a través del formulario de envío o envío automático de ejemplos    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Lista de revocación de certificados (CRL)|Utilizado por Windows al crear la conexión SSL a MAPS para actualizar el CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Tienda de símbolos|Utilizado por Antivirus de Microsoft Defender para restaurar ciertos archivos críticos durante los flujos de corrección  | `https://msdl.microsoft.com/download/symbols` |
| Cliente universal de telemetría| Utilizado por Windows para enviar datos de diagnóstico de cliente; Antivirus de Microsoft Defender utiliza telemetría para fines de monitoreo de la calidad del producto   | La actualización utiliza SSL (puerto TCP 443) para descargar manifiestos y cargar datos de diagnóstico en Microsoft que utiliza los siguientes puntos de conexión DNS:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Valide las conexiones entre la red y la nube

Después de permitir las DIRECCIONES URL enumeradas anteriormente, puede probar si está conectado al servicio en la nube Antivirus de Microsoft Defender y está informando y recibiendo información correctamente para asegurarse de que está totalmente protegido.

**Utilice la herramienta cmdline para validar la protección entregada en la nube:**

Utilice el siguiente argumento con la utilidad de línea de comandos Antivirus de Microsoft Defender ( `mpcmdrun.exe` ) para comprobar que la red puede comunicarse con el servicio en la nube Antivirus de Microsoft Defender:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Debe abrir una versión de nivel de administrador del símbolo del sistema. Haga clic con el botón derecho en el elemento en el menú Inicio, haga clic en **Ejecutar como administrador** y haga clic en **Sí** en la solicitud de permisos. Este comando solo funcionará en Windows 10, versión 1703 o superior.

Para obtener más información, consulte [Administrar Antivirus de Microsoft Defender con la herramienta de línea de comandos mpcmdrun.exe](command-line-arguments-microsoft-defender-antivirus.md).

**Intente descargar un archivo de malware falso de Microsoft:**

Puede descargar un archivo de ejemplo que Antivirus de Microsoft Defender detectará y bloqueará si está conectado correctamente a la nube.

Descargue el archivo visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Este archivo no es una pieza real de malware. Es un archivo falso que está diseñado para probar si está conectado correctamente a la nube.

Si estás conectado correctamente, verás una notificación de advertencia Antivirus de Microsoft Defender.

Si usas Microsoft Edge, también verás un mensaje de notificación:

![Microsoft Edge informar al usuario que se encontró malware](images/defender/wdav-bafs-edge.png)

Se produce un mensaje similar si usa Internet Explorer:

![Antivirus de Microsoft Defender notificación informando al usuario que se encontró malware](images/defender/wdav-bafs-ie.png)

También verás una detección en Amenazas en **cuarentena** en la sección **Historial de análisis** de la aplicación Seguridad de Windows:

1. Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo en la barra de tareas o buscando en el menú inicio **de Seguridad**.

2. Seleccione **Virus & protección contra amenazas** y, a continuación, seleccione Historial de **protección**.

3. En la sección **Amenazas en cuarentena,** seleccione **Ver historial completo** para ver el malware falso detectado.

   > [!NOTE]
   > Las versiones de Windows 10 antes de la versión 1703 tienen una interfaz de usuario diferente. Consulte [Antivirus de Microsoft Defender en la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).

   El registro de eventos Windows también mostrará [Windows Defender identificador de evento de cliente 1116](troubleshoot-microsoft-defender-antivirus.md).

## <a name="related-articles"></a>Artículos relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Argumentos de línea de comandos](command-line-arguments-microsoft-defender-antivirus.md)

- [Cambios importantes en el punto de conexión de Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
