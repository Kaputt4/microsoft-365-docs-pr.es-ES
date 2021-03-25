---
title: Marcas de eventos de escala de tiempo de dispositivo de Microsoft Defender para punto de conexión
description: Usar Microsoft Defender para las marcas de eventos de escala de tiempo del dispositivo de punto de conexión para
keywords: Defender para la escala de tiempo del dispositivo de punto de conexión, marcas de evento
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165158"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Marcas de eventos de escala de tiempo de dispositivo de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Las marcas de eventos en la escala de tiempo del dispositivo Defender para endpoint te ayudan a filtrar y organizar eventos específicos cuando se investigan posibles ataques.

La escala de tiempo del dispositivo Defender for Endpoint proporciona una vista cronológica de los eventos y las alertas asociadas observadas en un dispositivo. Esta lista de eventos proporciona visibilidad completa de los eventos, archivos y direcciones IP observados en el dispositivo. La lista a veces puede ser larga. Las marcas de eventos de escala de tiempo del dispositivo te ayudan a realizar un seguimiento de los eventos que podrían estar relacionados. 

Después de pasar por una escala de tiempo del dispositivo, puedes ordenar, filtrar y exportar los eventos específicos marcados.

Al navegar por la escala de tiempo del dispositivo, puedes buscar y filtrar eventos específicos. Puede establecer las marcas de eventos mediante: 

- Resaltar los eventos más importantes 
- Marcar eventos que requieren profundizar 
- Creación de una escala de tiempo de vulneración limpia



## <a name="flag-an-event"></a>Marcar un evento
1. Buscar el evento que desea marcar
2. Haga clic en el icono de marca de la columna Marca. 
![Imagen de la marca de escala de tiempo del dispositivo](images/device-flags.png)

## <a name="view-flagged-events"></a>Ver eventos marcados  
1. En la sección **Filtros de** escala de tiempo, habilite **Eventos marcados**.
2. Haga clic en **Aplicar**. Solo se muestran los eventos marcados.
Puede aplicar filtros adicionales haciendo clic en la barra de horas. Solo se mostrarán los eventos anteriores al evento marcado.  
![Imagen de la marca de escala de tiempo del dispositivo con el filtro en](images/device-flag-filter.png)
