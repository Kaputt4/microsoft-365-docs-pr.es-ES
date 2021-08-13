---
title: Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Obtenga información sobre las directivas de protección que le permiten administrar cómo los usuarios tienen acceso Office aplicaciones y archivos de trabajo desde dispositivos móviles.
ms.openlocfilehash: 6e48ef857de8046854a94d470b28ba5db96b373bc8b190dc1062d4f408a9802c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53809260"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles

Este artículo se aplica a Microsoft 365 Empresa Premium.

La configuración de directiva que controla cómo acceden los usuarios a los archivos de Office desde sus dispositivos móviles están **desactivadas** de forma predeterminada. Se recomienda aceptar los valores predeterminados durante la instalación para crear directivas de aplicación para Android, iOS y Windows 10 que se aplican a todos los usuarios. Podrá crear más directivas cuando se complete la configuración. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles

Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:

|Configuración  <br/> |Descripción  <br/> |
|:-----|:-----|
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  <br/> |Si esta configuración es **On**, los usuarios deben proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar Office aplicaciones en su dispositivo móvil.  <br/> |
|Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces  <br/> |Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.  <br/> |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante  <br/> |Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que inicie sesión de nuevo.  <br/> |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  <br/> |Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto significa que el usuario puede modificar el sistema operativo, lo que puede hacer que el dispositivo sea más susceptible al malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  <br/> |
|No permitir que los usuarios copien contenido de aplicaciones Office en aplicaciones personales  <br/> |Cuando la configuración es **On**, el usuario no puede copiar información de un archivo de trabajo en un archivo personal. Si la configuración es **Off,** el usuario puede copiar información de un archivo de trabajo en una aplicación personal o cuenta personal.  <br/> |
   

