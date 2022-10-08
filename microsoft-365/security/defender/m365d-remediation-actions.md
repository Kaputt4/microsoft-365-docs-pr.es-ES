---
title: Acciones de corrección en Microsoft 365 Defender
description: Obtenga información general sobre las acciones de corrección que siguen las investigaciones automatizadas en Microsoft 365 Defender
keywords: automatizada, investigación, alerta, desencadenante, acción, corrección
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 6f1888505def4a4f7125f87dc19df4825e430bbe
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68064286"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Acciones de corrección en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Durante y después de una investigación automatizada en Microsoft 365 Defender, se identifican acciones de corrección para elementos malintencionados o sospechosos. Algunos tipos de acciones de corrección se realizan en los dispositivos, también conocidos como puntos de conexión. Otras acciones de corrección se realizan en identidades, cuentas y contenido de correo electrónico. Las investigaciones automatizadas se completan después de que se realicen, aprueben o rechacen las acciones de corrección.

> [!IMPORTANT]
> El hecho de que las acciones de corrección se realicen automáticamente o solo tras la aprobación depende de ciertas configuraciones, como los niveles de automatización. Para más información, consulte los artículos siguientes:
>
> - [Configuración de las funcionalidades automatizadas de investigación y respuesta en Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)
> - [Configuración de cuentas de acción en Microsoft Defender for Identity](/defender-for-identity/manage-action-accounts)
> - [Cómo se corrigen las amenazas en los dispositivos](../defender-endpoint/automated-investigations.md)
> - [Amenazas y acciones de corrección en el correo electrónico & contenido de colaboración](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

En la tabla siguiente se resumen las acciones de corrección que se admiten actualmente en Microsoft 365 Defender.

|Acciones de corrección del dispositivo (punto de conexión)  |Acciones de corrección de correo electrónico  |Usuarios (cuentas)  |
|:---------|:---------|----------|
|- Recopilación del paquete de investigación <br/>- Aislar el dispositivo (esta acción se puede deshacer)<br/>- Offboard machine <br/>- Ejecución de código de versión <br/>- Liberación de la cuarentena <br/>- Ejemplo de solicitud <br/>- Restringir la ejecución de código (esta acción se puede deshacer) <br/>- Ejecutar examen de antivirus <br/>- Detener y poner en cuarentena <br/>- Contener dispositivos de la red     |- Dirección URL de bloqueo (tiempo de clic)<br/>- Eliminación temporal de mensajes de correo electrónico o clústeres<br/>- Poner en cuarentena el correo electrónico<br/>- Poner en cuarentena los datos adjuntos de un correo electrónico<br/>- Desactivar el reenvío de correo externo          |- Deshabilitar usuario<br />- Restablecer contraseña de usuario<br />- Confirmación del usuario como en peligro          |

Las acciones de corrección, ya sean pendientes de aprobación o ya completadas, se pueden ver en el [Centro de acciones](m365d-action-center.md).

## <a name="remediation-actions-that-follow-automated-investigations"></a>Acciones de corrección que siguen investigaciones automatizadas

Cuando se completa una investigación automatizada, se llega a un veredicto por cada pieza de evidencia implicada. En función del veredicto, se identifican las acciones de corrección. En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación. Todo depende de cómo [se configure la investigación y la respuesta automatizadas](m365d-configure-auto-investigation-response.md).

En la tabla siguiente se muestran los posibles resultados:

| Veredicto    | Entidades afectadas    | Resultados|
|------|------|------|
| Malintencionado    | Dispositivos (puntos de conexión)    | Las acciones de corrección se realizan automáticamente (suponiendo que los [grupos de dispositivos](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) de la organización estén **establecidos en Completo: corrija las amenazas automáticamente**).|
| Comprometido | Usuarios | Las acciones de corrección se toman automáticamente |
| Malintencionado    | Contenido de correo electrónico (URL y datos adjuntos) | Acciones de corrección recomendadas pendientes de aprobación|
| Sospechoso    | Dispositivos o contenido de correo electrónico | Acciones de corrección recomendadas pendientes de aprobación|
| No se encontraron amenazas    | Dispositivos o contenido de correo electrónico    | No es necesario realizar ninguna acción correctiva|

## <a name="remediation-actions-that-are-taken-manually"></a>Acciones de corrección que se realizan manualmente

Además de las acciones de corrección que siguen las investigaciones automatizadas, el equipo de operaciones de seguridad puede realizar determinadas acciones de corrección manualmente. Entre ellas se incluyen las siguientes:

- Acción manual del dispositivo, como aislamiento de dispositivos o cuarentena de archivos
- Acción de correo electrónico manual, como la eliminación temporal de mensajes de correo electrónico
- Acción manual del usuario, como deshabilitar el usuario o restablecer la contraseña de usuario
- [Acción de búsqueda avanzada](../defender-endpoint/advanced-hunting-overview.md) en dispositivos, usuarios o correo electrónico
- [Acción del Explorador](../office-365-security/threat-explorer.md) en el contenido del correo electrónico, como mover correo electrónico a correo no deseado, eliminar correo electrónico temporalmente o eliminar correo electrónico de forma rígida
- Acción de [respuesta dinámica](/windows/security/threat-protection/microsoft-defender-atp/live-response) manual, como eliminar un archivo, detener un proceso y quitar una tarea programada
- Acción de respuesta en vivo con [Microsoft Defender para punto de conexión API](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), como aislar un dispositivo, ejecutar un examen antivirus y obtener información sobre un archivo

## <a name="next-steps"></a>Pasos siguientes

- [Visite el Centro de actividades](m365d-action-center.md)
- [Ver y aprobar acciones de corrección](m365d-autoir-actions.md)
- [Dirección de falsos positivos o falsos negativos](m365d-autoir-report-false-positives-negatives.md)
- [Contener dispositivos de la red](../defender-endpoint\respond-machine-alerts.md#contain-devices-from-the-network)
