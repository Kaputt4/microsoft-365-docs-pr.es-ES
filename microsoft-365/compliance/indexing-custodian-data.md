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
description: Cuando se agrega un custodio a un caso de eDiscovery avanzado, cualquier contenido que se considere indizado parcialmente se vuelve a procesar para que pueda buscarse por completo.
ms.openlocfilehash: 0618af5bcc18622ee8091782f55648f455230b6b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637902"
---
# <a name="advanced-indexing-of-custodian-data"></a>Clasificación avanzada de los datos de administración

Cuando se agrega un custodio a un caso de eDiscovery avanzado, cualquier contenido que se considere indizado parcialmente se vuelve a procesar para que pueda buscarse por completo.  Este proceso se denomina *indización avanzada*. El contenido se puede indizar parcialmente por varios motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.

Para obtener más información acerca de la compatibilidad de procesamiento y los elementos indizados parcialmente, consulte:

- [Tipos de archivo admitidos en eDiscovery avanzado](supported-filetypes-ediscovery20.md)

- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de archivo indizados por la búsqueda de Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Ver resultados de indización avanzada

Una vez completado el proceso de indización avanzado, puede comprender la efectividad del procesamiento.  En la vista de resultados de indización avanzada de la ficha **procesamiento** de un caso, el gráfico muestra el número de elementos agregados al *Índice híbrido*.  El índice híbrido es donde la exhibición avanzada de documentos electrónicos almacena el contenido que se ha vuelto a procesar.

Esta vista también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea:

- [Corrección de errores al procesar los datos](error-remediation.md)

- [Corrección de errores de un único elemento](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Actualización del índice avanzado para los custodios

Cuando se agrega un custodio a un caso de eDiscovery avanzado, todos los elementos parcialmente indizados se vuelven a procesar. Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.  Si es necesario, puede actualizar el índice de un custodio específico. Para obtener más información, consulte [administrar custodios en un caso de exhibición avanzada de](manage-new-custodians.md#re-index-custodian-data)documentos electrónicos. También puede actualizar el índice de todos los custodios en un caso haciendo clic en el **Índice de actualización** en la pestaña **procesando** .

> [!NOTE]
> La actualización de los índices de custodios es un proceso de ejecución prolongada. Se recomienda no actualizar índices más de una vez al día en un caso.
