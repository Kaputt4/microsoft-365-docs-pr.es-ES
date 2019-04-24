---
title: Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Obtenga información sobre las directivas de protección que pueden ayudar a proteger el acceso a las aplicaciones de Office desde dispositivos móviles.
ms.openlocfilehash: b77d30686b26f95de684238d1b9afd57550a7c7f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278617"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles

 La configuración de directiva que controla cómo acceden los usuarios a los archivos de Office desde sus dispositivos móviles están **desactivadas** de forma predeterminada. Le recomendamos que acepte los valores predeterminados durante la configuración para crear directivas de aplicación para Android, iOS y Windows 10 que se apliquen a todos los usuarios. Podrá crear más directivas cuando se complete la configuración. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles

Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:
  
|||
|:-----|:-----|
|Configuración  <br/> |Descripción  <br/> |
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  <br/> |Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.  <br/> |
|Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces  <br/> |Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.  <br/> |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante  <br/> |Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.  <br/> |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  <br/> |Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  <br/> |
|Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales  <br/> |Permitimos esta opción de forma predeterminada; pero, cuando está **activada**, el usuario podrá copiar la información de un archivo de trabajo en un archivo personal. Si la configuración está **desactivada**, el usuario no podrá copiar información de un archivo de trabajo a una aplicación personal o a una cuenta personal.  <br/> |
   

