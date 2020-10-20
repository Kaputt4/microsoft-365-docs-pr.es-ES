---
title: Tipos de archivo admitidos en investigaciones de datos (versión preliminar)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Una tabla que enumera los tipos de archivo admitidos y los visores que se pueden ver en para las investigaciones de datos (versión preliminar).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 826ad69b1fb0074cd0c8bc1b3b0208bb8e77d528
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600419"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>Tipos de archivo admitidos en investigaciones de datos (versión preliminar)

La herramienta de investigación de datos (versión preliminar) admite muchos tipos de archivos de varias formas, que se describen en la siguiente tabla. Esta lista no finaliza y agregamos nuevos tipos de archivo, ya que continuamos con nuestras pruebas de validación. La tabla también indica si se puede ver un tipo de archivo en los visores disponibles cuando se está revisando la evidencia.

| Tipo MIME | Clase File | Visor nativo | Visor de texto | Visor de anotaciones | Extracción de contenedores | Extensiones |
|:------|:------|:------|:------|:------|:------|:------|
|application/msword | Documento | Sí | Sí | Sí | No | . doc;. dat |
|application/pdf | Documento | Sí | Sí | Sí | No | .pdf |
|aplicación/RTF | Documento | Sí | Sí | Sí | No | . rtf;. doc |
|aplicación/vnd. MS-Excel | Documento | Sí | Sí | Sí | No | . xls;. dat |
|Application/vnd. MS-Excel. sheet. Binary. macroenabled. 12 | Formato de la productividad y el documento abierto | Sí | Sí | No | No | .xlsb |
|Application/vnd. MS-Excel. sheet. macroenabled. 12 | Documento | Sí | Sí | Sí | No | . xlsm |
|Application/vnd. MS-Excel. template. macroenabled. 12 | Formato de la productividad y el documento abierto | No | Sí | No | No | . xltm |
|aplicación/vnd. MS-Outlook | Productividad | No | No | No | No | . msg |
|aplicación/vnd. MS-Outlook-PST | Productividad y colaboración | No | No | No | Sí | .pst |
|aplicación/vnd. MS-PowerPoint | Documento | Sí | Sí | Sí | No | . ppt;. PPS;. pot |
|Application/vnd.ms-word.document. macroenabled. 12 | Documento | Sí | Sí | Sí | No | .docm |
|Application/vnd. MS-Word. template. macroenabled. 12 | Documento | Sí | Sí | Sí | No | . dotm |
|Application/vnd. oasis. opendocument. Text | Documento | Sí | Sí | Sí | No | ODT  |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Documento | Sí | Sí | Sí | No | .pptx |
|Application/vnd. openxmlformats-officedocument. presentationml. Slideshow | Formato de la productividad y el documento abierto | Sí | Sí | Sí | No | . ppsx |
|Application/vnd. openxmlformats-officedocument. presentationml. template | Documento | Sí | Sí | Sí | No | . potx |
| apadsheetml. sheet | Documento | Sí | Sí | Sí | No | .xlsx |
|Application/vnd. openxmlformats-officedocument. SpreadsheetML. template | Documento | Sí | Sí | Sí | No | . xltx |
|application/vnd.openxmlformats-officedocument.wordprocessingml.document | Documento | Sí | Sí | Sí | No | .docx |
|Application/vnd. openxmlformats-officedocument. WordprocessingML. template | Documento | Sí | Sí | Sí | No | . dotx |
|aplicación/vnd. Visio | Documento | Sí | Sí | Sí | No | . VSD |
|application/x-7z-Compressed | Archivo/contenedor | No | No | No | Sí | .7z |
|aplicación/XHTML + XML | Documento | Sí | Sí | Sí | No | . XHTML |
|Application/XML | Documento | Sí | Sí | Sí | No | . XML |
|application/x-Msaccess | Documento | Sí | Sí | Sí | No | .mdb |
|application/x-mspublisher | Documento | Sí | Sí | Sí | No | . pub |
|aplicación/x-rar-comprimido | Archivo/contenedor | No | No | No | Sí | . rar |
| aplicación/código postal | Archivo/contenedor | No | No | No | Sí | .zip |
|Image/BMP | Imagen | Sí | Sí | Sí | No | .bmp |
|Image/EMF | Imagen | Sí | Sí | Sí | No | .emf |
|image/gif | Documento | Sí | Sí | Sí | No | .gif |
|image/jpeg | Imagen | Sí | Sí | Sí | No | . jpg;. JPEG;. dat;. jpgt |
|image/png | Imagen | Sí | Sí | Sí | No | .png |
|Image/TIFF | Imagen | Sí | Sí | Sí | No | . tif |
|Image/vnd. DWG | Documento | Sí | Sí | Sí | No | . dwg;. DXF; |
|imagen/WMF | Documento | Sí | Sí | Sí | No | .wmf |
| mensaje/rfc822 | Productividad y colaboración | No | No | No | No | .eml |
|texto/CSV | Documento | Sí | Sí | Sí | No | . csv |
|texto/HTML | Documento | Sí | Sí | Sí | No | . html;. shtml;. htm |
|texto/sin formato | Documento | Sí | Sí | Sí | No | . txt;. CSS;. con;. pl;. csv;. dat |
|texto/vCard-contacto | Documento | Sí | Sí | Sí | No | . vcf |
||||||||
