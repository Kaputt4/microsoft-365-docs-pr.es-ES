---
title: Inscribir el dispositivo móvil con movilidad y seguridad básicas
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
description: Antes de poder usar los servicios de Microsoft 365 con el dispositivo, es posible que primero deba inscribirlo en Movilidad básica y seguridad para Microsoft 365.
ms.openlocfilehash: dc5a43b12fce50c9146200a4559fe9b7e6824b18
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877061"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="7a922-103">Inscribir el dispositivo móvil con movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="7a922-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="7a922-104">Usar su teléfono, tableta y otros dispositivos móviles para trabajar es una excelente manera de mantenerse informado y trabajar en proyectos empresariales mientras está fuera de la oficina.</span><span class="sxs-lookup"><span data-stu-id="7a922-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="7a922-105">Antes de poder usar los servicios de Microsoft 365 con el dispositivo, es posible que primero deba inscribirlo en Movilidad básica y seguridad para Microsoft 365 mediante el Portal de empresa de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="7a922-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="7a922-106">Las organizaciones eligen Movilidad y seguridad básicas para que los empleados puedan usar sus dispositivos móviles para acceder de forma segura al correo electrónico, calendarios y documentos del trabajo mientras la empresa protege los datos importantes y cumple sus requisitos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7a922-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="7a922-107">Para obtener más información, consulte Información general sobre movilidad y [seguridad básicas para Microsoft 365.](overview.md)</span><span class="sxs-lookup"><span data-stu-id="7a922-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="7a922-108">Para obtener más información, consulta [¿Qué información puede ver mi organización cuando inscribo mi dispositivo?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)</span><span class="sxs-lookup"><span data-stu-id="7a922-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="7a922-109">Al inscribir el dispositivo en movilidad básica y seguridad para Microsoft 365, es posible que deba configurar una contraseña, además de permitir que la organización del trabajo borre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a922-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="7a922-110">Se puede realizar una eliminación del dispositivo desde el Centro de administración de Microsoft 365, por ejemplo, para quitar todos los datos del dispositivo si la contraseña se ha escrito incorrectamente demasiadas veces o si se rompen los términos de uso.</span><span class="sxs-lookup"><span data-stu-id="7a922-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="7a922-111">Dispositivos admitidos</span><span class="sxs-lookup"><span data-stu-id="7a922-111">Supported devices</span></span>

<span data-ttu-id="7a922-112">La movilidad y seguridad básicas para Microsoft 365 hospedada por el servicio intune funciona con la mayoría de los dispositivos móviles, pero no con todos.</span><span class="sxs-lookup"><span data-stu-id="7a922-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="7a922-113">Los siguientes elementos son compatibles con la movilidad y la seguridad básicas:</span><span class="sxs-lookup"><span data-stu-id="7a922-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="7a922-114">iOS 10.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="7a922-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="7a922-115">Android 4.4 o posterior</span><span class="sxs-lookup"><span data-stu-id="7a922-115">Android 4.4 or later</span></span>

- <span data-ttu-id="7a922-116">Windows 8.1 y Windows 10 (teléfono y PC)</span><span class="sxs-lookup"><span data-stu-id="7a922-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="7a922-117">Si el dispositivo no aparece en la lista anterior y necesitas usarlo con Movilidad y seguridad básicas, ponte en contacto con el administrador de tu trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="7a922-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="7a922-118">Si tienes problemas para inscribir el dispositivo, consulta Solucionar problemas [de movilidad y seguridad básicas.](/basic-mobility-security/troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="7a922-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](/basic-mobility-security/troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="7a922-119">Configurar el dispositivo móvil con Intune y movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="7a922-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="7a922-120">El Portal de empresa de Intune permite que Microsoft 365 y Basic Mobility and Security administren un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a922-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="7a922-121">iPhone o iPad</span><span class="sxs-lookup"><span data-stu-id="7a922-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="7a922-122">No podrá enviar ni recibir correo electrónico hasta que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="7a922-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="7a922-123">Vaya a La App Store de Apple y descargue e instale el Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="7a922-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="7a922-124">Para conectar y configurar su teléfono o tableta iOS con el portal de empresa a Office 365, consulte Configurar el acceso de [dispositivos iOS](https://go.microsoft.com/fwlink/?linkid=875316)a los recursos de su empresa.</span><span class="sxs-lookup"><span data-stu-id="7a922-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="7a922-125">Teléfono o tableta Android</span><span class="sxs-lookup"><span data-stu-id="7a922-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="7a922-126">No podrá enviar ni recibir correo electrónico hasta que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="7a922-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="7a922-127">Vaya a Google Play Store y descargue e instale el Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="7a922-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="7a922-128">Para conectar y configurar su teléfono o tableta Android con el portal de empresa a Microsoft 365, consulte Inscribir el dispositivo [en el Portal de empresa.](https://go.microsoft.com/fwlink/?linkid=875317)</span><span class="sxs-lookup"><span data-stu-id="7a922-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="7a922-129">Windows 8.1 y Windows 10</span><span class="sxs-lookup"><span data-stu-id="7a922-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="7a922-130">Vaya a Microsoft Store y descargue e instale el Portal de empresa de Intune</span><span class="sxs-lookup"><span data-stu-id="7a922-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="7a922-131">Para conectar y configurar su teléfono o pc Windows con el portal de empresa a Microsoft 365, consulte Inscripción de [dispositivos Windows en el Portal de empresa de Intune.](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="7a922-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="7a922-132">¿Cuál es el siguiente paso?</span><span class="sxs-lookup"><span data-stu-id="7a922-132">What's next?</span></span>

<span data-ttu-id="7a922-133">Después de inscribir el dispositivo en movilidad y seguridad básicas, puede empezar a usar las aplicaciones de Office en el dispositivo para trabajar con el correo electrónico, el calendario, los contactos y los documentos.</span><span class="sxs-lookup"><span data-stu-id="7a922-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
