---
title: Bloquear aplicaciones potencialmente no deseadas con Antivirus de Microsoft Defender
description: Habilite la característica antivirus de aplicaciones potencialmente no deseadas (PUA) para bloquear software no deseado como el software publicitario.
keywords: pua, enable, software no deseado, aplicaciones no deseadas, adware, barra de herramientas del explorador, detectar, bloquear, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 808eff2074dfe1573708264590b401f3d38db982
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904015"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Detectar y bloquear aplicaciones potencialmente no deseadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Las aplicaciones potencialmente no deseadas (PUA) son una categoría de software que puede hacer que el equipo se ejecute lentamente, mostrar anuncios inesperados o, en el peor de los casos, instalar otro software que pueda ser inesperado o no deseado. La PUA no se considera un virus, malware u otro tipo de amenaza, pero puede realizar acciones en puntos de conexión que afecten negativamente al rendimiento o uso de los puntos de conexión. El término *PUA* también puede hacer referencia a una aplicación que tiene una mala reputación, según lo evaluado por Microsoft Defender para Endpoint, debido a ciertos tipos de comportamiento no deseado.

Estos son algunos ejemplos:

- **Software de** publicidad que muestra anuncios o promociones, incluido el software que inserta anuncios en páginas web.
- **Agrupación de software** que ofrece instalar otro software que no está firmado digitalmente por la misma entidad. Además, software que ofrece instalar otro software que cumple los requisitos como PUA.
- **Software de evasión** que intenta eludir activamente la detección por parte de productos de seguridad, incluido el software que se comporta de forma diferente en presencia de productos de seguridad.

> [!TIP]
> Para obtener más ejemplos y una explicación de los criterios que usamos para etiquetar las aplicaciones para una atención especial de las características de seguridad, vea [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).

Las aplicaciones potencialmente no deseadas pueden aumentar el riesgo de que la red se infecte con malware real, dificultar la identificación de las infecciones de malware o desperdiciar recursos de TI al limpiarlas. La protección pua se admite en Windows 10, Windows Server 2019 y Windows Server 2016. En Windows 10 (versión 2004 y versiones posteriores), Antivirus de Microsoft Defender bloquea aplicaciones que se consideran dispositivos PUA para Empresas (E5) de forma predeterminada.

## <a name="microsoft-edge"></a>Microsoft Edge

