---
title: API de REST del modelo de comprensión mediante documentos de SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Información general sobre la API de REST del modelo de comprensión mediante documentos de SharePoint Syntex.
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904316"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>API de REST del modelo de comprensión mediante documentos de SharePoint Syntex

Puede usar la interfaz REST de SharePoint para crear un modelo de comprensión mediante documentos, aplicar o quitar el modelo a una o más bibliotecas, y obtener o actualizar información sobre el modelo. 

El servicio REST de SharePoint Online (y SharePoint 2016 o versiones posteriores locales) admite la combinación de varias solicitudes en una sola llamada al servicio mediante el uso de la opción de consulta $batch de OData. 

Para obtener información detallada y vínculos a los ejemplos de código, vea [Realizar solicitudes de lote con las API de REST](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, asegúrese de que está familiarizado con lo siguiente:

- [Introducción al servicio REST para SharePoint](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [Completar operaciones básicas con puntos de conexión REST de SharePoint](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a>Comandos de REST

Los siguientes comandos de REST están disponibles para trabajar con modelos de comprensión mediante documentos de Syntex:

- [Crear modelo](rest-createmodel-method.md): Crea un modelo y su tipo de contenido asociado.
- [GetByUniqueId](rest-getbyuniqueid-method.md): Obtiene o actualiza información sobre un modelo de comprensión mediante documentos de SharePoint Syntex.
- [GetByTitle](rest-getbytitle-method.md): Obtiene o actualiza información sobre un modelo de comprensión mediante documentos de SharePoint Syntex mediante el título del modelo.
- [Aplicar modelo](rest-applymodel-method.md): Aplica (o sincroniza) un modelo de comprensión mediante documentos entrenado a una o más bibliotecas.
- [Obtener información de modelo y biblioteca](rest-getmodelandlibraryinfo.md): Obtiene información sobre un modelo y la biblioteca donde se ha aplicado.
- [UpdateModelSettings](rest-updatemodelsettings-method.md): Actualiza la configuración disponible de los modelos (descripción del modelo y etiqueta de retención asociada) para un modelo de comprensión mediante documentos de SharePoint Syntex.
- [BatchDelete](rest-batchdelete-method.md) : Quita un modelo de comprensión mediante documentos aplicado de una o más bibliotecas.
- [Crear solicitud de clasificación](rest-createclassificationrequest.md): Crea una solicitud para clasificar un archivo o archivos especificados con el modelo aplicado.

## <a name="scenarios"></a>Escenarios

Tenga en cuenta los ejemplos de escenarios siguientes que no son intuitivos a partir del nombre del método. Para obtener más información, consulte todos los artículos.

El método de creación de modelo solo crea el objeto de modelo y su tipo de contenido asociado. Primero debe entrenar el modelo en el centro de contenido para que se pueda aplicar en una biblioteca.

El método de "aplicar modelo" se usa para configurar el modelo en la biblioteca de destino para clasificar documentos y, de manera opcional, extraer información adicional. Esta API también es compatible con la aplicación por lotes del modelo a varias bibliotecas.

El método de "eliminar modelo" solo quita el modelo de una o más bibliotecas donde se haya aplicado anteriormente. Si quiere eliminar el modelo, primero debe quitarse de todas las bibliotecas donde se ha aplicado.


## <a name="see-also"></a>Ver también

[Información general sobre la comprensión de documentos](../document-understanding-overview.md)

