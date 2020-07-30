---
title: Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft
description: Obtener información general sobre las acciones de corrección que siguen las investigaciones automatizadas en protección contra amenazas de Microsoft
keywords: automatizada, investigación, alerta, desencadenante, acción, corrección
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502942"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft

**Aplica para:**
- Protección contra amenazas de Microsoft


## <a name="remediation-actions"></a>Acciones de corrección

Durante y después de una investigación automatizada en protección contra amenazas de Microsoft, se identifican las acciones de corrección para los elementos malintencionados o sospechosos. Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión. Otras acciones de corrección se realizan en el contenido del correo electrónico. Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.

En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft: 

|Acciones de corrección de dispositivo (extremo)  |Acciones de corrección de correo electrónico  |
|---------|---------|
|-Recopilar un paquete de investigación <br/>-Isolater dispositivo (esta acción se puede deshacer)<br/>-Máquina desincorpora <br/>-Liberar la ejecución de código <br/>-Liberar de cuarentena <br/>Ejemplo de solicitud <br/>-Restringir la ejecución de código (esta acción se puede deshacer) <br/>-Ejecutar detección de virus <br/>-Detener y poner en cuarentena      |-Bloquear dirección URL (tiempo de clic)<br/>-Eliminación temporal de mensajes de correo electrónico o clústeres<br/>-Correo electrónico en cuarentena<br/>-Poner en cuarentena un archivo adjunto de correo electrónico<br/>-Desactivar el reenvío externo de correo          |

Las acciones de corrección, tanto si están pendientes de aprobación como si ya están completas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Las acciones de corrección siguen las investigaciones automatizadas

Cuando una investigación automatizada se completa, se llega a un veredicto para cada evidencia involucrada, y se identifican las acciones correctivas. En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación. En la tabla siguiente se muestran los posibles resultados:

|Veredicto    |Área    |Resultados|
|------|------|------|
|Malintencionado    |Dispositivos (puntos de conexión)    |Las acciones de corrección se toman automáticamente|
|Malintencionado    |Contenido de correo electrónico (URL y datos adjuntos) | Acciones de corrección recomendadas pendientes de aprobación|
|Sospechoso    |Dispositivos o contenido de correo electrónico |Acciones de corrección recomendadas pendientes de aprobación|
|No se encontraron amenazas    |Dispositivos o contenido de correo electrónico    |No es necesario realizar ninguna acción correctiva|

[Revisar una acción pendiente en el centro de actividades](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber. [Informar de falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Siguientes pasos

- [Aprobar o rechazar acciones](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Más información sobre el Centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
