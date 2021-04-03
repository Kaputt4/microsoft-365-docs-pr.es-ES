---
title: Probar cómo funcionan las características de Microsoft Defender para endpoint en modo auditoría
description: El modo auditoría le ayuda a ver cómo Microsoft Defender para Endpoint protegería sus dispositivos si estaba habilitado.
keywords: protección contra vulnerabilidades de seguridad, auditoría, auditoría, modo, habilitado, deshabilitado, prueba, demostración, evaluación, laboratorio
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570977"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>Probar cómo funcionan las características de Microsoft Defender para endpoint en modo auditoría

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Puedes habilitar reglas de reducción de superficie de ataque, protección contra vulnerabilidades, protección de red y acceso controlado a carpetas en modo auditoría. El modo auditoría te permite ver un registro de lo *que hubiera* ocurrido si hubieras habilitado la característica.

Es posible que desee habilitar el modo de auditoría al probar cómo funcionarán las características en su organización. Esto te ayudará a asegurarte de que tus aplicaciones de línea de negocio no se ven afectadas. También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos se producen durante un período de tiempo determinado.

Las características no bloquearán ni impedirán que se modifiquen aplicaciones, scripts o archivos. Sin embargo, el Registro de eventos de Windows registrará eventos como si las características estuvieran totalmente habilitadas. Con el modo de auditoría, puedes revisar el registro de eventos para ver qué impacto habría tenido la característica si se hubiera habilitado.

Para buscar las entradas auditadas, vaya a **Aplicaciones y servicios**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.

Puedes usar Defender para endpoint para obtener más detalles para cada evento, especialmente para investigar reglas de reducción de superficie de ataque. El uso de la consola defender para endpoint te permite investigar problemas como parte de la escala de tiempo de alerta y [los escenarios de investigación.](investigate-alerts.md)

Puede usar la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP) para habilitar el modo de auditoría.

> [!TIP]
> También puedes visitar el sitio web Windows Defender Testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.

 **Opciones de auditoría** | **Cómo habilitar el modo de auditoría** | **Cómo ver eventos**
|---------|---------|---------|
| La auditoría se aplica a todos los eventos | [Habilitar el acceso controlado a carpetas](enable-controlled-folders.md) | [Eventos de acceso controlado a carpetas](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| La auditoría se aplica a reglas individuales | [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md) | [Eventos de regla de reducción de superficie de ataque](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| La auditoría se aplica a todos los eventos | [Habilitar la protección de red](enable-network-protection.md) | [Eventos de protección de red](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| La auditoría se aplica a mitigaciones individuales | [Habilitar la protección contra vulnerabilidades de seguridad](enable-exploit-protection.md) | [Eventos de protección contra vulnerabilidades](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>Temas relacionados

* [Proteger los dispositivos contra vulnerabilidades de seguridad](exploit-protection.md)
* [Reducir superficies de ataque con reglas de reducción de superficie de ataque](attack-surface-reduction.md)
* [Proteger la red](network-protection.md)
* [Proteger carpetas importantes](controlled-folders.md)
