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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266056"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft

**Aplica para:**
- Protección contra amenazas de Microsoft


## <a name="remediation-actions"></a>Acciones de corrección

Durante y después de una investigación automatizada en protección contra amenazas de Microsoft, se identifican las acciones de corrección para los elementos malintencionados o sospechosos. Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión. Otras acciones de corrección se realizan en el contenido del correo electrónico. Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.

En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft: 

|Acciones de corrección de dispositivo (extremo)  |Acciones de corrección de correo electrónico  |
|---------|---------|
|Poner archivo en cuarentena<br/>Eliminar clave del registro<br/>Terminar proceso <br/>Detener el servicio <br/>Deshabilitar controlador <br/>Eliminar tarea programada.      |Eliminar temporalmente mensajes de correo electrónico o clústeres<br/>Bloquear URL (tiempo de clic)<br/>Desactivar el reenvío de correo externo          |

Las acciones de corrección, tanto si están pendientes de aprobación como si ya están completas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="verdicts-and-outcomes-following-automated-investigations"></a>Veredictos y resultados tras las investigaciones automatizadas

Cuando una investigación automatizada se completa, se llega a un veredicto para cada evidencia involucrada, y se identifican las acciones correctivas. En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación. En la tabla siguiente se muestran los posibles resultados:

|Veredicto    |Área   |Resultados|
|------|------|------|
|Malintencionado  |Dispositivos (puntos de conexión)    |Las acciones de corrección se toman automáticamente|
|Malintencionado  |Contenido de correo electrónico (URL y datos adjuntos) | Acciones de corrección recomendadas pendientes de aprobación|
|Sospechoso |Dispositivos o contenido de correo electrónico |Acciones de corrección recomendadas pendientes de aprobación|
|Limpiar  |Dispositivos o contenido de correo electrónico   |No es necesario realizar ninguna acción correctiva|

[Revisar una acción pendiente en el centro de actividades](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber. [Informar de falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Pasos siguientes

- [Aprobar o rechazar acciones](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Más información sobre el Centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
