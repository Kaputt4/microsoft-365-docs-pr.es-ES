---
title: Información sobre la configuración de los perfiles de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Perfiles de piloto automático le ayudarán a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen predeterminada y valores de configuración opcionales como omitir la instalación de Cortana.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871185"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración del perfil de piloto automático

Puede controlar cómo se instala Windows en los dispositivos de usuario mediante el uso de los perfiles de piloto automático. Los perfiles contienen los valores siguientes.
  
 **Piloto automático características predeterminadas de (obligatorio) que se establecen automáticamente:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir el registro OEM, OneDrive y Cortana  <br/> |Omite la instalación de aplicaciones de consumidor como Cortana y OneDrive personal. El usuario del dispositivo puede instalar más adelante, siempre y cuando éste sea un administrador local en el dispositivo. Debido a que el dispositivo estará administrado por Microsoft 365 empresarial, se omite el registro del fabricante original.  <br/> |
|Inicie sesión en la experiencia con la marca de su empresa  <br/> |Si su compañía tiene una [personalización de marca de agregar su compañía a Office 365 inicio de sesión en la página](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), el usuario del dispositivo obtendrá esa experiencia al iniciar la sesión.  <br/> |
|MDM la inscripción automática con cuentas AAD configuradas.  <br/> |La identidad del usuario estará administrada por Azure Active directory y los usuarios va a iniciar sesión en Windows y Office 365 con sus credenciales de Microsoft 365 empresarial.  <br/> |
   
 **Configuración opcional:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir la configuración de privacidad (desactivada de forma predeterminada)  <br/> |Si esta opción está establecida en **On**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando navegará primero inicia sesión en.  <br/> |
|No permitir que el usuario se convierta en el administrador local  <br/> |Si esta opción está establecida en **On**, el usuario del dispositivo no podrá instalar aplicaciones de personal, por ejemplo, Cortana.  <br/> |
   
