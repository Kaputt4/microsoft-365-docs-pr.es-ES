---
title: Evaluar las reglas de la reducción de la superficie expuesta a ataques
description: Vea cómo la reducción de superficie de ataque bloquearía e impediría ataques con la herramienta de demostración personalizada.
keywords: Reducción de superficie de ataque, caderas, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, vulnerabilidad, prevención de infecciones, evaluación, prueba, demostración
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 1f6479f3bbf6f636298858d50938846cfddca101
ms.sourcegitcommit: 59b1b0abfde30a8f2d8210b696aac3dc9183544e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2021
ms.locfileid: "61566644"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Evaluar las reglas de la reducción de la superficie expuesta a ataques

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Las reglas de reducción de superficie de ataque ayudan a evitar las acciones que suele usar el malware para poner en peligro dispositivos o redes. Las reglas de reducción de superficie de ataque ayudan a cerrar muchos de los puntos de entrada comunes usados por malware y ransomware.

Establecer reglas de reducción de superficie de ataque para dispositivos que ejecuten cualquiera de las siguientes ediciones y versiones de Windows:

- Windows 10 Pro versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows server, [versión 1803 (canal semianual)](/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)
- Windows Server 2022

> [!Note]
> Las reglas de reducción de superficie de ataque Windows Server 2012 R2 y Windows Server 2016 están disponibles con el paquete de soluciones unificado moderno. Para obtener más información, vea New [functionality in the modern unified solution for Windows 2012 R2 and 2016 Preview](configure-server-endpoints.md#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview) en el tema Onboard Windows servers to the Microsoft Defender for Endpoint [service](configure-server-endpoints.md).
Vea también [Microsoft Defender para Endpoint: Defender Windows Server 2012 R2 y 2016](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292).

Aprende a evaluar las reglas de reducción de superficie de ataque habilitando el modo [de](audit-windows-defender.md) auditoría para probar la característica directamente en tu organización.

> [!TIP]
> También puede visitar el sitio web de escenario de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.

## <a name="use-audit-mode-to-measure-impact"></a>Usar el modo de auditoría para medir el impacto

Habilita las reglas de reducción de superficie de ataque en modo auditoría para ver un registro de aplicaciones que se habrían bloqueado si la característica estaba totalmente habilitada. Pruebe cómo funcionará la característica en su organización para asegurarse de que no afecta a las aplicaciones de línea de negocio. También puedes obtener una idea de la frecuencia con la que se dispararán las reglas durante el uso normal.

Para habilitar una regla de reducción de superficie de ataque en modo auditoría, use el siguiente cmdlet de PowerShell:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Donde `<rule ID>` es un valor GUID de la regla de [reducción de superficie de ataque](attack-surface-reduction-rules-reference.md).

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

## <a name="see-also"></a>Vea también

- [Reducir superficies de ataque con reglas de reducción de superficie de ataque](attack-surface-reduction.md)
- [Usar el modo de auditoría para evaluar Windows Defender](audit-windows-defender.md)
- [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
