---
title: Duplicar un modelo en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información sobre cómo y por qué duplicar un modelo en Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446082"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>Duplicar un modelo en Microsoft SharePoint Syntex

Duplicar un modelo de compresión mediante documentos puede ahorrarle tiempo y esfuerzo si necesita crear un modelo nuevo y saber si un modelo existente es muy similar a lo que necesita.

Por ejemplo, un modelo existente denominado "Contratos" clasifica los mismos archivos con los que tiene que trabajar. El nuevo modelo extraerá algunos de los datos existentes, pero necesitará ser actualizado para poder extraer datos adicionales. En lugar de crear y entrenar un modelo desde cero, puede usar la característica de modelo duplicado para hacer una copia del modelo Contratos, que también copiará todos los elementos de aprendizaje asociados, como los archivos de ejemplo y los extractores de entidades.

Cuando duplique el modelo, después de cambiarle el nombre (por ejemplo, a "Renovaciones de contrato"), podrá realizar actualizaciones en él. Por ejemplo, puede quitar algunos de los campos extraídos existentes que no necesite y, después, entrenar el modelo para extraer uno nuevo (por ejemplo, "Fecha de renovación").

## <a name="duplicate-a-model"></a>Duplicar un modelo

Siga estos pasos para duplicar un modelo de comprensión mediante documentos.

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

## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Cambiar el nombre de un modelo](rename-a-model.md)

[Crear un extractor](create-an-extractor.md)

[Información general sobre la comprensión de los documentos](document-understanding-overview.md)

[Tipos de explicación](explanation-types-overview.md)

[Aplicar un modelo](apply-a-model.md) 

[Modo de accesibilidad de SharePoint Syntex](accessibility-mode.md)