---
title: Infraestructura de Windows 10 Enterprise para Microsoft 365 Enterprise
description: Proporciona instrucciones de alto nivel sobre los pasos necesarios para implementar Windows 10 Enterprise en equipos PC como parte de Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, Windows 10 Enterprise, implementación
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 3cdb5fd6644d76a843e109ff53f73eb9ec4638f8
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627544"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="83bdf-104">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83bdf-104">Phase 3: Windows 10 Enterprise</span></span>

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="83bdf-106">Microsoft 365 Enterprise incluye Windows 10 Enterprise, que proporciona las herramientas para hacer más y mantener la seguridad.</span><span class="sxs-lookup"><span data-stu-id="83bdf-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="83bdf-107">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="83bdf-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="83bdf-108">**Está integrado para simplificar** : aproveche la potencia de la nube para ayudar a reducir la complejidad de la administración del entorno de dispositivos de ti moderno actual, independientemente del tamaño.</span><span class="sxs-lookup"><span data-stu-id="83bdf-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="83bdf-109">**Tiene seguridad inteligente** , que es la versión más segura de Windows, con capacidades de seguridad inteligentes diseñadas para trabajar conjuntamente para proteger mejor su organización.</span><span class="sxs-lookup"><span data-stu-id="83bdf-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="83bdf-110">**Permite** la creatividad y el trabajo en equipo, lo que desbloquea la creatividad y el trabajo en equipo para proporcionar la experiencia más productiva que los usuarios y el equipo de ti les encantarán.</span><span class="sxs-lookup"><span data-stu-id="83bdf-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="83bdf-111">Necesitará comprender las distintas formas en las que puede implementar el sistema operativo Windows 10 y elegir el correcto para su organización.</span><span class="sxs-lookup"><span data-stu-id="83bdf-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="83bdf-112">En función de su suscripción de Microsoft 365 Enterprise, también hay características de seguridad y servicios de Windows 10 que tendrá que configurar para sacar el máximo partido de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="83bdf-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="83bdf-113">Para implementar Windows 10 Enterprise y Office 365 ProPlus juntos y cambiar a un [escritorio moderno](https://www.microsoft.com/microsoft-365/modern-desktop), consulte el [Centro de implementación de escritorio moderno](https://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="83bdf-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="83bdf-114">Implementación de Windows 10</span><span class="sxs-lookup"><span data-stu-id="83bdf-114">Windows 10 deployment</span></span>

