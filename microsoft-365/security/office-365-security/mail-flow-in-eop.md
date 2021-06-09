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
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842499"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="c23af-103">Flujo de correo en EOP</span><span class="sxs-lookup"><span data-stu-id="c23af-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c23af-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c23af-104">**Applies to**</span></span>
- [<span data-ttu-id="c23af-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c23af-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c23af-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c23af-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c23af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c23af-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c23af-108">En Microsoft 365 organizaciones con buzones Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, todos los mensajes enviados a su organización pasan a través de EOP antes de que los trabajadores los vean.</span><span class="sxs-lookup"><span data-stu-id="c23af-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="c23af-109">Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enrute a las bandejas de entrada de los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="c23af-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="c23af-110">Trabajar con mensajes y opciones de acceso de mensajes</span><span class="sxs-lookup"><span data-stu-id="c23af-110">Working with messages and message access options</span></span>

<span data-ttu-id="c23af-111">EOP ofrece flexibilidad en la forma en que se enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c23af-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="c23af-112">Los temas siguientes explican los pasos del proceso de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="c23af-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="c23af-113">[Usar el bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica bloqueo perimetral basado en directorios que le permite rechazar mensajes para destinatarios no válidos en el perímetro de la red de servicio.</span><span class="sxs-lookup"><span data-stu-id="c23af-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="c23af-114">[Ver o editar dominios aceptados en EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.</span><span class="sxs-lookup"><span data-stu-id="c23af-114">[View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="c23af-115">Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos.</span><span class="sxs-lookup"><span data-stu-id="c23af-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="c23af-116">Obtenga más información sobre los subdominios en [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="c23af-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="c23af-117">[Configurar el flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta conectores y muestra cómo puede usarlos para personalizar el enrutamiento de correo.</span><span class="sxs-lookup"><span data-stu-id="c23af-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="c23af-118">Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.</span><span class="sxs-lookup"><span data-stu-id="c23af-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="c23af-119">[El filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.</span><span class="sxs-lookup"><span data-stu-id="c23af-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="c23af-120">En entornos híbridos en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="c23af-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="c23af-121">Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span><span class="sxs-lookup"><span data-stu-id="c23af-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="c23af-122">Si no desea mover mensajes a la carpeta correo no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido).</span><span class="sxs-lookup"><span data-stu-id="c23af-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="c23af-123">Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c23af-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="c23af-124">Comprobar el flujo de correo</span><span class="sxs-lookup"><span data-stu-id="c23af-124">Verify mail flow</span></span>

<span data-ttu-id="c23af-p106">Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](/exchange/standalone-eop/set-up-your-eop-service).</span><span class="sxs-lookup"><span data-stu-id="c23af-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="c23af-127">[Probar el flujo de correo validando los conectores Microsoft 365 proporciona](/exchange/mail-flow-best-practices/test-mail-flow) instrucciones para probar que el flujo de correo está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c23af-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
