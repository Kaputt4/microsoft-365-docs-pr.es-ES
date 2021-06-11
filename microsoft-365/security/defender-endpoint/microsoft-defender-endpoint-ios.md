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
ms.openlocfilehash: b4c2d586cd23a346db1bcebf891689ff648b639b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844711"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="07cfc-104">Microsoft Defender para punto de conexión en iOS</span><span class="sxs-lookup"><span data-stu-id="07cfc-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07cfc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="07cfc-105">**Applies to:**</span></span>
- [<span data-ttu-id="07cfc-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="07cfc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="07cfc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07cfc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="07cfc-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="07cfc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="07cfc-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="07cfc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="07cfc-110">**Microsoft Defender para Endpoint en iOS** ofrecerá protección contra la suplantación de identidad (phishing) y las conexiones de red no seguras de sitios web, correos electrónicos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="07cfc-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="07cfc-111">Todas las alertas estarán disponibles a través de un único panel de cristal en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="07cfc-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="07cfc-112">El portal ofrece a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="07cfc-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="07cfc-113">Es probable que la ejecución de otros productos de protección de extremos de terceros junto con Defender for Endpoint en iOS cause problemas de rendimiento y errores impredecibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="07cfc-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="07cfc-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="07cfc-114">Pre-requisites</span></span>

<span data-ttu-id="07cfc-115">**Para usuarios finales**</span><span class="sxs-lookup"><span data-stu-id="07cfc-115">**For End Users**</span></span>

- <span data-ttu-id="07cfc-116">Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07cfc-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="07cfc-117">Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="07cfc-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="07cfc-118">Los dispositivos se [inscriben a](/mem/intune/user-help/enroll-your-device-in-intune-ios) través de la Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="07cfc-118">Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="07cfc-119">Esto requiere que al usuario final se le asigne una Microsoft Intune licencia.</span><span class="sxs-lookup"><span data-stu-id="07cfc-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="07cfc-120">Portal de empresa de Intune la aplicación se puede descargar desde la [Tienda de aplicaciones de Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="07cfc-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="07cfc-121">Ten en cuenta que Apple no permite que los usuarios redireccionamientos descarguen otras aplicaciones de la tienda de aplicaciones y, por lo tanto, este paso debe realizarlo el usuario antes de incorporarse a la aplicación Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="07cfc-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="07cfc-122">Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="07cfc-122">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="07cfc-123">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="07cfc-123">**For Administrators**</span></span>

- <span data-ttu-id="07cfc-124">Acceso al portal Centro de seguridad de Microsoft Defender web.</span><span class="sxs-lookup"><span data-stu-id="07cfc-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="07cfc-125">Microsoft Intune es la única solución de administración unificada de puntos de conexión (UEM) compatible para implementar Microsoft Defender para endpoints y aplicar directivas de cumplimiento de dispositivos relacionados con Defender for Endpoint en Intune.</span><span class="sxs-lookup"><span data-stu-id="07cfc-125">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

- <span data-ttu-id="07cfc-126">Acceso a [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en su organización.</span><span class="sxs-lookup"><span data-stu-id="07cfc-126">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="07cfc-127">**Requisitos del sistema**</span><span class="sxs-lookup"><span data-stu-id="07cfc-127">**System Requirements**</span></span>

- <span data-ttu-id="07cfc-128">Dispositivos iOS que ejecutan iOS 11.0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="07cfc-128">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="07cfc-129">iPad dispositivos se admiten oficialmente a partir de la versión 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="07cfc-129">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="07cfc-130">El dispositivo está inscrito con la [Portal de empresa de Intune aplicación](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span><span class="sxs-lookup"><span data-stu-id="07cfc-130">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="07cfc-131">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="07cfc-131">Installation instructions</span></span>

<span data-ttu-id="07cfc-132">La implementación de Microsoft Defender para endpoint en iOS es a través de Microsoft Intune (MDM) y se admiten dispositivos supervisados y no supervisados.</span><span class="sxs-lookup"><span data-stu-id="07cfc-132">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="07cfc-133">Los usuarios finales también pueden instalar directamente la aplicación desde la [Tienda de aplicaciones de Apple](https://aka.ms/mdatpiosappstore).</span><span class="sxs-lookup"><span data-stu-id="07cfc-133">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="07cfc-134">Para obtener más información, vea [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span><span class="sxs-lookup"><span data-stu-id="07cfc-134">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="07cfc-135">Recursos</span><span class="sxs-lookup"><span data-stu-id="07cfc-135">Resources</span></span>

- <span data-ttu-id="07cfc-136">Manténgase informado sobre las próximas versiones visitando Novedades de Microsoft Defender para endpoint [en iOS](ios-whatsnew.md) o nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span><span class="sxs-lookup"><span data-stu-id="07cfc-136">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="07cfc-137">Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través del [portal de SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="07cfc-137">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="07cfc-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="07cfc-138">Next steps</span></span>

- [<span data-ttu-id="07cfc-139">Implementar Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="07cfc-139">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="07cfc-140">Configurar Microsoft Defender para endpoint en características de iOS</span><span class="sxs-lookup"><span data-stu-id="07cfc-140">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
