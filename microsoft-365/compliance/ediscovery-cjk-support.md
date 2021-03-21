---
title: Compatibilidad con CJK/Double Byte para eDiscovery avanzada
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
description: Obtenga información sobre cómo la exhibición de documentos electrónicos avanzada en Microsoft 365 admite los idiomas chino, japonés y coreano (CJK), que usan un juego de caracteres de doble byte.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926606"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Compatibilidad con lenguaje CJK para exhibición de documentos electrónicos avanzada

La exhibición de documentos electrónicos avanzada admite idiomas de juego de caracteres de doble byte (entre los que se incluyen chino simplificado, chino tradicional, japonés y coreano, que se conocen colectivamente como idiomas *CJK)* para los siguientes escenarios avanzados de un conjunto de opiniones:

- Al consultar [los datos de un conjunto de revisión](review-set-search.md).

- Al [etiquetar documentos en un conjunto de revisión](tagging-documents.md).

- Al analizar [los datos de casos en un conjunto de revisión](analyzing-data-in-review-set.md) mediante la detección casi duplicada, el subproceso de correo electrónico y el análisis de temas.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Cómo puedo crear una búsqueda para recopilar elementos que contengan caracteres CJK?**

Puede usar caracteres CJK para [búsquedas](building-search-queries.md#keyword-searches)de palabras clave, consultas [de](keyword-queries-and-search-conditions.md) palabras clave y condiciones de búsqueda al buscar contenido en eDiscovery avanzada. También se admite la búsqueda de caracteres CJK al buscar contenido en la exhibición de documentos electrónicos principal y la búsqueda de contenido.

Proporcionamos compatibilidad con CJK para todos [los](keyword-queries-and-search-conditions.md#search-operators) operadores de búsqueda y las condiciones de [búsqueda,](keyword-queries-and-search-conditions.md#search-conditions)incluidos los operadores **booleanos AND**, **OR**, **NOT** y **NEAR**.

Si está seguro de que las ubicaciones de contenido o los elementos contienen caracteres CJK, pero las búsquedas no devuelven ningún resultado, haga clic en el icono idioma-país o región de la consulta ![Icono de idioma-país/región de consulta en búsqueda de contenido](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) y seleccione el valor de código de referencia cultural idioma-país correspondiente para la búsqueda. Por defecto, la versión del idioma/región es la neutra.

**¿Puedo buscar varios idiomas a la vez?**

Depende del escenario de búsqueda.

- Al consultar [datos en un conjunto de revisión](review-set-search.md) de eDiscovery avanzado, puede buscar varios idiomas.

- Al crear [una búsqueda para recopilar datos,](create-search-to-collect-data.md)cree una búsqueda independiente para cada idioma de destino. Por ejemplo, si está buscando un documento que contenga chino y coreano, seleccione Chino para la primera consulta y seleccione Coreano para la segunda consulta.

**No veo el icono de idioma-país o región de consulta para seleccionar un idioma para las consultas de un conjunto de revisión. ¿Cómo puedo especificar un idioma de consulta en una búsqueda de conjunto de revisión?**

Para las consultas de conjunto de revisión, no es necesario especificar un idioma del documento. La exhibición de documentos electrónicos avanzada detecta automáticamente los idiomas de los documentos al agregar contenido a un conjunto de revisión. Esto le ayuda a optimizar los resultados de la consulta en un conjunto de revisión.

**¿Puedo ver idiomas detectados en metadatos [de archivo?](view-documents-in-review-set.md#file-metadata)**

No, no puede ver los idiomas detectados en los metadatos de archivo.

**¿Puedo filtrar por idiomas de documento en un conjunto de revisión?**

No, no puede filtrar, ordenar o buscar por idiomas de documento en un conjunto de revisión.

**¿Afectará esta versión de CJK a los escenarios de conjunto de revisión alguno de mis conjuntos de búsquedas y revisión existentes?**

No, ninguna de las búsquedas y conjuntos de revisión existentes cambiará. No es necesario volver a indizar los datos existentes y los resultados de la búsqueda del texto en inglés serán los mismos.

**¿Cómo puedo cambiar mi idioma de presentación a chino, japonés o coreano?**

Para obtener información sobre cómo cambiar el idioma para mostrar y la zona horaria, vea [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Problemas conocidos

- OCR no admite caracteres CJK de archivos de imagen

- Los archivos de correo electrónico (como *.eml y *.msg) en la vista Anotación no son compatibles con los idiomas CJK. [](view-documents-in-review-set.md#annotate-view)

- El resaltado de resultados de búsqueda en [la vista](view-documents-in-review-set.md#text-view) Texto no es compatible con los idiomas CJK.

- El [módulo Relevancia](using-relevance.md) usado para analizar datos no admite idiomas CJK.

- [Las retenciones basadas en](managing-holds.md#manage-non-custodial-holds) consultas no son compatibles con los idiomas CJK.