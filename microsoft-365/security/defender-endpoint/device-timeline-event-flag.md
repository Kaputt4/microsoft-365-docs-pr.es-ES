---
title: Microsoft Defender para punto de conexión marcas de eventos de escala de tiempo del dispositivo
description: Use Microsoft Defender para punto de conexión marcas de eventos de escala de tiempo del dispositivo para
keywords: Escala de tiempo del dispositivo de Defender para punto de conexión, marcas de eventos
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 37607699d60ae2a74415551a9822e807a46c3b04
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701178"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Microsoft Defender para punto de conexión marcas de eventos de escala de tiempo del dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Las marcas de eventos en la escala de tiempo del dispositivo defender para punto de conexión ayudan a filtrar y organizar eventos específicos cuando se investigan posibles ataques.

La escala de tiempo del dispositivo defender para punto de conexión proporciona una vista cronológica de los eventos y las alertas asociadas observadas en un dispositivo. Esta lista de eventos proporciona visibilidad completa de los eventos, archivos y direcciones IP observados en el dispositivo. La lista a veces puede ser larga. Las marcas de eventos de escala de tiempo del dispositivo le ayudan a realizar un seguimiento de los eventos que podrían estar relacionados.

Después de pasar por una escala de tiempo del dispositivo, puede ordenar, filtrar y exportar los eventos específicos que ha marcado.

Al navegar por la escala de tiempo del dispositivo, puede buscar y filtrar eventos específicos. Puede establecer marcas de eventos mediante:

- Resaltar los eventos más importantes
- Marcado de eventos que requiere un análisis profundo
- Creación de una escala de tiempo de infracción limpia

## <a name="flag-an-event"></a>Marca de un evento

1. Buscar el evento que desea marcar

2. Haga clic en el icono de marca en la columna Marca. 

:::image type="content" source="images/device-flags.png" alt-text="Marca de escala de tiempo del dispositivo" lightbox="images/device-flags.png":::

## <a name="view-flagged-events"></a>Visualización de eventos marcados

1. En la sección **Filtros** de escala de tiempo, habilite **Eventos marcados**.
2. Haga clic en **Aplicar**. Solo se muestran los eventos marcados.

Puede aplicar filtros adicionales haciendo clic en la barra de tiempo. Esto solo mostrará eventos antes del evento marcado.  

:::image type="content" source="images/device-flag-filter.png" alt-text="Marca de escala de tiempo del dispositivo con el filtro activado" lightbox="images/device-flag-filter.png":::