---
title: Técnicas en la escala de tiempo del dispositivo
description: Descripción de la escala de tiempo del dispositivo en Microsoft Defender para endpoint
keywords: escala de tiempo del dispositivo, punto de conexión, MITRE, MITRE ATT&CK, técnicas, tácticas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d724b7663bd4484c630e97362eb5766490e1fa8e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465913"
---
# <a name="techniques-in-the-device-timeline"></a>Técnicas en la escala de tiempo del dispositivo

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

Puedes obtener más información en una investigación analizando los eventos que sucedieron en un dispositivo específico. En primer lugar, selecciona el dispositivo de interés de la [lista Dispositivos](machines-view-overview.md). En la página del dispositivo, puedes seleccionar la pestaña **Escala** de tiempo para ver todos los eventos que se produjeron en el dispositivo.

## <a name="understand-techniques-in-the-timeline"></a>Comprender técnicas en la escala de tiempo

> [!IMPORTANT]
> Parte de la información se relaciona con una característica de producto publicada previamente en la versión preliminar pública que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

En Microsoft Defender para endpoint, **las técnicas son** un tipo de datos adicional en la escala de tiempo del evento. Las técnicas proporcionan más información sobre las actividades asociadas con [MITRE ATT&técnicas de CK](https://attack.mitre.org/) o sub-técnicas.

Esta característica simplifica la experiencia de investigación al ayudar a los analistas a comprender las actividades que se observaron en un dispositivo. A continuación, los analistas pueden decidir investigar más a fondo.

Para la vista previa pública, las técnicas están disponibles de forma predeterminada y se muestran junto con los eventos cuando se visualiza la escala de tiempo de un dispositivo.

:::image type="content" source="images/device-timeline-2.png" alt-text="Las técnicas en la escala de tiempo del dispositivo" lightbox="images/device-timeline-2.png":::

Las técnicas se resaltan en texto en negrita y aparecen con un icono azul a la izquierda. El nombre de la técnica y el identificador&MITRE ATT correspondientes también aparecen como etiquetas en Información adicional.

Las opciones de búsqueda y exportación también están disponibles para Técnicas.

## <a name="investigate-using-the-side-pane"></a>Investigar con el panel lateral

Seleccione una técnica para abrir su panel lateral correspondiente. Aquí puede ver información e información adicionales, como att relacionado&técnicas de CK, tácticas y descripciones.

Seleccione la técnica *de ataque específica* para abrir la página relacionada&técnica de CK en la que puede encontrar más información sobre ella.

Puede copiar los detalles de una entidad cuando vea un icono azul a la derecha. Por ejemplo, para copiar el SHA1 de un archivo relacionado, seleccione el icono de página azul.

:::image type="content" source="images/techniques-side-pane-clickable.png" alt-text="Los detalles de la entidad para copiar" lightbox="images/techniques-side-pane-clickable.png":::

Puede hacer lo mismo con las líneas de comandos.

:::image type="content" source="images/techniques-side-pane-command.png" alt-text="La opción para copiar la línea de comandos" lightbox="images/techniques-side-pane-command.png":::

## <a name="investigate-related-events"></a>Investigar eventos relacionados

Para usar [la búsqueda avanzada](advanced-hunting-overview.md) para buscar eventos relacionados con la técnica seleccionada, seleccione **Buscar para eventos relacionados**. Esto lleva a la página de búsqueda avanzada con una consulta para encontrar eventos relacionados con la técnica.

:::image type="content" source="images/techniques-hunt-for-related-events.png" alt-text="La opción Buscar eventos relacionados" lightbox="images/techniques-hunt-for-related-events.png":::

> [!NOTE]
> Las consultas con el botón **Buscar** eventos relacionados desde un panel lateral Técnica muestran todos los eventos relacionados con la técnica identificada, pero no incluyen la técnica en sí en los resultados de la consulta.

## <a name="customize-your-device-timeline"></a>Personalizar la escala de tiempo del dispositivo

En la parte superior derecha de la escala de tiempo del dispositivo, puedes elegir un intervalo de fechas para limitar el número de eventos y técnicas de la escala de tiempo.

Puede personalizar las columnas que se deben exponer. También puede filtrar los eventos marcados por tipo de datos o por grupo de eventos.

### <a name="choose-columns-to-expose"></a>Elegir columnas para exponer

Puede elegir qué columnas exponer en la escala de tiempo seleccionando el **botón Elegir** columnas.

:::image type="content" source="images/filter-customize-columns.png" alt-text="Panel en el que puede personalizar columnas" lightbox="images/filter-customize-columns.png":::


Desde allí, puede seleccionar qué conjunto de información incluir.

### <a name="filter-to-view-techniques-or-events-only"></a>Filtrar solo para ver técnicas o eventos

Para ver solo eventos o técnicas, selecciona **Filtros en** la escala de tiempo del dispositivo y elige el tipo de datos que prefieras ver.

:::image type="content" source="images/device-timeline-filters.png" alt-text="Panel Filtros" lightbox="images/device-timeline-filters.png":::

## <a name="see-also"></a>Vea también

- [Ver y organizar la lista de dispositivos](machines-view-overview.md)
- [Marcas de eventos de escala de tiempo de dispositivo de Microsoft Defender para punto de conexión](device-timeline-event-flag.md)
