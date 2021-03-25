---
title: ATP de Microsoft Defender para Android
ms.reviewer: ''
description: Describe cómo instalar y usar ATP de Microsoft Defender para Android
keywords: microsoft, defender, atp, android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: e2432dc4aa2c67fadc9112512a080f24c0064df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187618"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="8214a-104">Microsoft Defender para endpoint para Android</span><span class="sxs-lookup"><span data-stu-id="8214a-104">Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8214a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8214a-105">**Applies to:**</span></span>
- [<span data-ttu-id="8214a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8214a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8214a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8214a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8214a-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="8214a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8214a-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="8214a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8214a-110">En este tema se describe cómo instalar, configurar, actualizar y usar Defender para Endpoint para Android.</span><span class="sxs-lookup"><span data-stu-id="8214a-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="8214a-111">Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para Endpoint para Android cause problemas de rendimiento y errores impredecibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="8214a-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="8214a-112">Cómo instalar Microsoft Defender para Endpoint para Android</span><span class="sxs-lookup"><span data-stu-id="8214a-112">How to install Microsoft Defender for Endpoint for Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="8214a-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8214a-113">Prerequisites</span></span>

-   <span data-ttu-id="8214a-114">**Para usuarios finales**</span><span class="sxs-lookup"><span data-stu-id="8214a-114">**For end users**</span></span>

    -   <span data-ttu-id="8214a-115">Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8214a-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="8214a-116">Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="8214a-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="8214a-117">La aplicación Portal de empresa de Intune se puede descargar desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y está disponible en el dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="8214a-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="8214a-118">Además, los dispositivos se pueden inscribir [a](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) través de la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="8214a-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="8214a-119">Esto requiere que al usuario final se le asigne una licencia de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8214a-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="8214a-120">Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="8214a-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="8214a-121">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="8214a-121">**For Administrators**</span></span>

    -   <span data-ttu-id="8214a-122">Acceso al portal del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8214a-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="8214a-123">Microsoft Intune es la única solución de administración de dispositivos móviles (MDM) compatible para implementar Microsoft Defender para Endpoint para Android.</span><span class="sxs-lookup"><span data-stu-id="8214a-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for Android.</span></span> <span data-ttu-id="8214a-124">Actualmente, solo se admiten dispositivos inscritos para aplicar las directivas de cumplimiento de dispositivos relacionados con Defender for Endpoint para Android en Intune.</span><span class="sxs-lookup"><span data-stu-id="8214a-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="8214a-125">Accede [al Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)para implementar la aplicación en grupos de usuarios inscritos en tu organización.</span><span class="sxs-lookup"><span data-stu-id="8214a-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="8214a-126">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="8214a-126">System Requirements</span></span>

-   <span data-ttu-id="8214a-127">Dispositivos Android que ejecutan Android 6.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8214a-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="8214a-128">La aplicación Portal de empresa de Intune se descarga [de Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e se instala.</span><span class="sxs-lookup"><span data-stu-id="8214a-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="8214a-129">La inscripción de dispositivos es necesaria para que se cumplan las directivas de cumplimiento de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="8214a-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="8214a-130">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="8214a-130">Installation instructions</span></span>

<span data-ttu-id="8214a-131">Microsoft Defender para Endpoint para Android admite la instalación en ambos modos de dispositivos inscritos: los modos heredados administrador de dispositivos y Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8214a-131">Microsoft Defender for Endpoint for Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="8214a-132">**Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten en Android Enterprise. La compatibilidad con otros modos de Android Enterprise se anunciará cuando esté listo.**</span><span class="sxs-lookup"><span data-stu-id="8214a-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrolments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="8214a-133">La implementación de Microsoft Defender para Endpoint para Android se realiza a través de Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="8214a-133">Deployment of Microsoft Defender for Endpoint for Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="8214a-134">Para obtener más información, vea [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="8214a-134">For more information, see [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="8214a-135">**Microsoft Defender para Endpoint para Android ya está disponible en [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="8214a-135">**Microsoft Defender for Endpoint for Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="8214a-136">Puedes conectarte a Google Play desde Intune para implementar la aplicación Microsoft Defender para endpoint, en los modos de inscripción administrador de dispositivos y Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8214a-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="8214a-137">Cómo configurar Microsoft Defender para endpoint para Android</span><span class="sxs-lookup"><span data-stu-id="8214a-137">How to Configure Microsoft Defender for Endpoint for Android</span></span>

<span data-ttu-id="8214a-138">Encontrará instrucciones sobre cómo configurar las características de Microsoft Defender para Endpoint para Android en [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span><span class="sxs-lookup"><span data-stu-id="8214a-138">Guidance on how to configure Microsoft Defender for Endpoint for Android features is available in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="8214a-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8214a-139">Related topics</span></span>
- [<span data-ttu-id="8214a-140">Implementar Microsoft Defender para endpoint para con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8214a-140">Deploy Microsoft Defender for Endpoint for with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="8214a-141">Configurar Microsoft Defender para las características de Punto de conexión para Android</span><span class="sxs-lookup"><span data-stu-id="8214a-141">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)

