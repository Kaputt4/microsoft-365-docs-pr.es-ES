---
title: Información general sobre la movilidad y la seguridad básicas de Microsoft 365
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
description: Use la movilidad y la seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430297"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="28443-103">Información general sobre la movilidad y la seguridad básicas de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28443-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="28443-104">Puede administrar y proteger los dispositivos móviles cuando están conectados a su organización de Microsoft 365 mediante la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="28443-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="28443-105">Los dispositivos móviles, como los smartphones y las tabletas, que se usan para tener acceso a elementos de trabajo como el correo electrónico, el calendario, los contactos y los documentos, desempeñan un papel muy importante a la hora de garantizar que los empleados puedan realizar su trabajo en cualquier momento y en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="28443-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="28443-106">Por lo tanto, es fundamental que ayude a proteger la información de su organización cuando los usuarios usan dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28443-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="28443-107">Puede usar la movilidad y la seguridad básicas para establecer las directivas de seguridad de los dispositivos y las reglas de acceso, así como para borrar los dispositivos móviles si se pierden o son robados.</span><span class="sxs-lookup"><span data-stu-id="28443-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuración básica de movilidad y seguridad":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="28443-109">¿Qué tipos de dispositivos se pueden administrar?</span><span class="sxs-lookup"><span data-stu-id="28443-109">What types of devices can you manage?</span></span>

<span data-ttu-id="28443-110">Puede usar la movilidad y la seguridad básicas para administrar muchos tipos de dispositivos móviles, como Windows Phone, Android, iPhone y iPad.</span><span class="sxs-lookup"><span data-stu-id="28443-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="28443-111">Para administrar los dispositivos móviles que usan las personas de la organización, cada persona debe tener una licencia de Microsoft 365 aplicable y su dispositivo debe estar inscrito en la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="28443-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="28443-112">Para ver qué es compatible con la movilidad y la seguridad básicas para cada tipo de dispositivo, consulte [Capabilities of Basic Mobility and Security](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="28443-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="28443-113">Pasos de configuración para la movilidad y la seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="28443-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="28443-114">Un administrador global de Microsoft 365 debe completar los pasos siguientes para activar y configurar la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="28443-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="28443-115">Para conocer los pasos detallados, siga las instrucciones de [set up Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="28443-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="28443-116">Este es un resumen de los pasos:</span><span class="sxs-lookup"><span data-stu-id="28443-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="28443-117">**Paso 1:** Para activar la movilidad y la seguridad básicas, siga los pasos descritos en [set up Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="28443-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="28443-118">**Paso 2:** Configure la movilidad y la seguridad básicas; por ejemplo, cree un certificado APN para administrar dispositivos iOS y agregar un registro de sistema de nombres de dominio (DNS) para su dominio para que admita Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="28443-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="28443-119">**Paso 3:** Crear directivas de dispositivo y aplicarlas a grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="28443-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="28443-120">Al hacerlo, los usuarios reciben un mensaje de inscripción en su dispositivo y, cuando hayan completado la inscripción, sus dispositivos estarán restringidos por las directivas que haya configurado para ellos.</span><span class="sxs-lookup"><span data-stu-id="28443-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="28443-121">Para obtener más información, vea [inscribir un dispositivo móvil con la seguridad y la movilidad básicos](enroll-your-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="28443-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración básica de la Directiva de seguridad y movilidad":::

## <a name="device-management-tasks"></a><span data-ttu-id="28443-123">Tareas de administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="28443-123">Device management tasks</span></span>

<span data-ttu-id="28443-124">Una vez que tenga una configuración básica de movilidad y seguridad y que los usuarios hayan inscrito sus dispositivos, puede administrar los dispositivos, bloquear el acceso o borrar un dispositivo, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="28443-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="28443-125">Para obtener más información sobre algunas de las tareas de administración de dispositivos comunes, como dónde completar las tareas, vea [administrar dispositivos inscritos en administración de dispositivos móviles para Microsoft 365](manage-enrolled-devices.md).</span><span class="sxs-lookup"><span data-stu-id="28443-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="28443-126">Otras formas de administrar dispositivos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="28443-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="28443-127">Si solo necesita la administración de aplicaciones móviles (MAM), quizás para las personas que actualicen proyectos de trabajo en sus propios dispositivos, Intune ofrece otra opción además de inscribir y administrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28443-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="28443-128">Una suscripción de Intune le permite configurar directivas de MAM mediante el portal de Azure, incluso si los dispositivos de los usuarios no están inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="28443-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="28443-129">Para obtener más información, vea [directivas de protección de aplicaciones](https://go.microsoft.com/fwlink/?LinkId=2132517).</span><span class="sxs-lookup"><span data-stu-id="28443-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="28443-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="28443-130">Related topics</span></span>

[<span data-ttu-id="28443-131">Configurar la Seguridad de Movilidad Básica</span><span class="sxs-lookup"><span data-stu-id="28443-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="28443-132">Inscribir el dispositivo móvil con la seguridad y la movilidad básicas</span><span class="sxs-lookup"><span data-stu-id="28443-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="28443-133">Administrar dispositivos inscritos en la administración de dispositivos móviles para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28443-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="28443-134">Obtener información sobre los dispositivos administrados por la seguridad y la movilidad básicos</span><span class="sxs-lookup"><span data-stu-id="28443-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)