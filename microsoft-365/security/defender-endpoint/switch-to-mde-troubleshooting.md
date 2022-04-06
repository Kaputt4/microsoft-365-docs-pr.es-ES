---
title: Solución de problemas al cambiar a Microsoft Defender para endpoint
description: Obtenga información sobre cómo solucionar problemas al cambiar a Microsoft Defender para endpoint.
keywords: 'migración, Windows Defender, protección avanzada de puntos de conexión, antivirus, antimalware, modo pasivo, modo activo, solución de problemas'
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
ms.date: 01/11/2022
ms.reviewer: 'jesquive, chventou, jonix, chriggs, owtho'
ms.technology: mde
---

# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>Solución de problemas al cambiar a Microsoft Defender para endpoint

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En este artículo se proporciona información de solución de problemas para los administradores de seguridad que tienen problemas al cambiar de una solución de protección de extremo que no es de Microsoft a Microsoft Defender para endpoint.

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Antivirus de Microsoft Defender se desinstala en Windows Server

Al cambiar a Defender for Endpoint, comienza con la protección contra antivirus o antimalware que no es de Microsoft en modo activo. Como parte del proceso de configuración, puede configurar Antivirus de Microsoft Defender en modo pasivo. En ocasiones, la solución antivirus o antimalware que no es de Microsoft puede impedir que Antivirus de Microsoft Defender se ejecute en Windows Server. De hecho, puede parecer que Antivirus de Microsoft Defender se ha quitado de Windows Server.

Para resolver este problema, siga estos pasos:

1. [Establezca la clave del Registro DisableAntiSpyware en false](#set-the-disableantispyware-registry-key-to-false).
2. [Agregue Microsoft Defender para endpoint a la lista de exclusión](#add-microsoft-defender-for-endpoint-to-the-exclusion-list).
3. [Establece Antivirus de Microsoft Defender en modo pasivo manualmente](#set-microsoft-defender-antivirus-to-passive-mode-manually).

### <a name="set-the-disableantispyware-registry-key-to-false"></a>Establecer la clave del Registro DisableAntiSpyware en false

La [clave del Registro DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) se usó en el pasado para deshabilitar Antivirus de Microsoft Defender e implementar otro producto antivirus, como McAfee, Symantec u otros. **En general,** no debe tener esta clave del Registro en los dispositivos y puntos de conexión de Windows; sin embargo,  `DisableAntiSpyware` si lo ha configurado, este es el modo de establecer su valor en false:

1. En el Windows servidor, abra el Editor del Registro.

2. Vaya a `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. En esa carpeta, busque una entrada DWORD denominada **DisableAntiSpyware**.
   - Si no ve esa entrada, está todo establecido.
   - Si ve **DisableAntiSpyware**, vaya al paso 4.

4. Haga clic con el botón secundario en el DWORD DisableAntiSpyware y, a continuación, elija **Modificar**.

5. Establezca el valor en `0`. (Esta acción establece el valor de la clave del Registro en *false*).

> [!TIP]
> Para obtener más información sobre esta clave del Registro, [vea DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list"></a>Agregar Microsoft Defender para endpoint a la lista de exclusión

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

## <a name="i-am-having-trouble-re-enabling-microsoft-defender-antivirus-on-windows-server-2016"></a>Tengo problemas para volver a habilitar Antivirus de Microsoft Defender en Windows Server 2016

Si usa una solución antivirus o antimalware que no sea de Microsoft en Windows Server 2016, es posible que la solución existente Antivirus de Microsoft Defender se deshabilite o desinstale. Puede usar la Utilidad de[ protección contra Command-Line malware](command-line-arguments-microsoft-defender-antivirus.md) para volver a habilitar Antivirus de Microsoft Defender en Windows Server 2016.

1. Como administrador local en el servidor, abra el símbolo del sistema.

2. Ejecute el siguiente comando: `MpCmdRun.exe -wdenable`

3. Reinicie el dispositivo.

## <a name="see-also"></a>Consulte también

- [Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md)

- [Herramientas y métodos de incorporación para Windows dispositivos en Defender para endpoint](configure-endpoints.md) 
