---
title: 'Temas: eDiscovery'
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
description: Use los temas de la exhibición avanzada de documentos electrónicos para organizar los conjuntos de revisiones buscando el tema dominante en cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285536"
---
# <a name="themes-in-advanced-ediscovery"></a>Temas en eDiscovery avanzado

¿Cómo escribe un documento un usuario? Por lo general, comienzan con una o más ideas que quieren transmitir en el documento y se redactan con palabras que se alinean con las ideas. Cuanto más frecuente sea la idea, más frecuentes serán las palabras relacionadas con dicha idea. Esto informa de cómo los usuarios también usan los documentos. Lo más importante que debe comprender a partir de la lectura de un documento son las ideas que el documento está tratando de transmitir, las ideas que aparecen en dónde y cuáles son las relaciones entre las ideas.

Esto puede ampliarse a cómo una persona desea consumir un conjunto de documentos. Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando sobre esas ideas. Además, si encuentran un documento concreto de interés, quieren poder ver documentos que discutan ideas similares.

La funcionalidad de temas en eDiscovery avanzado intenta imitar la razón de los documentos de los usuarios mediante el análisis de los *temas* que se tratan en un conjunto de revisiones y la asignación de un tema a los documentos en el conjunto de revisión. En la exhibición avanzada de documentos electrónicos, los temas van un paso más allá e identifican el *tema dominante* en cada documento. El tema dominante es el que aparece con más frecuencia en un documento.

## <a name="how-does-themes-work"></a>¿Cómo funciona los temas?

La funcionalidad temas analiza los documentos con texto en una revisión establecida para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión. EDiscovery avanzado asigna los temas a los documentos en los que aparecen. También etiqueta cada tema con las palabras que se usan en los documentos representativos del tema. Debido a que un documento puede contener varios tipos de asunto, eDiscovery avanzado suele asignar varios temas a los documentos. El tema que aparece más visiblemente en un documento se designa como su tema dominante.
