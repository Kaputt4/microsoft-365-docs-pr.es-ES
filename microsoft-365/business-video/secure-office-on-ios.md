---
title: Proteger aplicaciones de Office en iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Obtenga información sobre cómo proteger las aplicaciones de Office en iOS con Microsoft 365 Empresa Premium.
ms.openlocfilehash: 197041a4eb9ada65f4b6046d93f2a856cbdfb40d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422116"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="14d95-103">Proteger aplicaciones de Office en iOS</span><span class="sxs-lookup"><span data-stu-id="14d95-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="14d95-104">Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o una huella digital para iniciar sesión y también cifre los archivos de trabajo almacenados en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="14d95-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="14d95-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="14d95-105">Try it!</span></span>

1. <span data-ttu-id="14d95-106">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14d95-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="14d95-107">En **Directivas,** elija **Agregar directiva**.</span><span class="sxs-lookup"><span data-stu-id="14d95-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="14d95-108">En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y elija el tipo de directiva que desee en Tipo **de directiva**.</span><span class="sxs-lookup"><span data-stu-id="14d95-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="14d95-109">Activar Administrar **cómo los usuarios acceden a** los archivos de Office en dispositivos móviles y, a continuación, asegúrese de que las tres opciones de configuración siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="14d95-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="14d95-110">**Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**</span><span class="sxs-lookup"><span data-stu-id="14d95-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="14d95-111">**Proteger los archivos de trabajo cuando se pierden o se roban dispositivos**</span><span class="sxs-lookup"><span data-stu-id="14d95-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="14d95-112">**Cifrar archivos de trabajo**</span><span class="sxs-lookup"><span data-stu-id="14d95-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="14d95-113">En **Archivos de estas aplicaciones se protegerán,** seleccione las aplicaciones de Office que desea proteger en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="14d95-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="14d95-114">En **¿Quién va a obtener esta configuración?**, todos  los usuarios están seleccionados de forma predeterminada, pero puede elegir Cambiar para seleccionar los grupos de seguridad que haya creado.</span><span class="sxs-lookup"><span data-stu-id="14d95-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="14d95-115">Para finalizar la creación de la directiva, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="14d95-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="14d95-116">En la **página Agregar directiva,** elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="14d95-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="14d95-117">En la página principal del Centro de administración, confirme  que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.</span><span class="sxs-lookup"><span data-stu-id="14d95-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>