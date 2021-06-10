---
title: Acceder al portal Centro de seguridad de Microsoft Defender cliente de MSSP
description: Acceder al portal Centro de seguridad de Microsoft Defender cliente de MSSP
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164862"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="ee193-104">Acceder al portal Centro de seguridad de Microsoft Defender cliente de MSSP</span><span class="sxs-lookup"><span data-stu-id="ee193-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="ee193-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ee193-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee193-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ee193-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee193-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee193-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ee193-108">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ee193-108">**Applies to:**</span></span>

- [<span data-ttu-id="ee193-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ee193-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="ee193-110">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="ee193-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ee193-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ee193-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="ee193-112">Este conjunto de pasos se dirige al MSSP.</span><span class="sxs-lookup"><span data-stu-id="ee193-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="ee193-113">De forma predeterminada, los clientes MSSP tienen acceso Centro de seguridad de Microsoft Defender inquilino a través de la siguiente dirección URL: `https://securitycenter.windows.com` .</span><span class="sxs-lookup"><span data-stu-id="ee193-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="ee193-114">Sin embargo, los MSSP tendrán que usar una dirección URL específica del inquilino en el siguiente formato: para obtener acceso al portal de  `https://securitycenter.windows.com?tid=customer_tenant_id` clientes de MSSP.</span><span class="sxs-lookup"><span data-stu-id="ee193-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="ee193-115">En general, los MSSP tendrán que agregarse a cada uno de los Azure AD del cliente de MSSP que pretenden administrar.</span><span class="sxs-lookup"><span data-stu-id="ee193-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="ee193-116">Siga estos pasos para obtener el identificador de inquilino del cliente MSSP y, a continuación, use el identificador para obtener acceso a la dirección URL específica del inquilino:</span><span class="sxs-lookup"><span data-stu-id="ee193-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="ee193-117">Como MSSP, inicie sesión en Azure AD con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="ee193-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="ee193-118">Cambie el directorio al inquilino del cliente de MSSP.</span><span class="sxs-lookup"><span data-stu-id="ee193-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="ee193-119">Seleccione **Azure Active Directory > propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ee193-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="ee193-120">Encontrará el identificador de inquilino en el campo Id. de directorio.</span><span class="sxs-lookup"><span data-stu-id="ee193-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="ee193-121">Para obtener acceso al portal de clientes de MSSP, reemplace el `customer_tenant_id` valor en la siguiente dirección URL: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="ee193-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ee193-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ee193-122">Related topics</span></span>
- [<span data-ttu-id="ee193-123">Conceder acceso a MSSP al portal</span><span class="sxs-lookup"><span data-stu-id="ee193-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="ee193-124">Configurar notificaciones de alerta</span><span class="sxs-lookup"><span data-stu-id="ee193-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="ee193-125">Capturar alertas del espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="ee193-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
