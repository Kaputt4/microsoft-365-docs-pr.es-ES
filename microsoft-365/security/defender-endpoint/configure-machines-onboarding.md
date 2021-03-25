---
title: Obtener dispositivos incorporados a ATP de Microsoft Defender
description: Realiza un seguimiento de la incorporación de dispositivos administrados por Intune a ATP de Microsoft Defender y aumenta la velocidad de incorporación.
keywords: onboard, administración de Intune, MDATP, WDATP, Microsoft Defender, Windows Defender, protección contra amenazas avanzada, administración de configuración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6145acd5e8e2743ff42dce3cf01af0128e8ca225
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166094"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e5f62-104">Obtener dispositivos incorporados a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e5f62-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e5f62-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e5f62-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5f62-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e5f62-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5f62-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5f62-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e5f62-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e5f62-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5f62-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e5f62-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="e5f62-110">Cada dispositivo incorporado agrega un sensor de detección y respuesta de puntos de conexión (EDR) adicional y aumenta la visibilidad sobre la actividad de vulneración en la red.</span><span class="sxs-lookup"><span data-stu-id="e5f62-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="e5f62-111">La incorporación también garantiza que un dispositivo se pueda comprobar si hay componentes vulnerables, así como problemas de configuración de seguridad y puede recibir acciones críticas de corrección durante los ataques.</span><span class="sxs-lookup"><span data-stu-id="e5f62-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="e5f62-112">Antes de poder realizar un seguimiento y administrar la incorporación de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="e5f62-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="e5f62-113">Inscribir los dispositivos en la administración de Intune</span><span class="sxs-lookup"><span data-stu-id="e5f62-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="e5f62-114">Asegúrese de que tiene los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="e5f62-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="e5f62-115">Detectar y realizar un seguimiento de dispositivos sin protección</span><span class="sxs-lookup"><span data-stu-id="e5f62-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="e5f62-116">La **tarjeta** de incorporación proporciona una descripción general de alto nivel de la tasa de incorporación comparando el número de dispositivos Windows 10 que se han incorporado realmente a Defender para Endpoint con el número total de dispositivos Windows 10 administrados por Intune.</span><span class="sxs-lookup"><span data-stu-id="e5f62-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="e5f62-117">![Tarjeta de incorporación de administración de configuración de dispositivos](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="e5f62-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="e5f62-118">*Tarjeta que muestra dispositivos incorporados en comparación con el número total de dispositivos Windows 10 administrados por Intune*</span><span class="sxs-lookup"><span data-stu-id="e5f62-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="e5f62-119">Si usó Security Center Configuration Manager, el script de incorporación u otros métodos de incorporación que no usan perfiles de Intune, es posible que encuentre discrepancias de datos.</span><span class="sxs-lookup"><span data-stu-id="e5f62-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="e5f62-120">Para resolver estas discrepancias, crea un perfil de configuración de Intune correspondiente para la incorporación de Defender for Endpoint y asigna ese perfil a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e5f62-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="e5f62-121">Incorporación de más dispositivos con perfiles de Intune</span><span class="sxs-lookup"><span data-stu-id="e5f62-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="e5f62-122">Defender for Endpoint proporciona varias opciones convenientes para [incorporar dispositivos Windows 10.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e5f62-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="e5f62-123">Sin embargo, en el caso de los dispositivos administrados por Intune, puede aprovechar los perfiles de Intune para implementar cómodamente el sensor Defender for Endpoint para seleccionar dispositivos, incorporando estos dispositivos de forma eficaz al servicio.</span><span class="sxs-lookup"><span data-stu-id="e5f62-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="e5f62-124">En la **tarjeta incorporación,** selecciona **Incorporar más dispositivos** para crear y asignar un perfil en Intune.</span><span class="sxs-lookup"><span data-stu-id="e5f62-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="e5f62-125">El vínculo te lleva a la página de cumplimiento del dispositivo en Intune, que proporciona una introducción similar al estado de incorporación.</span><span class="sxs-lookup"><span data-stu-id="e5f62-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="e5f62-126">![Página de cumplimiento de dispositivos ATP de Microsoft Defender en la administración de dispositivos de Intune](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="e5f62-126">![Microsoft Defender ATP device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="e5f62-127">*Página de cumplimiento de dispositivos ATP de Microsoft Defender en la administración de dispositivos de Intune*</span><span class="sxs-lookup"><span data-stu-id="e5f62-127">*Microsoft Defender ATP device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="e5f62-128">Como alternativa, puede navegar a la página de cumplimiento de incorporación de Defender for Endpoint en [Microsoft Azure Portal](https://portal.azure.com/) desde Todos los servicios > Intune > Cumplimiento de dispositivos > ATP de Microsoft **Defender.**</span><span class="sxs-lookup"><span data-stu-id="e5f62-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="e5f62-129">Si quieres ver los datos de dispositivo más actualizados, haz clic en Lista de **dispositivos sin sensor ATP**.</span><span class="sxs-lookup"><span data-stu-id="e5f62-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="e5f62-130">Desde la página de cumplimiento del dispositivo, crea un perfil de configuración específicamente para la implementación del sensor Defender for Endpoint y asigna ese perfil a los dispositivos que quieras incorporar.</span><span class="sxs-lookup"><span data-stu-id="e5f62-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="e5f62-131">Para ello, puede:</span><span class="sxs-lookup"><span data-stu-id="e5f62-131">To do this, you can either:</span></span>

- <span data-ttu-id="e5f62-132">Selecciona **Crear un perfil de configuración de dispositivo para configurar el sensor DE ATP** para empezar con un perfil de configuración de dispositivo predefinido.</span><span class="sxs-lookup"><span data-stu-id="e5f62-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="e5f62-133">Crea el perfil de configuración del dispositivo desde cero.</span><span class="sxs-lookup"><span data-stu-id="e5f62-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="e5f62-134">Para obtener más información, [lea acerca del uso de perfiles](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)de configuración de dispositivos de Intune para incorporar dispositivos a Defender para endpoint .</span><span class="sxs-lookup"><span data-stu-id="e5f62-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="e5f62-135">¿Desea experimentar ATP de Microsoft Defender?</span><span class="sxs-lookup"><span data-stu-id="e5f62-135">Want to experience Microsoft Defender ATP?</span></span> [<span data-ttu-id="e5f62-136">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e5f62-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="e5f62-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e5f62-137">Related topics</span></span>
- [<span data-ttu-id="e5f62-138">Asegúrese de que los dispositivos estén configurados correctamente</span><span class="sxs-lookup"><span data-stu-id="e5f62-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="e5f62-139">Aumentar el cumplimiento de la línea base de seguridad de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e5f62-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="e5f62-140">Optimizar la implementación y detecciones de reglas ASR</span><span class="sxs-lookup"><span data-stu-id="e5f62-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
