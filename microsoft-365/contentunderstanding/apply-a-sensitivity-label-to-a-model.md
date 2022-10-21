---
title: Aplicar una etiqueta de confidencialidad a un modelo en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo aplicar una etiqueta de confidencialidad a un modelo de Microsoft Syntex.
ms.openlocfilehash: b38cbdd23270a16a7f912fe78dff920c670cfe95
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660893"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-syntex"></a>Aplicar una etiqueta de confidencialidad a un modelo en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; procesamiento de documentos no estructurados</sup>

Puede aplicar fácilmente una [etiqueta de confidencialidad](../compliance/sensitivity-labels.md) a los modelos de procesamiento de documentos no estructurados en Microsoft Syntex. 

> [!Note]
> Las etiquetas de confidencialidad aún no están disponibles para los modelos precompilados o para los modelos de procesamiento de documentos estructurados o de forma libre.

Las etiquetas de confidencialidad permiten aplicar cifrado a los documentos que identifican los modelos. Por ejemplo, quiere que el modelo no solo identifique los documentos financieros que contengan números de cuenta bancaria o números de tarjeta de crédito cargados en la biblioteca de documentos, sino también que aplique una etiqueta de confidencialidad configurada con la configuración de cifrado para restringir quién puede acceder a ese contenido y cómo se puede usar. Los modelos de Syntex respetan las reglas de [pedido de etiquetas](../compliance/apply-sensitivity-label-automatically.md#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) y tampoco sobrescriben una etiqueta existente que un usuario aplicó manualmente al archivo. 

Puede aplicar una etiqueta de confidencialidad preexistente al modelo en la página principal del modelo. Para que esté disponible en la selección desde la configuración del modelo, la etiqueta ya debe haberse publicado. Las etiquetas se aplican a los archivos de Office para Word (.docx), PowerPoint (.pptx) y Excel (.xlsx). 

> [!Important]
> Para que las etiquetas de confidencialidad estén disponibles para aplicarlas a los modelos, deben [crearse y publicarse en el portal de cumplimiento Microsoft Purview](../admin/security-and-compliance/set-up-compliance.md).

## <a name="add-a-sensitivity-label-to-a-model"></a>Adición de una etiqueta de confidencialidad a un modelo

1. En la página principal del modelo, seleccione **Configuración del modelo**.

   ![Captura de pantalla de la página Modelos con la opción Configuración de modelo resaltada.](../media/content-understanding/sensitivity-model-settings.png)

2. En el panel **Configuración del modelo**, sección **Cumplimiento**, seleccione el menú **Etiqueta de confidencialidad** para ver una lista de las etiquetas de confidencialidad disponibles para que se apliquen al modelo.

   ![Captura de pantalla del panel Configuración del modelo que muestra el menú de etiqueta de confidencialidad.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. Seleccione la etiqueta de confidencialidad que desea aplicar al modelo y, a continuación, seleccione **Guardar**.

Después de aplicar la etiqueta de confidencialidad al modelo, puede aplicarla a:

- una nueva biblioteca de documentos y
- una biblioteca de documentos en la que ya se aplica el modelo.
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Aplicar la etiqueta de confidencialidad a la biblioteca de documentos en la que ya se aplica el modelo

Si el modelo ya se ha aplicado a una biblioteca de documentos, puede hacer lo siguiente para sincronizar la actualización de la etiqueta de confidencialidad para aplicarla a la biblioteca de documentos:

1. En la Página principal del modelo, sección **Bibliotecas con este modelo**, seleccione la biblioteca de documentos a la que quiera aplicar la actualización de la etiqueta de confidencialidad.

2. Seleccione **Sincronizar**.

   ![Captura de pantalla que muestra la sección Bibliotecas en este modelo con Sincronización resaltada.](../media/content-understanding/sensitivity-libraries-sync.png)

Después de aplicar la actualización y sincronizarla con el modelo, puede confirmar que se ha aplicado haciendo lo siguiente:

1. En el centro de contenido, sección **Bibliotecas con este modelo**, seleccione la biblioteca a la que se ha aplicado el modelo actualizado. 

2. En la vista de la biblioteca de documentos, seleccione el icono de información para ver las propiedades del modelo.

3. En la lista **Modelos activos**, seleccione el modelo actualizado.

4. En la sección **etiqueta de confidencialidad**, verá el nombre de la etiqueta de confidencialidad aplicada.

En la página de vista del modelo de la biblioteca de documentos, se mostrará una nueva columna de la **Etiqueta de confidencialidad**. A medida que el modelo clasifica los archivos que identifica como pertenecientes al tipo de contenido y los muestra en la vista de biblioteca, en la columna **Etiqueta de confidencialidad** también se muestra el nombre de la etiqueta de confidencialidad que se ha aplicado con el modelo.

Por ejemplo, en todos los documentos financieros que identifique el modelo también se aplicará la etiqueta de confidencialidad *Cifrado*, lo que evitará que los usuarios no autorizados tengan acceso a ellos. Si una persona no autorizada intenta acceder al archivo desde la biblioteca de documentos, un error le informará de que no le está permitido debido a la etiqueta de confidencialidad aplicada.

## <a name="see-also"></a>Ver también

[Aplicar una etiqueta de retención](apply-a-retention-label-to-a-model.md)

