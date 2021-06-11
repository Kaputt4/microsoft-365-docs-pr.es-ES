---
title: Microsoft Defender para punto de conexión en Android
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para Endpoint en Android
keywords: microsoft, defender, Microsoft Defender para Endpoint, android, instalación, implementación, desinstalación, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 499ac9a6ee81bacb79cd83993d510f87e11c62c6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844723"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="3c158-104">Microsoft Defender para punto de conexión en Android</span><span class="sxs-lookup"><span data-stu-id="3c158-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c158-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3c158-105">**Applies to:**</span></span>
- [<span data-ttu-id="3c158-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3c158-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c158-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c158-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3c158-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="3c158-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3c158-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3c158-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3c158-110">En este tema se describe cómo instalar, configurar, actualizar y usar Defender para Endpoint en Android.</span><span class="sxs-lookup"><span data-stu-id="3c158-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="3c158-111">Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para Endpoint en Android cause problemas de rendimiento y errores impredecibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="3c158-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="3c158-112">Cómo instalar Microsoft Defender para Endpoint en Android</span><span class="sxs-lookup"><span data-stu-id="3c158-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="3c158-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3c158-113">Prerequisites</span></span>

-   <span data-ttu-id="3c158-114">**Para usuarios finales**</span><span class="sxs-lookup"><span data-stu-id="3c158-114">**For end users**</span></span>

    -   <span data-ttu-id="3c158-115">Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c158-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="3c158-116">Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="3c158-116">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="3c158-117">Portal de empresa de Intune aplicación se puede descargar desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y está disponible en el dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="3c158-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="3c158-118">Además, los dispositivos se [](/mem/intune/user-help/enroll-device-android-company-portal) pueden inscribir mediante la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="3c158-118">Additionally, device(s) can be [enrolled](/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="3c158-119">Esto requiere que al usuario final se le asigne una Microsoft Intune licencia.</span><span class="sxs-lookup"><span data-stu-id="3c158-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="3c158-120">Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="3c158-120">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="3c158-121">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="3c158-121">**For Administrators**</span></span>

    -   <span data-ttu-id="3c158-122">Acceso al portal Centro de seguridad de Microsoft Defender web.</span><span class="sxs-lookup"><span data-stu-id="3c158-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="3c158-123">Microsoft Intune es la única solución de administración de dispositivos móviles (MDM) compatible para implementar Microsoft Defender para Endpoint en Android.</span><span class="sxs-lookup"><span data-stu-id="3c158-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="3c158-124">Actualmente, solo se admiten dispositivos inscritos para aplicar las directivas de cumplimiento de dispositivos relacionados con Defender for Endpoint en Android en Intune.</span><span class="sxs-lookup"><span data-stu-id="3c158-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="3c158-125">Accede [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en tu organización.</span><span class="sxs-lookup"><span data-stu-id="3c158-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="3c158-126">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="3c158-126">Network Requirements</span></span>

- <span data-ttu-id="3c158-127">Para que Microsoft Defender para endpoint en Android funcione cuando se conecte a una red, el firewall/proxy tendrá que configurarse para habilitar el acceso a las direcciones URL del servicio De extremo [de Microsoft Defender.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="3c158-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="3c158-128">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="3c158-128">System Requirements</span></span>

-   <span data-ttu-id="3c158-129">Dispositivos Android que ejecutan Android 6.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3c158-129">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="3c158-130">Portal de empresa de Intune aplicación se descarga desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e se instala.</span><span class="sxs-lookup"><span data-stu-id="3c158-130">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="3c158-131">La inscripción de dispositivos es necesaria para que se cumplan las directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="3c158-131">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="3c158-132">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="3c158-132">Installation instructions</span></span>

<span data-ttu-id="3c158-133">Microsoft Defender para Endpoint en Android admite la instalación en ambos modos de dispositivos inscritos: el administrador de dispositivos heredado y los modos Enterprise Android.</span><span class="sxs-lookup"><span data-stu-id="3c158-133">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="3c158-134">**Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten en Android Enterprise. La compatibilidad con otros Enterprise Android se anunciará cuando esté listo.**</span><span class="sxs-lookup"><span data-stu-id="3c158-134">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="3c158-135">La implementación de Microsoft Defender para Endpoint en Android es a través Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="3c158-135">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="3c158-136">Para obtener más información, vea [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="3c158-136">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="3c158-137">**Microsoft Defender para Endpoint en Android ya está disponible [en Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="3c158-137">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="3c158-138">Puedes conectarte a Google Play desde Intune para implementar la aplicación Microsoft Defender para endpoint, entre los modos de inscripción de Administrador de dispositivos y Android Enterprise inscripción.</span><span class="sxs-lookup"><span data-stu-id="3c158-138">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="3c158-139">Cómo configurar Microsoft Defender para endpoint en Android</span><span class="sxs-lookup"><span data-stu-id="3c158-139">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="3c158-140">Encontrará instrucciones sobre cómo configurar las características de Microsoft Defender para Endpoint en Android en [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span><span class="sxs-lookup"><span data-stu-id="3c158-140">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="3c158-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3c158-141">Related topics</span></span>
- [<span data-ttu-id="3c158-142">Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3c158-142">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="3c158-143">Configurar Microsoft Defender para punto de conexión en funciones de Android</span><span class="sxs-lookup"><span data-stu-id="3c158-143">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

