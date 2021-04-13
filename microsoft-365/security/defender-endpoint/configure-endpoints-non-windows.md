---
title: Incorporación de dispositivos que no son de Windows al servicio de Microsoft Defender para puntos de conexión
description: Configura dispositivos que no son de Windows para que puedan enviar datos del sensor al servicio ATP de Microsoft Defender.
keywords: incorporar dispositivos que no son windows, macos, linux, administración de dispositivos, configurar dispositivos de Windows ATP, configurar Microsoft Defender para dispositivos de punto de conexión
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 71f230f557792d75659dc4dbfc5911811514d5ea
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687882"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="97ded-104">Incorporar dispositivos que no tienen Windows</span><span class="sxs-lookup"><span data-stu-id="97ded-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="97ded-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="97ded-105">**Applies to:**</span></span>
- [<span data-ttu-id="97ded-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="97ded-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="97ded-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97ded-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="97ded-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="97ded-108">**Platforms**</span></span>
- <span data-ttu-id="97ded-109">macOS</span><span class="sxs-lookup"><span data-stu-id="97ded-109">macOS</span></span>
- <span data-ttu-id="97ded-110">Linux</span><span class="sxs-lookup"><span data-stu-id="97ded-110">Linux</span></span>

><span data-ttu-id="97ded-111">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="97ded-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="97ded-112">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="97ded-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="97ded-113">Defender for Endpoint proporciona una experiencia de operaciones de seguridad centralizada para Windows, así como para plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="97ded-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="97ded-114">Podrás ver alertas de varios sistemas operativos compatibles (SO) en el Centro de seguridad de Microsoft Defender y proteger mejor la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="97ded-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="97ded-115">Deberá conocer las versiones exactas de Linux distros y macOS que son compatibles con Defender for Endpoint para que la integración funcione.</span><span class="sxs-lookup"><span data-stu-id="97ded-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="97ded-116">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="97ded-116">For more information, see:</span></span>
- [<span data-ttu-id="97ded-117">Requisitos del sistema de Microsoft Defender para endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="97ded-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="97ded-118">[Requisitos del sistema de Microsoft Defender para endpoint en macOS](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="97ded-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="97ded-119">Incorporación de dispositivos que no son de Windows</span><span class="sxs-lookup"><span data-stu-id="97ded-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="97ded-120">Tendrás que seguir los siguientes pasos para incorporar dispositivos que no son windows:</span><span class="sxs-lookup"><span data-stu-id="97ded-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="97ded-121">Seleccione el método de incorporación preferido:</span><span class="sxs-lookup"><span data-stu-id="97ded-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="97ded-122">Para dispositivos macOS, puedes elegir incorporarlo a través de ATP de Microsoft Defender o a través de una solución de terceros.</span><span class="sxs-lookup"><span data-stu-id="97ded-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="97ded-123">Para obtener más información, vea [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span><span class="sxs-lookup"><span data-stu-id="97ded-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="97ded-124">Para otros dispositivos que no son de Windows, elija Incorporar dispositivos que no son de Windows a **través de la integración de terceros.**</span><span class="sxs-lookup"><span data-stu-id="97ded-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="97ded-125">En el panel de navegación, seleccione **Socios de**  >  **interoperabilidad**.</span><span class="sxs-lookup"><span data-stu-id="97ded-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="97ded-126">Asegúrese de que la solución de terceros aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="97ded-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="97ded-127">En la **pestaña Aplicaciones de** partners, selecciona el partner que admita los dispositivos que no son windows.</span><span class="sxs-lookup"><span data-stu-id="97ded-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="97ded-128">Seleccione **Abrir página de socio** para abrir la página del partner.</span><span class="sxs-lookup"><span data-stu-id="97ded-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="97ded-129">Siga las instrucciones proporcionadas en la página.</span><span class="sxs-lookup"><span data-stu-id="97ded-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="97ded-130">Después de crear una cuenta o suscribirse a la solución de partners, debe llegar a una fase en la que se pida a un administrador global de inquilinos de la organización que acepte una solicitud de permiso de la aplicación asociada.</span><span class="sxs-lookup"><span data-stu-id="97ded-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="97ded-131">Lea atentamente la solicitud de permiso para asegurarse de que está alineada con el servicio que necesita.</span><span class="sxs-lookup"><span data-stu-id="97ded-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="97ded-132">Ejecute una prueba de detección siguiendo las instrucciones de la solución de terceros.</span><span class="sxs-lookup"><span data-stu-id="97ded-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="97ded-133">Dispositivos offboard que no son Windows</span><span class="sxs-lookup"><span data-stu-id="97ded-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="97ded-134">Siga la documentación del tercero para desconectar la solución de terceros de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="97ded-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="97ded-135">Quite los permisos de la solución de terceros en el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="97ded-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="97ded-136">Inicie sesión en el [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="97ded-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="97ded-137">Seleccione **Azure Active Directory > Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="97ded-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="97ded-138">Selecciona la aplicación que quieras quitar.</span><span class="sxs-lookup"><span data-stu-id="97ded-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="97ded-139">Seleccione el **botón** Eliminar.</span><span class="sxs-lookup"><span data-stu-id="97ded-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="97ded-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="97ded-140">Related topics</span></span>
- [<span data-ttu-id="97ded-141">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="97ded-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="97ded-142">Servidores integrados</span><span class="sxs-lookup"><span data-stu-id="97ded-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="97ded-143">Configurar las opciones del proxy y de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="97ded-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="97ded-144">Solución de problemas de incorporación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="97ded-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
