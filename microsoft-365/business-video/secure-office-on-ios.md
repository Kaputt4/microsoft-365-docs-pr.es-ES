---
title: Proteger aplicaciones de Office en iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Obtén información sobre cómo proteger Office aplicaciones en iOS con Microsoft 365 Empresa Premium.
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580467"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="40a1b-103">Proteger aplicaciones de Office en iOS</span><span class="sxs-lookup"><span data-stu-id="40a1b-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="40a1b-104">Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o una huella digital para iniciar sesión y también cifre los archivos de trabajo almacenados en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="40a1b-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="40a1b-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="40a1b-105">Try it!</span></span>

1. <span data-ttu-id="40a1b-106">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="40a1b-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="40a1b-107">En **Directivas,** elija **Agregar directiva**.</span><span class="sxs-lookup"><span data-stu-id="40a1b-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="40a1b-108">En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y elija el tipo de directiva que desee en Tipo **de directiva**.</span><span class="sxs-lookup"><span data-stu-id="40a1b-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="40a1b-109">Activa Administrar **cómo los usuarios acceden Office archivos en** dispositivos móviles y, a continuación, asegúrate de que las tres opciones de configuración siguientes estén activadas:</span><span class="sxs-lookup"><span data-stu-id="40a1b-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="40a1b-110">**Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**</span><span class="sxs-lookup"><span data-stu-id="40a1b-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="40a1b-111">**Proteger los archivos de trabajo cuando se pierden o se roban dispositivos**</span><span class="sxs-lookup"><span data-stu-id="40a1b-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="40a1b-112">**Cifrar archivos de trabajo**</span><span class="sxs-lookup"><span data-stu-id="40a1b-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="40a1b-113">En **Archivos de estas aplicaciones se protegerán,** selecciona las Office que quieras proteger en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="40a1b-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="40a1b-114">En **Quién se obtiene esta configuración?**, todos los usuarios están  seleccionados de forma predeterminada, pero puede elegir Cambiar para seleccionar los grupos de seguridad que haya creado.</span><span class="sxs-lookup"><span data-stu-id="40a1b-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="40a1b-115">Para finalizar la creación de la directiva, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40a1b-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="40a1b-116">En la **página Agregar directiva,** elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="40a1b-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="40a1b-117">En la página principal del Centro de administración, confirme  que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.</span><span class="sxs-lookup"><span data-stu-id="40a1b-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>