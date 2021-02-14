---
title: 'Temas: exhibición de documentos electrónicos'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use temas en eDiscovery avanzado para organizar conjuntos de revisión mediante la búsqueda del tema dominante en cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285536"
---
# <a name="themes-in-advanced-ediscovery"></a>Temas en eDiscovery avanzado

¿Cómo escribe un documento una persona? Por lo general, empiezan con una o más ideas que quieren transmitir en el documento y redactan con palabras que se alinean con las ideas. Cuando más frecuente sea una idea, más frecuentes serán las palabras relacionadas con esa idea. Esto informa de cómo los usuarios consumen documentos también. Lo importante que se debe comprender al leer un documento son las ideas que el documento intenta transmitir, qué ideas aparecen en qué lugar y cuáles son las relaciones entre las ideas.

Esto puede extenderse a la forma en que una persona desea consumir un conjunto de documentos. Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando de esas ideas. Además, si encuentran un documento de interés concreto, desean poder ver documentos que analizan ideas similares.

La funcionalidad De temas de eDiscovery avanzado intenta imitar  la razón de los usuarios sobre los documentos, analizando los temas que se analizan en un conjunto de revisión y asignando un tema a los documentos del conjunto de revisión. En eDiscovery avanzado, los temas van un paso más allá e identifican el *tema dominante* en cada documento. El tema dominante es el que aparece con más frecuencia en un documento.

## <a name="how-does-themes-work"></a>¿Cómo funcionan los temas?

La funcionalidad Temas analiza los documentos con texto en un conjunto de revisión para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión. EDiscovery avanzado asigna esos temas a los documentos en los que aparecen. También etiqueta cada tema con las palabras usadas en los documentos que son representativos del tema. Dado que un documento puede contener varios tipos de temas, eDiscovery avanzado suele asignar varios temas a los documentos. El tema que aparece más destacado en un documento se designa como su tema dominante.
