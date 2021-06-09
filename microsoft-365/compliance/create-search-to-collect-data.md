---
title: Crear una búsqueda
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
description: Obtenga información sobre cómo crear, definir y elegir custodios y ubicaciones de custodia para una búsqueda en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035772"
---
# <a name="create-a-search"></a>Crear una búsqueda

En la **pestaña** Búsquedas del caso, puede crear una nueva búsqueda haciendo clic en **Nueva búsqueda** y siguiendo el asistente.

![El asistente de búsqueda en un Advanced eDiscovery caso](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Asigne un nombre a la búsqueda y déle una descripción.

Cada búsqueda con un caso debe tener un nombre único. Opcionalmente, puede proporcionar una descripción para la búsqueda. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Elegir los custodios y ubicaciones de custodia para buscar

Elija ubicaciones de contenido de custodia para buscar especificando los custodios que ha agregado al caso. Al seleccionar un custodio, ejecutará la búsqueda en todos los orígenes de datos asignados al custodio. También tiene la opción de restringir la búsqueda a orígenes de datos seleccionados para cada custodio. Para obtener más información acerca de cómo agregar custodios y administrar sus orígenes de datos, vea [Trabajar con custodios.](managing-custodians.md)

## <a name="choose-non-custodial-locations"></a>Elegir ubicaciones sin custodia

En algunos casos, es posible que desee buscar orígenes de datos que no estén asociados con un custodio. En este caso, puede especificar las ubicaciones que desea buscar o elegir buscar en todas las ubicaciones de contenido para un servicio de Microsoft específico (como buscar todos los buzones de Exchange o todos los sitios SharePoint y OneDrive cuentas).

## <a name="define-the-search-query-and-conditions"></a>Definir las condiciones y la consulta de búsqueda

Puede definir la consulta de palabras clave y cualquier condición para la búsqueda mediante las tarjetas de condición predefinidas o mediante lenguaje de consulta de palabras clave (KQL). Para obtener más información, vea [Generar consultas de búsqueda](building-search-queries.md).
