---
title: Promover el entorno Microsoft 365 Defender evaluación a Producción, Microsoft 365 Defender evaluación, probar una evaluación, mantener una evaluación, evaluación de producción
description: Use este artículo para promover las evales de MDI, MDO, MDE y MCAS a su entorno vivo en Microsoft 365 Defender o M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458748"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="bbc7f-103">Promover el entorno Microsoft 365 Defender evaluación a la producción</span><span class="sxs-lookup"><span data-stu-id="bbc7f-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="bbc7f-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bbc7f-104">**Applies to:**</span></span>
- <span data-ttu-id="bbc7f-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbc7f-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="bbc7f-106">Para promover el entorno Microsoft 365 Defender evaluación a la producción, primero compre la licencia necesaria.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="bbc7f-107">Siga los pasos de [Crear el entorno de eval](eval-create-eval-environment.md) y compre la Office 365 E5 licencia (en lugar de seleccionar Iniciar prueba gratuita).</span><span class="sxs-lookup"><span data-stu-id="bbc7f-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="bbc7f-108">A continuación, complete cualquier configuración adicional y expanda los grupos piloto hasta que estos lleguen a la producción completa.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="bbc7f-109">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="bbc7f-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="bbc7f-110">Defender for Identity no requiere ninguna configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="bbc7f-111">Solo asegúrate de haber comprado las licencias necesarias e instalado el sensor en todos los controladores de dominio de Active Directory y servidores de Servicios de federación de Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="bbc7f-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="bbc7f-112">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bbc7f-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="bbc7f-113">Después de evaluar o pilotar MDO correctamente, se puede promover a todo el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="bbc7f-114">Compre y aprovisione las licencias necesarias y asígnelas a los usuarios de producción.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="bbc7f-115">Vuelva a ejecutar las configuraciones de directiva de línea base recomendadas (estándar o estricta) en el dominio de correo electrónico de producción o grupos específicos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="bbc7f-116">Si lo desea, cree y configure cualquier directiva MDO personalizada en su dominio de correo electrónico de producción o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="bbc7f-117">Sin embargo, recuerde que las directivas de línea base asignadas siempre tendrán prioridad sobre las directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="bbc7f-118">Actualice el registro MX público del dominio de correo electrónico de producción para resolverlo directamente en EOP.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="bbc7f-119">Retirar las puertas de enlace SMTP de terceros y deshabilitar o eliminar los conectores EXO asociados con esta retransmisión.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="bbc7f-120">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbc7f-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="bbc7f-121">Para promover el entorno de evaluación de Microsoft Defender para endpoints de un entorno piloto a la producción, simplemente incorpore más puntos de conexión al servicio con cualquiera de las herramientas y métodos [admitidos.](/defender-endpoint/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="bbc7f-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="bbc7f-122">Usa las siguientes directrices generales para incorporar más dispositivos a Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="bbc7f-123">Compruebe que el dispositivo cumple los [requisitos mínimos](/defender-endpoint/minimum-requirements).</span><span class="sxs-lookup"><span data-stu-id="bbc7f-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="bbc7f-124">Según el dispositivo, siga los pasos de configuración proporcionados en la sección incorporación del portal defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="bbc7f-125">Usa la herramienta de administración y el método de implementación adecuados para tus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="bbc7f-126">Ejecute una prueba de detección para comprobar que los dispositivos están correctamente incorporados e informando al servicio.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="bbc7f-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bbc7f-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="bbc7f-128">Microsoft Cloud App Security no requiere ninguna configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="bbc7f-129">Solo asegúrate de haber comprado las licencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="bbc7f-130">Si ha definido el ámbito de la implementación en determinados grupos de usuarios, aumente el ámbito de estos grupos hasta que alcance la escala de producción.</span><span class="sxs-lookup"><span data-stu-id="bbc7f-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

