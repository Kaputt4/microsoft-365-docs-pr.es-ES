---
title: Buscar estadísticas en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
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
description: Para validar los resultados de la búsqueda, vea las estadísticas que se generan después de ejecutar una búsqueda de colección en la exhibición avanzada de documentos electrónicos.
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286086"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Estadísticas de búsqueda en eDiscovery avanzado

Una forma de validar los resultados de la búsqueda es ver las estadísticas de los resultados para asegurarse de que se ajustan a sus expectativas. Una vez finalizada la búsqueda, se muestran las estadísticas de alto nivel en el control flotante de detalles de búsqueda:

- Número y volumen de los elementos recuperados por la búsqueda

- Número y volumen de los elementos sin indexar o parcialmente indizados que se encontraron en las ubicaciones de búsqueda

- Número de buzones y ubicaciones que se han buscado.
Para ver estadísticas más detalladas, haga clic en "estadísticas" en el control flotante de detalles de búsqueda.

## <a name="summary-view"></a>Vista de Resumen

En la vista de Resumen, puede ver los resultados de la búsqueda desglosados por tipo de ubicación (por ejemplo, Exchange). Para cada tipo de ubicación, puede ver:

- Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda

- Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda

- Volumen total de elementos que coinciden con las condiciones de búsqueda.

## <a name="top-locations-view"></a>Vista de ubicaciones superiores

En la vista de ubicaciones superiores, verá las ubicaciones individuales con más coincidencias. Para cada ubicación, verá:

- Nombre de la ubicación (por ejemplo, dirección URL de SharePoint)

- Tipo de ubicación

- Número de elementos que coinciden con las condiciones de búsqueda

- Volumen total de elementos que coinciden con las condiciones de búsqueda.

## <a name="queries-view"></a>Vista de consultas

Si ha usado (c:s) palabra clave o filas de palabra clave en la consulta, puede ver el desglose de la consulta en la vista consultas por tipo de ubicación. Para cada tipo de ubicación, verá:

- Parte: esta columna tendrá la palabra "principal" o "palabra clave". "Principal" significa que la fila presenta estadísticas sobre toda la consulta, mientras que "palabra clave" se refiere a uno de los componentes de consulta.

- Consulta: el componente de consulta real al que hace referencia la fila. Si la parte es "principal", será toda la consulta; Si la parte es "keyword", verá uno de los componentes de consulta aquí.
  
  - Cuando busca en todo el contenido de los buzones (sin especificar ninguna palabra clave), la consulta real es (Size >= 0) para que se devuelvan todos los elementos.
  
  - Al buscar sitios de SharePoint Online y OneDrive para la empresa, se agregan los dos componentes siguientes:
    
    - NO IsExternalContent: 1-excluye el contenido de una organización de SharePoint local
    
    - NO isOneNotePage: 1: excluye todos los archivos de OneNote porque serían duplicados de cualquier documento que coincida con la consulta de búsqueda.

- Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda.

- Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda.

- Volumen total de elementos que coinciden con las condiciones de búsqueda.
