---
title: Recopilar datos para un caso en eDiscovery avanzado
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
description: Obtenga información sobre cómo identificar un conjunto de documentos para su revisión en una investigación mediante la herramienta de búsqueda en eDiscovery avanzado.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751277"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Recopilar datos para un caso en eDiscovery avanzado

Una vez que haya identificado administradores y orígenes de datos que son de interés para su caso, es el momento de identificar el conjunto de documentos en los que profundizar. Puede usar la herramienta de búsqueda en eDiscovery avanzado para identificar documentos relevantes de ubicaciones de custodia y no custodia en Microsoft 365.

Después de ejecutar una búsqueda, puede ver estadísticas de los elementos recuperados, como las ubicaciones con más elementos que coincidieron con la consulta de búsqueda. También puede obtener una vista previa de un subconjunto de los resultados. Cuando haya identificado el conjunto de documentos que desea examinar, puede agregar los resultados de la búsqueda a un conjunto de revisión para recopilar y procesar.

## <a name="create-a-search"></a>Crear una búsqueda

Si selecciona **Nueva búsqueda en** la pestaña **Búsquedas,** se iniciará un asistente que le guiará a través de la creación de una búsqueda. Para obtener información detallada sobre cómo crear una búsqueda, vea [Crear una búsqueda para recopilar datos.](create-search-to-collect-data.md)

Después de crear una búsqueda, se muestra una página desplegable con detalles. Los **botones Estadísticas** **y Vista** previa no están disponibles inicialmente porque la búsqueda aún no se ha completado. Puede realizar un seguimiento del progreso de la búsqueda en la **pestaña** Búsquedas.

## <a name="view-search-results-and-statistics"></a>Ver resultados de búsqueda y estadísticas

Hay dos componentes de una búsqueda de contenido: estadísticas (estimaciones) y vista previa. A medida que se complete cada uno de estos componentes,  verá que el estado que se muestra en las columnas correspondientes en la pestaña Búsquedas cambia de **Enviado** a En curso **a** **Completado.**

Una vez completada la estimación de búsqueda, seleccione la búsqueda para mostrar la página desplegable, que mostrará algunas estadísticas de alto nivel sobre los resultados de la búsqueda. En este punto, el **botón Estadísticas** estará activo. Puede seleccionarla para ver estadísticas de búsqueda, como:

- Resumen
- Ubicaciones principales
- Consultas

Para obtener más información acerca de las estadísticas de búsqueda, vea [Estadísticas de búsqueda.](search-statistics-in-advanced-ediscovery.md)

Una vez completada la vista previa, **el** botón Vista previa estará activo. Selecciónelo para obtener una vista previa de un subconjunto de muestra de los resultados.

## <a name="add-search-results-to-a-review-set"></a>Agregar los resultados de búsqueda a un conjunto de revisión

Cuando esté listo para recopilar y procesar todos los resultados de una búsqueda, puede hacerlo agregándole a un conjunto de revisión. Para obtener más información, [vea Agregar datos a un conjunto de revisión.](add-data-to-review-set.md)

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Agregar datos que no son de Microsoft 365 a un conjunto de revisión

Como parte del proceso de recopilación de un caso, también puede agregar datos que no son de Office 365 a un conjunto de revisión y revisar y analizar junto con los datos de Office 365 que recopiló mediante la herramienta de búsqueda. Cuando agrega un usuario que no es de Office 365, tiene que asociarlo con un administrador específico en el caso. Para obtener más información, vea Cargar datos que no son [de Microsoft 365 en un conjunto de revisión.](load-non-Office-365-data-into-a-review-set.md)
