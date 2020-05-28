---
title: Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: Obtenga información sobre las directivas de protección que le permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo y aplicaciones de Office desde dispositivos móviles.
ms.openlocfilehash: f613e518c3607010cae55443456be9d3ddc3d689
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403086"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="7d6be-103">Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="7d6be-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="7d6be-104">La configuración de directiva que controla cómo acceden los usuarios a los archivos de Office desde sus dispositivos móviles están **desactivadas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d6be-104">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="7d6be-105">Le recomendamos que acepte los valores predeterminados durante la configuración para crear directivas de aplicación para Android, iOS y Windows 10 que se aplican a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7d6be-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="7d6be-106">Podrá crear más directivas cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="7d6be-106">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="7d6be-107">Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="7d6be-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="7d6be-108">Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:</span><span class="sxs-lookup"><span data-stu-id="7d6be-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7d6be-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="7d6be-109">Setting</span></span>  <br/> |<span data-ttu-id="7d6be-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d6be-110">Description</span></span>  <br/> |
|<span data-ttu-id="7d6be-111">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="7d6be-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="7d6be-112">Si esta configuración está **activada**, los usuarios deben proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar las aplicaciones de Office en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="7d6be-112">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="7d6be-113">Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces</span><span class="sxs-lookup"><span data-stu-id="7d6be-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="7d6be-114">Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.</span><span class="sxs-lookup"><span data-stu-id="7d6be-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="7d6be-115">Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante</span><span class="sxs-lookup"><span data-stu-id="7d6be-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="7d6be-116">Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="7d6be-116">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="7d6be-117">Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting</span><span class="sxs-lookup"><span data-stu-id="7d6be-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="7d6be-118">Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting.</span><span class="sxs-lookup"><span data-stu-id="7d6be-118">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="7d6be-119">Esto significa que el usuario puede modificar el sistema operativo, lo que puede hacer que el dispositivo sea más susceptible a malware.</span><span class="sxs-lookup"><span data-stu-id="7d6be-119">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="7d6be-120">Estos dispositivos se bloquean cuando esta configuración está **activada**.</span><span class="sxs-lookup"><span data-stu-id="7d6be-120">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="7d6be-121">No permitir a los usuarios copiar contenido de las aplicaciones de Office en aplicaciones personales</span><span class="sxs-lookup"><span data-stu-id="7d6be-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="7d6be-122">Cuando la configuración está **activada**, el usuario no puede copiar la información de un archivo de trabajo a un archivo personal.</span><span class="sxs-lookup"><span data-stu-id="7d6be-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="7d6be-123">Si la configuración está **desactivada**, el usuario puede copiar información de un archivo de trabajo a una aplicación personal o a una cuenta personal.</span><span class="sxs-lookup"><span data-stu-id="7d6be-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

