---
title: Agregar un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
description: Obtenga información sobre cómo agregar otro dominio a la suscripción.
ms.openlocfilehash: 8899cb9667ffa080746ca9173b61897f9c5db399
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579006"
---
# <a name="add-another-domain"></a><span data-ttu-id="32d2e-103">Agregar otro dominio</span><span class="sxs-lookup"><span data-stu-id="32d2e-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="32d2e-104">Es posible que su empresa necesite varios nombres de dominio para fines diferentes.</span><span class="sxs-lookup"><span data-stu-id="32d2e-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="32d2e-105">Por ejemplo, es posible que desee agregar una ortografía diferente del nombre de la compañía porque los clientes ya lo están usando y sus comunicaciones no le han llegado.</span><span class="sxs-lookup"><span data-stu-id="32d2e-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="32d2e-106">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="32d2e-106">Try it!</span></span>

1. <span data-ttu-id="32d2e-107">En el Centro de administración de Microsoft 365, elija **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="32d2e-108">En **Obtener la configuración del dominio personalizado,** seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="32d2e-109">Elija **Administrar** y, a **continuación, Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="32d2e-110">Escriba el nuevo nombre de dominio que desea agregar y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="32d2e-111">Inicie sesión en el registrador de dominio, en este caso GoDaddy y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="32d2e-112">Si se le solicita, inicie sesión en el registrador y, a continuación, elija **Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="32d2e-113">Elija **Agregar los registros DNS para mí** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="32d2e-114">Elija los servicios para el nuevo dominio y desactive las casillas para los servicios que se administrarán mediante un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="32d2e-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="32d2e-115">Por ejemplo, si solo desea usar el nuevo dominio para correo electrónico, elija **Exchange** y desactive las casillas **de Skype** Empresarial y Administración de dispositivos móviles para **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="32d2e-116">Seleccione **Siguiente**, **Autorizar**, **Siguiente** y, a continuación, **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="32d2e-117">Se ha agregado el nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="32d2e-117">Your new domain has been added.</span></span>

<span data-ttu-id="32d2e-118">Para recibir correo electrónico en el nuevo dominio, deberá agregar un nuevo alias de correo electrónico para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="32d2e-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="32d2e-119">Seleccione **Usuarios**, **Usuarios activos** y, a continuación, seleccione el usuario al que se le asignará el nuevo alias.</span><span class="sxs-lookup"><span data-stu-id="32d2e-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="32d2e-120">Elija **Administrar alias de correo** electrónico **y, a continuación, Agregar un alias**.</span><span class="sxs-lookup"><span data-stu-id="32d2e-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="32d2e-121">Escriba el nombre de usuario y, a continuación, elija el nuevo dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="32d2e-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="32d2e-122">Seleccione **Guardar cambios** y, a continuación, cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="32d2e-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="32d2e-123">Repita estos pasos para cada usuario que debe recibir correo electrónico en el nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="32d2e-123">Repeat these steps for each user who should receive email at the new domain.</span></span>