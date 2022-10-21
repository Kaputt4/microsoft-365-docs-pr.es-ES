---
title: Requisitos y limitaciones de los modelos en Microsoft Syntex
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
description: Obtenga información sobre las limitaciones de archivos, los tipos de archivo, los idiomas admitidos y otros requisitos para los modelos de Microsoft Syntex.
ms.openlocfilehash: 967a47f96c2345772fb8a7eac12db6e95d5128c8
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664410"
---
# <a name="requirements-and-limitations-for-models-in-microsoft-syntex"></a>Requisitos y limitaciones de los modelos en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; Todos los modelos &ensp; | &ensp; personalizados &#10003; Todos los modelos precompilados</sup>

Microsoft Syntex le permite crear [modelos personalizados y modelos precompilados](model-types-overview.md). En función del tipo de modelo que elija, puede haber diferentes requisitos, como el tipo de archivo y el tamaño, los idiomas que se deben admitir, las consideraciones geográficas y otros factores que le ayudarán a decidir qué tipo de modelo usar.

Modelos personalizados:

- [Procesamiento de documentos no estructurados](#unstructured-document-processing)
- [Procesamiento de documentos de forma libre](#freeform-document-processing)
- [Procesamiento estructurado de documentos](#structured-document-processing)
 
Modelos precompilados:

- [Procesamiento de facturas](#invoice-processing)
- [Procesamiento de recibos](#receipt-processing)

## <a name="custom-models"></a>Modelos personalizados

### <a name="unstructured-document-processing"></a>Procesamiento de documentos no estructurados

| Icono          | Descripción   |
| ------------- | ------------- |
| ![Símbolo de archivos.](/office/media/icons/files-blue.png)  | **Tipos de archivo admitidos** <br>Este modelo admite los siguientes tipos de archivo: .csv, .doc, .docx, .eml, .heic, .heif, .htm, .html, .jpeg, .jpg, .md, .msg, .pdf, .png, .ppt, .pptx, .rtf, .tif, .tiff, .txt, .xls y .xlsx. |
| ![Símbolo de conversación.](/office/media/icons/chat-room-conversation-blue.png)  | **Idiomas admitidos** <br>Este modelo admite todos los idiomas latinos, incluidos inglés, francés, alemán, italiano y español. |
| ![Símbolo de párrafo.](/office/media/icons/paragraph-writing-blue.png)  | **Consideraciones de OCR** <br>Este modelo usa la tecnología de reconocimiento óptico de caracteres (OCR) para examinar .pdf archivos, archivos de imagen y archivos .tiff. El procesamiento de OCR funciona mejor en documentos que cumplen los siguientes requisitos: <br> - Formato de archivo de .jpg, .png o .pdf (texto o escaneado). Los archivos de .pdf insertados en texto son mejores, ya que no habrá errores en la extracción y ubicación de caracteres. <br> - Si los archivos de .pdf están bloqueados con contraseña, debe quitar el bloqueo antes de enviarlos. <br> - El tamaño de archivo combinado de los documentos utilizados para el entrenamiento por colección no debe superar los 50 MB, y los documentos PDF no deben tener más de 500 páginas. <br> - Para las imágenes, las dimensiones deben estar entre 50 x 50 y 10 000 x 10 000 píxeles. Es posible que las imágenes muy anchas o con dimensiones inusuales (por ejemplo, planos de planta) se trunquen en el proceso de OCR y pierdan precisión. <br> - Para .pdf archivos, las dimensiones deben ser como máximo de 17 x 17 pulgadas, correspondientes a tamaños de papel Legal o A3 y más pequeños. <br> - Si escaneó de documentos en papel, los escaneos deben ser imágenes de alta calidad. <br> - Debe usar el alfabeto latino (caracteres en inglés). <br> Tenga en cuenta las siguientes diferencias sobre los archivos basados en texto de Microsoft Office y los archivos escaneados con OCR (.pdf, imagen o .tiff): <br> - Archivos de Office: truncados con 64 000 caracteres (en entrenamiento y cuando se ejecutan en archivos de una biblioteca de documentos). <br> - Archivos escaneados con OCR: hay un límite de 500 páginas. OCR solo procesa los tipos de archivo PDF y de imagen. |
| ![Símbolo de globo.](/office/media/icons/globe-internet.png)  | **Entornos de Multi-Geo** <br>Al configurar Syntex en un entorno [multigeográfico de Microsoft 365](/microsoft-365/enterprise/microsoft-365-multi-geo) , solo puede configurarlo para que use el tipo de modelo en la ubicación central. Si desea usar este tipo de modelo en una ubicación satélite, póngase en contacto con el soporte técnico de Microsoft. |
| ![Símbolo de objetos.](/office/media/icons/objects-blue.png)  | **Bibliotecas multimodelo** <br>Si se aplican dos o más modelos entrenados a la misma biblioteca, el archivo se clasifica mediante el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas serán solo del modelo aplicado. |

### <a name="freeform-document-processing"></a>Procesamiento de documentos de forma libre

| Icono          | Descripción   |
| ------------- | ------------- |
| ![Símbolo de archivos.](/office/media/icons/files-blue.png)  | **Tipos de archivo admitidos** <br>Este modelo admite los siguientes tipos de archivo: consulte [requisitos de tipo de archivo](/ai-builder/form-processing-model-requirements#requirements). |
| ![Símbolo de conversación.](/office/media/icons/chat-room-conversation-blue.png)  | **Idiomas admitidos** <br>Este modelo admite el siguiente idioma: inglés. |
| ![Símbolo de párrafo.](/office/media/icons/paragraph-writing-blue.png) | **Consideraciones de OCR** <br>Este modelo usa la tecnología de reconocimiento óptico de caracteres (OCR) para examinar .pdf archivos, archivos de imagen y archivos .tiff. El procesamiento de OCR funciona mejor en documentos que cumplen [estos requisitos](/ai-builder/form-processing-model-requirements#requirements). |
| ![Símbolo de ancho de banda y eficiencia.](/office/media/icons/bandwidth-efficiency-blue.png)  | **Sugerencias de optimización** <br>Si el modelo no funciona como quiere, pruebe [estos pasos para mejorar el rendimiento del modelo](/ai-builder/improve-form-processing-performance). |
| ![Símbolo de globo.](/office/media/icons/globe-internet.png)  | **Entornos de Multi-Geo** <br>Al configurar Syntex en un entorno [multigeográfico de Microsoft 365](/microsoft-365/enterprise/microsoft-365-multi-geo) , solo puede configurarlo para que use el tipo de modelo en la ubicación central. Si desea usar este tipo de modelo en una ubicación satélite, póngase en contacto con el soporte técnico de Microsoft. |
| ![Símbolo de bloques.](/office/media/icons/blocks-blue.png)  | **Entornos de Power Platform personalizados** <br>Si usa un entorno personalizado (en lugar del entorno predeterminado) para el procesamiento de Power Platform, hay requisitos de configuración adicionales. Para obtener más información, consulte [Entornos de Power Platform personalizados](/microsoft-365/contentunderstanding/set-up-content-understanding#custom-power-platform-environments). |
| ![Símbolo de objetos.](/office/media/icons/objects-blue.png)  | **Bibliotecas multimodelo** <br>Si se aplican dos o más modelos entrenados a la misma biblioteca, el archivo se clasifica mediante el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas serán solo del modelo aplicado. Solo puede tener una forma libre o un modelo estructurado por biblioteca. |

### <a name="structured-document-processing"></a>Procesamiento estructurado de documentos

| Icono          | Descripción   |
| ------------- | ------------- |
| ![Símbolo de archivos.](/office/media/icons/files-blue.png)  | **Tipos de archivo admitidos** <br>Este modelo admite los siguientes tipos de archivo: consulte [requisitos de tipo de archivo](/ai-builder/form-processing-model-requirements#requirements). |
| ![Símbolo de conversación.](/office/media/icons/chat-room-conversation-blue.png)  | **Idiomas admitidos** <br>Este modelo admite 73 idiomas: consulte [los idiomas admitidos](/ai-builder/form-processing-model-requirements#languages-supported). |
| ![Símbolo de párrafo.](/office/media/icons/paragraph-writing-blue.png) | **Consideraciones de OCR** <br>Este modelo usa la tecnología de reconocimiento óptico de caracteres (OCR) para examinar .pdf archivos, archivos de imagen y archivos .tiff. El procesamiento de OCR funciona mejor en documentos que cumplen [estos requisitos](/ai-builder/form-processing-model-requirements#requirements). |
| ![Símbolo de ancho de banda y eficiencia.](/office/media/icons/bandwidth-efficiency-blue.png)  | **Sugerencias de optimización** <br>Si el modelo no funciona como quiere, pruebe [estos pasos para mejorar el rendimiento del modelo](/ai-builder/improve-form-processing-performance). |
| ![Símbolo de globo.](/office/media/icons/globe-internet.png)  | **Entornos de Multi-Geo** <br>Al configurar Syntex en un entorno [multigeográfico de Microsoft 365](/microsoft-365/enterprise/microsoft-365-multi-geo) , solo puede configurarlo para que use el tipo de modelo en la ubicación central. Si desea usar este tipo de modelo en una ubicación satélite, póngase en contacto con el soporte técnico de Microsoft. |
| ![Símbolo de bloques.](/office/media/icons/blocks-blue.png)  | **Entornos de Power Platform personalizados** <br>Si usa un entorno personalizado (en lugar del entorno predeterminado) para el procesamiento de Power Platform, hay requisitos de configuración adicionales. Para obtener más información, consulte [Entornos de Power Platform personalizados](/microsoft-365/contentunderstanding/set-up-content-understanding#custom-power-platform-environments). |
| ![Símbolo de objetos.](/office/media/icons/objects-blue.png)  | **Bibliotecas multimodelo** <br>Si se aplican dos o más modelos entrenados a la misma biblioteca, el archivo se clasifica mediante el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas serán solo del modelo aplicado. Solo puede tener una forma libre o un modelo estructurado por biblioteca. |

## <a name="prebuilt-models"></a>Modelos creados previamente

### <a name="invoice-processing"></a>Procesamiento de facturas

| Icono          | Descripción   |
| ------------- | ------------- |
| ![Símbolo de archivos.](/office/media/icons/files-blue.png)  | **Tipos de archivo admitidos** <br>Este modelo admite los siguientes tipos de archivo: .bmp, .jpeg, .pdf, .png y .tiff. |
| ![Símbolo de conversación.](/office/media/icons/chat-room-conversation-blue.png)  | **Idiomas admitidos** <br>Este modelo solo admite facturas en inglés de la Estados Unidos. |
| ![Símbolo de párrafo.](/office/media/icons/paragraph-writing-blue.png)  | **Consideraciones de OCR** <br>Este modelo usa la tecnología de reconocimiento óptico de caracteres (OCR) para examinar .pdf archivos, archivos de imagen y archivos .tiff. El procesamiento de OCR funciona mejor en documentos que cumplen los siguientes requisitos: <br> - Formato de archivo de .jpg, .png o .pdf (texto o escaneado). Los archivos de .pdf insertados en texto son mejores, ya que no habrá errores en la extracción y ubicación de caracteres. <br> - Para archivos .pdf y .tiff, se pueden procesar hasta 2000 páginas. <br> - El tamaño del archivo debe ser inferior a 50 MB. <br> - Para las imágenes, las dimensiones deben estar entre 50 x 50 y 10 000 x 10 000 píxeles. <br> - Para .pdf archivos, las dimensiones deben ser como máximo de 17 x 17 pulgadas, correspondientes a tamaños de papel Legal o A3 y más pequeños. <br> - El tamaño total de los datos de entrenamiento es de 500 páginas o menos. <br> Tenga en cuenta las siguientes diferencias sobre los archivos basados en texto de Microsoft Office y los archivos escaneados con OCR (.pdf, imagen o .tiff): <br> - Archivos de Office: truncados con 64 000 caracteres (en entrenamiento y cuando se ejecutan en archivos de una biblioteca de documentos). <br> - Archivos escaneados con OCR: hay un límite de 20 páginas.|
| ![Símbolo de globo.](/office/media/icons/globe-internet.png)  | **Entornos de Multi-Geo** <br>Al configurar Syntex en un entorno [multigeográfico de Microsoft 365](/microsoft-365/enterprise/microsoft-365-multi-geo) , solo puede configurarlo para que use el tipo de modelo en la ubicación central. Si desea usar este tipo de modelo en una ubicación satélite, póngase en contacto con el soporte técnico de Microsoft. |
| ![Símbolo de objetos.](/office/media/icons/objects-blue.png)  | **Bibliotecas multimodelo** <br>Si se aplican dos o más modelos entrenados a la misma biblioteca, el archivo se clasifica mediante el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas serán solo del modelo aplicado. |

### <a name="receipt-processing"></a>Procesamiento de recibos

| Icono          | Descripción   |
| ------------- | ------------- |
| ![Símbolo de archivos.](/office/media/icons/files-blue.png)  | **Tipos de archivo admitidos** <br>Este modelo admite los siguientes tipos de archivo: .bmp, .jpeg, .pdf, .png y .tiff. |
| ![Símbolo de conversación.](/office/media/icons/chat-room-conversation-blue.png)  | **Idiomas admitidos** <br>Este modelo admite recibos de ventas en inglés de Australia, Canadá, Gran Bretaña, India y el Estados Unidos. |
| ![Símbolo de párrafo.](/office/media/icons/paragraph-writing-blue.png)  | **Consideraciones de OCR** <br>Este modelo usa la tecnología de reconocimiento óptico de caracteres (OCR) para examinar .pdf archivos, archivos de imagen y archivos .tiff. El procesamiento de OCR funciona mejor en documentos que cumplen los siguientes requisitos: <br> - Formato de archivo de .jpg, .png o .pdf (texto o escaneado). Los archivos de .pdf insertados en texto son mejores, ya que no habrá errores en la extracción y ubicación de caracteres. <br> - Para archivos .pdf y .tiff, se pueden procesar hasta 2000 páginas. <br> - El tamaño del archivo debe ser inferior a 50 MB. <br> - Para las imágenes, las dimensiones deben estar entre 50 x 50 y 10 000 x 10 000 píxeles. <br> - Para .pdf archivos, las dimensiones deben ser como máximo de 17 x 17 pulgadas, correspondientes a tamaños de papel Legal o A3 y más pequeños. <br> - El tamaño total de los datos de entrenamiento es de 500 páginas o menos. <br> Tenga en cuenta las siguientes diferencias sobre los archivos basados en texto de Microsoft Office y los archivos escaneados con OCR (.pdf, imagen o .tiff): <br> - Archivos de Office: truncados con 64 000 caracteres (en entrenamiento y cuando se ejecutan en archivos de una biblioteca de documentos). <br> - Archivos escaneados con OCR: hay un límite de 20 páginas.|
| ![Símbolo de globo.](/office/media/icons/globe-internet.png)  | **Entornos de Multi-Geo** <br>Al configurar Syntex en un entorno [multigeográfico de Microsoft 365](/microsoft-365/enterprise/microsoft-365-multi-geo) , solo puede configurarlo para que use el tipo de modelo en la ubicación central. Si desea usar este tipo de modelo en una ubicación satélite, póngase en contacto con el soporte técnico de Microsoft. |
| ![Símbolo de objetos.](/office/media/icons/objects-blue.png)  | **Bibliotecas multimodelo** <br>Si se aplican dos o más modelos entrenados a la misma biblioteca, el archivo se clasifica mediante el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas serán solo del modelo aplicado. |
