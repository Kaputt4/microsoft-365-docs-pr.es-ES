---
title: Solucionar problemas de movilidad y seguridad básicas
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
description: Pruebe estos pasos para realizar un seguimiento de los problemas de movilidad y seguridad básicas
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876857"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="0ab3f-103">Solucionar problemas de movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="0ab3f-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="0ab3f-104">Si tiene problemas al intentar inscribir un dispositivo en Movilidad y Seguridad básica, siga estos pasos para realizar un seguimiento del problema.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="0ab3f-105">Si los pasos generales no solucionan el problema, consulta una de las secciones posteriores con pasos específicos para el tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="0ab3f-106">Pasos para probar primero</span><span class="sxs-lookup"><span data-stu-id="0ab3f-106">Steps to try first</span></span>

<span data-ttu-id="0ab3f-107">Para empezar, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ab3f-107">To start, check the following:</span></span>

- <span data-ttu-id="0ab3f-108">Asegúrate de que el dispositivo no esté inscrito con otro proveedor de administración de dispositivos móviles, como Intune.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="0ab3f-109">Asegúrate de que el dispositivo está establecido en la fecha y hora correctas.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="0ab3f-110">Cambia a otra red WIFI o de telefonía móvil en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="0ab3f-111">Para dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación Portal de empresa de Intune en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="0ab3f-112">Teléfono o tableta iOS</span><span class="sxs-lookup"><span data-stu-id="0ab3f-112">iOS phone or tablet</span></span>

- <span data-ttu-id="0ab3f-113">Asegúrese de que ha configurado un certificado de APNs.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="0ab3f-114">Para obtener más información, consulta [Crear un certificado APNs para dispositivos iOS.](create-an-apns-certificate-for-ios-devices.md)</span><span class="sxs-lookup"><span data-stu-id="0ab3f-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="0ab3f-115">En **Configuración** de perfil general (o administración de   >  \*\*\*\*   >  **dispositivos),** asegúrese de que un perfil de administración no esté instalado todavía.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="0ab3f-116">Si es así, quítela.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-116">If it is, remove it.</span></span>

- <span data-ttu-id="0ab3f-117">Si ve el mensaje de error "El dispositivo no se inscribió", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="0ab3f-118">Si aparece el mensaje de error "No se pudo instalar el perfil", pruebe uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0ab3f-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="0ab3f-119">Asegúrese de que Safari es el explorador predeterminado en el dispositivo y de que las cookies no están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="0ab3f-120">Reinicia el dispositivo y, a continuación, navega hasta portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="0ab3f-121">Inicie sesión con su identificador de usuario y contraseña de Microsoft 365 e intente instalar el perfil manualmente.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="0ab3f-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="0ab3f-122">Windows RT</span></span>

- <span data-ttu-id="0ab3f-123">Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="0ab3f-124">Para obtener más información, consulta [Configurar movilidad y seguridad básicas.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="0ab3f-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="0ab3f-125">Asegúrese de que el usuario elige **Activar** en lugar de   elegir **Unirse.**</span><span class="sxs-lookup"><span data-stu-id="0ab3f-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="0ab3f-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="0ab3f-126">Windows 10 PC</span></span>

- <span data-ttu-id="0ab3f-127">Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="0ab3f-128">Para obtener más información, consulta [Configurar movilidad y seguridad básicas.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="0ab3f-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="0ab3f-129">A menos que tenga Azure Active Directory Premium, \*\*\*\* asegúrese de que el usuario elija Inscribirse en la administración de dispositivos solo en lugar de   elegir **Conectar.**</span><span class="sxs-lookup"><span data-stu-id="0ab3f-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="0ab3f-130">Teléfono o tableta Android</span><span class="sxs-lookup"><span data-stu-id="0ab3f-130">Android phone or tablet</span></span>

- <span data-ttu-id="0ab3f-131">Asegúrate de que el dispositivo ejecuta Android 4.4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="0ab3f-132">Asegúrese de que Chrome está actualizado y está configurado como explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="0ab3f-133">Si ve el mensaje de error "No hemos podido inscribir este dispositivo", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="0ab3f-134">Comprueba el área de notificación del dispositivo para ver si hay alguna acción necesaria del usuario final pendiente y, si es así, completa las acciones.</span><span class="sxs-lookup"><span data-stu-id="0ab3f-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>