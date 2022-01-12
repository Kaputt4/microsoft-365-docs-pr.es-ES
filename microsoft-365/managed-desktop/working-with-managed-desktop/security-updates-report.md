---
title: Informe de actualizaciones de seguridad de Windows
description: Explica la información presentada en este informe
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 498330ffdf791a0688b9d6bfad432ba5ebea3b2a
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61935818"
---
# <a name="windows-security-updates-report"></a>Informe de actualizaciones de seguridad de Windows

Este informe proporciona información general sobre el progreso de la implementación de una actualización Windows seguridad de los dispositivos de Escritorio administrado de Microsoft. Al principio de cada ciclo de lanzamiento de actualización de seguridad, Microsoft Managed Desktop toma una instantánea de todos los dispositivos inscritos. El destino de implementación se establece en el 95 % de **los dispositivos activos** de esa población. El gráfico muestra el progreso de la implementación de una fecha de lanzamiento seleccionada en comparación con el promedio de Escritorio administrado de Microsoft. Mientras nos centramos en la población activa, también puedes  pivotar este informe para mostrar las poblaciones de dispositivos **activos +** sincronizados y no sincronizados. Puedes ver el progreso de la implementación de versiones anteriores cambiando los filtros disponibles, pero los detalles del nivel de dispositivo solo están disponibles para la versión actual. La información del dispositivo que se puede ver en la tabla que sigue al gráfico también se puede exportar para el análisis sin conexión.

:::image type="content" source="../../media/mmd-security-updates.png" alt-text="Informe que muestra el progreso de la instalación de actualización con el tiempo en la parte superior izquierda, filtra en la parte superior derecha con un botón para generar el informe y tabla de detalles del informe a lo largo de la parte inferior":::

Normalmente, Microsoft publica actualizaciones de seguridad cada segundo martes del mes, aunque pueden publicarse en otras ocasiones cuando sea necesario. Cada versión agrega actualizaciones importantes para vulnerabilidades de seguridad conocidas. Microsoft Managed Desktop garantiza que el 95 % de sus dispositivos activos se actualicen con la última actualización de seguridad disponible cada mes. Cuando las actualizaciones de seguridad se lanzan en otras ocasiones para abordar con urgencia nuevas amenazas, Microsoft Managed Desktop implementa estas actualizaciones de forma similar. Categorizamos el estado de las versiones de actualización de seguridad con estos términos: 

- **Actual:** dispositivos que ejecutan la actualización publicada en el mes actual 
- **Anterior:** dispositivos que ejecutan la actualización que se publicó en el mes anterior 
- **Anterior:** dispositivos que ejecutan cualquier actualización de seguridad publicada antes del mes anterior 

Solo debe haber unos pocos dispositivos en la **categoría Anterior.** Una población mayor **o** creciente probablemente indica un problema sistémico que debe informar a Microsoft Managed Desktop para que podamos investigar. 
