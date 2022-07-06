---
title: Configuración de etiquetas inteligentes en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Las etiquetas inteligentes permiten aplicar las funcionalidades de aprendizaje automático al revisar el contenido en un caso de eDiscovery (Premium). Use grupos de etiquetas inteligentes para mostrar los resultados de los modelos de detección de aprendizaje automático, como el modelo de privilegios abogado-cliente.
ms.openlocfilehash: 30d2d6f30f09fe8fb6772a4fb46c6895b174991f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629087"
---
# <a name="set-up-smart-tags-in-ediscovery-premium"></a>Configuración de etiquetas inteligentes en eDiscovery (Premium)

Las funcionalidades de Aprendizaje automático (ML) en Microsoft Purview eDiscovery (Premium) pueden ayudarle a hacer que el proceso de decisión sea más eficaz al revisar documentos de casos en un conjunto de revisión. Las etiquetas inteligentes son una manera de llevar las funcionalidades de ML al lugar donde se registran las decisiones: al etiquetar documentos durante la revisión. Al crear un grupo de etiquetas inteligentes, las decisiones que son el resultado del modelo de ML que ha asociado al grupo de etiquetas inteligentes se muestran en línea con las etiquetas del grupo de etiquetas. Esto ayuda a ver la información de resultados de ML en línea al revisar documentos específicos.

## <a name="how-to-set-up-a-smart-tag-group"></a>Configuración de un grupo de etiquetas inteligentes

1. En un conjunto de revisiones, haga clic en **Administrar conjunto de revisión** y, a continuación, haga clic en **Administrar etiquetas**.

2. Haga clic en **Agregar grupo de etiquetas** y, a continuación, seleccione **Agregar grupo de etiquetas inteligentes**.

3. Seleccione el modelo de ML que desea asociar al grupo de etiquetas.
    
   Esto crea un grupo de etiquetas y *N* etiquetas secundarias, donde *N* es el número de posibles salidas del modelo. Por ejemplo, el [modelo de detección de privilegios abogado-cliente](attorney-privilege-detection.md) tiene dos salidas posibles: 

   - **Positivo** : se usa para etiquetar documentos que contienen contenido con privilegios de abogado-cliente.
   
   - **Negativo** : se usa para etiquetar documentos que no contienen contenido con privilegios de abogado-cliente.
    
    Si selecciona este modelo, se crea un grupo de etiquetas con dos etiquetas secundarias (una etiqueta secundaria denominada **Positive** y la otra denominada **Negative**) para el conjunto de revisión. En este ejemplo, cada etiqueta secundaria corresponde a una de las posibles salidas del modelo de detección de privilegios abogado-cliente.

4. Opcionalmente, puede cambiar el nombre del grupo de etiquetas y las etiquetas secundarias. Por ejemplo, podría cambiar el nombre de la etiqueta **Positive** a **Privileged** y la etiqueta **Negative** a **Not privileged(No con privilegios**).

## <a name="how-to-use-smart-tags"></a>Uso de etiquetas inteligentes

Al revisar un documento, los resultados del modelo se muestran junto a la etiqueta secundaria adecuada. Por ejemplo, si tiene un grupo de etiquetas inteligentes para la detección de privilegios abogado-cliente y revisa un documento que tiene potencialmente privilegios, el motivo de esa conclusión se muestra junto a la etiqueta adecuada. Es importante tener en cuenta que la etiqueta no se aplica automáticamente al documento. El revisor toma la decisión sobre cómo etiquetar el documento.
