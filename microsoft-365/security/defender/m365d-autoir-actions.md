---
title: Ver y administrar acciones en el Centro de acciones
description: Usar el Centro de acciones para ver y administrar acciones de corrección
keywords: action, center, autoair, automated, investigation, response, remediation
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 9e82f1c5de9fe1f4a03385458338edf18c4f35bd
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538848"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Ver y administrar acciones en el Centro de acciones

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Las características de protección contra amenazas de Microsoft 365 Defender pueden dar lugar a determinadas acciones de corrección. Estos son algunos ejemplos:

- [Las investigaciones automatizadas](m365d-autoir.md) pueden dar como resultado acciones de corrección que se toman automáticamente o esperar su aprobación.
- Antivirus, antimalware y otras características de protección contra amenazas pueden provocar acciones de corrección, como bloquear un archivo, una dirección URL o un proceso, o enviar un artefacto a la cuarentena.
- El equipo de operaciones de seguridad puede realizar [](advanced-hunting-overview.md) acciones de corrección manualmente, como durante la búsqueda avanzada o al investigar [alertas](investigate-alerts.md) [o incidentes.](investigate-incidents.md)

> [!NOTE]
> Debe tener los [permisos adecuados para](m365d-action-center.md#required-permissions-for-action-center-tasks) aprobar o rechazar acciones de corrección. Para obtener más información, vea los [requisitos previos](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).

## <a name="review-pending-actions-in-the-action-center"></a>Revisar acciones pendientes en el Centro de acciones

Es importante aprobar (o rechazar) las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna. 

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En el Centro de acciones, en la **pestaña** Pendiente, seleccione un elemento de la lista. Se abre el panel desplegable. Por ejemplo:

   ![Aprobar o rechazar una acción](../../media/air-actioncenter-itemselected.png)

4. Revise la información del panel desplegable y, a continuación, siga uno de los pasos siguientes:
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se haga una acción pendiente.
   - Seleccione **Ir a la búsqueda** para ir a Búsqueda [avanzada.](advanced-hunting-overview.md) 

## <a name="undo-completed-actions"></a>Deshacer acciones completadas

Si has determinado que un dispositivo o un archivo no es una amenaza, puedes deshacer las acciones de corrección que se realizaron, independientemente de si dichas acciones se realizaron de forma automática o manual. En el Centro de acciones, en la **ficha** Historial, puede deshacer cualquiera de las siguientes acciones:  

| Origen de la acción | Acciones admitidas |
|:---|:---|
| - Investigación automatizada <br/>- Antivirus de Microsoft Defender <br/>- Acciones de respuesta manuales | - Aislar dispositivo <br/>- Restringir la ejecución de código <br/>- Poner en cuarentena un archivo <br/>- Quitar una clave del Registro <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada |

### <a name="undo-one-remediation-action"></a>Deshacer una acción de corrección

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.

2. En la **pestaña** Historial, seleccione una acción que desee deshacer.

3. En el panel de la parte derecha de la pantalla, seleccione **Deshacer**.

### <a name="undo-multiple-remediation-actions"></a>Deshacer varias acciones de corrección

1. Vaya al Centro de acciones ( https://security.microsoft.com/action-center) e inicie sesión.

2. En la **pestaña** Historial, seleccione las acciones que desea deshacer. Asegúrese de seleccionar los elementos que tienen el mismo tipo de acción. Se abre un panel desplegable.

3. En el panel desplegable, seleccione **Deshacer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para quitar un archivo de la cuarentena en varios dispositivos 

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.

2. En la **pestaña Historial,** seleccione un archivo que tenga un tipo de acción **de archivo en** cuarentena.

3. En el panel de la parte derecha de la pantalla, seleccione **Aplicar a X más** instancias de este archivo y, a continuación, seleccione **Deshacer**.

## <a name="next-steps"></a>Pasos siguientes

- [Ver los detalles y los resultados de una investigación automatizada](m365d-autoir-results.md)
- [Dirección de falsos positivos o falsos negativos](m365d-autoir-report-false-positives-negatives.md)
