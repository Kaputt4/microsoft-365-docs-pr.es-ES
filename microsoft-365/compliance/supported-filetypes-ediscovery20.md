---
title: Tipos de archivo admitidos en eDiscovery avanzado
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
description: Una lista de tipos de archivo admitidos en eDiscovery avanzado de Microsoft 365, incluidos los tipos de archivo de imagen admitidos por la funcionalidad OCR en eDiscovery avanzado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a552e6cf0d32e77c2a21bc959ae313e6fc53d4eb
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817133"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Tipos de archivo admitidos en eDiscovery avanzado

EDiscovery avanzado admite muchos tipos de archivo en muchos niveles diferentes. Los tipos de archivos de soporte técnico se describen en las tablas siguientes de este artículo. Esta lista no se ha finalizado y agregaremos nuevos tipos de archivo a medida que continúemos las pruebas de validación. Estas tablas indican si se admite un tipo de archivo para la extracción de texto (y reconocimiento óptico de caracteres o extracción de texto OCR para archivos de imagen), que se puede ver en el visor nativo y también se admite en el visor de anotaciones en eDiscovery avanzado.

## <a name="archive--container"></a>Archivo o contenedor

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de contenedores | Extensiones posibles |
|:---- |:---- |:---- |:---- |:---- |
|application/x-7z-compressed | Sí | Sí | Sí | .7z |
|application/x-rar-compressed | Sí | Sí | Sí | .rar |
|application/x-tar | Sí | Sí | Sí | .tar |
|application/zip | Sí | Sí | Sí | .zip |
||||||||

## <a name="audio--video"></a>Audio y vídeo

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
| application/mp4 | Sí | Sí | No | Sí | No | .f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; .mpeg4 |
|audio/mpeg | Sí | Sí | No | Sí | No | .mpeg |
|video/3gpp | Sí | Sí | No | Sí | No | .3gp |
|video/3gpp2 | Sí | Sí | No | Sí | No | .3g2; .3gp2 |
|vídeo/quicktime | Sí | Sí | No | Sí | No | .moov; .mov; .qt |
|video/x-m4v | Sí | Sí | No | Sí | No | .m4v |
||||||||

## <a name="database"></a>Database

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | Sí | Sí | Sí | No | No | .mdb |
||||||||

## <a name="email"></a>Correo electrónico

|Tipo Mime |Identificación de archivo |Extracción de metadatos |Extracción de texto |Visor nativo |Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | Sí | Sí | Sí | Sí | Sí | .msg |
|message/rfc822 | Sí | Sí | Sí | Sí | Sí | .eml |
|text/vcard-contact | Sí | Sí | Sí | Sí | Sí | .vcf |
||||||||

## <a name="email-container"></a>Contenedor de correo electrónico

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de contenedores | Extensiones posibles |
|:------| :------| :------| :------| :------|
|application/mbox | Sí | Sí | Sí | .mbox |
|application/vnd.ms-outlook-pst | Sí | Sí | Sí | .pst |
||||||||

## <a name="html"></a>HTML

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/xhtml+xml | Sí | Sí | Sí | Sí | Sí | .xhtml |
|application/xml | Sí | Sí | Sí | Sí | Sí | .xml |
|text/html | Sí | Sí | Sí | Sí | Sí | .htm; .html; .shtml |
||||||||

## <a name="image"></a>Imagen

|Tipo Mime |Identificación de archivo |Extracción de metadatos |Extracción de texto OCR |Visor nativo |Visor de anotaciones |Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|image/bmp | Sí | Sí | Sí | Sí | Sí | .bmp |
|image/emf | Sí | Sí | Sí | Sí | Sí | .emf |
|image/gif | Sí | Sí | Sí | Sí | Sí | .gif |
|image/jpeg | Sí | Sí | Sí | Sí | Sí | .jpeg; .jpg |
|image/png | Sí | Sí | Sí | Sí | Sí | .png |
|image/svg+xml | Sí | Sí | Sí | Sí | No | .svg |
|image/tiff | Sí | Sí | Sí | Sí | Sí | .tif |
|image/vnd.dwg | Sí | Sí | Sí | Sí | Sí | .dxf; .dxf |
|image/wmf | Sí | Sí | Sí | Sí | Sí | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | Sí | Sí | Sí | Sí | Sí | .dat; .xls |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | Sí | Sí | Sí | Sí | No | .xlsb |
|application/vnd.ms-excel.sheet.macroenabled.12 | Sí | Sí | Sí | Sí | Sí | .xlsm |
|application/vnd.ms-excel.template.macroenabled.12 | Sí | Sí | Sí | No | No | .xltm |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Sí | Sí | Sí | Sí | Sí | .xlsx |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | Sí | Sí | Sí | Sí | Sí | .xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/onenote | Sí | Sí | Sí | Sí | No | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | Sí | Sí | Sí | Sí | Sí | .pot; .pps; .ppt |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Sí | Sí | Sí | Sí | Sí | .pptx |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | Sí | Sí | Sí | Sí | Sí | .ppsx |
|application/vnd.openxmlformats-officedocument.presentationml.template | Sí | Sí | Sí | Sí | Sí | .potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-project | Sí | Sí | Sí | No | Sí | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-mspublisher | Sí | Sí | Sí | Sí | Sí | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-visio.drawing | Sí | Sí | Sí | Sí | No |  |
|application/vnd.visio | Sí | Sí | Sí | Sí | Sí | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/msword | Sí | Sí | Sí | Sí | Sí | .dat; .doc |
| application/rtf | Sí | Sí | Sí | Sí | Sí | .doc; .rtf |
|application/vnd.ms-word.document.macroenabled.12 | Sí | Sí | Sí | Sí | Sí | .docm |
|application/vnd.ms-word.template.macroenabled.12 | Sí | Sí | Sí | Sí | Sí | .dotm |
|application/vnd.openxmlformats-officedocument.wordprocessingml.document | Sí | Sí | Sí | Sí | Sí | .docx |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | Sí | Sí | Sí | Sí | Sí | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | Sí | Sí | No | No | No | .wps |
|application/vnd.ms-works-wp | Sí | Sí | No | No | No | .wps |
||||||||

## <a name="open-document-format"></a>Abrir formato de documento

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.oasis.opendocument.text | Sí | Sí | Sí | Sí | Sí | .odt |
||||||||

## <a name="other"></a>Otros

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/json | Sí | Sí | Sí | Sí | Sí | No aplicable |
|application/vnd.ms-graph | Sí | Sí | No | No | No |  |
|application/winhlp | Sí | Sí | No | No | No | .hlp |
|application/x-tnef | Sí | Sí | No | No | No |  |
||||||||

## <a name="plain-text"></a>Texto sin formato

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|text/csv | Sí | Sí | Sí | Sí | Sí | .csv |
|texto/sin formato | Sí | Sí | Sí | Sí | Sí | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/pdf | Sí | Sí | Sí | Sí | Sí | .pdf |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.wordperfect; version=5.0 | Sí | Sí | Sí | No | No | .wpd |
|application/vnd.wordperfect; version=5.1 | Sí | Sí | Sí | No | No | .wpd |
|application/vnd.wordperfect; version=6.x | Sí | Sí | Sí | No | No | .wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Tipo Mime | Identificación de archivo | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.lotus-wordpro | Sí | Sí | No | No | No | .lwp |
||||||||
