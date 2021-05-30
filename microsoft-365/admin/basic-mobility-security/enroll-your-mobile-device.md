---
title: Inscribir el dispositivo móvil con movilidad básica y seguridad
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Antes de poder usar Microsoft 365 con el dispositivo, es posible que deba inscribirlo primero en Movilidad básica y seguridad para Microsoft 365.
ms.openlocfilehash: 2ad0aac331969696bbf53d0b06c18ee5c0ee90f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706171"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="41ea8-103">Inscribir el dispositivo móvil con movilidad básica y seguridad</span><span class="sxs-lookup"><span data-stu-id="41ea8-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="41ea8-104">Usar el teléfono, la tableta y otros dispositivos móviles para trabajar es una excelente manera de mantenerse informado y trabajar en proyectos empresariales mientras está fuera de la oficina.</span><span class="sxs-lookup"><span data-stu-id="41ea8-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="41ea8-105">Antes de poder usar Microsoft 365 con el dispositivo, es posible que primero deba inscribirlo en Movilidad básica y seguridad para Microsoft 365 usar Microsoft Intune Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="41ea8-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="41ea8-106">Las organizaciones eligen Movilidad básica y seguridad para que los empleados puedan usar sus dispositivos móviles para acceder de forma segura al correo electrónico, calendarios y documentos del trabajo, mientras que la empresa protege los datos importantes y cumple sus requisitos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="41ea8-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="41ea8-107">Para obtener más información, vea [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="41ea8-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="41ea8-108">Para obtener más información, consulta ¿Qué información puede [ver mi organización cuando inscribo mi dispositivo?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="41ea8-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="41ea8-109">Al inscribir el dispositivo en Movilidad básica y seguridad para Microsoft 365, es posible que deba configurar una contraseña, además de permitir que la organización del trabajo borre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="41ea8-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="41ea8-110">Un borrado de dispositivo se puede realizar desde el centro de administración de Microsoft 365, por ejemplo, para quitar todos los datos del dispositivo si la contraseña se introduce incorrectamente demasiadas veces o si se rompen los términos de uso.</span><span class="sxs-lookup"><span data-stu-id="41ea8-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="41ea8-111">Dispositivos admitidos</span><span class="sxs-lookup"><span data-stu-id="41ea8-111">Supported devices</span></span>

<span data-ttu-id="41ea8-112">Movilidad básica y seguridad para Microsoft 365 hospedados por el servicio de Intune funciona con la mayoría de los dispositivos móviles, pero no todos.</span><span class="sxs-lookup"><span data-stu-id="41ea8-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="41ea8-113">Los siguientes son compatibles con movilidad y seguridad básicas:</span><span class="sxs-lookup"><span data-stu-id="41ea8-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="41ea8-114">iOS 10.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="41ea8-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="41ea8-115">Android 4.4 o posterior</span><span class="sxs-lookup"><span data-stu-id="41ea8-115">Android 4.4 or later</span></span>

- <span data-ttu-id="41ea8-116">Windows 8.1 y Windows 10 (Teléfono y PC)</span><span class="sxs-lookup"><span data-stu-id="41ea8-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="41ea8-117">Si el dispositivo no aparece anteriormente y necesitas usarlo con Movilidad y seguridad básicas, ponte en contacto con el administrador profesional o educativo.</span><span class="sxs-lookup"><span data-stu-id="41ea8-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="41ea8-118">Si tienes problemas para inscribir el dispositivo, consulta Solucionar problemas [de movilidad y seguridad básicas.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="41ea8-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="41ea8-119">Configurar el dispositivo móvil con Intune y movilidad básica y seguridad</span><span class="sxs-lookup"><span data-stu-id="41ea8-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="41ea8-120">El Portal de empresa de Intune permite administrar un dispositivo mediante Microsoft 365 y movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="41ea8-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="41ea8-121">iPhone o iPad</span><span class="sxs-lookup"><span data-stu-id="41ea8-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="41ea8-122">No podrá enviar y recibir correo electrónico hasta que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="41ea8-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="41ea8-123">Ve a la Tienda de aplicaciones de Apple y descarga e instala Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="41ea8-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="41ea8-124">Para conectar y configurar su teléfono o tableta iOS con el portal de empresa para que Office 365, consulte Configurar el acceso de [dispositivos iOS](/mem/intune/user-help/enroll-your-device-in-intune-ios)a los recursos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="41ea8-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="41ea8-125">Teléfono o tableta Android</span><span class="sxs-lookup"><span data-stu-id="41ea8-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="41ea8-126">No podrá enviar y recibir correo electrónico hasta que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="41ea8-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="41ea8-127">Ve a la Tienda Google Play y descarga e instala Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="41ea8-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="41ea8-128">Para conectar y configurar su teléfono o tableta Android con el portal de la empresa para Microsoft 365, consulte Inscribir el dispositivo [con Portal de empresa](/mem/intune/user-help/enroll-device-android-company-portal).</span><span class="sxs-lookup"><span data-stu-id="41ea8-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="41ea8-129">Windows 8.1 y Windows 10</span><span class="sxs-lookup"><span data-stu-id="41ea8-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="41ea8-130">Vaya a la Microsoft Store y descargue e instale Portal de empresa de Intune</span><span class="sxs-lookup"><span data-stu-id="41ea8-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="41ea8-131">Para conectar y configurar el Windows teléfono o equipo con el portal de la empresa para Microsoft 365, consulte Windows inscripción de [dispositivos en Portal de empresa de Intune](/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="41ea8-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="41ea8-132">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="41ea8-132">Next steps</span></span>

<span data-ttu-id="41ea8-133">Después de inscribir el dispositivo en Movilidad y seguridad básicas, puedes empezar a usar Office aplicaciones en el dispositivo para trabajar con correo electrónico, calendario, contactos y documentos.</span><span class="sxs-lookup"><span data-stu-id="41ea8-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>