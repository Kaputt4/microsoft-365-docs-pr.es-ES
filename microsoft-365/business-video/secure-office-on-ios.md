---
title: Proteger las aplicaciones de Office en iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo proteger las aplicaciones de Office en iOS con Microsoft 365 empresa Premium.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702654"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="97218-103">Proteger las aplicaciones de Office en iOS</span><span class="sxs-lookup"><span data-stu-id="97218-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="97218-104">Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o una huella digital para iniciar sesión, y también se cifran los archivos de trabajo almacenados en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="97218-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="97218-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="97218-105">Try it!</span></span>

1. <span data-ttu-id="97218-106">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97218-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="97218-107">En **directivas**, elija **Agregar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="97218-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="97218-108">En el panel **Agregar Directiva** , escriba un nombre en **nombre de directiva** y elija el tipo de directiva que desee en **tipo de directiva**.</span><span class="sxs-lookup"><span data-stu-id="97218-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="97218-109">Active administrar la forma en que **los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** y asegúrese de que estén activadas las tres opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="97218-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="97218-110">**Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**</span><span class="sxs-lookup"><span data-stu-id="97218-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="97218-111">**Proteger los archivos de trabajo cuando se pierden o se roban dispositivos**</span><span class="sxs-lookup"><span data-stu-id="97218-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="97218-112">**Cifrar archivos de trabajo**</span><span class="sxs-lookup"><span data-stu-id="97218-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="97218-113">En **los archivos de estas aplicaciones estarán protegidos**, seleccione las aplicaciones de Office que quiera proteger en los dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="97218-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="97218-114">En ¿ **quién recibirá esta configuración?**, todos los usuarios están seleccionados de forma predeterminada, pero puede elegir **cambiar** para seleccionar los grupos de seguridad que haya creado.</span><span class="sxs-lookup"><span data-stu-id="97218-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="97218-115">Para finalizar la creación de la Directiva, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="97218-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="97218-116">En la página **Agregar Directiva** , elija **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="97218-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="97218-117">En la Página principal del centro de administración, confirme que se ha agregado la nueva Directiva eligiendo **directivas** y revisando la Directiva en la página **directivas** .</span><span class="sxs-lookup"><span data-stu-id="97218-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>