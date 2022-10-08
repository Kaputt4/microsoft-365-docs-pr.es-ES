---
title: Técnicas en la escala de tiempo del dispositivo
description: Descripción de la escala de tiempo del dispositivo en Microsoft Defender para punto de conexión
keywords: escala de tiempo del dispositivo, punto de conexión, MITRE, MITRE ATT&CK, técnicas, tácticas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: b028d9d571721ee933c3caa694b4578755b9f57f
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68221398"
---
# <a name="techniques-in-the-device-timeline"></a>Técnicas en la escala de tiempo del dispositivo

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

Puede obtener más información en una investigación mediante el análisis de los eventos que ocurrieron en un dispositivo específico. En primer lugar, seleccione el dispositivo de interés en la [lista Dispositivos](machines-view-overview.md). En la página del dispositivo, puede seleccionar la pestaña **Escala de tiempo** para ver todos los eventos que se produjeron en el dispositivo.

## <a name="understand-techniques-in-the-timeline"></a>Descripción de las técnicas en la escala de tiempo

> [!IMPORTANT]
> Cierta información se relaciona con una característica de producto preliminar en versión preliminar pública que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

En Microsoft Defender para punto de conexión, **Técnicas** es un tipo de datos adicional en la escala de tiempo de eventos. Las técnicas proporcionan más información sobre las actividades asociadas a [MITRE ATT&](https://attack.mitre.org/) técnicas de CK o sub técnicas.

Esta característica simplifica la experiencia de investigación al ayudar a los analistas a comprender las actividades que se observaron en un dispositivo. A continuación, los analistas pueden decidir investigar más.

Para la versión preliminar pública, Las técnicas están disponibles de forma predeterminada y se muestran junto con eventos cuando se ve la escala de tiempo de un dispositivo.

:::image type="content" source="images/device-timeline-2.png" alt-text="Técnicas en la escala de tiempo del dispositivo" lightbox="images/device-timeline-2.png":::

Las técnicas se resaltan en negrita y aparecen con un icono azul a la izquierda. El id. de CK y el nombre de la técnica de MITRE AT&T correspondientes también aparecen como etiquetas en Información adicional.

Las opciones de búsqueda y exportación también están disponibles para Técnicas.

## <a name="investigate-using-the-side-pane"></a>Investigación mediante el panel lateral

Seleccione una técnica para abrir su panel lateral correspondiente. Aquí puede ver información e información adicional, como técnicas, tácticas y descripciones relacionadas de ATT&CK.

Seleccione la *técnica de ataque* específica para abrir la página de técnica de ATT&CK relacionada, donde puede encontrar más información al respecto.

Puede copiar los detalles de una entidad cuando vea un icono azul a la derecha. Por ejemplo, para copiar sha1 de un archivo relacionado, seleccione el icono de página azul.

:::image type="content" source="images/techniques-side-pane-clickable.png" alt-text="que se va a copiar los detalles de la entidad" lightbox="images/techniques-side-pane-clickable.png":::

Puede hacer lo mismo con las líneas de comandos.

:::image type="content" source="images/techniques-side-pane-command.png" alt-text="Opción para copiar la línea de comandos" lightbox="images/techniques-side-pane-command.png":::

## <a name="investigate-related-events"></a>Investigación de eventos relacionados

Para usar la [búsqueda avanzada](advanced-hunting-overview.md) para buscar eventos relacionados con la técnica seleccionada, seleccione **Buscar eventos relacionados**. Esto conduce a la página de búsqueda avanzada con una consulta para buscar eventos relacionados con la técnica.

:::image type="content" source="images/techniques-hunt-for-related-events.png" alt-text="Opción Buscar eventos relacionados" lightbox="images/techniques-hunt-for-related-events.png":::

> [!NOTE]
> La consulta mediante el botón **Buscar eventos relacionados** de un panel lateral Técnica muestra todos los eventos relacionados con la técnica identificada, pero no incluye la propia técnica en los resultados de la consulta.

## <a name="customize-your-device-timeline"></a>Personalización de la escala de tiempo del dispositivo

En la parte superior derecha de la escala de tiempo del dispositivo, puede elegir un intervalo de fechas para limitar el número de eventos y técnicas en la escala de tiempo.

Puede personalizar las columnas que se van a exponer. También puede filtrar los eventos marcados por tipo de datos o por grupo de eventos.

### <a name="choose-columns-to-expose"></a>Elegir columnas que se van a exponer

Para elegir qué columnas se van a exponer en la escala de tiempo, seleccione el botón **Elegir columnas** .

:::image type="content" source="images/filter-customize-columns.png" alt-text="Panel en el que se pueden personalizar las columnas" lightbox="images/filter-customize-columns.png":::


Desde allí puede seleccionar qué información se va a incluir.

### <a name="filter-to-view-techniques-or-events-only"></a>Filtrar solo para ver técnicas o eventos

Para ver solo eventos o técnicas, seleccione **Filtros** en la escala de tiempo del dispositivo y elija el tipo de datos que quiera ver.

:::image type="content" source="images/device-timeline-filters.png" alt-text="Panel Filtros" lightbox="images/device-timeline-filters.png":::

## <a name="see-also"></a>Vea también

- [Ver y organizar la lista de dispositivos](machines-view-overview.md)
- [Microsoft Defender para punto de conexión marcas de eventos de escala de tiempo del dispositivo](device-timeline-event-flag.md)
