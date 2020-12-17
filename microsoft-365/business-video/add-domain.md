---
title: Agregar un dominio
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
description: Obtenga información sobre cómo agregar otro dominio a la suscripción.
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702787"
---
# <a name="add-another-domain"></a><span data-ttu-id="5d675-103">Agregar otro dominio</span><span class="sxs-lookup"><span data-stu-id="5d675-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="5d675-104">Es posible que su empresa necesite varios nombres de dominio para diferentes propósitos.</span><span class="sxs-lookup"><span data-stu-id="5d675-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="5d675-105">Por ejemplo, es posible que desee agregar una ortografía diferente al nombre de la compañía, ya que los clientes ya la usan y sus comunicaciones no han podido llegar a su nombre.</span><span class="sxs-lookup"><span data-stu-id="5d675-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="5d675-106">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="5d675-106">Try it!</span></span>

1. <span data-ttu-id="5d675-107">En el centro de administración de Microsoft 365, elija **instalar**.</span><span class="sxs-lookup"><span data-stu-id="5d675-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="5d675-108">En **obtener el dominio personalizado configurado**, seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="5d675-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="5d675-109">Elija **administrar** y, a continuación, **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="5d675-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="5d675-110">Escriba el nuevo nombre de dominio que desea agregar y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d675-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="5d675-111">Inicie sesión en su registrador de dominios, en este caso GoDaddy, y luego seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d675-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="5d675-112">Si se le solicita, inicie sesión en su registrador y, a continuación, elija **autorizar**.</span><span class="sxs-lookup"><span data-stu-id="5d675-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="5d675-113">Elija **Agregar los registros DNS por mí** y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d675-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="5d675-114">Elija los servicios para el nuevo dominio y desactive las casillas de verificación de los servicios que se controlarán mediante un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="5d675-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="5d675-115">Por ejemplo, si solo quiere usar el nuevo dominio para el correo electrónico, elija **Exchange** y desactive las casillas de verificación de **Skype empresarial** y **Administración de dispositivos móviles para Office 365**.</span><span class="sxs-lookup"><span data-stu-id="5d675-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="5d675-116">Seleccione **siguiente**, **autorice**, **siguiente** y, a continuación, **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5d675-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="5d675-117">Se ha agregado el nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="5d675-117">Your new domain has been added.</span></span>

<span data-ttu-id="5d675-118">Para recibir correo electrónico en su nuevo dominio, tendrá que agregar un nuevo alias de correo electrónico para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="5d675-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="5d675-119">Seleccione **usuarios**, **usuarios activos** y, a continuación, seleccione el usuario al que se asignará el nuevo alias.</span><span class="sxs-lookup"><span data-stu-id="5d675-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="5d675-120">Seleccione **administrar alias de correo electrónico** y, a continuación, **agregue un alias**.</span><span class="sxs-lookup"><span data-stu-id="5d675-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="5d675-121">Escriba el nombre de usuario y, a continuación, elija el nuevo dominio en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5d675-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="5d675-122">Seleccione **Guardar cambios** y, a continuación, cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="5d675-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="5d675-123">Repita estos pasos para cada usuario que deba recibir correo electrónico en el nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="5d675-123">Repeat these steps for each user who should receive email at the new domain.</span></span>