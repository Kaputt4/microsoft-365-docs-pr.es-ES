---
title: Ejecutar y personalizar exámenes a petición en Antivirus de Microsoft Defender
description: Ejecutar y configurar exámenes a petición con PowerShell, Windows Management Instrumentation o individualmente en puntos de conexión con la Seguridad de Windows aplicación
keywords: análisis, a petición, dos, intune, examen instantáneo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878813"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede ejecutar un examen a petición en puntos de conexión individuales. Estos exámenes se iniciarán inmediatamente y puede definir parámetros para el examen, como la ubicación o el tipo. Al ejecutar un examen, puede elegir entre tres tipos: Examen rápido, examen completo y examen personalizado. En la mayoría de los casos, use un examen rápido. Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio Windows de inicio. 

Combinado con la protección siempre activa y en tiempo real, que revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una protección segura contra malware que comienza con el malware del sistema y el nivel de kernel. En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para exámenes programados o a petición.  [Obtenga más información sobre los tipos de examen](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).

> [!IMPORTANT]
> Antivirus de Microsoft Defender se ejecuta en el contexto de la cuenta [LocalSystem](/windows/win32/services/localsystem-account) al realizar un examen local. Para los exámenes de red, usa el contexto de la cuenta del dispositivo. Si la cuenta de dispositivo de dominio no tiene los permisos adecuados para acceder al recurso compartido, el examen no funcionará. Asegúrese de que el dispositivo tiene permisos para el recurso compartido de red de acceso.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Usar Microsoft Endpoint Manager para ejecutar un examen

1. Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Elija **Endpoint security**  >  **Antivirus**.

3. En la lista de pestañas, **seleccione Windows 10 extremos en mal estado.**

4. En la lista de acciones proporcionadas, seleccione **Examen rápido** (recomendado) o **Examen completo**.

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Para obtener más información acerca del Microsoft Endpoint Manager para ejecutar un examen, vea [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Usar la utilidad mpcmdrun.exe línea de comandos para ejecutar un examen

Use el parámetro `-scan` siguiente:

```console
mpcmdrun.exe -scan -scantype 1
```

Para obtener más información acerca de cómo usar la herramienta y los parámetros adicionales, incluido el inicio de un examen completo o la definición de rutas de acceso, vea Usar la herramienta de línea de comandos mpcmdrun.exe para configurar y administrar [Antivirus de Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).

## <a name="use-microsoft-intune-to-run-a-scan"></a>Usar Microsoft Intune para ejecutar un examen

1. Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. En la barra lateral, selecciona  >  **Dispositivos todos los dispositivos** y elige el dispositivo que quieras examinar.

3. Seleccione **... Más**. En las opciones, **seleccione Examen rápido** (recomendado) o Examen **completo**.

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Usar la Seguridad de Windows para ejecutar un examen

Consulta [Ejecutar un examen en la aplicación Seguridad de Windows para](microsoft-defender-security-center-antivirus.md) obtener instrucciones sobre cómo ejecutar un examen en puntos de conexión individuales.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Usar cmdlets de PowerShell para ejecutar un examen

Use el siguiente cmdlet:

```PowerShell
Start-MpScan
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Usar Windows de administración de documentos (WMI) para ejecutar un examen

Use el [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) de la **MSFT_MpScan** clase.

Para obtener más información acerca de los parámetros permitidos, [vea Windows Defender API de WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

