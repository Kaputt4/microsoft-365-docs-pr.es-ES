---
title: Aprobar o rechazar acciones pendientes después de una investigación automatizada
description: Usar el Centro de actividades para administrar acciones relacionadas con la investigación y respuesta automatizadas
keywords: acción, centro, autoair, automatizado, investigación, respuesta, corrección
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
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930383"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Aprobar o rechazar acciones pendientes después de una investigación automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Cuando se ejecuta una investigación automatizada, puede dar como resultado una o más acciones de [corrección](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que requieren aprobación para continuar. Por ejemplo, es posible que sea necesario eliminar un clúster de mensajes de correo electrónico o que se deba quitar un archivo en cuarentena. Es importante aprobar (o rechazar) las acciones pendientes lo antes posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna. 

> [!TIP]
> Si cree que se ha perdido algo o que las características de investigación y respuesta automatizadas de Microsoft 365 Defender han detectado algo incorrectamente, háganoslo saber. Vea cómo informar de falsos positivos/negativos en las capacidades de investigación y respuesta [automatizada (AIR) en Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

Las acciones pendientes se pueden revisar y aprobar mediante el Centro [de actividades](#review-a-pending-action-in-the-action-center) o la vista de detalles de [la investigación.](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> Debe tener los [permisos adecuados para](mtp-action-center.md#required-permissions-for-action-center-tasks) aprobar o rechazar acciones correctivas. Para obtener más información, vea [Requisitos previos para la investigación automatizada y la respuesta en Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)

## <a name="review-a-pending-action-in-the-action-center"></a>Revisar una acción pendiente en el centro de actividades

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En el Centro de acciones, en la **pestaña** Pendiente, seleccione un elemento de la lista. 

    - Si selecciona un elemento en la columna **Número** de investigación, se abrirá la página de detalles de la investigación. Allí, puede ver los resultados de la investigación y, a continuación, aprobar o rechazar la acción recomendada.
 
    - Si selecciona una fila de la lista, se abrirá un menú desplegable, donde podrá ver información sobre ese elemento. <br/>![Aprobar o rechazar una acción](../../media/air-actioncenter-itemselected.png)<br/>Use los vínculos para ver una alerta asociada o una investigación, y aprobar o rechazar la acción.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Revisar una acción pendiente en la vista de detalles de la investigación

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

1. En una [página de detalles de](mtp-autoir-results.md) la investigación, seleccione la pestaña Acciones pendientes **(o** Acciones).  Los elementos que están pendientes de aprobación se enumeran aquí.

2. Seleccione un elemento de la lista y, a continuación, elija **Aprobar** o **Rechazar**.

## <a name="undo-completed-actions"></a>Deshacer acciones completadas

Si has determinado que un dispositivo o un archivo no es una amenaza, puedes deshacer las acciones de corrección que se realizaron, independientemente de si dichas acciones se realizaron de forma automática o manual. En el Centro de actividades, en la **ficha** Historial, puede deshacer cualquiera de las siguientes acciones:  

| Origen de la acción | Acciones admitidas |
|:---|:---|
| - Investigación automatizada <br/>- Antivirus de Microsoft Defender <br/>- Acciones de respuesta manuales | - Aislar dispositivo <br/>- Restringir la ejecución de código <br/>- Poner en cuarentena un archivo <br/>- Quitar una clave del Registro <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada |

### <a name="to-undo-a-remediation-action"></a>Para deshacer una acción de corrección

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.

2. En la **pestaña** Historial, seleccione una acción que desee deshacer.

3. En el panel del lado derecho de la pantalla, seleccione **Deshacer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para quitar un archivo de la cuarentena en varios dispositivos 

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.

2. En la **pestaña** Historial, seleccione un archivo que tenga el archivo de cuarentena de tipo **de acción.**

3. En el panel del lado derecho de la pantalla, seleccione Aplicar a **X más** instancias de este archivo y, a continuación, **seleccione Deshacer**.

## <a name="next-steps"></a>Siguientes pasos

- [Ver los detalles y los resultados de una investigación automatizada](mtp-autoir-results.md)
- [Controlar falsos positivos/negativos en las capacidades automatizadas de investigación y respuesta](mtp-autoir-report-false-positives-negatives.md)
