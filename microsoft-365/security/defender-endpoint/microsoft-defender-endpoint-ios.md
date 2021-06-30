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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194858"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="b000b-104">Microsoft Defender para punto de conexión en iOS</span><span class="sxs-lookup"><span data-stu-id="b000b-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b000b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b000b-105">**Applies to:**</span></span>
- [<span data-ttu-id="b000b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b000b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b000b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b000b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b000b-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b000b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b000b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b000b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b000b-110">**Microsoft Defender para Endpoint en iOS** ofrece protección contra la suplantación de identidad (phishing) y las conexiones de red no seguras de sitios web, correos electrónicos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b000b-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="b000b-111">Todas las alertas estarán disponibles a través de un único panel de cristal en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b000b-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="b000b-112">El portal ofrece a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="b000b-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="b000b-113">Es probable que la ejecución de otros productos de protección de extremos de terceros junto con Defender for Endpoint en iOS cause problemas de rendimiento y errores impredecibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="b000b-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="b000b-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b000b-114">Pre-requisites</span></span>

<span data-ttu-id="b000b-115">**Para usuarios finales**</span><span class="sxs-lookup"><span data-stu-id="b000b-115">**For End Users**</span></span>

- <span data-ttu-id="b000b-116">Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b000b-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="b000b-117">Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="b000b-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="b000b-118">**Para dispositivos inscritos:** los [](/mem/intune/user-help/enroll-your-device-in-intune-ios) dispositivos se inscriben a través de la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="b000b-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="b000b-119">Esto requiere que al usuario final se le asigne una Microsoft Intune licencia.</span><span class="sxs-lookup"><span data-stu-id="b000b-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="b000b-120">Portal de empresa de Intune la aplicación se puede descargar desde la [Tienda de aplicaciones de Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="b000b-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="b000b-121">Ten en cuenta que Apple no permite que los usuarios redireccionamientos descarguen otras aplicaciones de la tienda de aplicaciones y, por lo tanto, este paso debe realizarlo el usuario antes de incorporarse a la aplicación Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="b000b-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="b000b-122">**Para dispositivos no** inscritos: los dispositivos están registrados con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b000b-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="b000b-123">Esto requiere que el usuario final haya iniciado sesión [a través Microsoft Authenticator aplicación](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="b000b-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="b000b-124">Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="b000b-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="b000b-125">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="b000b-125">**For Administrators**</span></span>

- <span data-ttu-id="b000b-126">Acceso al portal Centro de seguridad de Microsoft Defender web.</span><span class="sxs-lookup"><span data-stu-id="b000b-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="b000b-127">Acceso a [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en su organización.</span><span class="sxs-lookup"><span data-stu-id="b000b-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b000b-128">Microsoft Intune es la única solución de administración unificada de puntos de conexión (UEM) compatible para implementar Microsoft Defender para endpoints y aplicar directivas de cumplimiento de dispositivos relacionados con Defender for Endpoint en Intune.</span><span class="sxs-lookup"><span data-stu-id="b000b-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="b000b-129">**Requisitos del sistema**</span><span class="sxs-lookup"><span data-stu-id="b000b-129">**System Requirements**</span></span>

- <span data-ttu-id="b000b-130">Dispositivo iOS que ejecuta iOS 11.0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="b000b-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="b000b-131">iPad dispositivos se admiten oficialmente a partir de la versión 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="b000b-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="b000b-132">El dispositivo se inscribe con la [aplicación Portal de empresa de Intune o](https://apps.apple.com/us/app/intune-company-portal/id719171358) se registra con Azure Active Directory a través de [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="b000b-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="b000b-133">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="b000b-133">Installation instructions</span></span>

<span data-ttu-id="b000b-134">La implementación de Microsoft Defender para endpoint en iOS se puede realizar a través de Microsoft Endpoint Manager (MEM) y se admiten dispositivos supervisados y no supervisados.</span><span class="sxs-lookup"><span data-stu-id="b000b-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="b000b-135">Los usuarios finales también pueden instalar directamente la aplicación desde la [Tienda de aplicaciones de Apple](https://aka.ms/mdatpiosappstore).</span><span class="sxs-lookup"><span data-stu-id="b000b-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="b000b-136">Para obtener más información, vea [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span><span class="sxs-lookup"><span data-stu-id="b000b-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="b000b-137">Recursos</span><span class="sxs-lookup"><span data-stu-id="b000b-137">Resources</span></span>

- <span data-ttu-id="b000b-138">Manténgase informado sobre las próximas versiones visitando Novedades de Microsoft Defender para endpoint [en iOS](ios-whatsnew.md) o nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span><span class="sxs-lookup"><span data-stu-id="b000b-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="b000b-139">Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través del [portal de SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b000b-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b000b-140">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="b000b-140">Next steps</span></span>

- [<span data-ttu-id="b000b-141">Implementar Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="b000b-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="b000b-142">Configurar Microsoft Defender para endpoint en características de iOS</span><span class="sxs-lookup"><span data-stu-id="b000b-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
