---
title: Cambiar la dirección de correo electrónico para usar el dominio personalizado
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Cambie su dirección de correo electrónico inicial a una dirección de correo electrónico descriptiva como tom@fourthcoffee.com. Para ello, debe comprar un nombre de dominio y agregarlo a Office 365. '
ms.openlocfilehash: 1c3c77f9626cdf292e0fb9400070cef3df05a9d6
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115984"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="21deb-104">Cambiar la dirección de correo electrónico para usar el dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="21deb-104">Change your email address to use your custom domain</span></span>

 <span data-ttu-id="21deb-105">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="21deb-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="21deb-p102">La dirección de correo electrónico inicial en Office 365 incluye .onmicrosoft.com, como tomas@fourthcoffee.onmicrosoft.com. Puede cambiarla por una más sencilla como tomas@fourthcoffee.com. Antes, necesitará su propio nombre de dominio, como fourthcoffee.com. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="21deb-p102">Your initial email address in Office 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com. You can change it to a friendlier address like tom@fourthcoffee.com. You'll need your own domain name, like fourthcoffee.com first. If you already have one, great! If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="21deb-111">Su dirección de correo electrónico inicial en Office 365 Germany incluye. onmicrosoft.de, como tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="21deb-111">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="21deb-112">Puede cambiarlo a una dirección más agradable como tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="21deb-112">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="21deb-113">Necesitará su propio nombre de dominio, como fourthcoffee.de primero.</span><span class="sxs-lookup"><span data-stu-id="21deb-113">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="21deb-114">Si ya tiene uno, ¡genial!</span><span class="sxs-lookup"><span data-stu-id="21deb-114">If you already have one, great!</span></span> <span data-ttu-id="21deb-115">Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="21deb-115">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="21deb-116">Su dirección de correo electrónico inicial en Office 365 operado por 21Vianet incluye partner.onmschina.cn, como tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="21deb-116">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="21deb-117">Puede cambiarlo a una dirección más agradable como tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="21deb-117">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="21deb-118">Necesitará su propio nombre de dominio, como fourthcoffee.cn primero.</span><span class="sxs-lookup"><span data-stu-id="21deb-118">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="21deb-119">Si ya tiene uno, ¡genial!</span><span class="sxs-lookup"><span data-stu-id="21deb-119">If you already have one, great!</span></span> <span data-ttu-id="21deb-120">Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="21deb-120">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="21deb-p105">Cuando modifica el correo electrónico de su dominio para que vaya a Office 365, al actualizar el registro MX del dominio durante la instalación, TODO el correo enviado a ese dominio empezará a llegar a Office 365. Asegúrese de que haya agregado a los usuarios y creado buzones en Office 365 para todos los usuarios que tengan correo electrónico en su dominio ANTES de cambiar el registro MX. ¿No desea mover el correo electrónico para todos los usuarios de su dominio a Office 365? Puede tomar medidas para [utilizar Office 365 con unas pocas direcciones de correo electrónico en su lugar](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span><span class="sxs-lookup"><span data-stu-id="21deb-p105">When you change your domain's email to come to Office 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Office 365. Make sure you've added users and created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record. Don't want to move email for everyone on your domain to Office 365? You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="21deb-125">Cambiar la dirección de correo electrónico para usar el dominio personalizado mediante el centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="21deb-125">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="21deb-126">Debe tener una cuenta de administrador global para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="21deb-126">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="21deb-127">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="21deb-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="21deb-128">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="21deb-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="21deb-129">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>.</span><span class="sxs-lookup"><span data-stu-id="21deb-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="21deb-130">Vaya a la página de **configuración** > de**dominios** .</span><span class="sxs-lookup"><span data-stu-id="21deb-130">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="21deb-131">En la página **dominios** , seleccione **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="21deb-131">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="21deb-132">Siga los pasos para confirmar que es el dueño del dominio y para cambiar la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="21deb-132">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="21deb-133">Se le guiará a lo largo del proceso de configuración del dominio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="21deb-133">You'll be guided to get everything set up correctly with your domain in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="21deb-134">Si no usa una licencia de Exchange, no puede usar el dominio para enviar o recibir mensajes de correo electrónico desde el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="21deb-134">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Office 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="21deb-135">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="21deb-135">Related articles</span></span>

[<span data-ttu-id="21deb-136">Comprar un dominio personalizado con Office 365</span><span class="sxs-lookup"><span data-stu-id="21deb-136">Buy a custom domain using Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
