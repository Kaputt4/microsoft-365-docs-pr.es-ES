---
title: Escenarios de modo de solución de problemas en Microsoft Defender para punto de conexión
description: Use el Microsoft Defender para punto de conexión modo de solución de problemas para solucionar diversos problemas antivirus.
keywords: antivirus, solución de problemas, modo de solución de problemas, protección contra alteraciones, compatibilidad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 87f73410cfe5eef6d6e161f1943d5af3737cc087
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227358"
---
# <a name="troubleshooting-mode-scenarios-in-microsoft-defender-for-endpoint"></a>Escenarios de modo de solución de problemas en Microsoft Defender para punto de conexión 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Microsoft Defender para punto de conexión modo de solución de problemas le permite solucionar problemas de varias características Microsoft Defender Antivirus al habilitarlas desde el dispositivo y probar diferentes escenarios, incluso si están controladas por la directiva de la organización. El modo de solución de problemas está deshabilitado de forma predeterminada y requiere que lo active para un dispositivo (o grupo de dispositivos) durante un tiempo limitado. Tenga en cuenta que se trata exclusivamente de una característica de solo empresa y requiere Microsoft 365 Defender acceso.

## <a name="scenario-1-unable-to-install-application"></a>Escenario 1: No se puede instalar la aplicación

Si desea instalar una aplicación pero recibe un mensaje de error que indica que Microsoft Defender Antivirus y la protección contra alteraciones están activadas, siga los pasos que se indican a continuación para solucionar el problema.

1. Solicite al administrador de seguridad que active el modo de solución de problemas. Recibirá una notificación Seguridad de Windows una vez que se inicie el modo de solución de problemas.  

2. Conéctese al dispositivo (por ejemplo, mediante Terminal Services) con permisos de administrador local.  

3. Iniciar monitor de procesos (ProcMon). Consulte los pasos descritos en [Solución de problemas de rendimiento relacionados con la protección en tiempo real](troubleshoot-performance-issues.md).  

4. Vaya a **Seguridad** >  de Windows **Protección contra amenazas & virus** > **Administrar configuración** > **Protección** >  contra alteraciones **desactivada**.  

5. Inicie un símbolo del sistema de PowerShell con privilegios elevados y desactive RTP. 

    - Ejecute `Get-MpComputerStatus` para comprobar el estado RealTimeProtection.
    - Ejecute `Set-mppreference -DisableRealtimeMonitoring $true` para desactivar RTP.
    - Vuelva a ejecutar `Get-MpComputerStatus` para comprobar el estado RealTimeProtection.

6. Intente instalar la aplicación.

## <a name="scenario-2-high-cpu-usage-due-to-windows-defender-msmpengexe"></a>Escenario 2: Uso elevado de CPU debido a Windows Defender (MsMpEng.exe)

A veces, durante un examen programado, MsMpEng.exe puede consumir una CPU elevada.

1. Vaya a la pestaña **Detalles** **del Administrador** >  de tareas para confirmar que MsMpEng.exe es el motivo del uso elevado de cpu. Compruebe también si hay un examen programado en curso.

2. Ejecute ProcMon durante el pico de CPU durante unos 5 minutos y, a continuación, revise el registro de ProcMon para obtener pistas. 

3. Una vez determinada la causa principal, active el modo de solución de problemas. 

4. Inicie sesión en la máquina e inicie un símbolo del sistema de PowerShell con privilegios elevados. 

5. Agregue exclusiones de proceso, archivo, carpeta o extensión en función de los resultados de ProcMon mediante uno de los siguientes comandos (la ruta de acceso, la extensión y las exclusiones de procesos que se mencionan a continuación son solo ejemplos): 

    - `Set-mppreference -ExclusionPath` (por ejemplo, C:\DB\DataFiles) 
    
    - `Set-mppreference –ExclusionExtension` (por ejemplo, .dbx) 
    
    - `Set-mppreference –ExclusionProcess` (por ejemplo, C:\DB\Bin\Convertdb.exe) 

6. Después de agregar la exclusión, compruebe si se ha quitado el uso de CPU. 

Para obtener más información sobre Set-MpPreference preferencias de configuración de cmdlets para exámenes y actualizaciones de Windows Defender, consulte [Set-MpPreference](/powershell/module/defender/set-mppreference). 

## <a name="scenario-3-application-taking-longer-to-perform-an-action"></a>Escenario 3: La aplicación tarda más en realizar una acción

Cuando Microsoft Defender protección antivirus en tiempo real está activada, la aplicación tarda mucho tiempo en realizar tareas básicas. Para desactivar la protección en tiempo real y solucionar el problema, siga estos pasos. 

1. Solicite al administrador de seguridad que active el modo de solución de problemas en el dispositivo. 

2. Para deshabilitar RTP para este escenario, primero desactive la protección contra alteraciones. Para obtener más información, consulte [Protección de la configuración de seguridad con protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md). 

3. Una vez deshabilitada la protección contra alteraciones, inicie sesión en el dispositivo. 

4. Inicie un símbolo del sistema de PowerShell con privilegios elevados. 

    - `Set-mppreference -DisableRealtimeMonitoring $true` 

5. Después de deshabilitar RTP, compruebe si la aplicación es lenta. 

## <a name="scenario-4-microsoft-office-plugin-blocked-by-attack-surface-reduction"></a>Escenario 4: Complemento de Microsoft Office bloqueado por reducción de superficie expuesta a ataques

La reducción de superficie expuesta a ataques (ASR) no permite que el complemento de Microsoft Office funcione correctamente, ya que **impedir que todas las aplicaciones de Office creen procesos secundarios** está establecido en modo de bloque. 

1. Active el modo de solución de problemas e inicie sesión en el dispositivo. 

2. Inicie un símbolo del sistema de PowerShell con privilegios elevados. 

    - `Set-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EFC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Disabled` 

3. Después de deshabilitar la regla ASR, confirme que el complemento de Microsoft Office ahora funciona.

Para obtener más información, consulte [Introducción a la reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md). 

## <a name="scenario-5-domain-blocked-by-network-protection"></a>Escenario 5: Dominio bloqueado por Network Protection

Network Protection bloquea el dominio de Microsoft, lo que impide que los usuarios accedan a él. 

1. Active el modo de solución de problemas e inicie sesión en el dispositivo. 

2. Inicie un símbolo del sistema de PowerShell con privilegios elevados. 

    - `Set-MpPreference -EnableNetworkProtection Disabled` 

3. Después de deshabilitar Protección de red, compruebe si el dominio ahora está permitido. 

Para obtener más información, consulte [Uso de la protección de red para ayudar a evitar las conexiones a sitios incorrectos](network-protection.md). 

## <a name="related-topics"></a>Temas relacionados

- [Habilitación del modo de solución de problemas](enable-troubleshooting-mode.md)
- [Configuración de seguridad de la protección con protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)
- [Set-MpPreference](/powershell/module/defender/set-mppreference)
- [Proteger la red](network-protection.md)
- [Introducción a la reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)
- [Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [Obtener información general de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- [Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md)
