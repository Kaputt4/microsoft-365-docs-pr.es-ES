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
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261057"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Acciones de corrección tras una investigación automatizada en Office 365

## <a name="remediation-actions"></a>Acciones de corrección

[Capacidades automatizadas de investigación y respuesta](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) en Office 365 Advanced Threat Protection incluye ciertas acciones de corrección. Siempre que se ejecuta una investigación automatizada o se ha completado, normalmente verá una o más acciones de corrección que requieren la aprobación del equipo de operaciones de seguridad para continuar. En la tabla siguiente se resumen las acciones de corrección disponibles actualmente en la protección contra amenazas avanzada de Office 365. 

|Acción | Descripción |
|-----|-----|
|Bloquear URL (tiempo de clic) |Protéjase contra mensajes de correo electrónico y documentos que contienen direcciones URL malintencionadas. Esto permite el bloqueo de vínculos malintencionados y de todas las páginas web relacionadas a través de [vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) cuando el usuario hace clic en un vínculo de un archivo existente de Office o en un mensaje de correo electrónico anterior. |
|Correo electrónico de eliminación de software  |Eliminar temporalmente mensajes de correo electrónico específicos del buzón de un usuario|
|Eliminación temporal de clústeres de correo electrónico  |Eliminación temporal de mensajes de correo malintencionado que coinciden con una consulta de los buzones de todos los usuarios|
|Desactivar el reenvío de correo externo |Quita la regla de reenvío del buzón de un usuario final específico.|

## <a name="approve-or-reject-pending-actions"></a>Aprobar (o rechazar) acciones pendientes

![Página de acción de investigaciones de aire](../../media/air-investigationactionspage.png)

Mientras ve los [detalles de una investigación](air-view-investigation-results.md), puede aprobar o rechazar cualquier acción de corrección pendiente. Le recomendamos hacerlo tan pronto como sea posible para que las investigaciones automatizadas se completen.

> [!IMPORTANT]
> Es necesario disponer de los permisos adecuados para aprobar o rechazar acciones de corrección. Consulte [permisos necesarios para usar la funcionalidad de Air](office-365-air.md#required-permissions-to-use-air-capabilities).

1. Seleccione la ficha **acciones** .

2. Seleccione un elemento de la lista. (Esto activa los botones aprobar y rechazar).

3. Revise la información disponible de los elementos seleccionados y, a continuación, apruebe o rechace las acciones. 
 - **APPROVE** permite que se inicie la corrección.
 - **Rechazar** no realiza ninguna acción adicional

## <a name="next-steps"></a>Pasos siguientes

- [Información sobre la guía de seguridad de usuario comprometida](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [Ver los informes de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)