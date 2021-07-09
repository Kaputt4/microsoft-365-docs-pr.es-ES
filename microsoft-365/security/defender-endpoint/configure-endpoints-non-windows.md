---
title: Incorporar dispositivos que no Windows en el servicio de Microsoft Defender para endpoints
description: Configure dispositivos que no Windows para que puedan enviar datos del sensor al servicio de Microsoft Defender para endpoints.
keywords: incorporar dispositivos no Windows, macos, linux, administración de dispositivos, configurar Microsoft Defender para dispositivos de punto de conexión
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
ms.openlocfilehash: 777f5f63c4739f277ec24f826bc8a61a226fb65f
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339675"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="03c9c-104">Incorporar dispositivos que no tienen Windows</span><span class="sxs-lookup"><span data-stu-id="03c9c-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="03c9c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="03c9c-105">**Applies to:**</span></span>
- [<span data-ttu-id="03c9c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="03c9c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03c9c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03c9c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="03c9c-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="03c9c-108">**Platforms**</span></span>
- <span data-ttu-id="03c9c-109">macOS</span><span class="sxs-lookup"><span data-stu-id="03c9c-109">macOS</span></span>
- <span data-ttu-id="03c9c-110">Linux</span><span class="sxs-lookup"><span data-stu-id="03c9c-110">Linux</span></span>

><span data-ttu-id="03c9c-111">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="03c9c-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="03c9c-112">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="03c9c-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="03c9c-113">Defender for Endpoint proporciona una experiencia de operaciones de seguridad centralizada para Windows y plataformas no Windows de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03c9c-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="03c9c-114">Podrás ver alertas de varios sistemas operativos compatibles (SO) en Microsoft 365 Defender y proteger mejor la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="03c9c-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft 365 Defender and better protect your organization's network.</span></span> 

<span data-ttu-id="03c9c-115">Deberá conocer las versiones exactas de Linux distros y macOS que son compatibles con Defender for Endpoint para que la integración funcione.</span><span class="sxs-lookup"><span data-stu-id="03c9c-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="03c9c-116">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="03c9c-116">For more information, see:</span></span>
- [<span data-ttu-id="03c9c-117">Requisitos del sistema de Microsoft Defender para endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="03c9c-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="03c9c-118">[Requisitos del sistema de Microsoft Defender para endpoint en macOS](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="03c9c-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="03c9c-119">Incorporación de dispositivos no Windows móviles</span><span class="sxs-lookup"><span data-stu-id="03c9c-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="03c9c-120">Tendrás que seguir los siguientes pasos para incorporar dispositivos que no Windows:</span><span class="sxs-lookup"><span data-stu-id="03c9c-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="03c9c-121">Seleccione el método de incorporación preferido:</span><span class="sxs-lookup"><span data-stu-id="03c9c-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="03c9c-122">Para dispositivos macOS, puedes elegir incorporarlo a través de Microsoft Defender para Endpoint o a través de una solución de terceros.</span><span class="sxs-lookup"><span data-stu-id="03c9c-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="03c9c-123">Para obtener más información, vea [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span><span class="sxs-lookup"><span data-stu-id="03c9c-123">For more information, see [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="03c9c-124">Para otros dispositivos que no Windows, elija Incorporar dispositivos que no Windows a través **de la integración de terceros.**</span><span class="sxs-lookup"><span data-stu-id="03c9c-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="03c9c-125">En el panel de navegación, seleccione **Socios de**  >  **interoperabilidad**.</span><span class="sxs-lookup"><span data-stu-id="03c9c-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="03c9c-126">Asegúrese de que la solución de terceros aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="03c9c-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="03c9c-127">En la **pestaña Aplicaciones de** partners, seleccione el partner que admita los dispositivos que no Windows asociados.</span><span class="sxs-lookup"><span data-stu-id="03c9c-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="03c9c-128">Seleccione **Abrir página de socio** para abrir la página del partner.</span><span class="sxs-lookup"><span data-stu-id="03c9c-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="03c9c-129">Siga las instrucciones proporcionadas en la página.</span><span class="sxs-lookup"><span data-stu-id="03c9c-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="03c9c-130">Después de crear una cuenta o suscribirse a la solución de partners, debe llegar a una fase en la que se pida a un administrador global de inquilinos de la organización que acepte una solicitud de permiso de la aplicación asociada.</span><span class="sxs-lookup"><span data-stu-id="03c9c-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="03c9c-131">Lea atentamente la solicitud de permiso para asegurarse de que está alineada con el servicio que necesita.</span><span class="sxs-lookup"><span data-stu-id="03c9c-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="03c9c-132">Ejecute una prueba de detección siguiendo las instrucciones de la solución de terceros.</span><span class="sxs-lookup"><span data-stu-id="03c9c-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="03c9c-133">Dispositivos no Windows offboard</span><span class="sxs-lookup"><span data-stu-id="03c9c-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="03c9c-134">Siga la documentación del tercero para desconectar la solución de terceros de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="03c9c-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="03c9c-135">Quite los permisos de la solución de terceros en el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="03c9c-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="03c9c-136">Inicie sesión en el [portal de Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="03c9c-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="03c9c-137">Seleccione **Azure Active Directory > Enterprise aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="03c9c-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="03c9c-138">Selecciona la aplicación que quieras quitar.</span><span class="sxs-lookup"><span data-stu-id="03c9c-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="03c9c-139">Seleccione el **botón** Eliminar.</span><span class="sxs-lookup"><span data-stu-id="03c9c-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="03c9c-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="03c9c-140">Related topics</span></span>
- [<span data-ttu-id="03c9c-141">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="03c9c-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="03c9c-142">Servidores integrados</span><span class="sxs-lookup"><span data-stu-id="03c9c-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="03c9c-143">Configurar las opciones del proxy y de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="03c9c-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="03c9c-144">Solución de problemas de incorporación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="03c9c-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
