---
title: Visite el Centro de acciones para ver acciones de corrección
description: Usar el centro de acción para ver detalles y resultados después de una investigación automatizada
keywords: acción, centro, autoir, automatizado, investigación, respuesta, corrección
ms.prod: m365-security
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
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: 3cd45506601202a4a1bd5a400eeb51a0e07cecc0
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473043"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Visite el Centro de acciones para ver acciones de corrección

Durante y después de una investigación automatizada, se identifican las acciones de corrección para las detecciones de amenazas. Según la amenaza en particular y la configuración de [Microsoft Defender para](/windows/security/threat-protection) endpoint para su organización, algunas acciones de corrección se toman automáticamente y otras requieren aprobación. Si forma parte del equipo de operaciones de seguridad de su organización, puede ver las acciones de corrección pendientes y completadas [en el](manage-auto-investigation.md#remediation-actions) **Centro de acciones**.


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(¡NUEVO!) Un centro de acción unificado


Nos complace anunciar un nuevo centro de acción unificado ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Página del Centro de acciones en el portal de Microsoft 365 Defender web" lightbox="images/mde-action-center-unified.png":::

En la tabla siguiente se compara el nuevo centro de acciones unificado con el centro de acciones anterior.

|El nuevo centro de acciones unificado  |El centro de acciones anterior  |
|---------|---------|
|Enumera las acciones pendientes y completadas para dispositivos y correo electrónico en una ubicación <br/>([Microsoft Defender para Endpoint](microsoft-defender-endpoint.md) más [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/office-365-atp))|Enumera las acciones pendientes y completadas para dispositivos <br/> ([Solo Microsoft Defender para punto de](microsoft-defender-endpoint.md) conexión)   |
|Se encuentra en:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Se encuentra en:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender</a>, elija **Centro de acciones**. <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Panel de navegación al Centro de acciones en el portal de Microsoft 365 Defender web" lightbox="images/action-center-nav-new.png"::: | En el portal Microsoft 365 Defender, elija **Centro de investigaciones automatizadas** > **.** <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Una versión anterior del panel de navegación al Centro de acciones en el portal Microsoft 365 Defender navegación" lightbox="images/action-center-nav-old.png":::  |

El Centro de acción unificado reúne acciones de corrección en Defender para Endpoint y Defender para Office 365. Define un lenguaje común para todas las acciones de corrección y proporciona una experiencia de investigación unificada.

Puede usar el Centro de acciones unificado si tiene los permisos adecuados y una o varias de las siguientes suscripciones:

- [Defender para punto de conexión](microsoft-defender-endpoint.md)
- [Defender para Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection)

> [!TIP]
> Para obtener más información, consulte [Requisitos](/microsoft-365/security/mtp/prerequisites).

## <a name="using-the-action-center"></a>Uso del Centro de acciones

Para llegar al Centro de acciones unificado en el portal de Microsoft 365 Defender mejorado:

1. Vaya al portal <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender e</a> inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**.

Cuando visita el Centro de acciones, verá dos pestañas: **Acciones pendientes** e **Historial**. En la tabla siguiente se resume lo que verá en cada pestaña:

|Pestaña|Descripción|
|---|---|
|**Pending**|Muestra una lista de acciones que requieren atención. Puede aprobar o rechazar acciones de una en una, o seleccionar varias acciones si tienen el mismo tipo de acción (como el **archivo de cuarentena**). <p> **SUGERENCIA**: Asegúrese de revisar y aprobar (o rechazar [)](manage-auto-investigation.md) las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan completarse de forma oportuna.|
|**Historial**|Sirve como registro de auditoría para las acciones que se han realizado, como: <ul><li>Acciones de corrección que se realizaron como resultado de investigaciones automatizadas</li><li>Acciones de corrección aprobadas por el equipo de operaciones de seguridad</li><li>Comandos que se ejecutaron y acciones de corrección que se aplicaron durante las sesiones de Live Response</li><li>Acciones de corrección realizadas por las características de protección contra amenazas en Antivirus de Microsoft Defender</li></ul> <p> Proporciona una forma de deshacer determinadas acciones (vea [Deshacer acciones completadas](manage-auto-investigation.md#undo-completed-actions)).|

Puede personalizar, ordenar, filtrar y exportar datos en el Centro de acciones.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="El Centro de acciones con columnas y filtros" lightbox="images/new-action-center-columnsfilters.png":::

- Seleccione un encabezado de columna para ordenar los elementos en orden ascendente o descendente.
- Use el filtro de período de tiempo para ver los datos del último día, semana, 30 días o 6 meses.
- Elija las columnas que desea ver.
- Especifique cuántos elementos se deben incluir en cada página de datos.
- Use filtros para ver solo los elementos que desea ver.
- Seleccione **Exportar** para exportar resultados a un .csv archivo.

## <a name="next-steps"></a>Siguientes pasos

- [Ver y aprobar acciones de corrección](manage-auto-investigation.md)
- [Consulta la guía interactiva: Investigar y corregir amenazas con Microsoft Defender para endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)

## <a name="see-also"></a>Vea también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
