---
title: Acciones de corrección en Microsoft 365 defender
description: Obtener información general sobre las acciones de corrección que siguen las investigaciones automatizadas en Microsoft 365 defender
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9e489e3b0100aa138b11d4bfb4ccc8048a2113f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683300"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Acciones de corrección en Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Acciones de corrección

Durante y después de una investigación automatizada en Microsoft 365 defender, se identifican las acciones de corrección para los elementos malintencionados o sospechosos. Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión. Otras acciones de corrección se realizan en el contenido del correo electrónico. Investigaciones automáticas completadas después de tomar, aprobar o rechazar acciones de corrección.

> [!IMPORTANT]
> El hecho de que las acciones de corrección se tomen automáticamente o solo después de la aprobación depende de determinadas opciones, como el nivel de automatización. Para obtener más información, vea los siguientes artículos:
> - [Configurar las capacidades de investigación y respuesta automatizadas en Microsoft 365 defender](mtp-configure-auto-investigation-response.md)
> - [Cómo se corrigen las amenazas en los dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Amenazas y acciones de corrección en el correo electrónico & contenido de colaboración](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

En la tabla siguiente se resumen las acciones de corrección que se admiten actualmente en Microsoft 365 defender: 

|Acciones de corrección de dispositivo (extremo)  |Acciones de corrección de correo electrónico  |
|---------|---------|
|-Recopilar un paquete de investigación <br/>-Isolater dispositivo (esta acción se puede deshacer)<br/>-Máquina desincorpora <br/>-Liberar la ejecución de código <br/>-Liberar de cuarentena <br/>Ejemplo de solicitud <br/>-Restringir la ejecución de código (esta acción se puede deshacer) <br/>-Ejecutar detección de virus <br/>-Detener y poner en cuarentena      |-Bloquear dirección URL (tiempo de clic)<br/>-Eliminación temporal de mensajes de correo electrónico o clústeres<br/>-Correo electrónico en cuarentena<br/>-Poner en cuarentena un archivo adjunto de correo electrónico<br/>-Desactivar el reenvío externo de correo          |

Las acciones de corrección, ya estén pendientes de aprobación o ya completadas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-that-follow-automated-investigations"></a>Acciones de corrección que siguen a investigaciones automatizadas

Cuando se completa una investigación automatizada, se alcanza un veredicto para cada fragmento de evidencia implicado. Según el veredicto, se identifican las acciones de corrección. En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación. Todo depende de cómo [esté configurada la investigación y la respuesta automatizadas](mtp-configure-auto-investigation-response.md).

En la tabla siguiente se muestran los posibles resultados:

| Veredicto    | Área    | Resultados|
|------|------|------|
| Malintencionado    | Dispositivos (puntos de conexión)    | Las acciones de corrección se realizan automáticamente (suponiendo que los [grupos de dispositivos](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) de la organización están configurados automáticamente para las amenazas de corrección **completa**)|
| Malintencionado    | Contenido de correo electrónico (URL y datos adjuntos) | Acciones de corrección recomendadas pendientes de aprobación|
| Sospechoso    | Dispositivos o contenido de correo electrónico | Acciones de corrección recomendadas pendientes de aprobación|
| No se encontraron amenazas    | Dispositivos o contenido de correo electrónico    | No es necesario realizar ninguna acción correctiva|


## <a name="remediation-actions-that-are-taken-manually"></a>Acciones de corrección que se realizan manualmente

Además de las acciones de corrección que siguen las investigaciones automatizadas, el equipo de operaciones de seguridad puede llevar a cabo determinadas acciones de corrección de forma manual. Se incluyen las siguientes acciones:

- Acción manual del dispositivo, como aislamiento de dispositivos o cuarentena de archivos.
- Acción manual del correo electrónico, como la eliminación temporal de mensajes de correo electrónico. 
- Acción de [búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) en dispositivos o correo electrónico.
- Acción del [Explorador](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) en el contenido de correo electrónico, como mover correo electrónico a correo no deseado, eliminar correo electrónico o eliminar correo electrónico de forma rígida.
- Acción de [respuesta automática](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) manual, como eliminar un archivo, detener un proceso y quitar una tarea programada.
- Acción de respuesta en directo con [Microsoft defender para las API de punto final](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), como aislar un dispositivo, ejecutar un análisis de antivirus y obtener información sobre un archivo. 

## <a name="next-steps"></a>Pasos siguientes

- [Visite el Centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Aprobar o rechazar acciones pendientes](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta](mtp-autoir-report-false-positives-negatives.md)
