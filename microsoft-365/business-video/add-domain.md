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
description: Es posible que su organización necesite varios dominios para que los clientes puedan encontrarlo. Obtenga información sobre cómo agregar otro dominio a la suscripción.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706435"
---
# <a name="add-another-domain"></a><span data-ttu-id="f2a2d-104">Agregar otro dominio</span><span class="sxs-lookup"><span data-stu-id="f2a2d-104">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="f2a2d-105">Es posible que su empresa necesite varios nombres de dominio para fines diferentes.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-105">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="f2a2d-106">Por ejemplo, es posible que desee agregar una ortografía diferente del nombre de la compañía porque los clientes ya lo están usando y sus comunicaciones no le han llegado.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-106">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="f2a2d-107">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="f2a2d-107">Try it!</span></span>

1. <span data-ttu-id="f2a2d-108">En el centro Microsoft 365 administración, elija **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-108">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="f2a2d-109">En **Obtener la configuración del dominio personalizado,** seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-109">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="f2a2d-110">Elija **Administrar** y, a **continuación, Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-110">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="f2a2d-111">Escriba el nuevo nombre de dominio que desea agregar y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-111">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="f2a2d-112">Inicie sesión en el registrador de dominio, en este caso GoDaddy y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-112">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="f2a2d-113">Si se le solicita, inicie sesión en el registrador y, a continuación, elija **Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-113">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="f2a2d-114">Elija **Agregar los registros DNS para mí** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-114">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="f2a2d-115">Elija los servicios para el nuevo dominio y desactive las casillas para los servicios que se administrarán mediante un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-115">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="f2a2d-116">Por ejemplo, si solo desea usar el nuevo dominio para el correo electrónico,  elija **Exchange** y desactive las casillas para Skype Empresarial y **Administración de dispositivos móviles para Office 365**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-116">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="f2a2d-117">Seleccione **Siguiente**, **Autorizar**, **Siguiente** y, a continuación, **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-117">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="f2a2d-118">Se ha agregado el nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-118">Your new domain has been added.</span></span>

<span data-ttu-id="f2a2d-119">Para recibir correo electrónico en el nuevo dominio, deberá agregar un nuevo alias de correo electrónico para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="f2a2d-119">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="f2a2d-120">Seleccione **Usuarios**, **Usuarios activos** y, a continuación, seleccione el usuario al que se le asignará el nuevo alias.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-120">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="f2a2d-121">Elija **Administrar alias de correo** electrónico **y, a continuación, Agregar un alias**.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-121">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="f2a2d-122">Escriba el nombre de usuario y, a continuación, elija el nuevo dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-122">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="f2a2d-123">Seleccione **Guardar cambios** y, a continuación, cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-123">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="f2a2d-124">Repita estos pasos para cada usuario que debe recibir correo electrónico en el nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="f2a2d-124">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="f2a2d-125">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f2a2d-125">Related content</span></span>

<span data-ttu-id="f2a2d-126">[Agregar un dominio a Microsoft 365](../admin/setup/add-domain.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f2a2d-126">[Add a domain to Microsoft 365](../admin/setup/add-domain.md) (article)</span></span>\
<span data-ttu-id="f2a2d-127">[Agregar registros DNS para conectar el dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f2a2d-127">[Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="f2a2d-128">[Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f2a2d-128">[Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="f2a2d-129">[Preguntas más frecuentes sobre dominios](../admin/setup/domains-faq.yml) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f2a2d-129">[Domains FAQ](../admin/setup/domains-faq.yml) (article)</span></span>