---
title: Ejecutar y personalizar exámenes a petición en Microsoft Defender AV
description: Ejecutar y configurar exámenes a petición con PowerShell, Instrumental de administración de Windows o individualmente en puntos de conexión con la aplicación Seguridad de Windows
keywords: análisis, a petición, dos, intune, examen instantáneo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691175"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Configurar y ejecutar exámenes de Antivirus de Microsoft Defender a petición

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede ejecutar un examen a petición en puntos de conexión individuales. Estos exámenes se iniciarán inmediatamente y puede definir parámetros para el examen, como la ubicación o el tipo.

## <a name="quick-scan-versus-full-scan"></a>Examen rápido frente a examen completo

El examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio conocidas de Windows.

> [!IMPORTANT]
> Antivirus de Microsoft Defender se ejecuta en el contexto de la cuenta [LocalSystem](/windows/win32/services/localsystem-account) al realizar un examen local. Para los exámenes de red, usa el contexto de la cuenta del dispositivo. Si la cuenta de dispositivo de dominio no tiene los permisos adecuados para acceder al recurso compartido, el examen no funcionará. Asegúrese de que el dispositivo tiene permisos para el recurso compartido de red de acceso.

Combinado con la funcionalidad de protección siempre activa en tiempo [real](configure-real-time-protection-microsoft-defender-antivirus.md)(que revisa los archivos cuando se abren y cierran y cuando un usuario navega a una carpeta), un examen rápido ayuda a proporcionar una cobertura segura tanto para malware que comienza con el malware del sistema como del nivel de kernel.  

En la mayoría de los casos, un examen rápido es adecuado para encontrar malware que no fue recogido por la protección en tiempo real.

Un examen completo puede ser útil en puntos de conexión que han notificado una amenaza de malware. El examen puede identificar si hay componentes inactivos que requieren una limpieza más exhaustiva. Esto es ideal si su organización está ejecutando exámenes a petición.

> [!NOTE]
> De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Usar Microsoft Endpoint Manager para ejecutar un examen

1. Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.
2. Elija **Endpoint security**  >  **Antivirus**.
3. En la lista de pestañas, selecciona Puntos de conexión en mal estado de **Windows 10.**
4. En la lista de acciones proporcionadas, seleccione **Examen rápido** o **Examen completo.**

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Para obtener más información acerca del uso de Microsoft Endpoint Manager para ejecutar un examen, vea [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Usar la utilidad mpcmdrun.exe línea de comandos para ejecutar un examen

Use el parámetro `-scan` siguiente:

```console
mpcmdrun.exe -scan -scantype 1
```

Para obtener más información acerca de cómo usar la herramienta y los parámetros adicionales, como iniciar un examen completo o definir rutas de acceso, vea Usar la herramienta de línea de comandos mpcmdrun.exe para configurar y administrar Antivirus de [Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).

## <a name="use-microsoft-intune-to-run-a-scan"></a>Usar Microsoft Intune para ejecutar un examen

1. Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.
2. En la barra lateral, selecciona **Dispositivos > Todos** los dispositivos y elige el dispositivo que quieras examinar.
3. Seleccione **... Más**. En las opciones, seleccione **Examen rápido** o **Examen completo**.

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Usar la aplicación Seguridad de Windows para ejecutar un examen

Consulta [Ejecutar un examen en la aplicación seguridad de Windows](microsoft-defender-security-center-antivirus.md) para obtener instrucciones sobre cómo ejecutar un examen en puntos de conexión individuales.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Usar cmdlets de PowerShell para ejecutar un examen

Use el siguiente cmdlet:

```PowerShell
Start-MpScan
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Usar Windows Management Instruction (WMI) para ejecutar un examen

Use el [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) de la **MSFT_MpScan** clase.

Para obtener más información acerca de los parámetros permitidos, [vea Windows Defender API de WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Artículos relacionados

- [Configurar opciones de análisis de Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configurar exámenes programados de Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)