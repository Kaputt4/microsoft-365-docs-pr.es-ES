---
title: Configurar etiquetas inteligentes en Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: Las etiquetas inteligentes le permiten aplicar las capacidades de aprendizaje automático al revisar el contenido en un Advanced eDiscovery caso. Use grupos de etiquetas inteligentes para mostrar los resultados de los modelos de detección de aprendizaje automático, como el modelo de privilegios abogado-cliente.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081087"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Configurar etiquetas inteligentes en Advanced eDiscovery

Las funcionalidades de aprendizaje automático (ML) en Advanced eDiscovery pueden ayudarle a hacer que el proceso de decisión sea más eficaz al revisar documentos de casos en un conjunto de opiniones. Las etiquetas inteligentes son una forma de llevar las ML a donde se registran las decisiones: al etiquetar documentos durante la revisión. Al crear un grupo de etiquetas inteligentes, las decisiones que son el resultado del modelo de ML asociado al grupo de etiquetas inteligentes se muestran en línea con las etiquetas del grupo de etiquetas. Esto ayuda a ver la ML de resultados en línea al revisar documentos específicos.

## <a name="how-to-set-up-a-smart-tag-group"></a>Cómo configurar un grupo de etiquetas inteligentes

1. En un conjunto de revisión, haga **clic en Administrar conjunto de revisión** y, a continuación, haga clic en Administrar **etiquetas**.

2. Haga **clic en Agregar grupo de** etiquetas y, a continuación, seleccione Agregar grupo de **etiquetas inteligentes**.

3. Seleccione el ML que desea asociar al grupo de etiquetas.
    
   Esto crea un grupo de etiquetas y *N* etiquetas secundarias, donde *N* es el número de salidas posibles del modelo. Por ejemplo, el [modelo de detección de privilegios abogado-cliente](attorney-privilege-detection.md) tiene dos salidas posibles: 

   - **Positivo:** se usa para etiquetar documentos que contienen contenido con privilegios de abogado-cliente.
   
   - **Negativo:** se usa para etiquetar documentos que no contienen contenido con privilegios de abogado-cliente.
    
    Si selecciona este modelo, se crea un grupo de etiquetas con dos etiquetas secundarias (una etiqueta secundaria denominada **Positivo** y la otra denominada **Negativo)** para el conjunto de opiniones. En este ejemplo, cada etiqueta secundaria corresponde a uno de los posibles resultados del modelo de detección de privilegios abogado-cliente.

4. Opcionalmente, puede cambiar el nombre del grupo de etiquetas y las etiquetas secundarias. Por ejemplo, puede cambiar el nombre de la **etiqueta Positive** a **Privileged** y **negative** tag a **Not privileged**.

## <a name="how-to-use-smart-tags"></a>Cómo usar etiquetas inteligentes

Al revisar un documento, los resultados del modelo se muestran junto a la etiqueta secundaria adecuada. Por ejemplo, si tiene un grupo de etiquetas inteligentes para la detección de privilegios de abogado-cliente y revisa un documento potencialmente con privilegios, el motivo de esa conclusión se muestra junto a la etiqueta adecuada. Es importante tener en cuenta que la etiqueta no se aplica automáticamente al documento. El revisor toma la decisión sobre cómo etiquetar el documento.
