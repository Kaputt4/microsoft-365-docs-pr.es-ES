---
title: Proteger dispositivos Windows
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Obtenga información sobre cómo configurar las opciones de la directiva de dispositivo predeterminada que recibirá cualquier dispositivo Windows al iniciar sesión en su cuenta profesional o educativa.
ms.openlocfilehash: d8a32dd5378ed1b16e6126e9091f2bd2bb8515f5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094646"
---
# <a name="secure-windows-devices"></a>Proteger dispositivos Windows

Este artículo aplica a Microsoft 365 Empresa Premium.

Las opciones que configure aquí forman parte de la directiva de dispositivo predeterminada para Windows 10 y 11. Todos los usuarios que se conecten a un dispositivo Windows, incluidos dispositivos móviles y equipos PC, recibirán automáticamente esta configuración al iniciar sesión con su cuenta profesional. Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.
  
## <a name="settings-to-secure-windows-10-devices"></a>Configuración para proteger dispositivos con Windows 10

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:<br/><br/>

|Configuración  <br/> |Descripción  <br/> |
|:-----|:-----|
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  <br/> |Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  <br/> |
|Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker  <br/> |BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso de robo o pérdida de un equipo. Para más información, vea [Preguntas más frecuentes sobre BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  <br/> |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  <br/> |
