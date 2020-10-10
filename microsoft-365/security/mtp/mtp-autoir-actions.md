---
title: Aprobar o rechazar acciones pendientes tras una investigación automatizada
description: Usar el centro de actividades para administrar acciones relacionadas con investigación y respuesta automatizadas
keywords: acción, centro, autoair, automatizado, investigación, respuesta, corrección
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
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 2e9e98fb69ed831a4a90c59ce26803a905625250
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413155"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Aprobar o rechazar acciones pendientes tras una investigación automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Cuando se ejecuta una investigación automatizada, puede resultar en una o más [acciones de corrección](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que requieran la aprobación para continuar. Por ejemplo, es posible que sea necesario eliminar un clúster de mensajes de correo electrónico o quitar un archivo en cuarentena. Es importante aprobar (o rechazar) acciones pendientes lo antes posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna. 

> [!TIP]
> Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber. Consulte [Cómo informar de falsos positivos/negativos en capacidades de investigación y respuesta automatizadas (Air) en la protección contra amenazas de Microsoft](mtp-autoir-report-false-positives-negatives.md).

Las acciones pendientes se pueden revisar y aprobar mediante el [centro de actividades](#review-a-pending-action-in-the-action-center) o la [vista detalles](#review-a-pending-action-in-the-investigation-details-view)de la investigación.

> [!NOTE]
> Debe tener [los permisos adecuados](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprobar o rechazar acciones de corrección.

## <a name="review-a-pending-action-in-the-action-center"></a>Revisar una acción pendiente en el centro de actividades

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En el centro de actividades, en la ficha **pendiente** , seleccione un elemento de la lista. 

    - Si selecciona un elemento en la columna **número de investigación** , se abrirá la página Detalles de la investigación. Allí puede ver los resultados de la investigación y, a continuación, aprobar o rechazar la acción recomendada.
 
    - Si selecciona una fila de la lista, se abre un control flotante, donde puede ver información sobre el elemento. <br/>![Aprobar o rechazar una acción](../../media/air-actioncenter-itemselected.png)<br/>Use los vínculos para ver una alerta asociada o una investigación y aprobar o rechazar la acción.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Revisar una acción pendiente en la vista detalles de la investigación

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

1. En una página de detalles de la [investigación](mtp-autoir-results.md) , seleccione la pestaña **acciones pendientes** (o **acciones**). Los elementos que están pendientes de aprobación se enumeran aquí.

2. Seleccione un elemento de la lista y, a continuación, elija **aprobar** o **rechazar**.

## <a name="next-steps"></a>Pasos siguientes

- [Ver los detalles y los resultados de una investigación automatizada](mtp-autoir-results.md)
- [Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta](mtp-autoir-report-false-positives-negatives.md)
