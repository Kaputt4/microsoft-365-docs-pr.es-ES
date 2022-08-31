---
title: Investigación de incidentes de pérdida de datos con Microsoft 365 Defender
description: Investigar la pérdida de datos en Microsoft 365 Defender.
keywords: Prevención de pérdida de datos, incidentes, alertas, investigación, análisis, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365
f1.keywords:
- NOCSH
ms.service: microsoft-365-security
ms.subservice: m365d
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
ms.openlocfilehash: 275a05db866de90eada1d948fff9fe559502d45f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67474542"
---
# <a name="investigate-data-loss-incidents-with-microsoft-365-defender"></a>Investigación de incidentes de pérdida de datos con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Los incidentes de Prevención de pérdida de datos de Microsoft Purview (DLP) ahora se pueden administrar en el portal de Microsoft 365 Defender. Puede administrar incidentes DLP junto con incidentes de seguridad de **Incidentes & alertas** \> **Incidentes** en el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. En esta página, puede hacer lo siguiente:

- Vea todas las alertas DLP agrupadas en incidentes en la cola de incidentes de Microsoft 365 Defender.
- Visualización de alertas correlacionadas entre soluciones inteligentes (DLP-MDE, DLP-MDO) y entre soluciones (DLP-DLP) en un único incidente.
- Busque registros de cumplimiento junto con la seguridad en Búsqueda avanzada.
- Acciones de corrección del administrador local en el usuario, el archivo y el dispositivo. 
- Asocie etiquetas personalizadas a incidentes DLP y filtre por ellos.
- Filtre por nombre de directiva DLP, etiqueta, fecha, origen del servicio, estado de incidente y usuario en la cola de incidentes unificada. 

También puede usar el conector de Microsoft 365 Defender en Microsoft Sentinel para extraer incidentes DLP junto con eventos y pruebas en Microsoft Sentinel para su investigación y corrección.

## <a name="licensing-requirements"></a>Requisitos de licencias

Para investigar Prevención de pérdida de datos de Microsoft Purview incidentes en el portal de Microsoft 365 Defender, necesita una licencia de una de las siguientes suscripciones: 

- Microsoft Office 365 E5/A5
- Microsoft 365 (E5/A5)
- Cumplimiento de Microsoft 365 E5/A5 
- Seguridad de Microsoft 365 E5/A5
- Gobernanza e Information Protection de Microsoft 365 E5/A5

> [!NOTE] 
> Cuando tenga licencia y sea apto para esta característica, las alertas DLP fluirán automáticamente a Microsoft 365 Defender. Abra un caso de soporte técnico si desea deshabilitar esta característica. 

## <a name="dlp-investigation-experience-in-the-microsoft-365-defender-portal"></a>Experiencia de investigación dlp en el portal de Microsoft 365 Defender

Antes de empezar, [active las alertas de todas las directivas DLP](/microsoft-365/compliance/dlp-configure-view-alerts-policies#alert-configuration-experience) en el <a href="https://purview.microsoft.com" target="_blank">portal de cumplimiento Microsoft Purview</a>.

1. Vaya al portal de Microsoft 365 Defender y seleccione **Incidentes** en el menú de navegación izquierdo para abrir la página incidentes.

2. Seleccione **Filtros** en la parte superior derecha y elija **Origen de servicio: Prevención de pérdida de datos** para ver todos los incidentes con alertas DLP.

3. Busque el nombre de la directiva DLP de las alertas e incidentes que le interesan.

4. Para ver la página de resumen de incidentes, seleccione el incidente en la cola. De forma similar, seleccione la alerta para ver la página de alerta DLP.

5. Vea la **historia de alertas** para obtener más información sobre la directiva y los tipos de información confidencial detectados en la alerta. Seleccione el evento en la sección **Eventos relacionados** para ver los detalles de la actividad del usuario.

6. Vea el contenido confidencial coincidente en la pestaña **Tipos de información confidencial** y el contenido del archivo en la pestaña **Origen** si tiene el permiso necesario (consulte los detalles <a href="/microsoft-365/compliance/dlp-alerts-dashboard-get-started#roles" target="_blank">aquí</a>).

7. También puede usar la búsqueda avanzada para buscar en registros de auditoría de usuarios, archivos y ubicaciones de sitio para la investigación. La tabla **CloudAppEvents** contiene todos los registros de auditoría en todas las ubicaciones, como SharePoint, OneDrive, Exchange y Dispositivos.

8. También puede descargar el correo electrónico seleccionando **Acciones** \> **Descargar correo electrónico**. 

9. Para las acciones de corrección en archivos en sitios de SPO o ODB, puede ver acciones como:

    - Aplicar etiqueta de retención
    - Aplicar etiqueta de confidencialidad
    - No compartir archivo
    - Delete

   Para las acciones de corrección, seleccione la **tarjeta Usuario** en la parte superior de la página de alertas para abrir los detalles del usuario.

   En Alertas DLP de dispositivos, seleccione la tarjeta del dispositivo en la parte superior de la página de alertas para ver los detalles del dispositivo y realizar acciones de corrección en el dispositivo.

10. Vaya a la página resumen de incidentes y seleccione **Administrar incidente** para agregar etiquetas de incidente, asignar o resolver un incidente.

## <a name="dlp-investigation-experience-in-microsoft-sentinel"></a>Experiencia de investigación dlp en Microsoft Sentinel

Puede usar el conector de Microsoft 365 Defender en Microsoft Sentinel para importar todos los incidentes DLP a Sentinel con el fin de ampliar la correlación, la detección y la investigación entre otros orígenes de datos y ampliar los flujos de orquestación automatizados mediante las funcionalidades soar nativas de Sentinel. 

1. Siga las instrucciones de Conexión de datos de Microsoft 365 Defender a Microsoft Sentinel para importar todos los incidentes, incluidos los incidentes y alertas DLP, a Sentinel. Habilite `CloudAppEvents` el conector de eventos para extraer todos los registros de auditoría de O365 en Sentinel.

   Debería poder ver los incidentes DLP en Sentinel una vez configurado el conector anterior.

2. Seleccione **Alertas** para ver la página de alertas.

3. Puede usar **AlertType**, **startTime** y **endTime** para consultar la tabla **CloudAppEvents** para obtener todas las actividades de usuario que contribuyeron a la alerta. Use esta consulta para identificar las actividades subyacentes:

```kusto
let Alert = SecurityAlert
| where TimeGenerated > ago(30d)
| where SystemAlertId == ""; // insert the systemAlertID here
CloudAppEvents
| extend correlationId1 = parse_json(tostring(RawEventData.Data)).cid
| extend correlationId = tostring(correlationId1)
| join kind=inner Alert on $left.correlationId == $right.AlertType
| where RawEventData.CreationTime > StartTime and RawEventData.CreationTime < EndTime
```

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)
