---
title: Recopilar datos para un caso en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: esclee
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
description: Obtenga información sobre cómo identificar un conjunto de documentos para su revisión en una investigación mediante la herramienta de búsqueda en eDiscovery avanzado.
ms.custom: seo-marvel-2020
ms.openlocfilehash: 9d8a88ddfc6bcb30f8678f39ad2bc4fbaf717ecc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034354"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Recopilar datos para un caso en eDiscovery avanzado

Una vez que haya identificado los custodios y los orígenes de datos que sean de interés para su caso, es el momento de identificar el conjunto de documentos en los que profundizar. Puede usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos para identificar los documentos relevantes de ubicaciones de apoyo y no Private en Microsoft 365.

Después de ejecutar una búsqueda, puede ver las estadísticas de los elementos recuperados, como las ubicaciones en las que la mayoría de los elementos coinciden con la consulta de búsqueda. También puede obtener una vista previa de un subconjunto de los resultados. Cuando haya identificado el conjunto de documentos que desea examinar con más detalle, puede Agregar los resultados de la búsqueda a un conjunto de revisión para recopilar y procesar.

## <a name="create-a-search"></a>Crear una búsqueda

Si selecciona **nueva búsqueda** en la ficha **búsquedas** , se iniciará un asistente que le guiará en la creación de una búsqueda. Para obtener información detallada sobre cómo crear una búsqueda, vea [crear una búsqueda para recopilar datos](create-search-to-collect-data.md).

Una vez creada la búsqueda, se muestra una página de control flotante con los detalles. Los botones **Statistics** y **Preview** no están inicialmente disponibles porque la búsqueda todavía no se ha completado. Puede realizar un seguimiento del progreso de la búsqueda en la ficha **búsquedas** .

## <a name="view-search-results-and-statistics"></a>Ver los resultados de la búsqueda y las estadísticas

Hay dos componentes de una búsqueda de contenido: Statistics (Estimations) y Preview. Cuando se completen todos estos componentes, verá que el estado que se muestra en las columnas correspondientes de la ficha **búsquedas** cambia de **enviado** a **en curso** a **completado**.

Una vez completada la estimación de la búsqueda, seleccione la búsqueda para mostrar la página de flotante, que mostrará algunas estadísticas de alto nivel sobre los resultados de la búsqueda. En este momento, el botón **estadísticas** estará activo. Puede seleccionarlo para ver las estadísticas de búsqueda, como:

- Resumen
- Principales ubicaciones
- Queries

Para obtener más información acerca de las estadísticas de búsqueda, vea [estadísticas de búsqueda](search-statistics.md).

Una vez completada la vista previa, el botón **vista previa** estará activo. Selecciónelo para obtener una vista previa de un subconjunto muestreado de los resultados.

## <a name="add-search-results-to-a-review-set"></a>Agregar los resultados de búsqueda a un conjunto de revisión

Cuando esté listo para recopilar y procesar todos los resultados de una búsqueda, puede hacerlo si lo agrega a un conjunto de revisión. Para obtener más información, consulte [Agregar datos a un conjunto de revisión](add-data-to-review-set.md).

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Agregar datos que no son de Microsoft 365 a un conjunto de revisión

Como parte del proceso de recopilación de un caso, también puede agregar datos que no sean de Office 365 a un conjunto de revisión y revisar y analizar junto con los datos de Office 365 que recopiló mediante la herramienta de búsqueda. Al agregar un servicio no de Office 365, debe asociarlo a un custodio específico en el caso. Para obtener más información, vea [cargar datos que no son de Microsoft 365 en un conjunto de revisión](load-non-Office-365-data-into-a-review-set.md).
