---
title: Acciones de corrección en investigación automatizada y funciones de respuesta de la protección contra amenazas de Microsoft
description: Obtenga información general sobre la investigación y respuesta automatizada en la Protección contra amenazas de Microsoft
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
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175967"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Acciones de corrección en investigación automatizada y funciones de respuesta de la protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

Las capacidades de investigación y respuesta automatizadas de Microsoft Threat Protection incluyen ciertas acciones de corrección. Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión. Otras acciones de corrección se realizan en el contenido del correo electrónico.

En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft: 

|Acciones de corrección de puntos de conexión  |Acciones de corrección de correo electrónico  |
|---------|---------|
|Poner archivo en cuarentena<br/>Eliminar clave del registro<br/>Terminar proceso <br/>Detener el servicio <br/>Eliminar clave del registro <br/>Deshabilitar controlador <br/>Eliminar tarea programada.      |Eliminar temporalmente mensajes de correo electrónico o clústeres<br/>Bloquear URL (tiempo de clic)<br/>Desactivar el reenvío de correo externo          |

Las acciones de corrección, tanto si están pendientes de aprobación como si ya están completas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="next-steps"></a>Siguientes pasos

- [Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Más información sobre el Centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
