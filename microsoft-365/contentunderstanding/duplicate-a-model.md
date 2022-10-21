---
title: Duplicar un modelo en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo y por qué duplicar un modelo en Microsoft Syntex.
ms.openlocfilehash: 88860487d14a7a4bab3742f610854623cc8f681d
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660783"
---
# <a name="duplicate-a-model-in-microsoft-syntex"></a>Duplicar un modelo en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; procesamiento de documentos no estructurados</sup>

Duplicar un modelo de procesamiento de documentos no estructurado puede ahorrarle tiempo y esfuerzo si necesita crear un nuevo modelo y saber que un modelo existente es muy similar a lo que necesita.

Por ejemplo, un modelo existente denominado "Contratos" clasifica los mismos archivos con los que tiene que trabajar. El nuevo modelo extraerá algunos de los datos existentes, pero necesitará ser actualizado para poder extraer datos adicionales. En lugar de crear y entrenar un modelo desde cero, puede usar la característica de modelo duplicado para hacer una copia del modelo Contratos, que también copiará todos los elementos de aprendizaje asociados, como los archivos de ejemplo y los extractores de entidades.

Cuando duplique el modelo, después de cambiarle el nombre (por ejemplo, a "Renovaciones de contrato"), podrá realizar actualizaciones en él. Por ejemplo, puede quitar algunos de los campos extraídos existentes que no necesite y, después, entrenar el modelo para extraer uno nuevo (por ejemplo, "Fecha de renovación").

## <a name="duplicate-a-model"></a>Duplicar un modelo

Siga estos pasos para duplicar un modelo de procesamiento de documentos no estructurado.

1. Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.

2. En la página **Modelos**, seleccione el modelo que quiere duplicar.

3. Mediante la cinta de opciones o el botón **Mostrar acciones** (junto al nombre del modelo), seleccione **Duplicar**.</br>

    ![Captura de pantalla de la página Modelos que muestra un modelo seleccionado con las opciones de Duplicar resaltadas.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. En el panel **Duplicar modelo**:

   a. En **Nombre**, escriba el nuevo nombre del modelo que quiere duplicar.</br>

    ![Captura de pantalla que muestra el panel Duplicar modelo.](../media/content-understanding/duplicate-model-panel.png) </br>

   b. En **Descripción**, agregue una descripción del modelo nuevo.

   c. (Opcional) En **Configuración avanzada**, seleccione si quiere asociar un [tipo de contenido](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) existente.

5. Seleccione **Duplicar**.

## <a name="see-also"></a>Vea también

[Cambiar el nombre de un modelo](rename-a-model.md)

[Modo de accesibilidad de Syntex](accessibility-mode.md)