---
title: Solución de problemas de movilidad y seguridad básicas
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Pruebe estos pasos para realizar un seguimiento de los problemas básicos de la movilidad y la seguridad
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430299"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="3ea5c-103">Solución de problemas de movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="3ea5c-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="3ea5c-104">Si tiene problemas al intentar inscribir un dispositivo en la movilidad y la seguridad básica, siga los pasos que se indican a continuación para realizar un seguimiento del problema.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="3ea5c-105">Si los pasos generales no solucionan el problema, consulte una de las secciones posteriores con pasos específicos para el tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="3ea5c-106">Pasos para probar primero</span><span class="sxs-lookup"><span data-stu-id="3ea5c-106">Steps to try first</span></span>

<span data-ttu-id="3ea5c-107">Para empezar, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ea5c-107">To start, check the following:</span></span>

- <span data-ttu-id="3ea5c-108">Asegúrese de que el dispositivo todavía no está inscrito con otro proveedor de administración de dispositivos móviles, como Intune.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="3ea5c-109">Asegúrese de que el dispositivo está configurado con la fecha y hora correctas.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="3ea5c-110">Cambia a otra red de telefonía móvil o Wi-Fi en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="3ea5c-111">Para dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación del portal de empresa de Intune en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="3ea5c-112">tableta o teléfono iOS</span><span class="sxs-lookup"><span data-stu-id="3ea5c-112">iOS phone or tablet</span></span>

- <span data-ttu-id="3ea5c-113">Asegúrese de que ha configurado un certificado de APNs.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="3ea5c-114">Para obtener más información, vea [crear un certificado de APNs para dispositivos iOS](create-an-apns-certificate-for-ios-devices.md).</span><span class="sxs-lookup"><span data-stu-id="3ea5c-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="3ea5c-115">En **configuración**   >  **General**de   >  **perfil (o administración de dispositivos)**, asegúrese de que ya hay un perfil de Administración instalado.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="3ea5c-116">Si es así, quítela.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="3ea5c-117">Si ve el mensaje de error "el dispositivo no pudo inscribirse", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="3ea5c-118">Si aparece el mensaje de error "no se pudo instalar el perfil", pruebe una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3ea5c-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="3ea5c-119">Asegúrese de que Safari es el explorador predeterminado en el dispositivo y de que las cookies no están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="3ea5c-120">Reinicie el dispositivo y, a continuación, vaya a portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="3ea5c-121">Inicie sesión con su identificador de usuario y contraseña de Microsoft 365 e intente instalar el perfil de forma manual.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="3ea5c-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="3ea5c-122">Windows RT</span></span>

- <span data-ttu-id="3ea5c-123">Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="3ea5c-124">Para obtener más información, consulte [set up Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3ea5c-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="3ea5c-125">Asegúrese de que el usuario está seleccionando **activar en**   lugar de elegir **unirse**.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="3ea5c-126">PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="3ea5c-126">Windows 10 PC</span></span>

- <span data-ttu-id="3ea5c-127">Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="3ea5c-128">Para obtener más información, consulte [set up Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3ea5c-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="3ea5c-129">A menos que tenga Azure Active Directory Premium, asegúrese de que el usuario solo está seleccionando **inscribirse en la administración de dispositivos**en   lugar de elegir **conectar**.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="3ea5c-130">Tableta o teléfono Android</span><span class="sxs-lookup"><span data-stu-id="3ea5c-130">Android phone or tablet</span></span>

- <span data-ttu-id="3ea5c-131">Asegúrese de que el dispositivo está ejecutando Android 4,4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="3ea5c-132">Asegúrese de que Chrome está actualizado y establecido como explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="3ea5c-133">Si ve el mensaje de error "no se pudo inscribir este dispositivo", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="3ea5c-134">Compruebe el área de notificación en el dispositivo para ver si hay acciones del usuario final necesarias y, si es así, complete las acciones.</span><span class="sxs-lookup"><span data-stu-id="3ea5c-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>