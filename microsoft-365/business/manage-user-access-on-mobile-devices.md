---
title: Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
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
description: Obtenga información acerca de las directivas de protección que pueden ayudar a proteger el acceso a las aplicaciones de Office desde dispositivos móviles.
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871474"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="808ab-103">Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="808ab-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="808ab-p101">La configuración de directiva que controla cómo acceden los usuarios a los archivos de Office desde sus dispositivos móviles están **desactivadas** de forma predeterminada. Le recomendamos que acepte los valores predeterminados durante la configuración para crear directivas de aplicación para Android, iOS y Windows 10 que se apliquen a todos los usuarios. Podrá crear más directivas cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="808ab-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="808ab-107">Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="808ab-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="808ab-108">Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:</span><span class="sxs-lookup"><span data-stu-id="808ab-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="808ab-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="808ab-109">Setting</span></span>  <br/> |<span data-ttu-id="808ab-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="808ab-110">Description</span></span>  <br/> |
|<span data-ttu-id="808ab-111">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="808ab-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="808ab-112">Si esta configuración está **activada**, los usuarios tendrán que proporcionar otra forma de autenticación, además de su nombre de usuario y la contraseña, para usar las aplicaciones de Office en sus dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="808ab-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="808ab-113">Restablecer el PIN cuando no se pueda iniciar sesión este número de veces</span><span class="sxs-lookup"><span data-stu-id="808ab-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="808ab-114">Para impedir que un usuario no autorizado pueda averiguar de forma aleatoria un PIN, este se restablecerá después del número de entradas incorrectas que especifique.</span><span class="sxs-lookup"><span data-stu-id="808ab-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="808ab-115">Exigir a los usuarios que vuelvan a iniciar sesión cuando las aplicaciones de Office estén inactivas durante</span><span class="sxs-lookup"><span data-stu-id="808ab-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="808ab-116">Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="808ab-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="808ab-117">Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting</span><span class="sxs-lookup"><span data-stu-id="808ab-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="808ab-p102">Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  </span><span class="sxs-lookup"><span data-stu-id="808ab-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="808ab-121">Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales</span><span class="sxs-lookup"><span data-stu-id="808ab-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="808ab-p103">Permitimos esta opción de forma predeterminada; pero, cuando está **activada**, el usuario podrá copiar la información de un archivo de trabajo en un archivo personal. Si la configuración está **desactivada**, el usuario no podrá copiar información de un archivo de trabajo a una aplicación personal o a una cuenta personal.  </span><span class="sxs-lookup"><span data-stu-id="808ab-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

