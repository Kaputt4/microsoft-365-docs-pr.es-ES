---
title: Configurar la compatibilidad con el proveedor de servicios de seguridad administrado
description: Siga los pasos necesarios para configurar la integración de MSSP con Microsoft Defender para endpoint
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165254"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="1f46f-104">Configurar la integración del proveedor de servicios de seguridad administrados</span><span class="sxs-lookup"><span data-stu-id="1f46f-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f46f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1f46f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f46f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1f46f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1f46f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f46f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1f46f-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1f46f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1f46f-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1f46f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1f46f-110">Deberá seguir los siguientes pasos de configuración para habilitar la integración del proveedor de servicios de seguridad administrado (MSSP).</span><span class="sxs-lookup"><span data-stu-id="1f46f-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="1f46f-111">En este artículo se usan los siguientes términos para distinguir entre el proveedor de servicios y el consumidor de servicios:</span><span class="sxs-lookup"><span data-stu-id="1f46f-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="1f46f-112">MSSP: organizaciones de seguridad que ofrecen supervisar y administrar dispositivos de seguridad para una organización.</span><span class="sxs-lookup"><span data-stu-id="1f46f-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="1f46f-113">Clientes de MSSP: organizaciones que interactúan con los servicios de MSSP.</span><span class="sxs-lookup"><span data-stu-id="1f46f-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="1f46f-114">La integración permitirá a los MSSP realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1f46f-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="1f46f-115">Obtener acceso al portal de Centro de seguridad de Microsoft Defender MSSP</span><span class="sxs-lookup"><span data-stu-id="1f46f-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="1f46f-116">Obtener notificaciones por correo electrónico y</span><span class="sxs-lookup"><span data-stu-id="1f46f-116">Get email notifications, and</span></span> 
- <span data-ttu-id="1f46f-117">Capturar alertas a través de herramientas de administración de eventos y de información de seguridad (SIEM)</span><span class="sxs-lookup"><span data-stu-id="1f46f-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="1f46f-118">Antes de que los MSSP puedan llevar a cabo estas acciones, el cliente de MSSP tendrá que conceder acceso a su inquilino de Defender for Endpoint para que el MSSP pueda acceder al portal.</span><span class="sxs-lookup"><span data-stu-id="1f46f-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="1f46f-119">Normalmente, los clientes de MSSP toman los pasos de configuración iniciales para conceder a los MSSP acceso a su inquilino Windows Defender Security Central.</span><span class="sxs-lookup"><span data-stu-id="1f46f-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="1f46f-120">Una vez concedido el acceso, el cliente MSSP o el MSSP pueden realizar otros pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f46f-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="1f46f-121">En general, deben realizarse los siguientes pasos de configuración:</span><span class="sxs-lookup"><span data-stu-id="1f46f-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="1f46f-122">**Conceda al MSSP acceso a Centro de seguridad de Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="1f46f-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="1f46f-123">Esta acción debe realizarla el cliente de MSSP.</span><span class="sxs-lookup"><span data-stu-id="1f46f-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="1f46f-124">Concede al MSSP acceso al inquilino Defender for Endpoint del cliente de MSSP.</span><span class="sxs-lookup"><span data-stu-id="1f46f-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="1f46f-125">**Configurar notificaciones de alerta enviadas a MSSP**</span><span class="sxs-lookup"><span data-stu-id="1f46f-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="1f46f-126">Esta acción puede realizarla el cliente de MSSP o MSSP.</span><span class="sxs-lookup"><span data-stu-id="1f46f-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="1f46f-127">Esto permite a los MSSP saber qué alertas deben abordar para el cliente de MSSP.</span><span class="sxs-lookup"><span data-stu-id="1f46f-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="1f46f-128">**Capturar alertas del inquilino del cliente de MSSP en el sistema SIEM**</span><span class="sxs-lookup"><span data-stu-id="1f46f-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="1f46f-129">El MSSP toma esta acción.</span><span class="sxs-lookup"><span data-stu-id="1f46f-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="1f46f-130">Permite a los MSSP capturar alertas en herramientas SIEM.</span><span class="sxs-lookup"><span data-stu-id="1f46f-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="1f46f-131">**Capturar alertas desde el inquilino del cliente de MSSP mediante API**</span><span class="sxs-lookup"><span data-stu-id="1f46f-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="1f46f-132">El MSSP toma esta acción.</span><span class="sxs-lookup"><span data-stu-id="1f46f-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="1f46f-133">Permite a los MSSP capturar alertas mediante API.</span><span class="sxs-lookup"><span data-stu-id="1f46f-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="1f46f-134">Acceso multiinquilino para MSSP</span><span class="sxs-lookup"><span data-stu-id="1f46f-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="1f46f-135">Para obtener información sobre cómo implementar un acceso delegado multiinquilino, vea [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span><span class="sxs-lookup"><span data-stu-id="1f46f-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="1f46f-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1f46f-136">Related topics</span></span>
- [<span data-ttu-id="1f46f-137">Conceder acceso a MSSP al portal</span><span class="sxs-lookup"><span data-stu-id="1f46f-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="1f46f-138">Acceder al portal de clientes de MSSP</span><span class="sxs-lookup"><span data-stu-id="1f46f-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="1f46f-139">Configurar notificaciones de alerta</span><span class="sxs-lookup"><span data-stu-id="1f46f-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="1f46f-140">Capturar alertas del espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="1f46f-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

