---
title: Microsoft Defender para punto de conexión en iOS
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para endpoint en iOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, overview, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3d9dd871edba29ec6119329f98ada990abad6e8d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246421"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="775f9-104">Microsoft Defender para punto de conexión en iOS</span><span class="sxs-lookup"><span data-stu-id="775f9-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="775f9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="775f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="775f9-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="775f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="775f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="775f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="775f9-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="775f9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="775f9-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="775f9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="775f9-110">**Microsoft Defender para Endpoint en iOS** ofrecerá protección contra la suplantación de identidad (phishing) y las conexiones de red no seguras de sitios web, correos electrónicos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="775f9-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="775f9-111">Todas las alertas estarán disponibles a través de un único panel de cristal en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="775f9-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="775f9-112">El portal ofrece a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="775f9-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="775f9-113">Es probable que la ejecución de otros productos de protección de extremos de terceros junto con Defender for Endpoint en iOS cause problemas de rendimiento y errores impredecibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="775f9-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="775f9-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="775f9-114">Pre-requisites</span></span>

<span data-ttu-id="775f9-115">**Para usuarios finales**</span><span class="sxs-lookup"><span data-stu-id="775f9-115">**For End Users**</span></span>

- <span data-ttu-id="775f9-116">Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="775f9-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="775f9-117">Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="775f9-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="775f9-118">Los dispositivos se [inscriben a](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) través de la Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="775f9-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="775f9-119">Esto requiere que al usuario final se le asigne una Microsoft Intune licencia.</span><span class="sxs-lookup"><span data-stu-id="775f9-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="775f9-120">Portal de empresa de Intune la aplicación se puede descargar desde la [Tienda de aplicaciones de Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="775f9-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="775f9-121">Ten en cuenta que Apple no permite que los usuarios redireccionamientos descarguen otras aplicaciones de la tienda de aplicaciones y, por lo tanto, este paso debe realizarlo el usuario antes de incorporarse a la aplicación Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="775f9-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="775f9-122">Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="775f9-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="775f9-123">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="775f9-123">**For Administrators**</span></span>

- <span data-ttu-id="775f9-124">Acceso al portal Centro de seguridad de Microsoft Defender web.</span><span class="sxs-lookup"><span data-stu-id="775f9-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="775f9-125">Microsoft Intune es la única solución de administración de dispositivos móviles (MDM) compatible para implementar Microsoft Defender para endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="775f9-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="775f9-126">Actualmente solo se admiten dispositivos inscritos para aplicar Defender para Endpoint en directivas de cumplimiento de dispositivos relacionados con iOS en Intune.</span><span class="sxs-lookup"><span data-stu-id="775f9-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint on iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="775f9-127">Acceso a [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en su organización.</span><span class="sxs-lookup"><span data-stu-id="775f9-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="775f9-128">**Requisitos de red**</span><span class="sxs-lookup"><span data-stu-id="775f9-128">**Network Requirements**</span></span>
- <span data-ttu-id="775f9-129">Para que Microsoft Defender para endpoint en iOS funcione cuando se conecte a una red, el firewall/proxy tendrá que configurarse para habilitar el acceso a las direcciones URL de servicio de [Endpoint de Microsoft Defender](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="775f9-129">For Microsoft Defender for Endpoint on iOS to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span></span>

<span data-ttu-id="775f9-130">**Requisitos del sistema**</span><span class="sxs-lookup"><span data-stu-id="775f9-130">**System Requirements**</span></span>

- <span data-ttu-id="775f9-131">Dispositivos iOS que ejecutan iOS 11.0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="775f9-131">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="775f9-132">iPad dispositivos se admiten oficialmente a partir de la versión 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="775f9-132">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="775f9-133">El dispositivo está inscrito con la [Portal de empresa de Intune aplicación](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span><span class="sxs-lookup"><span data-stu-id="775f9-133">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="775f9-134">**ATP de Microsoft Defender (Microsoft Defender para Endpoint) en iOS ya está disponible en [Apple App Store](https://aka.ms/mdatpiosappstore).**</span><span class="sxs-lookup"><span data-stu-id="775f9-134">**Microsoft Defender ATP (Microsoft Defender for Endpoint) on iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="775f9-135">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="775f9-135">Installation instructions</span></span>

<span data-ttu-id="775f9-136">La implementación de Microsoft Defender para endpoint en iOS es a través de Microsoft Intune (MDM) y se admiten dispositivos supervisados y no supervisados.</span><span class="sxs-lookup"><span data-stu-id="775f9-136">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="775f9-137">Para obtener más información, vea [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span><span class="sxs-lookup"><span data-stu-id="775f9-137">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="775f9-138">Recursos</span><span class="sxs-lookup"><span data-stu-id="775f9-138">Resources</span></span>

- <span data-ttu-id="775f9-139">Manténgase informado sobre las próximas versiones visitando Novedades de Microsoft Defender para endpoint [en iOS](ios-whatsnew.md) o nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span><span class="sxs-lookup"><span data-stu-id="775f9-139">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="775f9-140">Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través del [portal de SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="775f9-140">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="775f9-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="775f9-141">Next steps</span></span>

- [<span data-ttu-id="775f9-142">Implementar Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="775f9-142">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="775f9-143">Configurar Microsoft Defender para endpoint en características de iOS</span><span class="sxs-lookup"><span data-stu-id="775f9-143">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
