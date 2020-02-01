---
title: Administrar incidentes en Protección contra amenazas de Microsoft
description: Obtenga información acerca de cómo asignar, actualizar el estado
keywords: incidente, incidentes, alertas, alertas correlacionadas, asignar, actualizar, estado, administrar, clasificación, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 46904323a1ec8f969355931f8b69a3ed0ebf4519
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600217"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>Administrar incidentes en Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La administración de incidentes es esencial para lidiar con las amenazas y poder contenerlas. En Protección contra amenazas de Microsoft, tiene acceso a la administración de incidentes en dispositivos, usuarios y buzones de correo. 


Para administrar los incidentes, seleccione un incidente en la **Cola de incidentes**. 

Puede editar el nombre del incidente, resolverlo, y establecer su clasificación y determinación. También puede asignarse el incidente a usted mismo, y agregarle etiquetas o comentarios.

En los casos en los que, durante la investigación, quiera pasar las alertas de un incidente a otro, también puede hacerlo desde la pestaña Alertas. Así, puede crear un incidente mayor o menor que incluya todas las alertas relevantes.

## <a name="edit-incident-name"></a>Editar el nombre del incidente
De forma predeterminada, un incidente tiene asignado un número. Puede modificar el nombre del incidente para adecuarlo al sistema de nomenclatura que prefiera.
 
## <a name="assign-incidents"></a>Asignar incidentes
Si aún no se ha asignado un incidente, puede seleccionar **Asignarme a mí** para asignarse el incidente a usted mismo. Esta asignación no incluye solo el incidente, sino también todas las alertas asociadas a él.

## <a name="set-status-and-classification"></a>Establecer estado y clasificación
### <a name="incident-status"></a>Estado del incidente
Puede categorizar los incidentes (por ejemplo, como **Activo** o **Resuelto**) cambiando su estado a medida que progresa la investigación. Esto le ayuda a organizar y administrar la forma en que su equipo puede responder a incidencias.

Por ejemplo, su analista de SOC puede revisar los incidentes de urgencia clasificados como **Activo** durante el día y decidir asignárselos a sí mismo para investigarlos.

O, si el incidente se ha corregido, el analista puede establecerlo como **Resuelto**. Al resolver un incidente, se cierran automáticamente todas las alertas relacionadas con él que permanecieran abiertas. 

### <a name="classification-and-determination"></a>Clasificación y determinación
Si lo desea, puede decidir no establecer ninguna clasificación o especificar si un incidente es verdadero o falso. Al hacerlo, su equipo podrá ver los patrones y obtener información. 

## <a name="add-comments"></a>Agregar comentarios
Puede agregar comentarios y ver eventos históricos de un incidente para comprobar los cambios ya realizados.

Siempre que se realice un cambio o comentario en una alerta, esta se registra en la sección Comentarios e historial.

Los comentarios agregados aparecen al instante en el panel.

## <a name="add-incident-tags"></a>Agregar etiquetas de incidente
Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidencias con características comunes. Posteriormente, puede filtrar la cola de incidentes para ver los incidentes que tengan una etiqueta específica.

