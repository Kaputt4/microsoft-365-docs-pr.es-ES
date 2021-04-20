---
title: Aplicaciones conectadas en Microsoft Defender para endpoint
ms.reviewer: ''
description: Vea las aplicaciones asociadas conectadas que usan el protocolo estándar OAuth 2.0 para autenticar y proporcionar tokens para su uso con Microsoft Defender para las API de punto de conexión.
keywords: partners, aplicaciones, terceros, conexiones, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893502"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="5ce02-104">Aplicaciones conectadas en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="5ce02-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ce02-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5ce02-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ce02-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5ce02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ce02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ce02-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="5ce02-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5ce02-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5ce02-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5ce02-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="5ce02-110">Las aplicaciones conectadas se integran con la plataforma Defender for Endpoint mediante API.</span><span class="sxs-lookup"><span data-stu-id="5ce02-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="5ce02-111">Las aplicaciones usan el protocolo estándar OAuth 2.0 para autenticar y proporcionar tokens para su uso con Microsoft Defender para las API de extremo.</span><span class="sxs-lookup"><span data-stu-id="5ce02-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="5ce02-112">Además, las aplicaciones de Azure Active Directory (Azure AD) permiten a los administradores de inquilinos establecer un control explícito sobre las API a las que se puede tener acceso mediante la aplicación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5ce02-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="5ce02-113">Deberá seguir estos pasos [para](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) usar las API con la aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="5ce02-113">You'll need to follow [these steps](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="5ce02-114">Acceder a la página de la aplicación conectada</span><span class="sxs-lookup"><span data-stu-id="5ce02-114">Access the connected application page</span></span>
<span data-ttu-id="5ce02-115">En el menú de navegación izquierdo, seleccione **Partners & API**  >  **conectadas aplicaciones de AAD**.</span><span class="sxs-lookup"><span data-stu-id="5ce02-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="5ce02-116">Ver detalles de la aplicación conectada</span><span class="sxs-lookup"><span data-stu-id="5ce02-116">View connected application details</span></span>
<span data-ttu-id="5ce02-117">La página Aplicaciones conectadas proporciona información sobre las aplicaciones de Azure AD conectadas a Microsoft Defender para endpoint en su organización.</span><span class="sxs-lookup"><span data-stu-id="5ce02-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="5ce02-118">Puede revisar el uso de las aplicaciones conectadas: última vista, número de solicitudes en las últimas 24 horas y tendencias de solicitudes en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="5ce02-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Imagen de aplicaciones conectadas](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="5ce02-120">Editar, volver a configurar o eliminar una aplicación conectada</span><span class="sxs-lookup"><span data-stu-id="5ce02-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="5ce02-121">El **vínculo Abrir configuración de la** aplicación abre la página de administración de aplicaciones de Azure AD correspondiente en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="5ce02-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="5ce02-122">Desde Azure Portal, puede administrar permisos, reconfigurar o eliminar las aplicaciones conectadas.</span><span class="sxs-lookup"><span data-stu-id="5ce02-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
