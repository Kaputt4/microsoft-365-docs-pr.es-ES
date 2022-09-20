---
title: conectores de Microsoft Purview eDiscovery Graph
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 07/15/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365solution-ediscovery
- m365initiative-compliance
- m365solution-overview
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
description: Los clientes de Microsoft 365 pueden realizar búsquedas de exhibición de documentos electrónicos en el contenido ingerido para la búsqueda empresarial.
ms.openlocfilehash: 8b4a5435d589ba0fe4622c020bac3983a939008c
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67820423"
---
# <a name="use-graph-connectors-with-ediscovery-premium"></a>Uso de conectores de Graph con eDiscovery (Premium)

Los clientes de Microsoft 365 pueden realizar búsquedas de exhibición de documentos electrónicos en el contenido ingerido para la búsqueda empresarial. Esto ayudará a las organizaciones a mejorar su posición de cumplimiento con los orígenes de contenido externo al incorporarlos dentro del ámbito de las soluciones de cumplimiento de Microsoft.

Con los conectores de Graph, puede permitir que el contenido de orígenes de datos externos esté disponible para Microsoft Purview eDiscovery solución Premium. Obtenga más información sobre el establecimiento de conectores de Graph para su organización aquí: [Introducción a los conectores de Microsoft Graph para Microsoft Search](/microsoftsearch/connectors-overview).

## <a name="add-graph-connector-as-a-data-source-within-a-case"></a>Adición de Graph Connector como origen de datos dentro de un caso

Una vez que se establecen conectores de Graph para una organización y eDiscovery está habilitado, la opción para agregar el origen de datos del conector de Graph al caso estará disponible en ubicaciones que no sean de Microsoft 365. Solo los conectores que se han establecido y habilitado estarán disponibles para el administrador de exhibición de documentos electrónicos para su inclusión en un caso.

:::image type="content" source="../media/ediscovery-graph-new.png" alt-text="Puede seleccionar Graph como origen de datos.":::

## <a name="collect-graph-connectors-content"></a>Recopilación de contenido de Graph Connectors

Al agregar contenido de Graph Connectors como origen de datos, este contenido está disponible para la búsqueda y la recopilación. En el Asistente para recopilación, seleccione el contenido de Graph Connector como origen de datos que no sea de custodia, use condiciones como intervalo de fechas, palabras clave y mucho más para buscar en el contenido conectado para recopilar solo el contenido de interés. Una vez completado el asistente, obtenga estimaciones de la cantidad de contenido que contiene visitas a los criterios de búsqueda y confirme la colección en el conjunto de revisión.  

## <a name="review-content"></a>Revisión del contenido

Una vez recopilado en un conjunto de revisión, los administradores de eDiscovery pueden revisar el contenido de Graph Connectors para comprender mejor el contenido y trabajar para evaluar si la información es crítica y relevante para el caso.  

## <a name="export-content"></a>Exportar contenido

Una vez que se valida que el contenido recopilado en la revisión es el contenido correcto, este contenido está disponible para su exportación directamente desde el conjunto de revisión. Seleccione las opciones de exportación y envíe el trabajo de exportación para el contenido de conectores que se exportará desde el conjunto de revisión.
