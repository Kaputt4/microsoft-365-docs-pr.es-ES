---
title: Solución de problemas al cambiar a Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo solucionar problemas al realizar el cambio a Microsoft Defender para punto de conexión.
keywords: migración, Windows Defender, protección avanzada de puntos de conexión, antivirus, antimalware, modo pasivo, modo activo, solución de problemas
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/20/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.subservice: mde
ms.openlocfilehash: bbf10ee3881d5ff29451d5676118a79242b6f311
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67583526"
---
# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>Solución de problemas al cambiar a Microsoft Defender para punto de conexión

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En este artículo se proporciona información de solución de problemas para los administradores de seguridad que experimentan problemas al cambiar de una solución de protección de puntos de conexión que no es de Microsoft a Microsoft Defender para punto de conexión.

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Antivirus de Microsoft Defender se está desinstalando en Windows Server

Al cambiar a Defender para punto de conexión, comienza con la protección antivirus o antimalware que no es de Microsoft en modo activo. Como parte del proceso de instalación, configurará antivirus de Microsoft Defender en modo pasivo. En ocasiones, la solución antivirus o antimalware que no es de Microsoft podría impedir que el Antivirus de Microsoft Defender se ejecute en Windows Server. De hecho, puede parecer que antivirus de Microsoft Defender se ha quitado de Windows Server.

Para resolver este problema, siga estos pasos:

1. [Agregue Microsoft Defender para punto de conexión a la lista de exclusión](#add-microsoft-defender-for-endpoint-to-the-exclusion-list).
2. [Establezca Antivirus de Microsoft Defender en modo pasivo manualmente](#set-microsoft-defender-antivirus-to-passive-mode-manually).

### <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list"></a>Agregar Microsoft Defender para punto de conexión a la lista de exclusión

Ciertas exclusiones de Defender para punto de conexión deben definirse en la solución existente que no sea de Microsoft Endpoint Protection. Asegúrese de agregar las siguientes exclusiones:

`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-manually"></a>Establecer el Antivirus de Microsoft Defender en modo pasivo manualmente

En Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 o Windows Server 2012 R2, debes establecer antivirus de Microsoft Defender en modo pasivo manualmente. Esta acción ayuda a evitar problemas causados por tener varios productos antivirus instalados en un servidor. Puede establecer Antivirus de Microsoft Defender en modo pasivo mediante PowerShell, directiva de grupo o una clave del Registro.

Puede establecer antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:

Camino: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`

Nombre: `ForceDefenderPassiveMode`

Tipo: `REG_DWORD`

Valor: `1`

> [!NOTE]
> Para que el modo pasivo funcione en puntos de conexión que ejecutan Windows Server 2016 y Windows Server 2012 R2, esos puntos de conexión deben incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016).

Para obtener más información, consulte [Antivirus de Microsoft Defender en Windows](microsoft-defender-antivirus-windows.md).

## <a name="microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode"></a>Antivirus de Microsoft Defender parece estar bloqueado en modo pasivo

Si antivirus de Microsoft Defender está bloqueado en modo pasivo, establézcalo en modo activo manualmente siguiendo estos pasos:

1. En el dispositivo Windows, abra el Editor del Registro como administrador.

2. Ve a `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

3. Establezca o defina una entrada **REG_DWORD** denominada `ForceDefenderPassiveMode`y establezca su valor `0`en .

4. Reinicie el dispositivo.

> [!IMPORTANT]
> Si sigue teniendo problemas para establecer Antivirus de Microsoft Defender en modo activo después de seguir este procedimiento, [póngase en contacto con el soporte técnico](../../admin/get-help-support.md).

## <a name="i-am-having-trouble-re-enabling-microsoft-defender-antivirus-on-windows-server-2016"></a>Tengo problemas para volver a habilitar el Antivirus de Microsoft Defender en Windows Server 2016

Si usa una solución antivirus o antimalware que no es de Microsoft en Windows Server 2016, es posible que la solución existente haya requerido que el Antivirus de Microsoft Defender se deshabilite o desinstale. Puede usar la[ Utilidad de protección contra malware Command-Line](command-line-arguments-microsoft-defender-antivirus.md) para volver a habilitar antivirus de Microsoft Defender en Windows Server 2016.

1. Como administrador local en el servidor, abra el símbolo del sistema.

2. Ejecute el siguiente comando: `MpCmdRun.exe -wdenable`

3. Reinicie el dispositivo.

## <a name="see-also"></a>Vea también

- [Compatibilidad del Antivirus de Microsoft Defender con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md)

- [Incorporación de herramientas y métodos para dispositivos Windows en Defender para punto de conexión](configure-endpoints.md) 
