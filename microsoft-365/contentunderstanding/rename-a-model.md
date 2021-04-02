---
title: Cambiar el nombre de un modelo en Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo y por qué cambiar el nombre de un modelo en Microsoft SharePoint Syntex.
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446061"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a>Cambiar el nombre de un modelo en Microsoft SharePoint Syntex

En algún momento, puede que quiera cambiar el nombre de un modelo de comprensión mediante documentos. Un ejemplo común es cuando crea un borrador inicial de un modelo, para el que posiblemente no haya pensado demasiado en el nombre final (por ejemplo, es posible que lo llamara "AlexInerbaModel1"). A medida que está más cerca de finalizar el modelo y ponerlo en uso, se da cuenta de que un nombre más apropiado sería "Renovaciones de contrato" y decide cambiarle el nombre.  

Otro ejemplo es cuando su organización toma la decisión de referirse a un proceso o tipo de documento con un nombre diferente. Por ejemplo, después de crear el modelo y estar listo para aplicarlo, su organización podría pensar que todos los elementos con el nombre "Contratos" ahora se denominarán formalmente "Acuerdos". Si es necesario, puede elegir cambiar el nombre del modelo de "Renovaciones de contrato" a "Renovaciones de contrato".

> [!IMPORTANT]
> Solo puede cambiar el nombre de un modelo de comprensión mediante documentos si no se ha aplicado a una biblioteca de documentos. 

Al cambiar el nombre de un modelo también se cambia el [tipo de contenido](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que está asociado al modelo.

## <a name="rename-a-model"></a>Cambiar el nombre de un modelo

Siga estos pasos para cambiar el nombre a un modelo de comprensión mediante documentos.

1. Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.

2. En la página **Modelos**, seleccione el modelo al que quiere cambiar el nombre.

3. Mediante la cinta de opciones o el botón **Mostrar acciones** (junto al nombre del modelo), seleccione **Cambiar nombre**. </br>

    ![Captura de pantalla de la página Modelos que muestra un modelo seleccionado con las opciones de Cambiar nombre resaltadas.](../media/content-understanding/select-model-rename-both.png) </br>

4. En el panel **Cambiar nombre del modelo**:

   a. En **Nuevo nombre**, escriba el nuevo nombre del modelo cuyo nombre quiere cambiar.</br>

    ![Captura de pantalla que muestra el panel Cambiar nombre del modelo.](../media/content-understanding/rename-model-panel.png) </br>

   b. (Opcional) En **Configuración avanzada**, seleccione si quiere asociar un [tipo de contenido](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) existente. Si elige **Usar un tipo de contenido existente**, se cambiará el nombre del modelo para que coincida con el tipo de contenido seleccionado.

5. Seleccione **Cambiar nombre**.

## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Cambiar el nombre de un extractor](rename-an-extractor.md)

[Información general sobre la comprensión de los documentos](document-understanding-overview.md)

[Tipos de explicación](explanation-types-overview.md)

[Aplicar un modelo](apply-a-model.md) 