<span data-ttu-id="83bdf-115">Hay varias formas en las que puede implementar Windows 10 Enterprise en su organización.</span><span class="sxs-lookup"><span data-stu-id="83bdf-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="83bdf-116">Nos centraremos en cómo puede configurar e implementar una imagen de Windows 10 Enterprise a través de estos escenarios de implementación modernos.</span><span class="sxs-lookup"><span data-stu-id="83bdf-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="83bdf-117">Escenario de implementación</span><span class="sxs-lookup"><span data-stu-id="83bdf-117">Deployment scenario</span></span> | <span data-ttu-id="83bdf-118">Cuándo usarlo</span><span class="sxs-lookup"><span data-stu-id="83bdf-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="83bdf-119">Uso de Microsoft Endpoint Configuration Manager como actualización local</span><span class="sxs-lookup"><span data-stu-id="83bdf-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="83bdf-120">Seleccione esta opción si necesita actualizar equipos con Windows 7 o Windows 8,1 a la <a href="https://aka.ms/windows-10-release-information" target="_blank">versión actual</a> de Windows 10 Enterprise y los equipos están administrados actualmente con <a href="https://aka.ms/introtosccm" target="_blank">Configuration Manager (rama actual)</a>.</span><span class="sxs-lookup"><span data-stu-id="83bdf-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="83bdf-121">Uso de Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="83bdf-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="83bdf-122">Seleccione esta opción si va a configurar nuevos equipos con Windows que tienen instalado Windows 10 Enterprise, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="83bdf-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="83bdf-123">Los usuarios finales iniciarán la instalación con la configuración deseada; para ello, escriba sus credenciales de cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="83bdf-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="83bdf-124">Si estos escenarios de implementación no se ajustan a las necesidades de su organización, puede obtener información sobre otros escenarios y comprender las capacidades y limitaciones de cada uno de los [escenarios de implementación de Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="83bdf-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="83bdf-125">También puede <a href="https://aka.ms/planforwin10deployment" target="_blank">planear la implementación de Windows 10</a> por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="83bdf-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="83bdf-126">Puede obtener más información sobre Windows 10 con estos artículos:</span><span class="sxs-lookup"><span data-stu-id="83bdf-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="83bdf-127">Página del producto Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83bdf-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="83bdf-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="83bdf-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="83bdf-129">Implementar y actualizar Windows 10</span><span class="sxs-lookup"><span data-stu-id="83bdf-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="83bdf-130">Servicios y características adicionales</span><span class="sxs-lookup"><span data-stu-id="83bdf-130">Additional services and features</span></span>
<span data-ttu-id="83bdf-131">Como parte de la implementación de Windows 10 Enterprise, puede agregar estos servicios y características adicionales.</span><span class="sxs-lookup"><span data-stu-id="83bdf-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="83bdf-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="83bdf-132">Windows Analytics</span></span>

<span data-ttu-id="83bdf-133">Windows usa datos de diagnóstico para proporcionar información enriquecida y que requiere acción para ayudarle a obtener información detallada sobre la eficacia operativa y el estado de los dispositivos con Windows 10 en su entorno.</span><span class="sxs-lookup"><span data-stu-id="83bdf-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="83bdf-134">Preparación para la actualización: la preparación para la actualización le ayudará a pasar a Windows 10 y mantenerse al día con las nuevas actualizaciones de características de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="83bdf-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="83bdf-135">Cumplimiento de la actualización: el cumplimiento de la actualización se dirige al administrador de ti que desea obtener una vista holística de todos sus dispositivos con Windows 10, sin requisitos de infraestructura adicionales.</span><span class="sxs-lookup"><span data-stu-id="83bdf-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="83bdf-136">Estado del dispositivo: puede usar el estado del dispositivo para detectar y corregir de forma proactiva los problemas de impacto del usuario final.</span><span class="sxs-lookup"><span data-stu-id="83bdf-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="83bdf-137">Consulte [información general de Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="83bdf-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="83bdf-138">Seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="83bdf-138">Windows security</span></span>

<span data-ttu-id="83bdf-139">Windows 10 proporciona características para ayudar a proteger contra las amenazas, ayudar a proteger los dispositivos y ayudar con el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="83bdf-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="83bdf-140">Con Windows 10, obtendrás características de seguridad críticas que protegen el dispositivo desde el principio.</span><span class="sxs-lookup"><span data-stu-id="83bdf-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="83bdf-141">Microsoft 365 E3 agrega características de seguridad como Windows Hello para empresas, el control de aplicaciones de Windows Defender y Windows Information Protection.</span><span class="sxs-lookup"><span data-stu-id="83bdf-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="83bdf-142">Con Microsoft 365 E5, obtiene toda la protección de las características de seguridad basadas en la nube de Microsoft 365 E3 Security Plus y de la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="83bdf-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="83bdf-143">Para obtener más información sobre las características de seguridad que se obtienen con Windows 10 Enterprise y obtener instrucciones sobre cómo implementar, administrar, configurar y solucionar problemas de tres características clave de ecurity, vea [STEP 5: deploy Windows 10 Enterprise Security Features](windows10-enable-security-features.md).</span><span class="sxs-lookup"><span data-stu-id="83bdf-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="83bdf-144">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83bdf-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="83bdf-145">Obtenga una ojeada dentro de Microsoft y obtenga información sobre cómo la compañía [implementó Windows 10 Enterprise y está usando la autenticación segura, Intune y ATP de Microsoft defender](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="83bdf-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="83bdf-146">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83bdf-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="83bdf-147">Vea cómo contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó Windows 10 Enterprise](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="83bdf-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="83bdf-149">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="83bdf-149">Next step</span></span>

|||
|:-------|:-----|
|![Paso 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="83bdf-151">Preparar la organización para Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83bdf-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
