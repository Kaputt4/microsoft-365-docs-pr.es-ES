---
title: Evaluar las reglas de la reducción de la superficie expuesta a ataques
description: Vea cómo la reducción de superficie de ataque bloquearía e impediría ataques con la herramienta de demostración personalizada.
keywords: Reducción de superficie de ataque, caderas, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, vulnerabilidad, prevención de infecciones, evaluación, prueba, demostración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c2dea22cc8a0ebb875f83ebd5a3e42f723e5f254
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771326"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Evaluar las reglas de la reducción de la superficie expuesta a ataques

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Las reglas de reducción de superficie de ataque ayudan a evitar las acciones que suele usar el malware para poner en peligro dispositivos o redes. Las reglas de reducción de superficie de ataque ayudan a cerrar muchos de los puntos de entrada comunes usados por malware y ransomware. 

Establecer reglas de reducción de superficie de ataque para dispositivos que ejecuten cualquiera de las siguientes ediciones y versiones de Windows:

- Windows 10 Pro versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows Servidor, [versión 1803 (canal semianual)](/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Aprende a evaluar las reglas de reducción de superficie de ataque habilitando el modo de auditoría para probar la característica directamente en tu organización.

> [!TIP]
> También puede visitar el sitio web de escenario de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.

## <a name="use-audit-mode-to-measure-impact"></a>Usar el modo de auditoría para medir el impacto

Habilita las reglas de reducción de superficie de ataque en modo auditoría para ver un registro de aplicaciones que se habrían bloqueado si la característica estaba totalmente habilitada. Pruebe cómo funcionará la característica en su organización para asegurarse de que no afecta a las aplicaciones de línea de negocio. También puedes obtener una idea de la frecuencia con la que se dispararán las reglas durante el uso normal.

Para habilitar una regla de reducción de superficie de ataque en modo auditoría, use el siguiente cmdlet de PowerShell:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Donde `<rule ID>` es un valor GUID de la regla de [reducción de superficie de ataque](attack-surface-reduction.md#attack-surface-reduction-rules).

Para habilitar todas las reglas de reducción de superficie de ataque agregadas en modo auditoría, use el siguiente cmdlet de PowerShell:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Si quieres auditar completamente cómo funcionarán las reglas de reducción de superficie de ataque en tu organización, tendrás que usar una herramienta de administración para implementar esta configuración en dispositivos de tus redes.

También puedes usar la directiva de grupo, Intune o los proveedores de servicios de configuración (CSP) de administración de dispositivos móviles (MDM) para configurar e implementar la configuración. Obtenga más información en el artículo [principal Reglas de reducción de superficie de](attack-surface-reduction.md) ataque.

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Revisar los eventos de reducción de superficie de ataque Windows visor de eventos

Para revisar las aplicaciones que se habrían bloqueado, abra el Visor de eventos y filtre el identificador de evento 1121 en el registro de Microsoft-Windows-Windows Defender/Operativo. En la tabla siguiente se enumeran todos los eventos de protección de red.

Id. de evento | Descripción
-|-
 5007 | Evento cuando se cambia la configuración
 1121 | Evento cuando una regla de reducción de superficie de ataque se dispara en modo de bloqueo
 1122 | Evento cuando se desangre una regla de reducción de superficie de ataque en modo auditoría

## <a name="customize-attack-surface-reduction-rules"></a>Personalizar las reglas de la reducción de superficie expuesta a ataques

Durante la evaluación, es posible que desee configurar cada regla individualmente o excluir determinados archivos y procesos para que la característica evalúe.

Consulta [Personalizar reglas de reducción de](customize-attack-surface-reduction.md) superficie de ataque para obtener información sobre cómo configurar la característica con herramientas de administración, incluidas directivas de grupo y directivas de CSP de MDM.

## <a name="see-also"></a>Consulte también

* [Reducir superficies de ataque con reglas de reducción de superficie de ataque](attack-surface-reduction.md)
* [Usar el modo de auditoría para evaluar Windows Defender](audit-windows-defender.md)
* [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
