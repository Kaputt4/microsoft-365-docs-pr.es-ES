---
title: Proteger dispositivos con Windows 10
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Obtén información sobre cómo configurar la configuración de la directiva de dispositivo predeterminada que cualquier dispositivo Windows 10 recibirá al iniciar sesión en su cuenta laboral o educativa.
ms.openlocfilehash: 3f85549e722c9aa4196cf50fc02bee2e89506017
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925247"
---
# <a name="secure-windows-10-devices"></a>Proteger dispositivos con Windows 10

Este artículo se aplica a Microsoft 365 Empresa Premium.

Las opciones que configure aquí forman parte de la directiva de dispositivo predeterminada para Windows 10. Todos los usuarios que conecten un Windows 10, incluidos los dispositivos móviles y los equipos, al iniciar sesión con su cuenta de trabajo recibirán automáticamente esta configuración. Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.
  
## <a name="settings-to-secure-windows-10-devices"></a>Configuración para proteger dispositivos con Windows 10

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:
  


|Configuración  <br/> |Descripción  <br/> |
|:-----|:-----|
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  <br/> |Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  <br/> |
|Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker  <br/> |BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso del robo o pérdida de un equipo. Para obtener más información, consulta [Preguntas más frecuentes de Bitlocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  <br/> |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  <br/> |
|