---
title: Indización avanzada de datos para una investigación
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
description: Obtenga información sobre cómo usar la indización avanzada para asegurarse de que su búsqueda captura todos los datos que desea investigar.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b0bb1a757ac70466fb43f2385485ce6da1dc741
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285966"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>Indización avanzada de datos para una investigación

El contenido del sistema activo se puede indizar parcialmente por una serie de motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización. Cuando se trata de un derrame de datos de riesgo alto, desea asegurarse de que la búsqueda capturó todos los datos que desea investigar. Cuando se agrega a una persona de interés a una investigación de datos, todo el contenido que se considere indizado parcialmente se reprocesa para que se pueda buscar por completo. Este proceso se denomina *indización avanzada*. 

Para obtener más información acerca de la compatibilidad de procesamiento y los elementos indizados parcialmente, consulte:

- [Tipos de archivo admitidos en investigaciones de datos](supported-filetypes-datainvestigations.md)

- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)

- [Formatos de archivo indizados por la búsqueda de Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Ver resultados de indización avanzada

Una vez completado el proceso de indización avanzado, puede comprender la efectividad del reprocesamiento.  En la vista de indización de personas de interés, el gráfico muestra todos los elementos agregados al *Índice híbrido*.  El índice híbrido es donde las investigaciones de datos (versión preliminar) almacenan el contenido reprocesado.

El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md).

## <a name="updating-advanced-indexes-for-people-of-interest"></a>Actualización de índices avanzados para personas de interés

Cuando se agrega a una persona de interés a una investigación de datos, se reprocesan todos los elementos parcialmente indizados. Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.  Cuando sea necesario, puede actualizar los índices.

> [!NOTE]
> La actualización de personas de índices de interés es un proceso de ejecución prolongada. Se recomienda no actualizar índices más de una vez al día en una investigación.
