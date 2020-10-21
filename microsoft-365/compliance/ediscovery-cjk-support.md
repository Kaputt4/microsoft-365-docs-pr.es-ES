---
title: Soporte de bytes CJK o doble para eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo la exhibición avanzada de documentos electrónicos en Microsoft 365 admite idiomas de chino, Japonés y Coreano (CJK), que usan un juego de caracteres de doble byte.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626944"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Compatibilidad con el idioma CJK para eDiscovery avanzado

EDiscovery avanzado admite idiomas de juegos de caracteres de doble byte (incluidos el chino simplificado, el chino tradicional, el japonés y el coreano, que se denominan en conjunto idiomas *CJK* ) para los siguientes escenarios avanzados en un conjunto de revisión:

- Cuando se [consultan los datos de un conjunto de revisión](review-set-search.md).

- Al [etiquetar documentos en un conjunto de revisión](tagging-documents.md).

- Al [analizar datos de casos en un conjunto de revisiones mediante la](analyzing-data-in-review-set.md) detección de duplicados, el procesamiento de correo electrónico y los análisis de temas.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Cómo se crea una búsqueda para recopilar elementos que contienen caracteres CJK?**

Puede usar caracteres CJK para [búsquedas de palabras clave](building-search-queries.md#keyword-searches), [consultas de palabras clave y condiciones de búsqueda](keyword-queries-and-search-conditions.md) al buscar contenido en eDiscovery avanzado. La búsqueda de caracteres CJK también se admite al buscar contenido en la exhibición de documentos electrónicos y la búsqueda de contenido principales.

Se proporciona compatibilidad con CJK para todos los [operadores de búsqueda](keyword-queries-and-search-conditions.md#search-operators) y [condiciones de búsqueda](keyword-queries-and-search-conditions.md#search-conditions), incluidos los operadores booleanos **and**, **or**, **Not**y **Near**.

Si está seguro de que las ubicaciones de contenido o los elementos contienen caracteres CJK, pero las búsquedas no devuelven ningún resultado, haga clic en el icono de idioma de la consulta-país o región ![Idioma de consulta: icono de país o región en la búsqueda de contenido](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) y seleccione el valor de código de referencia cultural correspondiente al país de idioma para la búsqueda. Por defecto, la versión del idioma/región es la neutra.

**¿Puedo buscar varios idiomas a la vez?**

Depende del escenario de búsqueda.

- Cuando [consulta datos en un conjunto de revisión en la](review-set-search.md) exhibición avanzada de documentos electrónicos, puede buscar en varios idiomas.

- Al [crear una búsqueda para recopilar datos](create-search-to-collect-data.md), cree una búsqueda independiente para cada idioma al que esté destinado. Por ejemplo, si está buscando un documento que contenga tanto chino como coreano, seleccione chino para la primera consulta y seleccione Coreano para la segunda consulta.

**No veo el icono de idioma de la consulta, país o región, para seleccionar un idioma para las consultas de un conjunto de revisión. ¿Cómo puedo especificar un idioma de consulta en una búsqueda de conjunto de revisión?**

Para las consultas de set de revisión, no es necesario especificar un idioma de documento. EDiscovery avanzado detecta automáticamente los idiomas del documento cuando se agrega contenido a un conjunto de revisión. Esto le ayudará a optimizar los resultados de la consulta en un conjunto de revisión.

**¿Puedo ver los idiomas detectados en los [metadatos del archivo](view-documents-in-review-set.md#file-metadata)?**

No, no puede ver los idiomas detectados en los metadatos del archivo.

**¿Puedo filtrar por idiomas de documentos en un conjunto de revisión**?

No, no puede filtrar, ordenar o buscar por idiomas del documento en un conjunto de revisión.

**¿Esta versión CJK para los escenarios de revisión de revisión afecta a mis conjuntos de revisión y búsquedas existentes?**

No, se cambiará ninguna de las búsquedas y los conjuntos de revisión existentes. No es necesario reindizar los datos existentes y los resultados de búsqueda de texto en inglés serán los mismos.

**¿Cómo cambio el idioma para mostrar a chino, Japonés o Coreano?**

Para obtener información acerca de cómo cambiar la zona horaria y el idioma para mostrar, vea [el procedimiento para establecer la configuración de idioma y región para Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Problemas conocidos

- OCR no admite caracteres CJK de archivos de imagen

- Los archivos de correo electrónico (como *. eml y *. msg) en la [vista anotar](view-documents-in-review-set.md#annotate-view) no son compatibles con los idiomas CJK.

- El resaltado de referencias de búsqueda en la [vista de texto](view-documents-in-review-set.md#text-view) no es compatible con los idiomas CJK.

- El [módulo de relevancia](using-relevance.md) usado para analizar datos no admite idiomas CJK.

- Las [retenciones basadas en consultas](managing-holds.md#manage-non-custodial-holds) no son compatibles con los idiomas CJK. 
