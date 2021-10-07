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
ms.openlocfilehash: 747cfe06ef69703a9baf7bd360935c364b3c7832
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213186"
---
# <a name="windows-security-updates-report"></a>Informe de actualizaciones de seguridad de Windows

En este informe se proporciona información general sobre el progreso de la implementación de una actualización de Windows de seguridad para los dispositivos Escritorio administrado de Microsoft dispositivos. Al principio de cada ciclo de lanzamiento de actualización de seguridad,  Escritorio administrado de Microsoft toma una instantánea de todos los dispositivos con un estado de dispositivo activo y establece su destino de implementación en el 95 % de esa población. El gráfico muestra el progreso de la implementación de una fecha de lanzamiento seleccionada en comparación con la Escritorio administrado de Microsoft promedio. Mientras nos centramos en la población activa, también puedes  pivotar este informe para mostrar las poblaciones de dispositivos **activos +** sincronizados y no sincronizados. Puedes ver el progreso de la implementación de versiones anteriores cambiando los filtros disponibles, pero los detalles del nivel de dispositivo solo están disponibles para la versión actual. La información del dispositivo que se puede ver en la tabla que sigue al gráfico también se puede exportar para el análisis sin conexión.

:::image type="content" source="../../media/mmd-security-updates.png" alt-text="Informe que muestra el progreso de la instalación de actualización con el tiempo en la parte superior izquierda, filtra en la parte superior derecha con un botón para generar el informe y tabla de detalles del informe a lo largo de la parte inferior":::

Normalmente, Microsoft publica actualizaciones de seguridad cada segundo martes del mes, aunque pueden publicarse en otras ocasiones cuando sea necesario. Cada versión agrega actualizaciones importantes para vulnerabilidades de seguridad conocidas. Escritorio administrado de Microsoft garantiza que el 95 % de sus dispositivos activos se actualicen con la última actualización de seguridad disponible cada mes. Cuando las actualizaciones de seguridad se lanzan en otras ocasiones para abordar de forma urgente nuevas amenazas, Escritorio administrado de Microsoft las implementa de forma similar. Categorizamos el estado de las versiones de actualización de seguridad con estos términos: 

- **Actual:** dispositivos que ejecutan la actualización publicada en el mes actual 
- **Anterior:** dispositivos que ejecutan la actualización que se publicó en el mes anterior 
- **Anterior:** dispositivos que ejecutan cualquier actualización de seguridad publicada antes del mes anterior 

Solo debe haber unos pocos dispositivos en la **categoría Anterior.** Una población mayor **o** creciente probablemente indica un problema sistémico que debe informar a Escritorio administrado de Microsoft para que podamos investigar. 