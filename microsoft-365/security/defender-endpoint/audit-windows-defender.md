---
title: Probar cómo funcionan las características de Microsoft Defender para endpoint en modo auditoría
description: El modo auditoría le ayuda a ver cómo Microsoft Defender para Endpoint protegería sus dispositivos si estaba habilitado.
keywords: protección contra vulnerabilidades de seguridad, auditoría, auditoría, modo, habilitado, deshabilitado, prueba, demostración, evaluación, laboratorio
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 10/14/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 4c96f7a0f2788f1ed43d06e35c13896600a98b74
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170612"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Probar la reducción de superficie de ataque en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Como parte del equipo de seguridad de la organización, puedes configurar las capacidades de reducción de superficie de ataque para que se ejecuten en modo auditoría para ver cómo funcionarán. En el modo de auditoría, puede habilitar:

- Reglas de reducción de la superficie expuesta a ataques
- Protección contra vulnerabilidades de seguridad
- Protección de red
- Acceso controlado a carpetas en modo auditoría

El modo auditoría te permite ver un registro de lo *que hubiera* ocurrido si hubieras habilitado la característica.

Puedes habilitar el modo de auditoría al probar cómo funcionarán las características. Habilitar el modo de auditoría solo para pruebas ayuda a evitar que el modo de auditoría afecte a las aplicaciones de línea de negocio. También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos se producen durante un período de tiempo determinado.

Las características no bloquearán ni impedirán que se modifiquen aplicaciones, scripts o archivos. Sin embargo, el Windows de eventos registrará eventos como si las características estuvieran totalmente habilitadas. Con el modo de auditoría, puedes revisar el registro de eventos para ver qué efecto habría tenido la característica si se hubiera habilitado.

Para buscar las entradas auditadas, vaya a **Aplicaciones y servicios** de \> **Microsoft** \> **Windows** \> **Windows Defender** \> **Operativo**.

Usa Defender para endpoint para obtener más detalles para cada evento. Estos detalles son especialmente útiles para investigar reglas de reducción de superficie de ataque. El uso de la consola defender para endpoint te permite investigar problemas como parte de la escala de tiempo de alerta y [los escenarios de investigación.](investigate-alerts.md)

Puede habilitar el modo de auditoría mediante la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP).

> [!TIP]
> También puedes visitar el sitio web Windows Defender Testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.

|Opciones de auditoría|Cómo habilitar el modo de auditoría|Cómo ver eventos|
|---|---|---|
|La auditoría se aplica a todos los eventos|[Habilitar el acceso controlado a carpetas](enable-controlled-folders.md)|[Eventos de acceso controlado a carpetas](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
|La auditoría se aplica a reglas individuales|[Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)|[Eventos de regla de reducción de superficie de ataque](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
|La auditoría se aplica a todos los eventos|[Habilitar la protección de red](enable-network-protection.md)|[Eventos de protección de red](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
|La auditoría se aplica a mitigaciones individuales|[Habilitar la protección contra vulnerabilidades de seguridad](enable-exploit-protection.md)|[Eventos de protección contra vulnerabilidades](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
