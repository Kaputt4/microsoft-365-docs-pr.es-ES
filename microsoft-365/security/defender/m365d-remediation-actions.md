---
title: Acciones de corrección en Microsoft 365 Defender
description: Obtener información general sobre las acciones de corrección que siguen las investigaciones automatizadas en Microsoft 365 Defender
keywords: automatizada, investigación, alerta, desencadenante, acción, corrección
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c81f824a0faaca1c228aa650c003576cce210a67
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199212"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Acciones de corrección en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Acciones de corrección

Durante y después de una investigación automatizada en Microsoft 365 Defender, las acciones de corrección se identifican para elementos malintencionados o sospechosos. Algunos tipos de acciones de corrección se toman en dispositivos, también denominados puntos de conexión. Otras acciones de corrección se toman en el contenido del correo electrónico. Las investigaciones automatizadas se completan después de que se realicen, aprueben o rechacen las acciones de corrección.

> [!IMPORTANT]
> Si las acciones de corrección se toman automáticamente o solo tras la aprobación depende de determinadas configuraciones, como el modo en que los niveles de automatización. Para obtener más información, consulte los artículos siguientes:
> - [Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)
> - [Cómo se corrigen las amenazas en dispositivos](../defender-endpoint/automated-investigations.md)
> - [Amenazas y acciones de corrección en el correo & contenido de colaboración](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

En la tabla siguiente se resumen las acciones de corrección que se admiten actualmente en Microsoft 365 Defender: 

|Acciones de corrección del dispositivo (punto de conexión)  |Acciones de corrección de correo electrónico  |
|:---------|:---------|
|- Recopilar paquete de investigación <br/>- Aislar dispositivo (esta acción se puede deshacer)<br/>- Máquina offboard <br/>- Ejecución de código de lanzamiento <br/>- Liberar de cuarentena <br/>- Ejemplo de solicitud <br/>- Restringir la ejecución de código (esta acción se puede deshacer) <br/>- Ejecutar examen antivirus <br/>- Detener y poner en cuarentena      |- Dirección URL de bloqueo (hora de hacer clic)<br/>- Eliminar mensajes de correo electrónico o clústeres<br/>- Correo electrónico en cuarentena<br/>- Poner en cuarentena datos adjuntos de correo electrónico<br/>- Desactivar el reenvío de correo externo          |

Las acciones de corrección, ya sean pendientes de aprobación o ya completadas, se pueden ver en el [Centro de acciones](m365d-action-center.md).

## <a name="remediation-actions-that-follow-automated-investigations"></a>Acciones de corrección que siguen investigaciones automatizadas

Cuando se completa una investigación automatizada, se llega a un veredicto para cada elemento de prueba implicado. Según el veredicto, se identifican las acciones de corrección. En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación. Todo depende de cómo se configure [la investigación automatizada y la respuesta](m365d-configure-auto-investigation-response.md).

En la tabla siguiente se muestran los posibles resultados:

| Veredicto    | Área    | Resultados|
|------|------|------|
| Malintencionado    | Dispositivos (puntos de conexión)    | Las acciones de corrección se toman automáticamente [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) (suponiendo que los grupos de dispositivos de la organización estén establecidos en **Full - remediar las amenazas automáticamente)**|
| Malintencionado    | Contenido de correo electrónico (URL y datos adjuntos) | Acciones de corrección recomendadas pendientes de aprobación|
| Sospechoso    | Dispositivos o contenido de correo electrónico | Acciones de corrección recomendadas pendientes de aprobación|
| No se encontraron amenazas    | Dispositivos o contenido de correo electrónico    | No es necesario realizar ninguna acción correctiva|


## <a name="remediation-actions-that-are-taken-manually"></a>Acciones de corrección que se toman manualmente

Además de las acciones de corrección que siguen investigaciones automatizadas, el equipo de operaciones de seguridad puede realizar determinadas acciones de corrección manualmente. Entre ellas se incluyen las siguientes acciones:

- Acción manual del dispositivo, como aislamiento del dispositivo o cuarentena de archivos.
- Acción de correo electrónico manual, como la eliminación de mensajes de correo electrónico. 
- [Acción de búsqueda](../defender-endpoint/advanced-hunting-overview.md) avanzada en dispositivos o correo electrónico.
- [Acción](../office-365-security/threat-explorer.md) del explorador en el contenido de correo electrónico, como mover el correo electrónico a correo no deseado, eliminar correo electrónico de forma suave o eliminar correo electrónico de forma permanente.
- Acción [de respuesta en](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) directo manual, como eliminar un archivo, detener un proceso y quitar una tarea programada.
- Acción de respuesta en directo con [Microsoft Defender para](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)API de punto de conexión, como aislar un dispositivo, ejecutar un examen antivirus y obtener información sobre un archivo. 

## <a name="next-steps"></a>Siguientes pasos

- [Visite el Centro de actividades](m365d-action-center.md)
- [Ver y administrar acciones de corrección]( m365d-autoir-actions.md)
- [Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta](m365d-autoir-report-false-positives-negatives.md)
