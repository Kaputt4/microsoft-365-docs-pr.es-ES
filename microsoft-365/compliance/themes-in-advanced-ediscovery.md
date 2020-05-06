---
title: 'Temas: eDiscovery'
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
description: Use los temas de la exhibición avanzada de documentos electrónicos para organizar los conjuntos de revisiones buscando el tema dominante en cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: eb008e091cd8c8330d1cdd5b388e252af70922da
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034524"
---
# <a name="themes"></a>Temas

¿Cómo escribe un documento un usuario? Por lo general, comienzan con una o más ideas que quieren transmitir en el documento y se redactan con palabras que se alinean con las ideas. Cuanto más frecuente sea la idea, más frecuentes serán las palabras relacionadas con dicha idea. Esto informa de cómo los usuarios también usan los documentos. Lo más importante que debe comprender a partir de la lectura de un documento son las ideas que el documento está tratando de transmitir, las ideas que aparecen en dónde y cuáles son las relaciones entre las ideas.

Esto puede ampliarse a cómo una persona desea consumir un conjunto de documentos. Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando sobre esas ideas. Además, si encuentran un documento concreto de interés, quieren poder ver documentos que discutan ideas similares.

La funcionalidad de temas en eDiscovery avanzado intenta imitar la razón de los documentos de los usuarios mediante el análisis de los *temas* que se tratan en un conjunto de revisiones y la asignación de un tema a los documentos en el conjunto de revisión. En la exhibición avanzada de documentos electrónicos, los temas van un paso más allá e identifican el *tema dominante* en cada documento. El tema dominante es el que aparece con más frecuencia en un documento.

## <a name="how-does-themes-work"></a>¿Cómo funciona los temas?

La funcionalidad temas analiza los documentos con texto en una revisión establecida para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión. EDiscovery avanzado asigna los temas a los documentos en los que aparecen. También etiqueta cada tema con las palabras que se usan en los documentos representativos del tema. Debido a que un documento puede contener varios tipos de asunto, eDiscovery avanzado suele asignar varios temas a los documentos. El tema que aparece más visiblemente en un documento se designa como su tema dominante.
