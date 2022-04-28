---
title: Clasificación avanzada de los datos de administración
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Cuando se agrega un custodio a un caso de exhibición de documentos electrónicos (Premium), cualquier contenido que se considere parcialmente indexado se vuelve a procesar para que sea totalmente de búsqueda.
ms.openlocfilehash: 2a4cea13291bd592cf47a61b500a4f3a6012ac85
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096686"
---
# <a name="advanced-indexing-of-custodian-data"></a>Clasificación avanzada de los datos de administración

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Cuando se agrega un custodio a un caso de exhibición de documentos electrónicos (Premium), se vuelve a indexar cualquier contenido que se haya considerado parcialmente indexado o que haya tenido errores de indexación. Este proceso de reindexación se denomina *indexación avanzada*. Hay muchas razones por las que el contenido se indexa parcialmente o tiene errores de indexación. Esto incluye archivos de imagen o la presencia de imágenes en un archivo, tipos de archivos no admitidos o límites de indexación de tamaño de archivo. Para SharePoint archivos, la indexación avanzada solo se ejecuta en elementos marcados como parcialmente indizados o que tienen errores de indexación. En Exchange, los mensajes de correo electrónico que tienen datos adjuntos de imagen no se marcan como indizados parcialmente o con errores de indexación. Esto significa que el proceso de indexación avanzada no volverá a indexar esos archivos.

Para obtener más información sobre la compatibilidad con el procesamiento y los elementos parcialmente indexados, consulte:

- [Tipos de archivo admitidos en eDiscovery (Premium)](supported-filetypes-ediscovery20.md)

- [Elementos indizados parcialmente en eDiscovery](partially-indexed-items-in-content-search.md)

- [Formatos de archivo indizados por la búsqueda de Exchange](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visualización de resultados de indexación avanzada

Una vez completado el proceso de indexación avanzada, puede comprender la eficacia del reprocesamiento.  En la vista Resultados de indexación avanzada de la pestaña **Procesamiento** de un caso, el gráfico muestra el número de elementos agregados al *índice híbrido*.  El índice híbrido es donde eDiscovery (Premium) almacena el contenido reprocesado.

Esta vista también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para más información, vea:

- [Corrección de errores al procesar los datos](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Corrección de errores de un único elemento](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Actualización del índice avanzado para los custodios

Cuando se agrega un custodio a un caso de exhibición de documentos electrónicos (Premium), se vuelven a procesar todos los elementos indizados parcialmente. Sin embargo, a medida que pasa el tiempo, se pueden agregar elementos más parcialmente indizados al buzón de correo de un usuario o a OneDrive cuenta.  Si es necesario, puede actualizar el índice para un custodio específico. Para obtener más información, vea [Administrar custodios en un caso de exhibición de documentos electrónicos (Premium).](manage-new-custodians.md#reindex-custodian-data) También puede actualizar el índice de todos los custodios en un caso haciendo clic en el **índice Actualizar** de la pestaña **Procesamiento** .

> [!NOTE]
> La actualización de índices de custodios es un proceso de larga duración. Se recomienda no actualizar los índices más de una vez al día en un caso.
