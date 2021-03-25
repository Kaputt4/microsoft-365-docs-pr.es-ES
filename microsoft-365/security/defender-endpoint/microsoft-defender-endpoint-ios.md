---
title: Introducción a ATP para iOS de Microsoft Defender
ms.reviewer: ''
description: Describe cómo instalar y usar ATP de Microsoft Defender para iOS
keywords: microsoft, defender, atp, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 6e5aae9dcb361caf9133c1270a16711fc43033bb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074323"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="2e5cf-104">Microsoft Defender para endpoint para iOS</span><span class="sxs-lookup"><span data-stu-id="2e5cf-104">Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2e5cf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2e5cf-105">**Applies to:**</span></span>
- [<span data-ttu-id="2e5cf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2e5cf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2e5cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e5cf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2e5cf-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2e5cf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2e5cf-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2e5cf-110">**Microsoft Defender para Endpoint para iOS** ofrecerá protección contra la suplantación de identidad (phishing) y las conexiones de red no seguras de sitios web, correos electrónicos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-110">**Microsoft Defender for Endpoint for iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="2e5cf-111">Todas las alertas estarán disponibles a través de un único panel de cristal en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="2e5cf-112">El portal ofrece a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="2e5cf-113">Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para Endpoint para iOS cause problemas de rendimiento y errores impredecibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-113">Running other third-party endpoint protection products alongside Defender for Endpoint for iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="2e5cf-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2e5cf-114">Pre-requisites</span></span>

<span data-ttu-id="2e5cf-115">**Para usuarios finales**</span><span class="sxs-lookup"><span data-stu-id="2e5cf-115">**For End Users**</span></span>

- <span data-ttu-id="2e5cf-116">Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="2e5cf-117">Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="2e5cf-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="2e5cf-118">Los dispositivos se [inscriben a través de](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="2e5cf-119">Esto requiere que al usuario final se le asigne una licencia de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="2e5cf-120">La aplicación Portal de empresa de Intune se puede descargar desde [la Tienda de aplicaciones de Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="2e5cf-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="2e5cf-121">Ten en cuenta que Apple no permite que los usuarios redireccionamientos descarguen otras aplicaciones de la tienda de aplicaciones y, por lo tanto, este paso debe realizarlo el usuario antes de incorporarse a la aplicación Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="2e5cf-122">Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="2e5cf-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="2e5cf-123">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="2e5cf-123">**For Administrators**</span></span>

- <span data-ttu-id="2e5cf-124">Acceso al portal del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e5cf-125">Microsoft Intune es la única solución de administración de dispositivos móviles (MDM) compatible para implementar Microsoft Defender para endpoint para iOS.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for iOS.</span></span> <span data-ttu-id="2e5cf-126">Actualmente, solo se admiten dispositivos inscritos para aplicar las directivas de cumplimiento de dispositivos relacionados con iOS de Defender for Endpoint en Intune.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint for iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="2e5cf-127">Acceso al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en su organización.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="2e5cf-128">**Requisitos del sistema**</span><span class="sxs-lookup"><span data-stu-id="2e5cf-128">**System Requirements**</span></span>

- <span data-ttu-id="2e5cf-129">Dispositivos iOS que ejecutan iOS 11.0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="2e5cf-130">Los dispositivos iPad se admiten oficialmente a partir de la versión 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="2e5cf-131">El dispositivo está inscrito en la [aplicación Portal de empresa de Intune.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="2e5cf-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="2e5cf-132">**Atp de Microsoft Defender (Microsoft Defender para endpoint) para iOS ya está disponible en [Apple App Store](https://aka.ms/mdatpiosappstore).**</span><span class="sxs-lookup"><span data-stu-id="2e5cf-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="2e5cf-133">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="2e5cf-133">Installation instructions</span></span>

<span data-ttu-id="2e5cf-134">La implementación de Microsoft Defender para endpoint para iOS se realiza a través de Microsoft Intune (MDM) y se admiten dispositivos supervisados y no supervisados.</span><span class="sxs-lookup"><span data-stu-id="2e5cf-134">Deployment of Microsoft Defender for Endpoint for iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="2e5cf-135">Para obtener más información, vea [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span><span class="sxs-lookup"><span data-stu-id="2e5cf-135">For more information, see [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="2e5cf-136">Recursos</span><span class="sxs-lookup"><span data-stu-id="2e5cf-136">Resources</span></span>

- <span data-ttu-id="2e5cf-137">Manténgase informado acerca de las próximas versiones visitando nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span><span class="sxs-lookup"><span data-stu-id="2e5cf-137">Stay informed about upcoming releases by visiting our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="2e5cf-138">Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través del [portal de SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2e5cf-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="2e5cf-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2e5cf-139">Next steps</span></span>

- [<span data-ttu-id="2e5cf-140">Implementar Microsoft Defender para endpoint para iOS</span><span class="sxs-lookup"><span data-stu-id="2e5cf-140">Deploy Microsoft Defender for Endpoint for iOS</span></span>](ios-install.md)
- [<span data-ttu-id="2e5cf-141">Configurar Microsoft Defender para endpoint para características de iOS</span><span class="sxs-lookup"><span data-stu-id="2e5cf-141">Configure Microsoft Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
