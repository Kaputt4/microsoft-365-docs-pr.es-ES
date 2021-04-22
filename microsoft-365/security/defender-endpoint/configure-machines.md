---
title: Asegurarse de que los dispositivos estén configurados de manera adecuada
description: Configure correctamente los dispositivos para aumentar la resistencia general frente a las amenazas y mejorar su capacidad para detectar y responder a los ataques.
keywords: onboard, administración de Intune, Microsoft Defender para Endpoint, Microsoft Defender, Windows Defender, reducción de superficie de ataque, ASR, línea base de seguridad
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3fd58ee17b2cb86c0bcc858b9b0fd57c12ac501e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932816"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="2bc04-104">Asegurarse de que los dispositivos estén configurados de manera adecuada</span><span class="sxs-lookup"><span data-stu-id="2bc04-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bc04-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2bc04-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bc04-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2bc04-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bc04-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bc04-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2bc04-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2bc04-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2bc04-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2bc04-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="2bc04-110">Con dispositivos configurados correctamente, puedes aumentar la resistencia general frente a amenazas y mejorar tu capacidad para detectar y responder a los ataques.</span><span class="sxs-lookup"><span data-stu-id="2bc04-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="2bc04-111">La administración de la configuración de seguridad ayuda a garantizar que los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="2bc04-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="2bc04-112">Incorporación a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc04-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2bc04-113">Cumplir o superar la configuración de línea base de seguridad de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc04-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="2bc04-114">Tener mitigaciones de superficie de ataques estratégicos en su lugar</span><span class="sxs-lookup"><span data-stu-id="2bc04-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="2bc04-115">Haga **clic en Administración de** configuración en el menú de navegación para abrir la página Administración de configuración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2bc04-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="2bc04-116">![Página de administración de configuración de seguridad](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="2bc04-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="2bc04-117">*Página de administración de configuración de dispositivos*</span><span class="sxs-lookup"><span data-stu-id="2bc04-117">*Device configuration management page*</span></span>

<span data-ttu-id="2bc04-118">Puedes realizar un seguimiento del estado de configuración en un nivel organizativo y tomar medidas rápidamente en respuesta a una cobertura de incorporación deficiente, problemas de cumplimiento y mitigaciones de superficies de ataque mal optimizadas a través de vínculos directos y profundos a páginas de administración de dispositivos en Microsoft Intune y el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2bc04-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="2bc04-119">Al hacerlo, se beneficia de:</span><span class="sxs-lookup"><span data-stu-id="2bc04-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="2bc04-120">Visibilidad completa de los eventos en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="2bc04-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="2bc04-121">Inteligencia de amenazas sólida y tecnologías de aprendizaje de dispositivos eficaces para procesar eventos sin procesar e identificar la actividad de vulneración y los indicadores de amenazas</span><span class="sxs-lookup"><span data-stu-id="2bc04-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="2bc04-122">Una pila completa de características de seguridad configuradas para detener eficazmente la instalación de implantes malintencionados, el secuestro de archivos y procesos del sistema, la exfiltración de datos y otras actividades de amenazas</span><span class="sxs-lookup"><span data-stu-id="2bc04-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="2bc04-123">Mitigaciones optimizadas de superficie de ataque, maximizando las defensas estratégicas contra la actividad de amenazas al mismo tiempo que minimiza el impacto en la productividad</span><span class="sxs-lookup"><span data-stu-id="2bc04-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="2bc04-124">Inscribir dispositivos en la administración de Intune</span><span class="sxs-lookup"><span data-stu-id="2bc04-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="2bc04-125">La administración de configuración de dispositivos funciona estrechamente con la administración de dispositivos de Intune para establecer el inventario de los dispositivos de la organización y la configuración de seguridad de línea base.</span><span class="sxs-lookup"><span data-stu-id="2bc04-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="2bc04-126">Podrás realizar un seguimiento y administrar problemas de configuración en dispositivos Windows 10 administrados por Intune.</span><span class="sxs-lookup"><span data-stu-id="2bc04-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="2bc04-127">Antes de garantizar que los dispositivos estén configurados correctamente, inscríbalos en la administración de Intune.</span><span class="sxs-lookup"><span data-stu-id="2bc04-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="2bc04-128">La inscripción de Intune es sólida y tiene varias opciones de inscripción para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2bc04-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="2bc04-129">Para obtener más información acerca de las opciones de inscripción de Intune, lee sobre [cómo configurar la inscripción para dispositivos Windows](https://docs.microsoft.com/intune/windows-enroll).</span><span class="sxs-lookup"><span data-stu-id="2bc04-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](https://docs.microsoft.com/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="2bc04-130">Para inscribir dispositivos Windows en Intune, los administradores deben tener ya asignadas licencias.</span><span class="sxs-lookup"><span data-stu-id="2bc04-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="2bc04-131">[Lea acerca de la asignación de licencias para la inscripción de dispositivos.](https://docs.microsoft.com/intune/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="2bc04-131">[Read about assigning licenses for device enrollment](https://docs.microsoft.com/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="2bc04-132">Para optimizar la administración de dispositivos a través de Intune, [conecte Intune a Defender para endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span><span class="sxs-lookup"><span data-stu-id="2bc04-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="2bc04-133">Obtener los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="2bc04-133">Obtain required permissions</span></span>
<span data-ttu-id="2bc04-134">De forma predeterminada, solo los usuarios a los que se haya asignado el rol Administrador global o administrador de servicio de Intune en Azure AD pueden administrar y asignar los perfiles de configuración de dispositivos necesarios para incorporar dispositivos e implementar la línea base de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2bc04-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="2bc04-135">Si se le han asignado otros roles, asegúrese de que tiene los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="2bc04-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="2bc04-136">Permisos completos para configuraciones de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2bc04-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="2bc04-137">Permisos completos para las líneas base de seguridad</span><span class="sxs-lookup"><span data-stu-id="2bc04-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="2bc04-138">Permisos de lectura para directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2bc04-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="2bc04-139">Permisos de lectura para la organización</span><span class="sxs-lookup"><span data-stu-id="2bc04-139">Read permissions to the organization</span></span>

<span data-ttu-id="2bc04-140">![Permisos necesarios en Intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="2bc04-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="2bc04-141">*Permisos de configuración de dispositivos en Intune*</span><span class="sxs-lookup"><span data-stu-id="2bc04-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="2bc04-142">Para obtener más información sobre la asignación de permisos en Intune, [lea acerca de cómo crear roles personalizados](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span><span class="sxs-lookup"><span data-stu-id="2bc04-142">To learn more about assigning permissions on Intune, [read about creating custom roles](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2bc04-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2bc04-143">In this section</span></span>
<span data-ttu-id="2bc04-144">Tema</span><span class="sxs-lookup"><span data-stu-id="2bc04-144">Topic</span></span> | <span data-ttu-id="2bc04-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bc04-145">Description</span></span>
:---|:---
[<span data-ttu-id="2bc04-146">Obtener dispositivos incorporados a Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc04-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="2bc04-147">Realice un seguimiento del estado de incorporación de dispositivos administrados por Intune e incorpore más dispositivos a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="2bc04-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="2bc04-148">Aumentar el cumplimiento de la línea base de seguridad de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc04-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="2bc04-149">Realizar un seguimiento del cumplimiento de línea base y el incumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2bc04-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="2bc04-150">Implemente la línea base de seguridad en más dispositivos administrados por Intune.</span><span class="sxs-lookup"><span data-stu-id="2bc04-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="2bc04-151">Optimizar la implementación y detecciones de reglas ASR</span><span class="sxs-lookup"><span data-stu-id="2bc04-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="2bc04-152">Revise la implementación de reglas y ajuste las detecciones con herramientas de análisis de impacto en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2bc04-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="2bc04-153">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2bc04-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2bc04-154">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2bc04-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
