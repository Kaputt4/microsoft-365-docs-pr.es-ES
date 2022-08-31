---
title: Vincular los resultados de la consulta a un incidente
description: Vincular los resultados de la consulta a un incidente
keywords: advanced hunting, incident, pivot, entity, go hunt, relevant events, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3e4682e7c1fb2cc0496bbf4c737b106e7c17fed1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483198"
---
# <a name="link-query-results-to-an-incident"></a>Vincular los resultados de la consulta a un incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Puede usar el vínculo a la característica de incidente para agregar resultados de consultas de búsqueda avanzadas a un incidente nuevo o existente que se está investigando. Esta característica le ayuda a capturar fácilmente registros de actividades de búsqueda avanzadas, lo que le permite crear una escala de tiempo o un contexto más completos de eventos relacionados con un incidente. 

## <a name="link-results-to-new-or-existing-incidents"></a>Vinculación de resultados a incidentes nuevos o existentes

1. En la página consulta de búsqueda avanzada, escriba primero la consulta en el campo de consulta proporcionado y, después, seleccione **Ejecutar consulta** para obtener los resultados.

    :::image type="content" source="../../media/link-to-incident-1.png" alt-text="Página Consulta del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-1.png":::

2. En la página Resultados, seleccione los eventos o registros relacionados con una investigación nueva o actual en la que está trabajando y, a continuación, seleccione **Vincular al incidente**.

    :::image type="content" source="../../media/link-to-incident-1b.png" alt-text="La opción Vincular al incidente de la pestaña Resultados del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-1b.png":::

3. Busque la sección **Detalles** de la alerta en el panel Vincular a incidente y, a continuación, seleccione **Crear nuevo incidente** para convertir los eventos en alertas y agruparlos en un nuevo incidente:

    :::image type="content" source="../../media/link-to-incident-3-create-new.png" alt-text="La sección Detalles de la alerta del panel Vínculo a incidentes del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-3-create-new.png":::
    
    O bien, seleccione **Vincular a un incidente existente** para agregar los registros seleccionados a uno existente. Elija el incidente relacionado en la lista desplegable de incidentes existentes. También puede escribir los primeros caracteres del nombre o identificador del incidente para buscar el incidente existente. 

    :::image type="content" source="../../media/link-to-incident-3-link-to-existing.png" alt-text="La sección Detalles de la alerta del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-3-link-to-existing.png":::

4. Para cualquiera de las selecciones, proporcione los detalles siguientes y, a continuación, seleccione **Siguiente**:
      - **Título de alerta** : proporcione un título descriptivo para los resultados que los respondedores de incidentes pueden comprender. Este título descriptivo se convierte en el título de la alerta.
      - **Gravedad** : elija la gravedad aplicable al grupo de alertas.
      - **Categoría** : elija la categoría de amenaza adecuada para las alertas.
      - **Descripción** : proporcione una descripción útil para las alertas agrupadas.
      - **Acciones recomendadas** : proporcione acciones de corrección.

5. En la sección **Entidades afectadas** , seleccione la entidad principal afectada o afectada. En esta sección solo aparecen las entidades aplicables basadas en los resultados de la consulta. En nuestro ejemplo, usamos una consulta para buscar eventos relacionados con un posible incidente de filtración de correo electrónico, por lo que el remitente es la entidad afectada. Si hay cuatro remitentes diferentes, por ejemplo, se crean cuatro alertas y se vinculan al incidente elegido.

     :::image type="content" source="../../media/link-to-incident-4-impacted-entities.png" alt-text="La entidad afectada en la sección Vínculo al incidente del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-4-impacted-entities.png":::

1. Seleccione **Siguiente**.
1. Revise los detalles que ha proporcionado en la sección **Resumen** .
   :::image type="content" source="../../media/link-to-incident-5-summary.png" alt-text="Página de resultados de la sección Vínculo al incidente del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-5-summary.png":::
     
1. Seleccione **Listo**.

## <a name="view-linked-records-in-the-incident"></a>Visualización de registros vinculados en el incidente

Puede seleccionar el nombre del incidente para ver el incidente al que están vinculados los eventos.
:::image type="content" source="../../media/link-to-incident-6-incident-pg.png" alt-text="Pantalla de detalles del evento en la pestaña Resumen del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-6-incident-pg.png":::

En nuestro ejemplo, las cuatro alertas, que representan los cuatro eventos seleccionados, se vincularon correctamente a un nuevo incidente. 

En cada una de las páginas de alerta, puede encontrar la información completa sobre el evento o los eventos en la vista de escala de tiempo (si está disponible) y en la vista de resultados de la consulta.
:::image type="content" source="../../media/link-to-incident-7-alert-story.png" alt-text="Detalles completos de un evento en la pestaña Escala de tiempo del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-7-alert-story.png":::

También puede seleccionar el evento para abrir el panel **Inspeccionar registro** .
:::image type="content" source="../../media/link-to-incident-7-inspect-record.png" alt-text="Los detalles del registro de inspección de un evento en la pestaña Escala de tiempo del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-7-inspect-record.png":::

## <a name="filter-for-events-added-using-advanced-hunting"></a>Filtrar por los eventos agregados mediante la búsqueda avanzada
Puede ver qué alertas se generaron a partir de la búsqueda avanzada filtrando la cola incidentes y la cola de alertas por origen de detección **manual** .

:::image type="content" source="../../media/link-to-incident-8-filter.png" alt-text="Filtrado manual de la cola incidentes y alertas en la página Filtros del portal de Microsoft 365 Defender" lightbox="../../media/link-to-incident-8-filter.png":::
