---
title: Cómo se identifica el contenido para las recomendaciones de gobierno de datos
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
ms.custom: admindeeplinkDEFENDER
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: El portal Microsoft 365 Defender y el portal de cumplimiento Microsoft Purview proporcionan recomendaciones para el gobierno de datos en función de la configuración actual de la organización y permiten configurarlo todo en unos pocos clics. Algunas de estas recomendaciones detectan contenido específico de la organización y proporcionan pasos recomendados para administrar dicho contenido. Por ejemplo, una recomendación podría detectar elementos con contenido vital para la empresa (como secreto profesional entre abogado y cliente o información de acuerdos de confidencialidad) y le permitiría aplicar automáticamente una etiqueta de retención a esos elementos para asegurarse de que se clasifican y conservan según corresponda. En este tema se enumeran las recomendaciones de gobierno de datos que es posible que vea y se describe el contenido que se detecte para desencadenar cada uno.
ms.openlocfilehash: 27fcc5dd07695be355fc15ba2145ffa5540673ca
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66637315"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>Cómo se identifica el contenido para las recomendaciones de gobierno de datos

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> y el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> proporcionan recomendaciones para el gobierno de datos en función de la configuración actual de la organización y permiten configurarlo todo en unos pocos clics. Algunas de estas recomendaciones detectan contenido específico de la organización y proporcionan pasos recomendados para administrar dicho contenido. Por ejemplo, una recomendación podría detectar elementos con contenido vital para la empresa (como secreto profesional entre abogado y cliente o información de acuerdos de confidencialidad) y le permitiría aplicar automáticamente una etiqueta de retención a esos elementos para asegurarse de que se clasifican y conservan según corresponda.

En este tema se enumeran las recomendaciones de gobierno de datos que es posible que vea y se describe el contenido que se detecte para desencadenar cada uno.

## <a name="clean-up-voicemail"></a>Limpiar el correo de voz

Esta recomendación aparece cuando se detectan mensajes de correo identificados como tipo de mensaje "correo de voz" en los buzones de usuarios. Obtenga más información sobre las [propiedades de mensajes en Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators#searchable-properties-in-exchange).

## <a name="label-attorney-client-privilege-content"></a>Etiquetar contenido de privilegios abogado-cliente 

Esta recomendación aparece cuando se cumple uno de los siguientes criterios.

- Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:
  - ACP
  - Privilegio de abogado cliente
  - Privilegio de abogado-cliente
  - Confidencialidad abogado-cliente

- Cualquier combinación de estas palabras clave se detecta en archivos de SharePoint o OneDrive:
  - ACP
  - Privilegio de abogado cliente*
  - Privilegio AC

## <a name="retain-audio-files"></a>Conservar archivos de audio

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>Conservar archivos CAD

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>Conservar archivos de imagen

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>Conservar contenido NDA

Esta recomendación aparece cuando se cumple uno de los siguientes criterios.

- Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:
  - NDA
  - “Acuerdo de confidencialidad”
  - “Acuerdo de confidencialidad”

- Cualquier combinación de estas palabras clave se detecta en archivos .PDF o .DOC en SharePoint o OneDrive:
  - NDA
  - Acuerdo de confidencialidad

## <a name="retain-software-development-files"></a>Conservar archivos de desarrollo de software 

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>Conservar archivos de vídeo

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
