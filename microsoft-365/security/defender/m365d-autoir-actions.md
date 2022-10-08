---
title: Visualización y administración de acciones en el Centro de acciones
description: Uso del Centro de acciones para ver y administrar acciones de corrección
keywords: action, center, autoair, automated, investigation, response, remediation
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
ms.date: 07/27/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: 100a2615d6da0843414f3a2243696e3997e209ae
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68055378"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Visualización y administración de acciones en el Centro de acciones

**Se aplica a:**
- Microsoft 365 Defender

Las características de protección contra amenazas de Microsoft 365 Defender pueden dar lugar a ciertas acciones de corrección. Estos son algunos ejemplos:

- [Las investigaciones automatizadas](m365d-autoir.md) pueden dar lugar a acciones de corrección que se realizan automáticamente o esperan su aprobación.
- Antivirus, antimalware y otras características de protección contra amenazas pueden dar lugar a acciones de corrección, como bloquear un archivo, una dirección URL o un proceso, o enviar un artefacto a cuarentena.
- El equipo de operaciones de seguridad puede realizar acciones de corrección manualmente, como durante la [búsqueda avanzada](advanced-hunting-overview.md) o al investigar [alertas](investigate-alerts.md) o [incidentes](investigate-incidents.md).

> [!NOTE]
> Debe tener [los permisos adecuados](m365d-action-center.md#required-permissions-for-action-center-tasks) para aprobar o rechazar acciones de corrección. Para obtener más información, consulte los [requisitos previos](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).

Para ir al Centro de acciones, realice uno de los pasos siguientes:

- Vaya a [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center); o
- En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en la tarjeta de respuesta Investigación automatizada &, seleccione **Aprobar en el Centro de acciones**.

## <a name="review-pending-actions-in-the-action-center"></a>Revisar las acciones pendientes en el centro de actividades

Es importante aprobar (o rechazar) las acciones pendientes lo antes posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna. 

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En el Centro de acciones, en la pestaña **Pendiente** , seleccione un elemento de la lista. Se abre el panel flotante. Por ejemplo:

   :::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Opciones para aprobar o rechazar una acción" lightbox="../../media/air-actioncenter-itemselected.png":::

4. Revise la información del panel flotante y, a continuación, realice uno de los pasos siguientes:
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se realice una acción pendiente.
   - Seleccione **Ir a buscar** para ir a [Búsqueda avanzada](advanced-hunting-overview.md). 

## <a name="undo-completed-actions"></a>Deshacer acciones completadas

Si ha determinado que un dispositivo o un archivo no es una amenaza, puede deshacer las acciones de corrección que se realizaron, independientemente de si esas acciones se realizaron de forma automática o manual. En el Centro de acciones, en la pestaña **Historial** , puede deshacer cualquiera de las siguientes acciones:  

| Origen de la acción | Acciones admitidas |
|:---|:---|
| - Investigación automatizada <br/>- antivirus de Microsoft Defender <br/>- Acciones de respuesta manual | - Aislar el dispositivo <br/>- Restricción de la ejecución de código <br/>- Poner en cuarentena un archivo <br/>- Quitar una clave del registro <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada |

### <a name="undo-one-remediation-action"></a>Deshacer una acción de corrección

1. Vaya al Centro de acciones ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) e inicie sesión.

2. En la pestaña **Historial** , seleccione una acción que quiera deshacer.

3. En el panel del lado derecho de la pantalla, seleccione **Deshacer**.

### <a name="undo-multiple-remediation-actions"></a>Deshacer varias acciones de corrección

1. Vaya al Centro de acciones (https://security.microsoft.com/action-center) e inicie sesión.

2. En la pestaña **Historial** , seleccione las acciones que desea deshacer. Asegúrese de seleccionar elementos que tengan el mismo tipo de acción. Se abre un panel flotante.

3. En el panel flotante, seleccione **Deshacer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para quitar un archivo de la cuarentena en varios dispositivos 

1. Vaya al Centro de acciones ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) e inicie sesión.

2. En la pestaña **Historial** , seleccione un archivo que tenga un tipo de acción **de archivo de cuarentena** .

3. En el panel del lado derecho de la pantalla, seleccione **Aplicar a X más instancias de este archivo** y, a continuación, seleccione **Deshacer**.

## <a name="next-steps"></a>Pasos siguientes

- [Ver los detalles y los resultados de una investigación automatizada](m365d-autoir-results.md)
- [Dirección de falsos positivos o falsos negativos](m365d-autoir-report-false-positives-negatives.md)
