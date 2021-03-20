---
title: Clasificación avanzada de los datos de administración
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Cuando se agrega un custodio a un caso de exhibición de documentos electrónicos avanzada, cualquier contenido que se consideró parcialmente indizado se vuelve a procesar para que sea totalmente posible realizar búsquedas.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911214"
---
# <a name="advanced-indexing-of-custodian-data"></a>Clasificación avanzada de los datos de administración

Cuando se agrega un custodio a un caso de exhibición de documentos electrónicos avanzada, cualquier contenido que se consideró parcialmente indizado se vuelve a procesar para que sea totalmente posible realizar búsquedas.  Este proceso se denomina *Indización avanzada*. El contenido se puede indizar parcialmente por varios motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.

Para obtener más información sobre el procesamiento de soporte técnico y elementos parcialmente indizados, vea:

- [Tipos de archivo compatibles en eDiscovery avanzada](supported-filetypes-ediscovery20.md)

- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de archivo indizados por la búsqueda de Exchange](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visualización de resultados de indización avanzada

Una vez completado el proceso de indización avanzada, puede comprender la eficacia del reprocesamiento.  En la vista Resultados  de indización avanzada de la ficha Procesamiento de un caso, el gráfico enumera el número de elementos agregados al *índice híbrido*.  El índice híbrido es donde eDiscovery avanzado almacena el contenido reprocesado.

Esta vista también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea:

- [Corrección de errores al procesar los datos](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Corrección de errores de un único elemento](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Actualización del índice avanzado para custodios

Cuando se agrega un custodio a un caso de exhibición de documentos electrónicos avanzada, se vuelve a procesar todos los elementos parcialmente indizados. Sin embargo, a medida que pasa el tiempo, se pueden agregar elementos más indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.  Si es necesario, puede actualizar el índice para un custodio específico. Para obtener más información, vea [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data). También puede actualizar el índice de todos los custodios en un caso haciendo clic en el **índice Actualizar** de la **ficha** Procesamiento.

> [!NOTE]
> La actualización de índices de custodia es un proceso de larga ejecución. Se recomienda no actualizar índices más de una vez al día en un caso.