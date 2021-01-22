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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932855"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Acciones de corrección en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Acciones de corrección

Durante y después de una investigación automatizada en Microsoft 365 Defender, se identifican las acciones correctivas para elementos malintencionados o sospechosos. Algunos tipos de acciones de corrección se toman en dispositivos, también denominados puntos de conexión. Otras acciones de corrección se toman en el contenido del correo electrónico. Las investigaciones automatizadas se completan después de tomar, aprobar o rechazar las medidas correctivas.

> [!IMPORTANT]
> Si las acciones de corrección se toman automáticamente o solo en función de la aprobación depende de determinadas configuraciones, como la forma en que los niveles de automatización. Para obtener más información, consulte los artículos siguientes:
> - [Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Cómo se corrigen las amenazas en los dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Amenazas y acciones correctivas en el correo electrónico & contenido de colaboración](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

En la tabla siguiente se resumen las acciones de corrección que se admiten actualmente en Microsoft 365 Defender: 

|Acciones de corrección del dispositivo (punto de conexión)  |Acciones de corrección de correo electrónico  |
|---------|---------|
|- Recopilar paquete de investigación <br/>- Aislar el dispositivo (esta acción se puede deshacer)<br/>- Equipo de bajada <br/>- Ejecución de código de lanzamiento <br/>- Liberar de cuarentena <br/>- Ejemplo de solicitud <br/>- Restringir la ejecución de código (esta acción se puede deshacer) <br/>- Ejecutar examen antivirus <br/>- Detener y poner en cuarentena      |- Bloquear dirección URL (tiempo de clic)<br/>- Eliminar mensajes de correo electrónico o clústeres de forma flexible<br/>- Cuarentena de correo electrónico<br/>- Poner en cuarentena datos adjuntos de correo electrónico<br/>- Desactivar el reenvío de correo externo          |

Las acciones de corrección, ya sean pendientes de aprobación o ya completadas, se pueden ver en el [Centro de actividades.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Acciones de corrección que siguen investigaciones automatizadas

Cuando se completa una investigación automatizada, se llega a un veredicto para cada evidencia implicada. Según el veredicto, se identifican las acciones correctivas. En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación. Todo depende de cómo se configure [la investigación y respuesta automatizadas.](mtp-configure-auto-investigation-response.md)

En la tabla siguiente se muestran los posibles resultados:

| Veredicto    | Área    | Resultados|
|------|------|------|
| Malintencionado    | Dispositivos (puntos de conexión)    | Las acciones de corrección se toman automáticamente [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) (suponiendo que los grupos de dispositivos de la organización estén establecidos en Completo: corregir **las amenazas automáticamente)**|
| Malintencionado    | Contenido de correo electrónico (URL y datos adjuntos) | Acciones de corrección recomendadas pendientes de aprobación|
| Sospechoso    | Dispositivos o contenido de correo electrónico | Acciones de corrección recomendadas pendientes de aprobación|
| No se encontraron amenazas    | Dispositivos o contenido de correo electrónico    | No es necesario realizar ninguna acción correctiva|


## <a name="remediation-actions-that-are-taken-manually"></a>Acciones de corrección que se toman manualmente

Además de las acciones de corrección que siguen investigaciones automatizadas, el equipo de operaciones de seguridad puede realizar determinadas acciones de corrección manualmente. Entre ellas se incluyen las siguientes acciones:

- Acción manual del dispositivo, como aislamiento de dispositivos o cuarentena de archivos.
- Acción de correo electrónico manual, como la eliminación de mensajes de correo electrónico de forma flexible. 
- [Acción de búsqueda](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) avanzada en dispositivos o correo electrónico.
- [Acción](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) del explorador en el contenido del correo electrónico, como mover correo electrónico a correo no deseado, eliminar correo electrónico de forma flexible o eliminar correo electrónico de forma permanente.
- Acción [de respuesta en](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) directo manual, como eliminar un archivo, detener un proceso y quitar una tarea programada.
- Acción de respuesta en directo con [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)para las API de punto de conexión, como aislar un dispositivo, ejecutar un examen antivirus y obtener información sobre un archivo. 

## <a name="next-steps"></a>Siguientes pasos

- [Visite el Centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Aprobar o rechazar acciones pendientes](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Controlar falsos positivos/negativos en las capacidades automatizadas de investigación y respuesta](mtp-autoir-report-false-positives-negatives.md)
