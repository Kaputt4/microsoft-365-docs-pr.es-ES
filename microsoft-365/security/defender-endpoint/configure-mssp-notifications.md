---
title: Configurar las notificaciones de alerta que se envían a los MSSP
description: Configurar las notificaciones de alerta que se envían a los MSSP
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166058"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="1ac17-104">Configurar las notificaciones de alerta que se envían a los MSSP</span><span class="sxs-lookup"><span data-stu-id="1ac17-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1ac17-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1ac17-105">**Applies to:**</span></span>
- [<span data-ttu-id="1ac17-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1ac17-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1ac17-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ac17-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1ac17-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1ac17-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1ac17-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1ac17-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="1ac17-110">Este paso lo puede realizar el cliente de MSSP o MSSP.</span><span class="sxs-lookup"><span data-stu-id="1ac17-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="1ac17-111">Los MSSP deben tener los permisos adecuados para configurarlo en nombre del cliente de MSSP.</span><span class="sxs-lookup"><span data-stu-id="1ac17-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="1ac17-112">Una vez concedido el acceso al portal, se pueden crear reglas de notificación de alertas para que los correos electrónicos se envíen a los MSSP cuando se crean alertas asociadas con el espacio empresarial y se cumplen las condiciones establecidas.</span><span class="sxs-lookup"><span data-stu-id="1ac17-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="1ac17-113">Para obtener más información, vea [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span><span class="sxs-lookup"><span data-stu-id="1ac17-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="1ac17-114">Estas casillas deben estar activadas:</span><span class="sxs-lookup"><span data-stu-id="1ac17-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="1ac17-115">**Incluir nombre de organización:** el nombre del cliente se agregará a las notificaciones por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="1ac17-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="1ac17-116">**Incluir vínculo de portal específico del** inquilino: la dirección URL del vínculo de alerta tendrá un parámetro específico del inquilino (tid=target_tenant_id) que permite el acceso directo al portal de inquilinos de destino</span><span class="sxs-lookup"><span data-stu-id="1ac17-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="1ac17-117">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1ac17-117">Related topics</span></span>
- [<span data-ttu-id="1ac17-118">Conceder acceso a MSSP al portal</span><span class="sxs-lookup"><span data-stu-id="1ac17-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="1ac17-119">Acceder al portal de clientes de MSSP</span><span class="sxs-lookup"><span data-stu-id="1ac17-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="1ac17-120">Capturar alertas del espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="1ac17-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
