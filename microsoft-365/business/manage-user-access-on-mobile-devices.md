---
title: Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Obtenga información sobre las directivas de protección que pueden ayudar a proteger el acceso a las aplicaciones de Office desde dispositivos móviles.
ms.openlocfilehash: b49ec33f4899a25f92ffd9d7a25d3e435016749e
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660369"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="c5af9-103">Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="c5af9-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="c5af9-p101">La configuración de directiva que controla cómo acceden los usuarios a los archivos de Office desde sus dispositivos móviles están **desactivadas** de forma predeterminada. Le recomendamos que acepte los valores predeterminados durante la configuración para crear directivas de aplicación para Android, iOS y Windows 10 que se apliquen a todos los usuarios. Podrá crear más directivas cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="c5af9-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="c5af9-107">Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="c5af9-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="c5af9-108">Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:</span><span class="sxs-lookup"><span data-stu-id="c5af9-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c5af9-109">Valor</span><span class="sxs-lookup"><span data-stu-id="c5af9-109">Setting</span></span>  <br/> |<span data-ttu-id="c5af9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5af9-110">Description</span></span>  <br/> |
|<span data-ttu-id="c5af9-111">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="c5af9-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="c5af9-112">Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="c5af9-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="c5af9-113">Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces</span><span class="sxs-lookup"><span data-stu-id="c5af9-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="c5af9-114">Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.</span><span class="sxs-lookup"><span data-stu-id="c5af9-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="c5af9-115">Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante</span><span class="sxs-lookup"><span data-stu-id="c5af9-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="c5af9-116">Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="c5af9-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="c5af9-117">Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting</span><span class="sxs-lookup"><span data-stu-id="c5af9-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="c5af9-p102">Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  </span><span class="sxs-lookup"><span data-stu-id="c5af9-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="c5af9-121">No permitir a los usuarios copiar contenido de las aplicaciones de Office en aplicaciones personales</span><span class="sxs-lookup"><span data-stu-id="c5af9-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="c5af9-122">Cuando la configuración está **activada**, el usuario no puede copiar la información de un archivo de trabajo a un archivo personal.</span><span class="sxs-lookup"><span data-stu-id="c5af9-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="c5af9-123">Si la configuración está \*\*\*\* desactivada, el usuario puede copiar información de un archivo de trabajo a una aplicación personal o a una cuenta personal.</span><span class="sxs-lookup"><span data-stu-id="c5af9-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

