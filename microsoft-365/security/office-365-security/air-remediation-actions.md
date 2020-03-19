---
title: Acciones de corrección en Office 365 de investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga información sobre las acciones de corrección en la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836863"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Acciones de corrección tras una investigación automatizada en Office 365

## <a name="remediation-actions"></a>Acciones de corrección

La [funcionalidad de investigación y respuesta automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) en [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 incluyen determinadas acciones de corrección. Siempre que se ejecuta una investigación automatizada o se ha completado, normalmente verá una o más acciones de corrección que requieren la aprobación del equipo de operaciones de seguridad para continuar. 

En la tabla siguiente se resumen las acciones de corrección disponibles actualmente en ATP de Office 365. 

|Acción | Descripción |
|-----|-----|
|Bloquear URL (tiempo de clic) |Protege contra mensajes de correo electrónico y documentos que contienen direcciones URL malintencionadas. Esto permite el bloqueo de vínculos malintencionados y de todas las páginas web relacionadas a través de [vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) cuando el usuario hace clic en un vínculo de un archivo existente de Office o en un mensaje de correo electrónico anterior. |
|Correo electrónico de eliminación de software  |Eliminar de forma temporal los mensajes de correo electrónico específicos del buzón de un usuario. <br/>Un mensaje eliminado temporalmente se mueve a la carpeta elementos recuperables de un usuario y se conserva hasta que expira el período de retención de elementos eliminados. |
|Eliminación temporal de clústeres de correo electrónico  |Eliminar de forma temporal los mensajes de correo malintencionado que coinciden con una consulta de todos los buzones de los usuarios. <br/>Los mensajes eliminados temporalmente se mueven a la carpeta de elementos recuperables de los usuarios y se conservan hasta que expira el período de retención de elementos eliminados. |
|Desactivar el reenvío de correo externo |Quita una regla de reenvío de un buzón de correo del usuario final específico.|

> [!NOTE]
> En Office 365 ATP, no se realizan automáticamente acciones de corrección. Las acciones de corrección solo se realizan tras la aprobación del equipo de seguridad de la organización. 

## <a name="next-steps"></a>Siguientes pasos

- [Ver acciones de corrección pendientes o realizadas tras una investigación automatizada en Office 365](air-review-approve-pending-completed-actions.md)

- [Detalles y resultados de una investigación automatizada en Office 365](air-view-investigation-results.md)