El [nuevo Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)basado en Chromium, bloquea las descargas de aplicaciones potencialmente no deseadas y las direcciones URL de recursos asociadas. Esta característica se proporciona a través [de SmartScreen de Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Habilitar la protección de PUA en Microsoft Edge basado en Chromium

Aunque la protección de aplicaciones potencialmente no deseada en Microsoft Edge (basada en Chromium, versión 80.0.361.50) está desactivada de forma predeterminada, se puede desactivar fácilmente desde el explorador.

1. En el explorador perimetral, seleccione los puntos suspensivos y, a continuación, elija **Configuración**.

2. Seleccione **Privacidad, búsqueda y servicios**.

3. En la **sección Seguridad,** activa **Bloquear aplicaciones potencialmente no deseadas.**

> [!TIP]
> Si ejecuta Microsoft Edge (basado en Chromium), puede explorar con seguridad la característica de bloqueo de direcciones URL de la protección pua mediante la prueba en una de nuestras páginas de demostración de SmartScreen de [Microsoft Defender.](https://demo.smartscreen.msft.net/)

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Bloquear direcciones URL con SmartScreen de Microsoft Defender

En Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen te protege de las direcciones URL asociadas a PUA.

Los administradores de seguridad pueden [configurar](/DeployEdge/configure-microsoft-edge) el modo en que Microsoft Edge y SmartScreen de Microsoft Defender trabajan juntos para proteger grupos de usuarios de direcciones URL asociadas a PUA. Hay varias opciones [de configuración de directiva de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explícitamente disponibles para SmartScreen de Microsoft Defender, incluida una para bloquear [PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Además, los administradores pueden configurar [SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) de Microsoft Defender en su conjunto, mediante la configuración de directiva de grupo para activar o desactivar SmartScreen de Microsoft Defender.

Aunque Microsoft Defender para endpoint tiene su propia lista de bloqueo basada en un conjunto de datos administrado por Microsoft, puede personalizar esta lista en función de su propia inteligencia de amenazas. Si crea [y administra indicadores en](manage-indicators.md) el portal de Microsoft Defender para endpoints, SmartScreen de Microsoft Defender respeta la nueva configuración.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Protección contra antivirus y PUA de Microsoft Defender

La característica de protección de aplicaciones potencialmente no deseadas (PUA) en Antivirus de Microsoft Defender puede detectar y bloquear PUA en puntos de conexión de la red.

> [!NOTE]
> Esta característica está disponible en Windows 10, Windows Server 2019 y Windows Server 2016.

Antivirus de Microsoft Defender bloquea los archivos PUA detectados y cualquier intento de descargarlos, moverlos, ejecutarlos o instalarlos. Los archivos PUA bloqueados se mueven a la cuarentena. Cuando se detecta un archivo PUA en un punto de conexión, Antivirus de Microsoft Defender envía una notificación al usuario ( a menos que las notificaciones se hayan deshabilitado ) en el mismo formato que[otras](configure-notifications-microsoft-defender-antivirus.md)detecciones de amenazas. La notificación está precedida de para `PUA:` indicar su contenido.

La notificación aparece en la lista de [cuarentena habitual dentro de la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Configurar la protección de LA PUA en Antivirus de Microsoft Defender

Puede habilitar la protección de PUA con [Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [directiva](/azure/active-directory-domain-services/manage-group-policy)de grupo o mediante [cmdlets de PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).

También puede usar la protección pua en modo auditoría para detectar aplicaciones potencialmente no deseadas sin bloquearlas. Las detecciones se capturan en el registro de eventos de Windows.

> [!TIP]
> Visite el sitio web de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) para confirmar que la característica funciona y verla en acción.

La protección de PUA en modo auditoría es útil si su empresa realiza una comprobación de cumplimiento de seguridad de software interna y desea evitar falsos positivos.

### <a name="use-intune-to-configure-pua-protection"></a>Usar Intune para configurar la protección de PUA

Para [obtener más información,](/intune/device-restrictions-configure) consulta Configurar la configuración de restricción de dispositivos de Microsoft Intune y Antivirus de Microsoft Defender para [Windows 10 en Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Usar Configuration Manager para configurar la protección de PUA

La protección pua está habilitada de forma predeterminada en Microsoft Endpoint Manager (rama actual).

Vea [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).

Para System Center 2012 Configuration Manager, consulte [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> Los eventos de PUA bloqueados por Antivirus de Microsoft Defender se notifican en el Visor de eventos de Windows y no en Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Usar la directiva de grupo para configurar la protección de LA PUA

1. Descargar e instalar [plantillas administrativas (.admx) para Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. En el equipo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Seleccione el objeto de directiva de grupo que desea configurar y, a continuación, elija **Editar**.

4. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**

5. Expande el árbol a **Componentes de Windows** Antivirus de Microsoft  >  **Defender**.

6. Haga doble clic en **Configurar la detección para aplicaciones potencialmente no deseadas.**

7. Seleccione **Habilitado para** habilitar la protección de LA PUA.

8. En **Opciones,** seleccione **Bloquear para** bloquear aplicaciones potencialmente no deseadas o seleccione **Modo** de auditoría para probar el funcionamiento de la configuración en el entorno. Seleccione **Aceptar**.

9. Implemente el objeto de directiva de grupo como suele hacer.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Usar cmdlets de PowerShell para configurar la protección de PUA

#### <a name="to-enable-pua-protection"></a>Para habilitar la protección de PUA

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Al establecer el valor de este cmdlet `Enabled` para que se activa la característica si se ha deshabilitado.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Para establecer la protección de LA PUA en modo auditoría

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

La `AuditMode` configuración detecta LAS PUA sin bloquearlas.

#### <a name="to-disable-pua-protection"></a>Para deshabilitar la protección de PUA

Se recomienda mantener activada la protección de PUA. Sin embargo, puede desactivarlo con el siguiente cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Establecer el valor de este cmdlet `Disabled` para desactivar la característica si se ha habilitado.

Para obtener más información, vea [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index).

## <a name="view-pua-events-using-powershell"></a>Ver eventos pua con PowerShell

Los eventos PUA se notifican en el Visor de eventos de Windows, pero no en Microsoft Endpoint Manager ni en Intune. También puede usar el `Get-MpThreat` cmdlet para ver las amenazas que controló Antivirus de Microsoft Defender. Aquí le mostramos un ejemplo:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>Obtener notificaciones por correo electrónico sobre detecciones de PUA

Puedes activar las notificaciones de correo electrónico para recibir correo sobre detecciones de PUA.

Consulta [Solucionar problemas de los IDs de eventos](troubleshoot-microsoft-defender-antivirus.md) para obtener más información sobre cómo ver los eventos del Antivirus de Microsoft Defender. Los eventos PUA se registran con el identificador **de evento 1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>Ver eventos de PUA con la búsqueda avanzada

Si usa Microsoft [Defender](microsoft-defender-endpoint.md)para endpoint, puede usar una consulta de búsqueda avanzada para ver eventos pua. Esta es una consulta de ejemplo:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

Para obtener más información sobre la búsqueda avanzada, vea [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Excluir archivos de la protección de PUA

A veces, la protección de PUA bloquea erróneamente un archivo o se requiere una característica de una PUA para completar una tarea. En estos casos, se puede agregar un archivo a una lista de exclusión.

Para obtener más información, vea [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Vea también

- [Protección de última generación](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar la protección en tiempo real, heurística y de comportamiento](configure-protection-features-microsoft-defender-antivirus.md)