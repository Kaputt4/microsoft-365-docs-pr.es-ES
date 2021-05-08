---
title: Paso 1. Usar SharePoint Syntex para identificar archivos de contrato y extraer datos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo usar SharePoint Syntex para identificar archivos de contrato y extraer datos mediante una Microsoft 365 solución.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281340"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Paso 1. Usar SharePoint Syntex para identificar archivos de contrato y extraer datos

Su organización necesita una forma de identificar y clasificar todos los documentos de contrato de los muchos archivos que recibe. También desea poder ver rápidamente varios elementos clave en cada uno de los archivos de contrato identificados (por ejemplo, *Client*, *Contractor* y *Fee amount*). Para ello, use SharePoint [Syntex](index.md) para crear un modelo de descripción de documentos y aplicarlo a una biblioteca de documentos.

[La comprensión de](document-understanding-overview.md) documentos usa modelos de inteligencia artificial (IA) para automatizar la clasificación de archivos y la extracción de información. Los modelos de comprensión de documentos también son óptimos para extraer información de documentos no estructurados y semiestructurados donde la información que necesita no está contenida en tablas o formularios, como contratos.

1. En primer lugar, debe buscar al menos cinco archivos de ejemplo que pueda usar para "entrenar" el modelo para buscar características específicas del tipo de contenido que está intentando identificar (un contrato). 

2. Con SharePoint Syntex, cree un nuevo modelo de comprensión de documentos. Con los archivos de ejemplo, debe [crear un clasificador](create-a-classifier.md). Al entrenar al clasificador con los archivos de ejemplo, se le enseña a buscar características específicas de lo que vería en los contratos de su empresa. Por ejemplo, [cree una "explicación"](create-a-classifier.md#create-an-explanation) que busque cadenas específicas que estén en sus contratos, como *Contrato* de servicio, *Términos* de contrato y *Compensación*. Incluso puede entrenar su explicación para buscar estas cadenas en secciones específicas del documento o ubicadas junto a otras cadenas. Cuando piense que ha formado al clasificador con la información que necesita, puede probar el modelo en un conjunto de ejemplos de archivos de ejemplo para ver su eficacia. Después de realizar las pruebas, si es necesario, puede elegir realizar cambios en sus explicaciones para hacerlos más eficientes. 

3. En el modelo, puede crear [un extractor](create-an-extractor.md) para extraer partes específicas de datos de cada contrato. Por ejemplo, para cada contrato, la información que más le preocupa es quién es el cliente, el nombre del contratista y el costo total.

4. Después de crear correctamente el modelo, [apliquenlo a](apply-a-model.md)una biblioteca SharePoint documentos . Al cargar documentos en la biblioteca de documentos, el modelo de descripción de documentos se ejecutará e identificará y clasificará todos los archivos que coincidan con el tipo de contenido de contratos definido en el modelo. Todos los archivos clasificados como contratos se mostrarán en una vista de biblioteca personalizada. Los archivos también mostrarán los valores de cada contrato definido en el extractor.

   ![Contratos en la biblioteca de documentos](../media/content-understanding/doc-lib-solution.png)

5. Además, si tiene requisitos de retención para sus contratos, también puede usar el modelo para aplicar una etiqueta de retención que impedirá que los contratos se eliminen durante un período de tiempo especificado. [](apply-a-retention-label-to-a-model.md)

## <a name="next-step"></a>Paso siguiente

[Paso 2. Usar Microsoft Teams para crear el canal de administración de contratos](solution-manage-contracts-step2.md)