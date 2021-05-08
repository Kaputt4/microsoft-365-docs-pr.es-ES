---
title: Bloquear aplicaciones potencialmente no deseadas con Antivirus de Microsoft Defender
description: Habilite la característica antivirus de aplicaciones potencialmente no deseadas (PUA) para bloquear software no deseado como, por ejemplo, adware.
keywords: pua, habilitar, software no deseado, aplicaciones no deseadas, barra de herramientas del explorador, detectar, bloquear, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275245"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Detectar y bloquear aplicaciones potencialmente no deseadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Las aplicaciones potencialmente no deseadas (PUA) son una categoría de software que puede hacer que su equipo funcione lentamente, muestre anuncios inesperados o, en el peor de los casos, instale otro software que pueda ser inesperado o no deseado. PUA no se considera un virus, malware u otro tipo de amenaza, pero puede realizar acciones en los puntos de conexión que afecten negativamente al rendimiento o al uso de los puntos de conexión. El término *PUA* también puede hacer referencia a una aplicación que tenga mala reputación, según la evaluación de Microsoft Defender para punto de conexión, debido a determinados tipos de comportamiento no deseado.

Estos son algunos ejemplos:

- **Software de publicidad**, que muestra anuncios o promociones, incluido software que inserta anuncios en páginas web.
- **Software de agrupación**, que ofrece instalar otro software que no está firmado digitalmente por la misma entidad. Además, existe software que ofrece instalar otro software que se considera PUA.
- **Software de evasión**, que intenta evitar activamente que los productos de seguridad lo detecten, incluido software que se comporta de forma diferente en presencia de productos de seguridad.

> [!TIP]
> Para obtener más ejemplos y una explicación de los criterios que usamos para etiquetar aplicaciones para que las características de seguridad les presten especial atención, consulte [Cómo identifica Microsoft el malware y las aplicaciones potencialmente no deseadas](/windows/security/threat-protection/intelligence/criteria).

Las aplicaciones potencialmente no deseadas pueden aumentar el riesgo de que su red se infecte con malware real, puede hacer que sea más difícil identificar infecciones de malware o que se pierdan recursos de TI al limpiar las infecciones. La protección contra PUA es compatible con Windows 10, Windows Server 2019 y Windows Server 2016. En Windows 10 (versión 2004 y posteriores), Antivirus de Microsoft Defender bloquea las aplicaciones que se consideran PUA para dispositivos Enterprise (E5) de forma predeterminada.

## <a name="microsoft-edge"></a>Microsoft Edge

