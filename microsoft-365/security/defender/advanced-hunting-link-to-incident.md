---
title: Vincular resultados de consulta a un incidente
description: Vincular resultados de consulta a un incidente
keywords: búsqueda avanzada, incidente, pivot, entidad, ir a buscar, eventos relevantes, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5302c078da3ded781007412a2807fc20fa77319e
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2021
ms.locfileid: "61220901"
---
# <a name="link-query-results-to-an-incident"></a>Vincular resultados de consulta a un incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

El vínculo a la característica de incidente le permite agregar resultados avanzados de consulta de búsqueda a un incidente nuevo o existente en investigación. Esta característica te ayuda a capturar fácilmente registros de actividades avanzadas de búsqueda para que puedas crear una escala de tiempo o un contexto más enriquecido de eventos relacionados con un incidente. 

## <a name="link-results-to-new-or-existing-incidents"></a>Vincular resultados a incidentes nuevos o existentes

1. En la página de consulta de búsqueda avanzada, escriba primero la consulta en el campo de consulta proporcionado y, a continuación, seleccione **Ejecutar consulta** para obtener los resultados.

    :::image type="content" source="../../media/link-to-incident-1.png" alt-text="Un ejemplo de la página **Query** en el portal Microsoft 365 Defender web" lightbox="../../media/link-to-incident-1.png":::

2. En la página Resultados, seleccione los eventos o registros relacionados con una investigación nueva o actual en la que está trabajando y, a continuación, **seleccione Vincular a incidente**.

    :::image type="content" source="../../media/link-to-incident-1b.png" alt-text="La opción **Vínculo a incidente** de la pestaña **Resultados** en el portal de Microsoft 365 Defender web" lightbox="../../media/link-to-incident-1b.png":::

3. Busque la **sección Detalles de** alerta en  el panel Vincular a incidentes y, a continuación, seleccione Crear nuevo incidente para convertir los eventos en alertas y agruparlos en un nuevo incidente:

    :::image type="content" source="../../media/link-to-incident-3-create-new.png" alt-text="Un ejemplo de la sección **Detalles de alerta** en el panel **Vínculo a incidente** en el portal Microsoft 365 Defender web" lightbox="../../media/link-to-incident-3-create-new.png":::
    
    O **bien, seleccione Vincular a un incidente existente** para agregar los registros seleccionados a uno existente. Elija el incidente relacionado en la lista desplegable de incidentes existentes. También puede escribir los primeros caracteres del nombre o identificador del incidente para buscar el incidente existente. 

    :::image type="content" source="../../media/link-to-incident-3-link-to-existing.png" alt-text="Un ejemplo de sección **Detalles de alerta** en el panel **Vínculo a incidente** en el portal Microsoft 365 Defender web":::

4. Para cualquiera de las selecciones, proporcione los siguientes detalles y, a continuación, **seleccione Siguiente**:
      - **Título de alerta:** proporciona un título descriptivo para los resultados que los respondedores de incidentes pueden comprender. Esto se convierte en el título de alerta.
      - **Gravedad:** elija la gravedad aplicable al grupo de alertas.
      - **Categoría:** elija la categoría de amenaza adecuada para las alertas.
      - **Descripción:** proporcionar una descripción útil para las alertas agrupadas.
      - **Acciones recomendadas:** proporcionar acciones de corrección.

5. En la **sección Entidades afectadas,** seleccione la entidad principal afectada o afectada. En esta sección solo aparecen las entidades aplicables basadas en los resultados de la consulta. En nuestro ejemplo, se usa una consulta para buscar eventos relacionados con un posible incidente de exfiltración de correo electrónico, por lo tanto, el remitente es la entidad afectada. Si hay cuatro remitentes diferentes, por ejemplo, se crean cuatro alertas y se vinculan al incidente elegido.

     :::image type="content" source="../../media/link-to-incident-4-impacted-entities.png" alt-text="Un ejemplo de una entidad afectada en la sección **Vínculo a incidente** en el portal de Microsoft 365 Defender web" lightbox="../../media/link-to-incident-4-impacted-entities.png":::

1. Seleccione **Siguiente**.
1. Revise los detalles que ha proporcionado en **la sección Resumen.**
     :::image type="content" source="../../media/link-to-incident-5-summary.png" alt-text="Un ejemplo de la página de resultados de la sección **Vincular a incidentes** en el portal de Microsoft 365 Defender web" lightbox="../../media/link-to-incident-5-summary.png":::
     
1. Seleccione **Listo**.

## <a name="view-linked-records-in-the-incident"></a>Ver registros vinculados en el incidente

Puede seleccionar el nombre del incidente para ver el incidente al que están vinculados los eventos.
     :::image type="content" source="../../media/link-to-incident-6-incident-pg.png" alt-text="Un ejemplo de pantalla de detalles de eventos en la pestaña **Resumen** en el portal de Microsoft 365 Defender eventos" lightbox="../../media/link-to-incident-6-incident-pg.png":::

En nuestro ejemplo, las cuatro alertas, que representan los cuatro eventos seleccionados, se vincularon correctamente a un nuevo incidente. 

En cada una de las páginas de alerta, puede encontrar la información completa sobre el evento o eventos en la vista escala de tiempo (si está disponible) y la vista de resultados de consulta.
     :::image type="content" source="../../media/link-to-incident-7-alert-story.png" alt-text="Un ejemplo de detalles completos de un evento en la pestaña **Escala de tiempo** en el portal Microsoft 365 Defender web" lightbox="../../media/link-to-incident-7-alert-story.png":::

También puede seleccionar el evento para abrir el panel **Inspeccionar registro.**
:::image type="content" source="../../media/link-to-incident-7-inspect-record.png" alt-text="Un ejemplo de inspeccionar los detalles del registro de un evento en la pestaña **Escala de tiempo** en el portal Microsoft 365 Defender web" lightbox="../../media/link-to-incident-7-inspect-record.png":::

## <a name="filter-for-events-added-using-advanced-hunting"></a>Filtrar por eventos agregados mediante la búsqueda avanzada
Puede ver qué alertas se generaron a partir de la búsqueda avanzada filtrando la cola incidentes y la cola de alertas por **origen de** detección manual.

:::image type="content" source="../../media/link-to-incident-8-filter.png" alt-text="Un ejemplo de filtrado manual de la cola de incidentes y alertas en la página **Filtros** del portal de Microsoft 365 Defender web" lightbox="../../media/link-to-incident-8-filter.png":::
