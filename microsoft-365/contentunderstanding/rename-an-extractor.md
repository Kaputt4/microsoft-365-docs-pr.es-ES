---
title: Cambiar el nombre de un extractor en Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo y por qué cambiar el nombre de un extractor en Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446055"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>Cambiar el nombre de un extractor en Microsoft SharePoint Syntex

En algún momento, puede que tenga que cambiar el nombre de un extractor para referirse a un campo de datos extraído por un nombre diferente. Por ejemplo, su organización decide realizar cambios en sus documentos de contrato y se refiere a los "consumidores" como "clientes" en sus documentos. Si estaba extrayendo un campo "Consumidor" en su modelo, puede cambiarle el nombre a "Cliente".

Al sincronizar el modelo actualizado con la biblioteca de documentos de SharePoint, verá una nueva columna de "Cliente" en la vista de biblioteca de documentos. La vista conservará la columna "Consumidor" para la actividad anterior, pero actualizará la nueva columna "Cliente" para todos los documentos nuevos que procese su modelo. 

> [!IMPORTANT]
>  Asegúrese de sincronizar el modelo actualizado con las bibliotecas de documentos donde lo había aplicado anteriormente para que se muestre el nuevo nombre de la columna. 

## <a name="rename-an-extractor"></a>Cambiar el nombre de un extractor

Siga estos pasos para cambiar el nombre de un extractor de entidades.

1. Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.

2. En la página **Modelos**, en la columna **Nombre**, seleccione el modelo para el que quiere cambiar el nombre de un extractor.

3. En **Extractores de entidades**, seleccione el nombre del extractor al que quiere cambiar el nombre y, después, **Cambiar nombre**.</br>

    ![Captura de pantalla de la sección de Extractores de entidades que muestra un extractor seleccionado con la opción Cambiar nombre resaltada.](../media/content-understanding/entity-extractor-rename.png) </br>

4. En el panel **Cambiar nombre al extractor de entidades**:

   a. En **Nuevo nombre**, escriba el nuevo nombre del extractor.</br>

    ![Captura de pantalla en la que se muestra el panel del Extractor de entidades.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (Opcional) En **Configuración avanzada**, seleccione si quiere asociar una columna de sitio existente.

5. Seleccione **Cambiar nombre**.

## <a name="see-also"></a>Consulte también
[Crear un extractor](create-an-extractor.md)

[Crear un clasificador](create-a-classifier.md)

[Cambiar el nombre de un modelo](rename-a-model.md)

[Tipos de explicación](explanation-types-overview.md)

[Aprovechar la taxonomía del almacén de términos al crear un extractor](leverage-term-store-taxonomy.md)

[Información general sobre la comprensión mediante documentos](document-understanding-overview.md)

[Aplicar un modelo](apply-a-model.md) 
