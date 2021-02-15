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
description: Cuando se agrega un administrador a un caso de eDiscovery avanzado, se vuelve a procesar todo el contenido que se considera parcialmente indizado para que sea totalmente posible realizar búsquedas.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750761"
---
# <a name="advanced-indexing-of-custodian-data"></a>Clasificación avanzada de los datos de administración

Cuando se agrega un administrador a un caso de eDiscovery avanzado, se vuelve a procesar todo el contenido que se considera parcialmente indizado para que sea totalmente posible realizar búsquedas.  Este proceso se denomina *indización avanzada.* El contenido se puede indizar parcialmente por varios motivos, incluida la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.

Para obtener más información sobre el procesamiento de compatibilidad y elementos parcialmente indizados, vea:

- [Tipos de archivo admitidos en eDiscovery avanzado](supported-filetypes-ediscovery20.md)

- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de archivo indizados por la búsqueda de Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visualización de resultados de indización avanzados

Una vez completado el proceso de indización avanzada, puede comprender la eficacia del reprocesamiento.  En la vista de resultados de indización avanzada de la ficha Procesamiento de un caso, el gráfico muestra el número de elementos agregados al *índice híbrido.*   El índice híbrido es donde eDiscovery avanzado almacena el contenido reprocesado.

Esta vista también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea:

- [Corrección de errores al procesar los datos](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Corrección de errores de un único elemento](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Actualización del índice avanzado para administradores

Cuando se agrega un administrador a un caso de eDiscovery avanzado, se vuelve a procesar todos los elementos parcialmente indizados. Sin embargo, a medida que pasa el tiempo, se pueden agregar elementos más parcialmente indizados al buzón de un usuario o a una cuenta de OneDrive.  Si es necesario, puede actualizar el índice para un administrador específico. Para obtener más información, vea [Administrar administradores en un caso de eDiscovery avanzado.](manage-new-custodians.md#re-index-custodian-data) También puede actualizar el índice de todos los administradores en un caso haciendo clic en el índice **Actualizar** en la **pestaña Procesamiento.**

> [!NOTE]
> La actualización de índices de administradores es un proceso de larga duración. Se recomienda no actualizar los índices más de una vez al día en un caso.
