---
title: Informe de citas virtuales del conector HCE de Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ''
description: Obtenga información sobre cómo usar el informe de citas virtuales del conector HCE de Teams en el Centro de administración de Microsoft Teams para obtener información general sobre el uso de citas virtuales integradas en HCE en su organización.
ms.openlocfilehash: 6ec3423df4b6cd094bd2cab07e44c06923ec58bf
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822672"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Informe de citas virtuales del conector HCE de Microsoft Teams

El informe de citas virtuales del conector de la historia clínica electrónica (HCE) de Microsoft Teams en el centro de administración de Microsoft Teams le ofrece una forma rápida y sencilla de ver el uso de las citas virtuales integradas en la HCE de Teams en su organización.

Para ver el informe, debe ser administrador global, administrador de Teams, lector global o lector de informes.

## <a name="view-the-report"></a>Ver el informe

Hay dos maneras de acceder y ver el informe en el Centro de administración de Teams.

- A través de la tarjeta de uso del conector [HCE](#the-ehr-connector-usage-card) en el panel
- Directamente eligiendo [**el conector de Citas Virtuales de HCE**](#the-teams-ehr-connector-virtual-appointments-report)**en Análisis e informes** > **Informes de uso** 

### <a name="the-ehr-connector-usage-card"></a>Tarjeta de uso del conector HCE

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, elija **Panel** y, a continuación, vaya a la tarjeta **citas virtuales del conector HCE**.

Aquí, obtendrá una vista rápida de la actividad de citas virtuales integradas en HCE de Teams por mes, incluidas las citas completadas, la asignación restante y si ha superado el límite mensual (en función de la licencia que tenga).

:::image type="content" source="media/ehr-connector-report-card.png" alt-text="Captura de pantalla de la tarjeta de uso del conector HCE en el panel del Centro de administración de Teams." lightbox="media/ehr-connector-report-card.png":::

Elija **Ver detalles** para ver los detalles del informe. Para comprar más licencias, elija **Comprar más**.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Informe de citas virtuales del conector HCE de Teams

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Análisis e informes** > **Informes de uso**.
1. En la pestaña **Ver informes**, elija **Citas virtuales del conector HCE** y un intervalo de fechas. A continuación, seleccione **Ejecutar informe**.

    :::image type="content" source="media/ehr-connector-report.png" alt-text="Captura de pantalla del informe Citas virtuales del conector HCE de Teams en el Centro de administración de Teams." lightbox="media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>Interpretar el informe

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Cada informe muestra la fecha en que se generó el informe y el intervalo de fechas que eligió.|
|**2**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. Tenga en cuenta que no verá las entradas de citas en las que un miembro del personal o un paciente no se han unido. <ul><li>**La hora de inicio (UTC)** es la fecha y hora en que un miembro del personal y un participante están en la cita.  </li> <li>**Duración** es la diferencia de hora entre la hora de inicio y el momento en que la última persona abandona la cita.</li> <li>**Principal** es el nombre del organizador de la reunión. <li>**Correo electrónico principal** es la dirección de correo electrónico del organizador de la reunión.</li> <li> **Departamento** es la información del departamento para la cita. Si la información no se muestra correctamente, póngase en contacto con el equipo de soporte técnico de HCE. Para la integración con Epic, asegúrese de que ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` forma parte del registro de integración del proveedor. </li></li> <li>**Asistentes** es el número total de miembros del personal y de participantes en la cita.</li> <li>**Dentro del límite** indica si la cita está dentro del límite de asignación. </li> </ul> |
|**3**   |Puede exportar el informe a un archivo CSV para su análisis sin conexión. Seleccione **Exportar a Excel** para descargar el informe. |
|**4**   |Seleccione **Filtro** para filtrar la vista de detalles del informe. |
|**5**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa. |
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas de la tabla |

> [!NOTE]
> Para obtener más análisis sobre las citas virtuales integradas en HCE de Teams, consulte el [informe de uso de visitas virtuales](virtual-visits-usage-report.md). Con el informe de uso de visitas virtuales, puede ver métricas clave, como el total de citas, el tiempo de espera en la sala de espera, la duración de las citas y las ausencias. Use esta información para obtener información sobre las tendencias de uso que le ayudarán a optimizar las citas virtuales para ofrecer mejores resultados empresariales.

## <a name="related-articles"></a>Artículos relacionados

- [Citas virtuales con Teams: integración en Cerner EHR](ehr-admin-cerner.md)
- [Citas virtuales con Teams: integración en Epic EHR](ehr-admin-epic.md) 
