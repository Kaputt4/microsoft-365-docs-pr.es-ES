---
title: Visite el Centro de acciones para ver acciones de corrección
description: Usar el centro de acción para ver detalles y resultados después de una investigación automatizada
keywords: acción, centro, autoir, automatizado, investigación, respuesta, corrección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: 6caa1cfe08a20aa824d85966c104a25988b8be53
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165362"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Visite el Centro de acciones para ver acciones de corrección

Durante y después de una investigación automatizada, se identifican las acciones de corrección para las detecciones de amenazas. Según la amenaza en particular y la configuración de [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) endpoint para su organización, algunas acciones de corrección se toman automáticamente y otras requieren aprobación. Si forma parte del equipo de operaciones de seguridad de su organización, puede ver las acciones de corrección pendientes y completadas [en](manage-auto-investigation.md#remediation-actions) el Centro **de acciones**. 


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(¡NUEVO!) Un centro de acción unificado


Nos complace anunciar un nuevo centro de acción unificado ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Centro de acciones en el Centro de seguridad de Microsoft 365":::

En la tabla siguiente se compara el nuevo centro de acciones unificado con el centro de acciones anterior.

|El nuevo centro de acciones unificado  |El centro de acciones anterior  |
|---------|---------|
|Enumera las acciones pendientes y completadas para dispositivos y correo electrónico en una ubicación <br/>([Microsoft Defender para Endpoint](microsoft-defender-advanced-threat-protection.md) más Microsoft Defender para Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))|Enumera las acciones pendientes y completadas para dispositivos <br/> ([Solo Microsoft Defender para punto de](microsoft-defender-advanced-threat-protection.md) conexión)   |
|Se encuentra en:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Se encuentra en:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| En el Centro de seguridad de Microsoft 365, elija **Centro de acciones**. <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navegar al Centro de acciones en el Centro de seguridad de Microsoft 365"::: | En el Centro de seguridad de Microsoft Defender, elija **Centro de acciones de investigaciones automatizadas.**  >   <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navegar al Centro de acciones desde el Centro de seguridad de Microsoft Defender":::  |

El Centro de acción unificado reúne acciones de corrección en Defender para Endpoint y Defender para Office 365. Define un lenguaje común para todas las acciones de corrección y proporciona una experiencia de investigación unificada. 

Puede usar el Centro de acciones unificado si tiene los permisos adecuados y una o varias de las siguientes suscripciones:
- [Defender para punto de conexión](microsoft-defender-advanced-threat-protection.md)
- [Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Para obtener más información, vea [Requisitos](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).

## <a name="using-the-action-center"></a>Uso del Centro de acciones

Para llegar al Centro de acciones unificado en el centro de seguridad mejorado de Microsoft 365:
1. Vaya al Centro de seguridad de Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.
2. En el panel de navegación, seleccione **Centro de acciones**. 

Al visitar el Centro de acciones, verá dos pestañas: **Acciones pendientes** e **Historial**. En la tabla siguiente se resume lo que verá en cada pestaña:

|Pestaña  |Descripción  |
|---------|---------|
|**Pending**     | Muestra una lista de acciones que requieren atención. Puede aprobar o rechazar acciones de una en una, o seleccionar varias acciones si tienen el mismo tipo de acción (como el **archivo en cuarentena).** <br/>**SUGERENCIA:** Asegúrese de revisar y aprobar [(o rechazar)](manage-auto-investigation.md) las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan completarse de forma oportuna. |
|**Historial**     | Sirve como registro de auditoría para las acciones que se han realizado, como: <br/>- Acciones de corrección que se realizaron como resultado de investigaciones automatizadas <br>- Acciones de corrección aprobadas por el equipo de operaciones de seguridad  <br/>- Comandos que se ejecutaron y acciones de corrección que se aplicaron durante las sesiones de Live Response  <br/>- Acciones de corrección realizadas por las características de protección contra amenazas en Antivirus de Microsoft Defender  <p>Proporciona una forma de deshacer determinadas acciones (vea [Deshacer acciones completadas](manage-auto-investigation.md#undo-completed-actions)).       |

Puede personalizar, ordenar, filtrar y exportar datos en el Centro de acciones.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Columnas y filtros en el Centro de acciones":::

- Seleccione un encabezado de columna para ordenar los elementos en orden ascendente o descendente.
- Use el filtro de período de tiempo para ver los datos del último día, semana, 30 días o 6 meses.
- Elija las columnas que desea ver.
- Especifique cuántos elementos se deben incluir en cada página de datos.
- Use filtros para ver solo los elementos que desea ver.
- Seleccione **Exportar para** exportar resultados a un archivo .csv. 

## <a name="next-steps"></a>Pasos siguientes

- [Ver y aprobar acciones de corrección](manage-auto-investigation.md)
- [Consulta la guía interactiva: Investigar y corregir amenazas con Microsoft Defender para endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Ver también

- [Dirección de falsos positivos/negativos en Microsoft Defender para endpoint](defender-endpoint-false-positives-negatives.md)
