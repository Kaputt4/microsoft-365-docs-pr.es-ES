---
title: Solución de problemas al cambiar a Pertahanan Microsoft untuk Titik Akhir
description: Obtenga información sobre cómo solucionar problemas al cambiar a Pertahanan Microsoft untuk Titik Akhir.
keywords: migración, Windows Defender, protección avanzada de puntos de conexión, antivirus, antimalware, modo pasivo, modo activo, solución de problemas
ms.prod: m365-security
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
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 8334ce03bac5b7d4518433f83ab34d5f86e71339
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634171"
---
# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>Solución de problemas al cambiar a Pertahanan Microsoft untuk Titik Akhir

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En este artículo se proporciona información de solución de problemas para los administradores de seguridad que tienen problemas al cambiar de una solución de protección de puntos de conexión que no es de Microsoft a Pertahanan Microsoft untuk Titik Akhir.

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Antivirus de Microsoft Defender se desinstala en Windows Server

Al cambiar a Defender for Endpoint, comienza con la protección contra antivirus o antimalware que no es de Microsoft en modo activo. Como parte del proceso de configuración, puede configurar Antivirus de Microsoft Defender en modo pasivo. En ocasiones, la solución antivirus o antimalware que no es de Microsoft puede impedir que Antivirus de Microsoft Defender se ejecute en Windows Server. De hecho, puede parecer que Antivirus de Microsoft Defender se ha quitado de Windows Server.

Para resolver este problema, siga estos pasos:

1. [Agregue Pertahanan Microsoft untuk Titik Akhir a la lista de exclusión](#add-microsoft-defender-for-endpoint-to-the-exclusion-list).
2. [Establece Antivirus de Microsoft Defender en modo pasivo manualmente](#set-microsoft-defender-antivirus-to-passive-mode-manually).

### <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list"></a>Agregar Pertahanan Microsoft untuk Titik Akhir a la lista de exclusión

Determinadas exclusiones para Defender for Endpoint deben definirse en la solución de protección de puntos de conexión existente que no sea de Microsoft. Asegúrese de agregar las siguientes exclusiones:

`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-manually"></a>Establecer Antivirus de Microsoft Defender en modo pasivo manualmente

En Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 o Windows Server 2012 R2, debe establecer Antivirus de Microsoft Defender en modo pasivo manualmente. Esta acción ayuda a evitar problemas causados por tener varios productos antivirus instalados en un servidor. Puede establecer el Antivirus de Microsoft Defender en modo pasivo mediante PowerShell, directiva de grupo o una clave del Registro.

Puede establecer el Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:

Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`

Nombre: `ForceDefenderPassiveMode`

Tipo: `REG_DWORD`

Valor: `1`

> [!NOTE]
> Para que el modo pasivo funcione en puntos de conexión que ejecuten Windows Server 2016 y Windows Server 2012 R2, estos extremos deben incorporarse con las instrucciones de [Onboard Windows servers](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016).

Para obtener más información, [vea Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md).

## <a name="microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode"></a>Antivirus de Microsoft Defender parece estar atascado en modo pasivo

Si Antivirus de Microsoft Defender está atascado en modo pasivo, estadóla en modo activo manualmente siguiendo estos pasos:

1. En el Windows, abra el Editor del Registro como administrador.

2. Ve a `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

3. Establezca o defina una **REG_DWORD** llamada `ForceDefenderPassiveMode`, y establezca su valor en `0`.

4. Reinicie el dispositivo.

> [!IMPORTANT]
> Si sigues teniendo problemas para configurar Antivirus de Microsoft Defender en modo activo después de seguir este procedimiento, ponte en contacto [con el soporte técnico](../../admin/get-help-support.md).

## <a name="i-am-having-trouble-re-enabling-microsoft-defender-antivirus-on-windows-server-2016"></a>Tengo problemas para volver a habilitar Antivirus de Microsoft Defender en Windows Server 2016

Si usa una solución antivirus o antimalware que no sea de Microsoft en Windows Server 2016, es posible que la solución existente Antivirus de Microsoft Defender se deshabilite o desinstale. Puede usar la Utilidad de[ protección contra Command-Line malware](command-line-arguments-microsoft-defender-antivirus.md) para volver a habilitar Antivirus de Microsoft Defender en Windows Server 2016.

1. Como administrador local en el servidor, abra el símbolo del sistema.

2. Ejecute el siguiente comando: `MpCmdRun.exe -wdenable`

3. Reinicie el dispositivo.

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md)

- [Herramientas y métodos de incorporación para Windows dispositivos en Defender para endpoint](configure-endpoints.md) 
