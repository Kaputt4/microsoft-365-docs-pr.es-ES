---
title: Temas en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use Temas en eDiscovery (Premium) para organizar los conjuntos de revisión mediante la búsqueda del tema dominante en cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1cfbbafe6551f4483174665390d71ceb6bec0328
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096598"
---
# <a name="themes-in-ediscovery-premium"></a>Temas en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

¿Cómo escribe una persona un documento? Por lo general, comienzan con una o más ideas que quieren transmitir en el documento y redactan con palabras que se alinean con las ideas. Cuanto más frecuente sea una idea, más frecuentes suelen ser las palabras relacionadas con esa idea. Esto también informa de cómo las personas consumen documentos. Lo importante que hay que entender al leer un documento son las ideas que el documento intenta transmitir, qué ideas aparecen donde y cuáles son las relaciones entre las ideas.

Esto se puede ampliar a la forma en que una persona quiere consumir un conjunto de documentos. Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando de esas ideas. Además, si encuentran un documento de interés determinado, quieren poder ver documentos que analicen ideas similares.

La funcionalidad Temas de eDiscovery (Premium) intenta imitar cómo los seres humanos razonan sobre los documentos, analizando los *temas* que se tratan en un conjunto de revisión y asignando un tema a los documentos del conjunto de revisión. En eDiscovery (Premium), Themes va un paso más allá e identifica el *tema dominante* en cada documento. El tema dominante es el que aparece más a menudo en un documento.

## <a name="how-does-themes-work"></a>¿Cómo funcionan los temas?

La función Temas analiza documentos con texto en un conjunto de revisión para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión. eDiscovery (Premium) asigna esos temas a los documentos en los que aparecen. También etiqueta cada tema con las palabras usadas en los documentos que son representativos del tema. Dado que un documento puede contener varios tipos de materia, eDiscovery (Premium) suele asignar varios temas a los documentos. El tema que aparece de forma más destacada en un documento se designa como su tema final.
