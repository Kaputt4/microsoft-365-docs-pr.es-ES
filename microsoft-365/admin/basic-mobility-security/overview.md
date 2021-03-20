---
title: Información general sobre movilidad básica y seguridad para Microsoft 365
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
description: Usa Movilidad y seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso.
ms.openlocfilehash: e74a5df6d10f8f3fb7b420e428380af97ba75597
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906257"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="ab1ce-103">Información general sobre movilidad básica y seguridad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab1ce-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="ab1ce-104">Puedes administrar y proteger los dispositivos móviles cuando estén conectados a tu organización de Microsoft 365 mediante movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="ab1ce-105">Los dispositivos móviles, como los smartphones y las tabletas, que se usan para tener acceso a elementos de trabajo como el correo electrónico, el calendario, los contactos y los documentos, desempeñan un papel muy importante a la hora de garantizar que los empleados puedan realizar su trabajo en cualquier momento y en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="ab1ce-106">Por lo tanto, es fundamental que ayudes a proteger la información de la organización cuando las personas usan dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="ab1ce-107">Puedes usar Movilidad y seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso, y para borrar los dispositivos móviles si se pierden o se roban.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuración básica de movilidad y seguridad":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="ab1ce-109">¿Qué tipos de dispositivos se pueden administrar?</span><span class="sxs-lookup"><span data-stu-id="ab1ce-109">What types of devices can you manage?</span></span>

<span data-ttu-id="ab1ce-110">Puedes usar Movilidad y seguridad básicas para administrar muchos tipos de dispositivos móviles como Windows Phone, Android, iPhone y iPad.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="ab1ce-111">Para administrar los dispositivos móviles que usan los usuarios de la organización, cada persona debe tener una licencia de Microsoft 365 aplicable y su dispositivo debe estar inscrito en Movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="ab1ce-112">Para ver qué admite movilidad y seguridad básicas para cada tipo de dispositivo, consulta [Funcionalidades de movilidad y seguridad básicas.](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="ab1ce-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="ab1ce-113">Pasos de configuración para movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="ab1ce-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="ab1ce-114">Un administrador global de Microsoft 365 debe completar los siguientes pasos para activar y configurar la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="ab1ce-115">Para conocer los pasos detallados, siga las instrucciones [de Configurar movilidad y seguridad básicas.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="ab1ce-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="ab1ce-116">Este es un resumen de los pasos:</span><span class="sxs-lookup"><span data-stu-id="ab1ce-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="ab1ce-117">**Paso 1:** Active La movilidad y la seguridad básicas siguiendo los pasos descritos  [en Configurar la movilidad básica y la seguridad.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="ab1ce-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="ab1ce-118">**Paso 2:** Configura movilidad y seguridad básicas mediante, por ejemplo, crear un certificado de APNs para administrar dispositivos iOS y agregar un registro de sistema de nombres de dominio (DNS) para que tu dominio admita teléfonos Windows.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="ab1ce-119">**Paso 3:** Crear directivas de dispositivo y aplicarlas a grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="ab1ce-120">Al hacerlo, los usuarios obtienen un mensaje de inscripción en su dispositivo y, cuando han completado la inscripción, sus dispositivos están restringidos por las directivas que haya configurado para ellos.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="ab1ce-121">Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="ab1ce-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración básica de la directiva de seguridad y movilidad":::

## <a name="device-management-tasks"></a><span data-ttu-id="ab1ce-123">Tareas de administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ab1ce-123">Device management tasks</span></span>

<span data-ttu-id="ab1ce-124">Después de configurar La movilidad y la seguridad básicas y de que los usuarios se han inscrito en sus dispositivos, puedes administrar los dispositivos, bloquear el acceso o borrar un dispositivo, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="ab1ce-125">Para obtener más información sobre algunas tareas comunes de administración de dispositivos, como dónde completar las tareas, consulta Administrar dispositivos inscritos en [Mobile Device Management para Microsoft 365](manage-enrolled-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ab1ce-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="ab1ce-126">Otras formas de administrar dispositivos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ab1ce-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="ab1ce-127">Si solo necesitas administración de aplicaciones móviles (MAM), quizás para personas que actualicen proyectos de trabajo en sus propios dispositivos, Intune ofrece otra opción además de inscribir y administrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="ab1ce-128">Una suscripción a Intune te permite configurar directivas de MAM con Azure Portal, incluso si los dispositivos de las personas no están inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="ab1ce-129">Para obtener más información, consulta [Introducción a las directivas de protección de aplicaciones.](/mem/intune/apps/app-protection-policy)</span><span class="sxs-lookup"><span data-stu-id="ab1ce-129">For more info, see [App protection policies overview](/mem/intune/apps/app-protection-policy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab1ce-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ab1ce-130">Related topics</span></span>

[<span data-ttu-id="ab1ce-131">Configurar la Seguridad de Movilidad Básica</span><span class="sxs-lookup"><span data-stu-id="ab1ce-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="ab1ce-132">Inscribir el dispositivo móvil con movilidad básica y seguridad</span><span class="sxs-lookup"><span data-stu-id="ab1ce-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="ab1ce-133">Administrar dispositivos inscritos en Administración de dispositivos móviles para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab1ce-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="ab1ce-134">Obtener detalles sobre los dispositivos administrados por Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="ab1ce-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)