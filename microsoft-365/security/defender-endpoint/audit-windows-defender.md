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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 06/02/2021
ms.topic: article
ms.openlocfilehash: 10351d97ba72945f929e042dc72a37724a1df291
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769610"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Probar la reducción de superficie de ataque en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Si formas parte del equipo de seguridad de la organización, puedes configurar las capacidades de reducción de superficie de ataque para que se ejecuten en modo auditoría para ver cómo funcionarán en la organización. En particular, puedes habilitar reglas de reducción de superficie de ataque, protección contra vulnerabilidades, protección de red y acceso controlado a carpetas en modo auditoría. El modo auditoría te permite ver un registro de lo *que hubiera* ocurrido si hubieras habilitado la característica.

Es posible que desee habilitar el modo de auditoría al probar cómo funcionarán las características en su organización. Esto te ayudará a asegurarte de que tus aplicaciones de línea de negocio no se ven afectadas. También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos se producen durante un período de tiempo determinado.

Las características no bloquearán ni impedirán que se modifiquen aplicaciones, scripts o archivos. Sin embargo, el Windows de eventos registrará eventos como si las características estuvieran totalmente habilitadas. Con el modo de auditoría, puedes revisar el registro de eventos para ver qué impacto habría tenido la característica si se hubiera habilitado.

Para buscar las entradas auditadas, vaya a **Aplicaciones y servicios** de  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.

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


