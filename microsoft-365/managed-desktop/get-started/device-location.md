---
title: Servicio de ubicación de Windows 10
description: Cómo tener activados los servicios de ubicación de Windows para tus dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929526"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="7a818-104">Servicio de ubicación de Windows 10</span><span class="sxs-lookup"><span data-stu-id="7a818-104">Windows 10 location service</span></span>

<span data-ttu-id="7a818-105">Los dispositivos de Escritorio administrado de Microsoft se registran mediante Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7a818-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="7a818-106">Este proceso nos permite administrarlos con Azure Active Directory y Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="7a818-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="7a818-107">De forma predeterminada, el servicio de ubicación de Windows 10 está deshabilitado cuando se activa un dispositivo por primera vez, a menos que esta característica esté habilitada en la configuración de privacidad durante la "experiencia de inicio de sesión".</span><span class="sxs-lookup"><span data-stu-id="7a818-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="7a818-108">Esta configuración se oculta durante la inscripción de Autopilot en Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="7a818-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="7a818-109">Para obtener más información acerca de cómo se configura Autopilot, vea [First-run experience with Autopilot y la página Enrollment Status .](esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="7a818-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="7a818-110">Por este motivo, los dispositivos de Escritorio administrado de Microsoft no pueden obtener su ubicación de dispositivo, lo que limita la funcionalidad de varias características de Windows, como las zonas horarias.</span><span class="sxs-lookup"><span data-stu-id="7a818-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="7a818-111">Para obtener más información acerca del servicio de ubicación de Windows 10, consulta Servicio de ubicación y [privacidad de Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="7a818-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="7a818-112">No tiene que usar el servicio de ubicación para participar en Microsoft Managed Desktop, pero la experiencia del usuario estará restringida.</span><span class="sxs-lookup"><span data-stu-id="7a818-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="7a818-113">Por ejemplo, los dispositivos no podrán determinar automáticamente la zona horaria en la que se encuentra cuando los usuarios trabajan en una zona horaria diferente.</span><span class="sxs-lookup"><span data-stu-id="7a818-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="7a818-114">Habilitar el servicio de ubicación</span><span class="sxs-lookup"><span data-stu-id="7a818-114">Enable the location service</span></span>

<span data-ttu-id="7a818-115">Puede optar por usar el servicio de ubicación al inscribir dispositivos en el servicio de Escritorio administrado de Microsoft o puede activar o desactivar el servicio después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="7a818-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="7a818-116">Participar durante la inscripción</span><span class="sxs-lookup"><span data-stu-id="7a818-116">Opt in during enrollment</span></span>

<span data-ttu-id="7a818-117">Puede hacer que el servicio de Escritorio administrado de Microsoft habilite el servicio de ubicación.</span><span class="sxs-lookup"><span data-stu-id="7a818-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="7a818-118">Durante la secuencia de inscripción, se te pedirá que selecciones si quieres permitir que el servicio de ubicación de Windows 10 esté habilitado en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7a818-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="7a818-119">Controlar el servicio de ubicación después de la inscripción</span><span class="sxs-lookup"><span data-stu-id="7a818-119">Control the location service after enrollment</span></span>

<span data-ttu-id="7a818-120">Puede tener el servicio de ubicación activado (o desactivado) en cualquier momento enviando una solicitud de soporte [técnico](../working-with-managed-desktop/admin-support.md) a través del [portal de administración](access-admin-portal.md).</span><span class="sxs-lookup"><span data-stu-id="7a818-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="7a818-121">Cómo Microsoft Managed Desktop configura el servicio de ubicación de Windows 10</span><span class="sxs-lookup"><span data-stu-id="7a818-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="7a818-122">Si opta por usar el servicio de ubicación, usamos la configuración mínima necesaria sin afectar a la privacidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a818-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="7a818-123">Para obtener más información, consulta Servicio de ubicación de [Windows 10 y privacidad.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="7a818-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="7a818-124">Microsoft Managed Desktop habilita la configuración **De privacidad de** ubicación en la configuración de **Windows** para Permitir el acceso a la ubicación en **este dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="7a818-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="7a818-125">La interfaz de usuario tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="7a818-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Configuración de ubicación en la configuración de Windows":::

> [!NOTE]
> <span data-ttu-id="7a818-127">Si optas por usar el servicio de ubicación, esto solo se aplica al propio sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="7a818-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="7a818-128">Las aplicaciones no pueden usar servicios de ubicación.</span><span class="sxs-lookup"><span data-stu-id="7a818-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="7a818-129">Cada usuario puede elegir si desea permitir que las aplicaciones accedan a su ubicación.</span><span class="sxs-lookup"><span data-stu-id="7a818-129">Each user can choose whether to allow apps to access their location.</span></span>