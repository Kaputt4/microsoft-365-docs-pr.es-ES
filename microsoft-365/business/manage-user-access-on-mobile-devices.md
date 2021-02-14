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
description: Obtenga información sobre las directivas de protección que le permiten administrar cómo los usuarios acceden a las aplicaciones de Office y a los archivos de trabajo desde dispositivos móviles.
ms.openlocfilehash: b2b828cf2e201360f12b8fadcb395e72958230f6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471075"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="5da6d-103">Administrar la forma en que los usuarios obtienen acceso a documentos de Office en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="5da6d-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="5da6d-104">Este artículo se aplica a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="5da6d-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="5da6d-105">La configuración de directiva que controla cómo acceden los usuarios a los archivos de Office desde sus dispositivos móviles están **desactivadas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5da6d-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="5da6d-106">Te recomendamos que aceptes los valores predeterminados durante la instalación para crear directivas de aplicación para Android, iOS y Windows 10 que se apliquen a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5da6d-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="5da6d-107">Podrá crear más directivas cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="5da6d-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="5da6d-108">Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="5da6d-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="5da6d-109">Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:</span><span class="sxs-lookup"><span data-stu-id="5da6d-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5da6d-110">Configuración</span><span class="sxs-lookup"><span data-stu-id="5da6d-110">Setting</span></span>  <br/> |<span data-ttu-id="5da6d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5da6d-111">Description</span></span>  <br/> |
|<span data-ttu-id="5da6d-112">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="5da6d-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="5da6d-113">Si esta configuración **está** on , los usuarios deben proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="5da6d-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="5da6d-114">Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces</span><span class="sxs-lookup"><span data-stu-id="5da6d-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="5da6d-115">Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.</span><span class="sxs-lookup"><span data-stu-id="5da6d-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="5da6d-116">Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante</span><span class="sxs-lookup"><span data-stu-id="5da6d-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="5da6d-117">Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="5da6d-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="5da6d-118">Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting</span><span class="sxs-lookup"><span data-stu-id="5da6d-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="5da6d-119">Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting.</span><span class="sxs-lookup"><span data-stu-id="5da6d-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="5da6d-120">Esto significa que el usuario puede modificar el sistema operativo, lo que puede hacer que el dispositivo sea más susceptible a malware.</span><span class="sxs-lookup"><span data-stu-id="5da6d-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="5da6d-121">Estos dispositivos se bloquean cuando esta configuración está **activada**.</span><span class="sxs-lookup"><span data-stu-id="5da6d-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="5da6d-122">No permitir que los usuarios copien contenido de aplicaciones de Office en aplicaciones personales</span><span class="sxs-lookup"><span data-stu-id="5da6d-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="5da6d-123">Cuando la configuración está **on**, el usuario no puede copiar la información de un archivo de trabajo a un archivo personal.</span><span class="sxs-lookup"><span data-stu-id="5da6d-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="5da6d-124">Si la configuración está **desactivada,** el usuario puede copiar información de un archivo de trabajo a una aplicación personal o cuenta personal.</span><span class="sxs-lookup"><span data-stu-id="5da6d-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

