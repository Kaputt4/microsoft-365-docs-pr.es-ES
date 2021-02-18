---
title: Flujo de correo en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: El administrador puede obtener información sobre las opciones para configurar el flujo de correo y el enrutamiento en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c988f58a04abf2322e993ae1b75106a338674acb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289656"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="30f43-103">Flujo de correo en EOP</span><span class="sxs-lookup"><span data-stu-id="30f43-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="30f43-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="30f43-104">**Applies to**</span></span>
- [<span data-ttu-id="30f43-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="30f43-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="30f43-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="30f43-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="30f43-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30f43-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="30f43-108">En las organizaciones de Microsoft 365 con buzones de Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, todos los mensajes enviados a su organización pasan a través de EOP antes de que sus trabajadores los vean.</span><span class="sxs-lookup"><span data-stu-id="30f43-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="30f43-109">Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enrutar a las bandejas de entrada de los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="30f43-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="30f43-110">Trabajar con mensajes y opciones de acceso de mensajes</span><span class="sxs-lookup"><span data-stu-id="30f43-110">Working with messages and message access options</span></span>

<span data-ttu-id="30f43-111">EOP ofrece flexibilidad para enrutar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="30f43-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="30f43-112">Los temas siguientes explican los pasos del proceso de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="30f43-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="30f43-113">[Usar el bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica bloqueo perimetral basado en directorios, que permite rechazar mensajes de destinatarios no válidos en el perímetro de la red de servicio.</span><span class="sxs-lookup"><span data-stu-id="30f43-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="30f43-114">[Ver o editar dominios administrados en EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.</span><span class="sxs-lookup"><span data-stu-id="30f43-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="30f43-115">Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos.</span><span class="sxs-lookup"><span data-stu-id="30f43-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="30f43-116">Obtenga más información sobre subdominios en [Habilitar flujo de correo para subdominios en Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="30f43-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="30f43-117">[Configurar el flujo de correo mediante conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta conectores y muestra cómo puede usarlos para personalizar el enrutamiento de correo.</span><span class="sxs-lookup"><span data-stu-id="30f43-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="30f43-118">Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.</span><span class="sxs-lookup"><span data-stu-id="30f43-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="30f43-119">[El filtrado mejorado para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.</span><span class="sxs-lookup"><span data-stu-id="30f43-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="30f43-120">En las organizaciones de EOP independientes, debe realizar un par de pasos de configuración para asegurarse de que el correo no deseado se enruta correctamente a la carpeta de correo no deseado de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="30f43-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="30f43-121">Estos se detallan en Configurar EOP independiente para entregar correo no deseado a la carpeta correo no deseado [en entornos híbridos.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="30f43-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="30f43-122">Si no desea mover mensajes a la carpeta de correo no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido).</span><span class="sxs-lookup"><span data-stu-id="30f43-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="30f43-123">Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="30f43-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="30f43-124">Comprobar el flujo de correo</span><span class="sxs-lookup"><span data-stu-id="30f43-124">Verify mail flow</span></span>

<span data-ttu-id="30f43-p106">Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="30f43-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="30f43-127">Para probar el flujo de correo mediante la validación de los conectores de [Microsoft 365,](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) se proporcionan instrucciones para probar que el flujo de correo está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="30f43-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
