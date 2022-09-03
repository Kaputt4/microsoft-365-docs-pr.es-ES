---
title: Ejecución y personalización de exámenes a petición en el Antivirus de Microsoft Defender
description: Ejecución y configuración de exámenes a petición mediante PowerShell, Instrumental de administración de Windows o individualmente en puntos de conexión con la aplicación Seguridad de Windows
keywords: examen, a petición, dos, intune, examen instantáneo
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/22/2021
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 582edcff46b6576b1e11ddff0e10cd1e1b43facb
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584559"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede ejecutar un examen a petición en puntos de conexión individuales. Estos exámenes se iniciarán inmediatamente y puede definir parámetros para el examen, como la ubicación o el tipo. Al ejecutar un examen, puede elegir entre tres tipos: examen rápido, examen completo y examen personalizado. En la mayoría de los casos, use un examen rápido. Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio conocidas de Windows.

Combinado con la protección siempre activa en tiempo real, que revisa los archivos cuando se abren y cierran, y cada vez que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una protección segura contra el malware que comienza con el sistema y el malware de nivel de kernel. En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para los exámenes programados o a petición. [Obtenga más información sobre los tipos de examen](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).

> [!IMPORTANT]
> El Antivirus de Microsoft Defender se ejecuta en el contexto de la cuenta [LocalSystem](/windows/win32/services/localsystem-account) al realizar un examen local. En el caso de los exámenes de red, usa el contexto de la cuenta de dispositivo. Si la cuenta de dispositivo de dominio no tiene los permisos adecuados para acceder al recurso compartido, el examen no funcionará. Asegúrese de que el dispositivo tiene permisos para el recurso compartido de red de acceso.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Uso de Microsoft Endpoint Manager para ejecutar un examen

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Elija **Antivirus de seguridad** \> de puntos de conexión.

3. En la lista de pestañas, seleccione **Windows 10 puntos de conexión incorrectos** o **Windows 11 puntos de conexión incorrectos**.

4. En la lista de acciones proporcionadas, seleccione **Examen rápido** (recomendado) o **Examen completo**.

   [![Opciones de examen en la pestaña Windows 10 puntos de conexión incorrectos.](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Para obtener más información sobre el uso de Microsoft Endpoint Manager para ejecutar un examen, consulte [Tareas antimalware y firewall: Cómo realizar un examen a petición](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Uso de la utilidad de línea de comandos mpcmdrun.exe para ejecutar un examen

Use el parámetro siguiente `-scan` :

```console
mpcmdrun.exe -scan -scantype 1
```

Para obtener más información sobre cómo usar la herramienta y parámetros adicionales, como iniciar un examen completo o definir rutas de acceso, consulte [Uso de la herramienta de línea de comandos mpcmdrun.exe para configurar y administrar antivirus de Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).

## <a name="use-microsoft-intune-to-run-a-scan"></a>Uso de Microsoft Intune para ejecutar un examen

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. En la barra lateral, seleccione **Dispositivos** \> **todos los dispositivos** y elija el dispositivo que desea examinar.

3. Seleccione **... Más**. En las opciones, seleccione **Examen rápido** (recomendado) o **Examen completo**.

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Uso de la aplicación Seguridad de Windows para ejecutar un examen

Consulte [Ejecución de un examen en la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md) para obtener instrucciones sobre cómo ejecutar un examen en puntos de conexión individuales.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Uso de cmdlets de PowerShell para ejecutar un examen

Use el siguiente cmdlet:

```PowerShell
Start-MpScan
```

Para obtener más información sobre cómo usar PowerShell con el Antivirus de Microsoft Defender, consulte [Uso de cmdlets de PowerShell para configurar y ejecutar antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Antivirus de Defender](/powershell/module/defender/).

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Uso de Instrucciones de administración de Windows (WMI) para ejecutar un examen

Use el [método **Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) de la clase **MSFT_MpScan**.

Para obtener más información sobre qué parámetros se permiten, consulte [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)