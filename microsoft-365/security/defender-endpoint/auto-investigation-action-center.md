---
title: Visite el Centro de acciones para ver las acciones de corrección.
description: Uso del centro de acciones para ver los detalles y los resultados después de una investigación automatizada
keywords: action, center, autoir, automated, investigation, response, remediation
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
search.appverid: met150
ms.openlocfilehash: 0a681c896ea01f98e1fa9cb176bc3e0580b9bf89
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67740146"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Visite el Centro de acciones para ver las acciones de corrección.

Durante y después de una investigación automatizada, se identifican las acciones de corrección para las detecciones de amenazas. En función de la amenaza en particular y de cómo [se configuren las funcionalidades automatizadas de investigación y corrección](configure-automated-investigations-remediation.md) para su organización, algunas acciones de corrección se realizan automáticamente y otras requieren aprobación. Si forma parte del equipo de operaciones de seguridad de la organización, puede ver [las acciones de corrección](manage-auto-investigation.md#remediation-actions) pendientes y completadas en el **Centro de acciones**.

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

## <a name="the-unified-action-center"></a>Centro de acciones unificado

Recientemente, se actualizó el Centro de acciones. Ahora tiene una experiencia unificada del Centro de acciones. Para acceder al Centro de acciones, vaya a [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) e inicie sesión.

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Página del Centro de acciones en el portal de Microsoft 365 Defender" lightbox="images/mde-action-center-unified.png":::

### <a name="whats-changed"></a>¿Qué ha cambiado?

En la tabla siguiente se compara el nuevo centro de acciones unificado con el centro de acciones anterior.

|El nuevo centro de acciones unificado  |Centro de acciones anterior  |
|---------|---------|
|Enumera las acciones pendientes y completadas para los dispositivos y el correo electrónico en una ubicación <br/>([Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md) más [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/office-365-atp))|Enumera las acciones pendientes y completadas para los dispositivos <br/> (solo [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md))   |
|Se encuentra en:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Se encuentra en:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, elija **Centro de acciones**. <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Panel de navegación al Centro de acciones en el portal de Microsoft 365 Defender" lightbox="images/action-center-nav-new.png"::: | En el portal de Microsoft 365 Defender, elija **Centro de** **acciones Investigaciones automatizadas** > . <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Una versión anterior del panel de navegación al Centro de acciones en el portal de Microsoft 365 Defender" lightbox="images/action-center-nav-old.png":::  |

El Centro de acciones unificado reúne acciones de corrección en Defender para punto de conexión y Defender para Office 365. Define un lenguaje común para todas las acciones de corrección y proporciona una experiencia de investigación unificada.

Puede usar el Centro de acciones unificado si tiene los permisos adecuados y una o varias de las siguientes suscripciones:

- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection)
- [Defender para punto de conexión](microsoft-defender-endpoint.md)
- [Defender para Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Defender para Empresas](../defender-business/mdb-overview.md)

## <a name="using-the-action-center"></a>Uso del Centro de acciones

Para acceder al centro de acciones unificado en el portal de Microsoft 365 Defender mejorado:

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> e inicie sesión.

2. En el panel de navegación, seleccione **Centro de acciones**.

3. Use las **pestañas Acciones pendientes** e **Historial** . En la tabla siguiente se resume lo que verá en cada pestaña:

   |Pestaña|Descripción|
   |---|---|
   |**Pending**|Muestra una lista de acciones que requieren atención. Puede aprobar o rechazar acciones de una en una, o seleccionar varias acciones si tienen el mismo tipo de acción (como el **archivo de cuarentena**). <p> **SUGERENCIA**: Asegúrese de [revisar y aprobar (o rechazar) las acciones pendientes](manage-auto-investigation.md) lo antes posible para que las investigaciones automatizadas puedan completarse de forma oportuna.|
   |**Historial**|Actúa como registro de auditoría para las acciones que se realizaron, como: <ul><li>Acciones de corrección que se realizaron como resultado de investigaciones automatizadas</li><li>Acciones de corrección aprobadas por el equipo de operaciones de seguridad</li><li>Comandos que se ejecutaron y acciones de corrección que se aplicaron durante las sesiones de live response</li><li>Acciones de corrección realizadas por las características de protección contra amenazas en el Antivirus de Microsoft Defender</li></ul> <p> Proporciona una manera de deshacer ciertas acciones (consulte [Deshacer acciones completadas](manage-auto-investigation.md#undo-completed-actions)).|

4. Para personalizar, ordenar, filtrar y exportar datos en el Centro de acciones, realice uno o varios de los pasos siguientes:

   :::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Centro de acciones con columnas y filtros" lightbox="images/new-action-center-columnsfilters.png":::

   - Seleccione un encabezado de columna para ordenar los elementos en orden ascendente o descendente.
   - Use el filtro de período de tiempo para ver los datos del último día, semana, 30 días o 6 meses.
   - Elija las columnas que desea ver.
   - Especifique cuántos elementos se van a incluir en cada página de datos.
   - Use filtros para ver solo los elementos que desea ver.
   - Seleccione **Exportar** para exportar los resultados a un archivo .csv.

## <a name="next-steps"></a>Pasos siguientes

- [Ver y aprobar acciones de corrección](manage-auto-investigation.md)
- [Consulte la guía interactiva: Investigación y corrección de amenazas con Microsoft Defender para punto de conexión](https://aka.ms/MDATP-IR-Interactive-Guide)

## <a name="see-also"></a>Vea también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
- [Comparación de características de seguridad en planes de Microsoft 365 para pequeñas y medianas empresas](../defender-business/compare-mdb-m365-plans.md)