El nuevo [Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), basado Chromium, bloquea las descargas de aplicaciones potencialmente no deseadas y las direcciones URL de recursos asociados. Esta característica se ofrece a través de [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Habilitar la protección de PUA en Microsoft Edge basado en Chromium

Si bien la protección de aplicaciones potencialmente no deseadas en Microsoft Edge (basada en Chromium, versión 80.0.361.50) está desactivada de manera predeterminada, se puede activar fácilmente desde el explorador.

1. En el explorador Edge, seleccione los puntos suspensivos y, después, elija **Configuración**.

2. Seleccione **Privacidad, búsqueda y servicios**.

3. En la sección **Seguridad**, active **Bloquear aplicaciones potencialmente no deseadas**.

> [!TIP]
> Si ejecuta Microsoft Edge (basado en Chromium), puede explorar de forma segura la característica de bloqueo de direcciones URL de la protección contra PUA. Puede probarla en una de nuestras [Páginas de demostración de SmartScreen de Microsoft Defender](https://demo.smartscreen.msft.net/).

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Bloquear direcciones URL con SmartScreen de Microsoft Defender

En Edge basado en Chromium con la protección activada contra PUA, SmartScreen de Microsoft Defender le protege de direcciones URL asociadas a PUA.

Los administradores de seguridad pueden [configurar](/DeployEdge/configure-microsoft-edge) la manera en la que Microsoft Edge y SmartScreen de Microsoft Defender trabajan juntos para proteger a grupos de usuarios frente a direcciones URL asociadas a PUA. Hay disponibles varias opciones de [configuración de directiva de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) expresamente para SmartScreen de Microsoft Defender, incluida una [configuración para bloquear PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Además, los administradores pueden [configurar SmartScreen de Microsoft Defender](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) en general, con la configuración de directiva de grupo para activar o desactivar SmartScreen de Microsoft Defender.

Aunque Microsoft Defender para punto de conexión tiene su propia lista de bloqueo basada en un conjunto de datos administrado por Microsoft, puede personalizar esta lista según su propia inteligencia sobre amenazas. Si [crea y administra indicadores](manage-indicators.md) en el portal de Microsoft Defender para punto de conexión, SmartScreen de Microsoft Defender respetará la nueva configuración.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Antivirus de Microsoft Defender y protección contra PUA

La característica de protección contra aplicaciones potencialmente no deseadas (PUA) de Antivirus de Microsoft Defender puede detectar y bloquear PUA en los puntos de conexión de su red.

> [!NOTE]
> Esta característica está disponible en Windows 10, Windows Server 2019 y Windows Server 2016.

Antivirus de Microsoft Defender bloquea los archivos PUA que se detecten y cualquier intento de descargarlos, moverlos, ejecutarlos o instalarlos. A continuación, los archivos PUA bloqueados se ponen en cuarentena. Cuando se detecta un archivo PUA en un punto de conexión, Antivirus de Microsoft Defender envía una notificación al usuario ([a menos que se hayan deshabilitado las notificaciones](configure-notifications-microsoft-defender-antivirus.md)) en el mismo formato de otras detecciones de amenazas. A la notificación se antepone `PUA:` para indicar su contenido.

La notificación aparece en la [lista habitual de cuarentena dentro de la aplicación de Seguridad de Windows](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Configurar la protección contra PUA en Antivirus de Microsoft Defender

Puede habilitar la protección contra PUA con [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Directiva de grupo](/azure/active-directory-domain-services/manage-group-policy) o mediante [cmdlets de PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).

También puede usar la protección contra PUA en modo de auditoría para detectar aplicaciones potencialmente no deseadas sin bloquearlas. Las detecciones se capturan en el registro de eventos de Windows.

> [!TIP]
> Visite el sitio web de demostración de Microsoft Defender para punto de conexión en [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) para confirmar que la característica funciona y verla en acción.

La protección contra PUA en el modo de auditoría es útil si su empresa está realizando una comprobación interna de cumplimiento de seguridad de software y quiere evitar falsos positivos.

### <a name="use-intune-to-configure-pua-protection"></a>Usar Intune para configurar la protección contra PUA

Consulte [Configurar la configuración de restricciones de dispositivo en Microsoft Intune](/intune/device-restrictions-configure) y la [Configuración de restricciones de dispositivo de Antivirus de Microsoft Defender para Windows 10 en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para más información.

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Usar Configuration Manager para configurar la protección contra PUA

La protección contra PUA está habilitada de forma predeterminada en Microsoft Endpoint Manager (rama actual).

Consulte [Información sobre cómo crear e implementar directivas de antimalware: configuración de análisis programados](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) para obtener más información sobre cómo configurar Microsoft Endpoint Manager (rama actual).

Para System Center 2012 Configuration Manager, consulte [Cómo implementar una directiva de protección de aplicaciones potencialmente no deseadas para Endpoint Protection en Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> Los eventos de PUA bloqueados por Antivirus de Microsoft Defender se notifican en el Visor de eventos de Windows, en lugar de en Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Usar una directiva de grupo para configurar la protección contra PUA

1. Descargue e instale [Plantillas administrativas (.admx) para la actualización de octubre de 2020 de Windows 10 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Seleccione el objeto de directiva de grupo que quiera configurar y, después, seleccione **Editar**.

4. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

5. Expanda el árbol en **Componentes de Windows** > **Antivirus de Microsoft Defender**.

6. Haga doble clic en **Configurar la detección de aplicaciones potencialmente no deseadas**.

7. Seleccione **Habilitado** para habilitar la protección contra PUA.

8. En **Opciones**, seleccione **Bloquear** para bloquear aplicaciones potencialmente no deseadas o seleccione **Modo de auditoría** para probar cómo funciona la configuración en su entorno. Seleccione **Aceptar**.

9. Implemente el objeto de directiva de grupo como lo haría normalmente.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Usar cmdlets de PowerShell para configurar la protección contra PUA

#### <a name="to-enable-pua-protection"></a>Para habilitar la protección contra PUA

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Al establecer el valor de este cmdlet en `Enabled`, se activa la característica si se había deshabilitado.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Para configurar la protección contra PUA en modo de auditoría

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Al establecer `AuditMode` se detectan las PUA sin bloquearlas.

#### <a name="to-disable-pua-protection"></a>Para deshabilitar la protección contra PUA

Se recomienda mantener activada la protección contra PUA. Sin embargo, puede desactivarla con el cmdlet siguiente:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Al establecer el valor de este cmdlet en `Disabled`, se desactiva la característica si se había habilitado.

Para más información, consulte [Usar cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Defender](/powershell/module/defender/index).

## <a name="view-pua-events-using-powershell"></a>Ver eventos de PUA con PowerShell

Los eventos de PUA se notifican en el Visor de eventos de Windows, en lugar de en Microsoft Endpoint Manager o Intune. Asimismo, puede usar el cmdlet `Get-MpThreat` para ver las amenazas que Antivirus de Microsoft Defender ha administrado. Aquí le mostramos un ejemplo:

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

## <a name="get-email-notifications-about-pua-detections"></a>Obtener notificaciones de correo electrónico sobre las detecciones de PUA

Puede activar las notificaciones de correo electrónico para recibir un correo electrónico sobre las detecciones de PUA.

Consulte [Solucionar id. de evento](troubleshoot-microsoft-defender-antivirus.md) para obtener más información sobre cómo ver los eventos de Antivirus de Microsoft Defender. Los eventos de PUA se registran en el id. de evento **1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>Ver eventos de PUA con la búsqueda avanzada de amenazas

Si usa [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md), puede usar una consulta de búsqueda avanzada de amenazas para ver eventos de PUA. Esta es una consulta de ejemplo:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

Para más información sobre la búsqueda avanzada de amenazas, consulte [Buscar amenazas de forma proactiva con la búsqueda avanzada de amenazas](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Excluir archivos de la protección contra PUA

A veces, la protección contra PUA bloquea un archivo por error, o se requiere una característica de una PUA para completar una tarea. En estos casos, se puede agregar un archivo a una lista de exclusiones.

Para más información, consulte [Configurar y validar exclusiones según la extensión de archivo y la ubicación de carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Vea también

- [Protección de última generación](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar la protección en tiempo real, heurística y de comportamiento](configure-protection-features-microsoft-defender-antivirus.md)