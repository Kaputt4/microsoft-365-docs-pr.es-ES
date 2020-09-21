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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 205809bac14cc82e850ea1cbc0349256432bfe68
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962590"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Acciones de corrección tras investigaciones automatizadas en protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft


## <a name="remediation-actions"></a>Acciones de corrección

Durante y después de una investigación automatizada en protección contra amenazas de Microsoft, se identifican las acciones de corrección para los elementos malintencionados o sospechosos. Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión. Otras acciones de corrección se realizan en el contenido del correo electrónico. Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.

En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft: 

|Acciones de corrección de dispositivo (extremo)  |Acciones de corrección de correo electrónico  |
|---------|---------|
|-Recopilar un paquete de investigación <br/>-Isolater dispositivo (esta acción se puede deshacer)<br/>-Máquina desincorpora <br/>-Liberar la ejecución de código <br/>-Liberar de cuarentena <br/>Ejemplo de solicitud <br/>-Restringir la ejecución de código (esta acción se puede deshacer) <br/>-Ejecutar detección de virus <br/>-Detener y poner en cuarentena      |-Bloquear dirección URL (tiempo de clic)<br/>-Eliminación temporal de mensajes de correo electrónico o clústeres<br/>-Correo electrónico en cuarentena<br/>-Poner en cuarentena un archivo adjunto de correo electrónico<br/>-Desactivar el reenvío externo de correo          |

Las acciones de corrección, ya estén pendientes de aprobación o ya completadas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Las acciones de corrección siguen las investigaciones automatizadas

Cuando se completa una investigación automatizada, se alcanza un veredicto para cada fragmento de evidencia implicado. Según el veredicto, se identifican las acciones de corrección. En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación. Todo depende de cómo [esté configurada la investigación y la respuesta automatizadas](mtp-configure-auto-investigation-response.md).

En la tabla siguiente se muestran los posibles resultados:

|Veredicto    |Área    |Resultados|
|------|------|------|
|Malintencionado    |Dispositivos (puntos de conexión)    |Las acciones de corrección se realizan automáticamente (suponiendo que los [grupos de dispositivos](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) de la organización están configurados automáticamente para las amenazas de corrección **completa**)|
|Malintencionado    |Contenido de correo electrónico (URL y datos adjuntos) | Acciones de corrección recomendadas pendientes de aprobación|
|Sospechoso    |Dispositivos o contenido de correo electrónico |Acciones de corrección recomendadas pendientes de aprobación|
|No se encontraron amenazas    |Dispositivos o contenido de correo electrónico    |No es necesario realizar ninguna acción correctiva|

> [!IMPORTANT]
> El hecho de que las acciones de corrección se tomen automáticamente o solo tras la aprobación depende de determinadas opciones, como las directivas de grupo de dispositivos de la organización. Para obtener más información, vea los siguientes artículos:
> - [Configuración de capacidades de investigación y respuesta automatizadas en Microsoft Threat Protection](mtp-configure-auto-investigation-response.md)
> - [Cómo se corrigen las amenazas en los dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>Pasos siguientes

- [Visitar el centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Aprobar o rechazar acciones pendientes](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta](mtp-autoir-report-false-positives-negatives.md)
