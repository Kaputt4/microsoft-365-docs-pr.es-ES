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
description: Usa Temas en Advanced eDiscovery para organizar conjuntos de revisión buscando el tema dominante en cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 342984d2482ea0027b9f6a77bdba911ede2404a6428f7b6bf4fb7a397c8c65a7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53795439"
---
# <a name="themes-in-advanced-ediscovery"></a>Temas de Advanced eDiscovery

¿Cómo escribe una persona un documento? Por lo general, comienzan con una o más ideas que desean transmitir en el documento y redactan con palabras que se alinean con las ideas. The more prevalent an idea is, the more frequent the words that are related to that idea tend to be. Esto también informa de cómo los usuarios consumen documentos. Lo importante que se debe comprender al leer un documento son las ideas que el documento está intentando transmitir, qué ideas aparecen donde y cuáles son las relaciones entre las ideas.

Esto se puede extender a la forma en que una persona quiere consumir un conjunto de documentos. Quieren ver qué ideas están presentes en los conjuntos y qué documentos hablan de esas ideas. Además, si encuentran un documento de interés concreto, desean poder ver documentos que deba ton de ideas similares.

La funcionalidad Temas de Advanced eDiscovery intenta imitar la razón  de los humanos acerca de los documentos, analizando los temas que se debaten en un conjunto de revisión y asignando un tema a los documentos del conjunto de revisión. En Advanced eDiscovery, Temas va un paso más allá e identifica el *tema dominante* en cada documento. El tema dominante es el que aparece con más frecuencia en un documento.

## <a name="how-does-themes-work"></a>¿Cómo funciona Themes?

La función Temas analiza documentos con texto en un conjunto de revisión para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión. La exhibición avanzada de documentos electrónicos asigna esos temas a los documentos en los que aparecen. También etiqueta cada tema con las palabras usadas en los documentos que son representativos del tema. Dado que un documento puede contener varios tipos de asunto, la exhibición avanzada de documentos electrónicos a menudo asigna varios temas a los documentos. El tema que aparece de forma más destacada en un documento se designa como su tema final.
