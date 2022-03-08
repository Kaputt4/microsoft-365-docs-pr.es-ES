---
title: Dispositivos Windows seguros
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
ms.localizationpriority: medium
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
description: Obtén información sobre cómo configurar la configuración de la directiva de dispositivo predeterminada que cualquier dispositivo Windows recibirá al iniciar sesión en su cuenta laboral o educativa.
ms.openlocfilehash: b58e63abf19c3078eb5d4356b155df13804c95d5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331200"
---
# <a name="secure-windows-devices"></a>Dispositivos Windows seguros

Este artículo se aplica a Microsoft 365 Empresa Premium.

Las opciones que configuras aquí forman parte de la directiva de dispositivo predeterminada para Windows 10 o 11. Todos los usuarios que conecten un Windows, incluidos los dispositivos móviles y los equipos, al iniciar sesión con su cuenta de trabajo recibirán automáticamente esta configuración. Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.
  
## <a name="settings-to-secure-windows-10-devices"></a>Configuración para proteger dispositivos con Windows 10

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:<br/><br/>

|Configuración  <br/> |Descripción  <br/> |
|:-----|:-----|
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  <br/> |Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  <br/> |
|Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker  <br/> |BitLocker protege los datos mediante el cifrado de las unidades de disco duro del equipo y protege contra la exposición a datos si se pierde o se roba un equipo. Para obtener más información, consulta [Preguntas más frecuentes de BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  <br/> |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  <br/> |
