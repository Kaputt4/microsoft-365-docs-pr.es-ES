---
title: Trabajar con resultados de consulta en modo guiado para la búsqueda en Microsoft 365 Defender
description: Use y personalice los resultados de la consulta en modo guiado para la búsqueda avanzada en Microsoft 365 Defender
keywords: modo guiado, búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.openlocfilehash: 3e125b8fef6c1c42f125f3a2744ce5c060293ac6
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68078181"
---
# <a name="work-with-query-results-in-guided-mode"></a>Trabajar con resultados de consulta en modo guiado
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

En la búsqueda mediante el modo guiado, los resultados de la consulta aparecen en la pestaña **Resultados** . 

[![Captura de pantalla de la pestaña](../../media/guided-hunting/results-view.png) de resultados ](../../media/guided-hunting/results-view.png#lightbox)

Puede seguir trabajando en los resultados exportándolos a un archivo CSV seleccionando **Exportar**. Esto descarga el archivo CSV para su uso.

Puede ver otra información en la vista Resultados:
- Número de registros en la lista de resultados (junto al botón Buscar)
- Duración del tiempo de ejecución de la consulta
- Uso de recursos de la consulta

## <a name="view-more-columns"></a>Ver más columnas

En los resultados se incluyen algunas columnas estándar para facilitar la visualización. 

Para ver más columnas:
1. Seleccione **Personalizar columnas** en la parte superior derecha de la vista de resultados.
 

2. Desde aquí, seleccione las columnas que se van a incluir en la vista de resultados y anule la selección de las columnas que se van a ocultar. 


[![Captura de pantalla de la lista de columnas que puede agregar a la vista](../../media/guided-hunting/results-view-customize-columns.png) de resultados ](../../media/guided-hunting/results-view-customize-columns-tb.png#lightbox)

3. Seleccione **Aplicar** para ver los resultados con las columnas agregadas. Use las barras de desplazamiento si es necesario.


## <a name="see-also"></a>Vea también
- [Cuotas de búsqueda avanzadas y parámetros de uso](advanced-hunting-limits.md)
- [Cambiar al modo avanzado](advanced-hunting-query-builder-details.md#switch-to-advanced-mode-after-building-a-query)
- [Refinar la consulta en modo guiado](advanced-hunting-query-builder-details.md)