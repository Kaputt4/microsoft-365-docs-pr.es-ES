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
ms.openlocfilehash: 0b98e48b128eeaea0e0dd5cb9613ece95e991861
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982751"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="bc6ad-104">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bc6ad-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="bc6ad-105">Microsoft 365 Enterprise incluye Windows 10 Enterprise, que proporciona las herramientas para hacer más y mantener la seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-105">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="bc6ad-106">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="bc6ad-106">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="bc6ad-107">**Está integrado para simplificar** : aproveche la potencia de la nube para ayudar a reducir la complejidad de la administración del entorno de dispositivos de ti moderno actual, independientemente del tamaño.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="bc6ad-108">**Tiene seguridad inteligente** , que es la versión más segura de Windows, con capacidades de seguridad inteligentes diseñadas para trabajar conjuntamente para proteger mejor su organización.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="bc6ad-109">**Permite** la creatividad y el trabajo en equipo, lo que desbloquea la creatividad y el trabajo en equipo para proporcionar la experiencia más productiva que los usuarios y el equipo de ti les encantarán.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="bc6ad-110">Necesitará comprender las distintas formas en las que puede implementar el sistema operativo Windows 10 y elegir el correcto para su organización.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-110">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="bc6ad-111">En función de su suscripción de Microsoft 365 Enterprise, también hay características de seguridad y servicios de Windows 10 que tendrá que configurar para sacar el máximo partido de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-111">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="bc6ad-112">Para implementar Windows 10 Enterprise y Office 365 ProPlus juntos y cambiar a un [escritorio moderno](https://www.microsoft.com/microsoft-365/modern-desktop), consulte el [Centro de implementación de escritorio moderno](http://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="bc6ad-112">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="bc6ad-113">Implementación de Windows 10</span><span class="sxs-lookup"><span data-stu-id="bc6ad-113">Windows 10 deployment</span></span>

<span data-ttu-id="bc6ad-114">Hay varias formas en las que puede implementar Windows 10 Enterprise en su organización.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-114">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="bc6ad-115">Nos centraremos en cómo puede configurar e implementar una imagen de Windows 10 Enterprise a través de estos escenarios de implementación modernos.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-115">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="bc6ad-116">Escenario de implementación</span><span class="sxs-lookup"><span data-stu-id="bc6ad-116">Deployment scenario</span></span> | <span data-ttu-id="bc6ad-117">Cuándo usarlo</span><span class="sxs-lookup"><span data-stu-id="bc6ad-117">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="bc6ad-118">Uso de System Center Configuration Manager como actualización local</span><span class="sxs-lookup"><span data-stu-id="bc6ad-118">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="bc6ad-119">Seleccione esta opción si necesita actualizar equipos con Windows 7 o Windows 8,1 a la <a href="https://aka.ms/windows-10-release-information" target="_blank">versión actual</a> de Windows 10 Enterprise y los equipos están administrados actualmente con <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (rama actual)</a>.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-119">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="bc6ad-120">Uso de Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="bc6ad-120">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="bc6ad-121">Seleccione esta opción si va a configurar nuevos equipos con Windows que tienen instalado Windows 10 Enterprise, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-121">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="bc6ad-122">Los usuarios finales iniciarán la instalación con la configuración deseada; para ello, escriba sus credenciales de cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-122">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="bc6ad-123">Si estos escenarios de implementación no se ajustan a las necesidades de su organización, puede obtener información sobre otros escenarios y comprender las capacidades y limitaciones de cada uno de los [escenarios de implementación de Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="bc6ad-123">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="bc6ad-124">También puede <a href="https://aka.ms/planforwin10deployment" target="_blank">planear la implementación de Windows 10</a> por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-124">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="bc6ad-125">Puede obtener más información sobre Windows 10 con estos artículos:</span><span class="sxs-lookup"><span data-stu-id="bc6ad-125">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="bc6ad-126">Página del producto Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bc6ad-126">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="bc6ad-127">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bc6ad-127">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="bc6ad-128">Implementar y actualizar Windows 10</span><span class="sxs-lookup"><span data-stu-id="bc6ad-128">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="bc6ad-129">Servicios y características adicionales</span><span class="sxs-lookup"><span data-stu-id="bc6ad-129">Additional services and features</span></span>
<span data-ttu-id="bc6ad-130">Como parte de la implementación de Windows 10 Enterprise, puede agregar estos servicios y características adicionales.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-130">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="bc6ad-131">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="bc6ad-131">Windows Analytics</span></span>

<span data-ttu-id="bc6ad-132">Windows usa datos de diagnóstico para proporcionar información enriquecida y que requiere acción para ayudarle a obtener información detallada sobre la eficacia operativa y el estado de los dispositivos con Windows 10 en su entorno.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-132">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="bc6ad-133">Preparación para la actualización: la preparación para la actualización le ayudará a pasar a Windows 10 y mantenerse al día con las nuevas actualizaciones de características de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-133">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="bc6ad-134">Cumplimiento de la actualización: el cumplimiento de la actualización se dirige al administrador de ti que desea obtener una vista holística de todos sus dispositivos con Windows 10, sin requisitos de infraestructura adicionales.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-134">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="bc6ad-135">Estado del dispositivo: puede usar el estado del dispositivo para detectar y corregir de forma proactiva los problemas de impacto del usuario final.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-135">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="bc6ad-136">Consulte [información general de Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-136">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="bc6ad-137">Seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="bc6ad-137">Windows security</span></span>

<span data-ttu-id="bc6ad-138">Windows 10 proporciona características para ayudar a proteger contra las amenazas, ayudar a proteger los dispositivos y ayudar con el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-138">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="bc6ad-139">Con Windows 10, obtendrás características de seguridad críticas que protegen el dispositivo desde el principio.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-139">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="bc6ad-140">Microsoft 365 E3 agrega características de seguridad como Windows Hello para empresas, el control de aplicaciones de Windows Defender y Windows Information Protection.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-140">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="bc6ad-141">Con Microsoft 365 E5, obtiene toda la protección de las características de seguridad basadas en la nube de Microsoft 365 E3 Security Plus y de la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="bc6ad-141">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="bc6ad-142">Para obtener más información sobre las características de seguridad que se obtienen con Windows 10 Enterprise y obtener instrucciones sobre cómo implementar, administrar, configurar y solucionar problemas de tres características clave de ecurity, vea [STEP 5: deploy Windows 10 Enterprise Security Features](windows10-enable-security-features.md).</span><span class="sxs-lookup"><span data-stu-id="bc6ad-142">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="bc6ad-143">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bc6ad-143">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bc6ad-144">Obtenga una ojeada dentro de Microsoft y obtenga información sobre cómo la compañía [implementó Windows 10 Enterprise y está usando la autenticación segura, Intune y ATP de Microsoft defender](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="bc6ad-144">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="bc6ad-145">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bc6ad-145">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bc6ad-146">Vea cómo contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó Windows 10 Enterprise](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="bc6ad-146">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="bc6ad-147">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="bc6ad-147">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="bc6ad-148">Preparar la organización para Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bc6ad-148">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
