---
title: Compatibilidad con CJK/Double Byte para eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo Microsoft Purview eDiscovery (Premium) en Microsoft 365 admite idiomas chino, japonés y coreano (CJK), que usan un juego de caracteres de doble byte.
ms.openlocfilehash: e6221d37a3ebb07414f87f349b020365c80990e3
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64992224"
---
# <a name="cjk-language-support-for-ediscovery-premium"></a>Compatibilidad del lenguaje CJK con eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview eDiscovery (Premium) admite idiomas de juego de caracteres de doble byte (estos incluyen chino simplificado, chino tradicional, japonés y coreano, que se conocen colectivamente como lenguajes *CJK*) para los siguientes escenarios avanzados en un conjunto de revisión:

- Al [consultar los datos de un conjunto de revisión](review-set-search.md).

- Al [etiquetar documentos en un conjunto de revisión](tagging-documents.md).

- Al [analizar los datos de casos en un conjunto de revisión mediante el](analyzing-data-in-review-set.md) análisis de temas, subprocesos de correo electrónico y detección casi duplicados.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**Cómo crear una búsqueda para recopilar elementos que contengan caracteres CJK?**

Puede usar caracteres CJK para [búsquedas de palabras clave](building-search-queries.md#keyword-searches), [consultas de palabras clave y condiciones de búsqueda](keyword-queries-and-search-conditions.md) al buscar contenido en eDiscovery (Premium). La búsqueda de caracteres CJK también se admite al buscar contenido en Microsoft Purview eDiscovery (Estándar) y Búsqueda de contenido.

Proporcionamos compatibilidad con CJK para todos los [operadores de búsqueda](keyword-queries-and-search-conditions.md#search-operators) y [las condiciones de búsqueda](keyword-queries-and-search-conditions.md#search-conditions), incluidos los operadores booleanos **AND**, **OR**, **NOT** y **NEAR**.

Si está seguro de que las ubicaciones de contenido o los elementos contienen caracteres CJK, pero las búsquedas no devuelven ningún resultado, haga clic en el icono idioma-país o región de la consulta. ![Icono idioma-país o región de consulta en búsqueda de contenido.](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) y seleccione el valor de código de referencia cultural idioma-país correspondiente para la búsqueda. Por defecto, la versión del idioma/región es la neutra.

**¿Puedo buscar varios idiomas a la vez?**

Depende del escenario de búsqueda.

- Al [consultar datos en un conjunto de revisión](review-set-search.md) en eDiscovery (Premium), puede buscar varios idiomas.

- Al [crear una búsqueda para recopilar datos](create-draft-collection.md), cree colecciones independientes para cada idioma de destino. Por ejemplo, si está buscando un documento que contenga chino y coreano, seleccione Chino para la primera colección y seleccione Coreano para la segunda colección.

**No veo el icono idioma-país o región de consulta para seleccionar un idioma para las consultas de un conjunto de revisión. ¿Cómo puedo especificar un lenguaje de consulta en una búsqueda de conjuntos de revisión?**

En el caso de las consultas de conjunto de revisión, no es necesario especificar un idioma de documento. eDiscovery (Premium) detecta automáticamente los idiomas del documento al agregar contenido a un conjunto de revisión. Esto le ayuda a optimizar los resultados de la consulta en un conjunto de revisión.

**¿Puedo ver los idiomas [detectados en los metadatos de archivo](view-documents-in-review-set.md#file-metadata)?**

No, no puede ver los idiomas detectados en los metadatos de archivo.

**¿Puedo filtrar por idiomas de documento en un conjunto de revisión**?

No, no puede filtrar, ordenar ni buscar por idiomas de documento en un conjunto de revisión.

**¿Afectará esta versión de CJK a los escenarios de conjuntos de revisión cualquiera de mis búsquedas y conjuntos de revisión existentes?**

No, ninguna de las búsquedas y conjuntos de revisión existentes cambiará. No es necesario volver a indexar los datos existentes y los resultados de búsqueda del texto en inglés serán los mismos.

**Cómo cambiar mi idioma de presentación a chino, japonés o coreano?**

Para obtener información sobre cómo cambiar el idioma de visualización y la zona horaria, consulte [Cómo establecer la configuración de idioma y región para Office 365](/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Problemas conocidos

- OCR no admite caracteres CJK de archivos de imagen

- Los archivos de correo electrónico (como *.eml y *.msg) en la [vista Anotar](view-documents-in-review-set.md#annotate-view) no son compatibles con los idiomas CJK.

- El resaltado de aciertos de búsqueda en [la vista Texto](view-documents-in-review-set.md#text-view) no se admite para los idiomas CJK.

- El [módulo Relevancia](using-relevance.md) que se usa para analizar datos no admite lenguajes CJK.

- Las [retenciones basadas en consultas](managing-holds.md#manage-non-custodial-holds) no se admiten en los lenguajes CJK.