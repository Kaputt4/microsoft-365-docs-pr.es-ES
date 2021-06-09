---
title: Estadísticas de búsqueda en la exhibición de documentos electrónicos avanzada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Valide los resultados de la búsqueda viendo las estadísticas que se generan después de ejecutar una búsqueda de colección en Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750781"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Estadísticas de búsqueda en Advanced eDiscovery

Una forma de validar los resultados de búsqueda es mirar las estadísticas alrededor de los resultados para asegurarse de que se alinean con sus expectativas. Cuando se completa una búsqueda, las estadísticas de alto nivel se muestran en el control desplegable de detalles de búsqueda:

- Número y volumen de elementos recuperados por la búsqueda

- Número y volumen de elementos parcialmente indexados o no indexados que se encontraron en las ubicaciones de búsqueda

- Número de buzones y ubicaciones buscados.
Para ver estadísticas más detalladas, haga clic en "Estadísticas" en el menú desplegable de detalles de búsqueda.

## <a name="summary-view"></a>Vista de resumen

En la vista Resumen, puede ver los resultados de búsqueda desglosados por tipo de ubicación (por ejemplo, Exchange). Para cada tipo de ubicación, puede ver:

- Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda

- Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda

- Volumen total de elementos que coinciden con las condiciones de búsqueda.

## <a name="top-locations-view"></a>Vista Ubicaciones superiores

En la vista Ubicaciones principales, verá las ubicaciones individuales con más coincidencias. Para cada ubicación, verá:

- Nombre de ubicación (por ejemplo, SharePoint URL)

- Tipo de ubicación

- Número de elementos que coinciden con las condiciones de búsqueda

- Volumen total de elementos que coinciden con las condiciones de búsqueda.

## <a name="queries-view"></a>Vista Consultas

Si ha usado filas de palabras clave o palabras clave (c:s) en la consulta, puede ver el desglose de la consulta en la vista Consultas por tipo de ubicación. Para cada tipo de ubicación, verá:

- Parte: esta columna tendrá la palabra "Primary" o "Keyword". "Primary" significa que la fila presenta estadísticas en toda la consulta, mientras que "Keyword" significa uno de los componentes de consulta.

- Consulta: el componente de consulta real al que hace referencia la fila. Si Part es "Primary", esta será la consulta completa; si Part era "Keyword", verá uno de los componentes de consulta aquí.
  
  - Al buscar en todos los buzones de contenido (sin especificar palabras clave), la consulta real es (tamaño >= 0) para que se devuelvan todos los elementos
  
  - Al buscar en SharePoint online y OneDrive para la Empresa web, se agregan los dos componentes siguientes:
    
    - NOT IsExternalContent:1: excluye cualquier contenido de una organización SharePoint local
    
    - NOT isOneNotePage: 1: excluye todos los OneNote porque se trataría de duplicados de cualquier documento que coincida con la consulta de búsqueda.

- Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda.

- Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda.

- Volumen total de elementos que coinciden con las condiciones de búsqueda.
