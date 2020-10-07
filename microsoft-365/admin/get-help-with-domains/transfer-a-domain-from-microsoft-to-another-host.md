---
title: Transferir un dominio de Microsoft a otro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Busque aquí los pasos para transferir un dominio de Microsoft a otro registrador. '
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370329"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="2b4c4-103">Transferir un dominio de Microsoft a otro host</span><span class="sxs-lookup"><span data-stu-id="2b4c4-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="2b4c4-104">No puede transferir un dominio de Microsoft 365 a otro registrador durante 60 días después de comprar el dominio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="2b4c4-105">Una consulta _Whois_   muestra un registrador de dominios comprado por Microsoft como dominios silvestres de Westn LLC.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="2b4c4-106">Sin embargo, solo se debe poner en contacto con Microsoft en relación con el dominio adquirido de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="2b4c4-107">Siga estos pasos para obtener un código en Microsoft 365 y, a continuación, vaya al otro sitio web del registrador de dominios para configurar la transferencia de su nombre de dominio al nuevo registrador.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="2b4c4-108">Transferir un dominio</span><span class="sxs-lookup"><span data-stu-id="2b4c4-108">Transfer a domain</span></span>

1. <span data-ttu-id="2b4c4-109">En el centro de administración, vaya a  **configuración**de   >  **dominios**.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="2b4c4-110">En la página **dominios** , seleccione el dominio 365 de Microsoft que desea transferir a otro registrador de dominios y, a continuación, seleccione **comprobar estado**.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="2b4c4-111">En la parte superior de la página, seleccione **transferir dominio**.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="2b4c4-112">En la página **Elija dónde desea transferir su dominio** , seleccione **un registrador diferente**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="2b4c4-113">En la página **desbloquear la transferencia del dominio** , seleccione \*\*desbloquear transferencia para <_su dominio_ > \*\*y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="2b4c4-114">Compruebe la información de contacto de transferencia de dominio y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="2b4c4-115">Copie el código de autorización y espere unos 30 minutos hasta que el estado de transferencia del dominio cambie a **desbloqueado para transferencia** en la ficha **registro** antes de continuar con los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="2b4c4-116">Vaya al sitio web del registrador de dominios en el que desea administrar el nombre de dominio que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="2b4c4-117">Siga las instrucciones para transferir un dominio (busque ayuda en su sitio web).</span><span class="sxs-lookup"><span data-stu-id="2b4c4-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="2b4c4-118">Normalmente, esto significa pagar cuotas de transferencia y conceder el AuthCode al nuevo registrador para que puedan iniciar la transferencia.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="2b4c4-119">Microsoft le enviará un correo electrónico para confirmar que hemos recibido la solicitud de transferencia y que el dominio se transferirá en un plazo de 5 días.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="2b4c4-120">Puede encontrar la ficha **registro** de código de autorización en la página  **dominios** de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2b4c4-121">los dominios de. uk requieren un procedimiento diferente.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="2b4c4-122">Póngase en contacto con el soporte técnico de Microsoft y solicite un **cambio de etiqueta IPS** para que se ajuste al registrador que desea para administrar su dominio en adelante.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="2b4c4-123">Una vez que la etiqueta cambia, el dominio se transfiere inmediatamente al nuevo registrador.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="2b4c4-124">A continuación, tendrá que trabajar con el nuevo registrador para completar la transferencia, probablemente pagaremos cuotas de transferencia y agregar el dominio transferido a su cuenta con su nuevo registrador.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="2b4c4-125">Una vez completada la transferencia, renovará su dominio en el nuevo registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="2b4c4-126">Para finalizar el proceso, vuelva a la página **dominios** en el centro de administración y, a continuación, seleccione  **transferencia de dominio completa**.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="2b4c4-127">Esto marcará el dominio como ya no comprado de Microsoft 365 y deshabilitará la suscripción de dominio.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="2b4c4-128">No se quitará el dominio del espacio empresarial y no afectará a los usuarios y buzones existentes en el dominio.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="2b4c4-129">Los dominios adquiridos de Microsoft 365 no son válidos para los cambios de nameserver o para transferir el dominio entre las organizaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="2b4c4-130">Si alguno de ellos es necesario, el registro de dominio debe transferirse a otro registrador.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
