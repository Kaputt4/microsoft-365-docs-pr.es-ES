---
title: Flujo de correo en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: El administrador puede obtener información sobre las opciones para configurar el flujo de correo y el enrutamiento en Exchange Online Protection (EOP).
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208335"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="37b34-103">Flujo de correo en EOP</span><span class="sxs-lookup"><span data-stu-id="37b34-103">Mail flow in EOP</span></span>

<span data-ttu-id="37b34-104">En Microsoft 365 organizaciones con buzones de Exchange online o con organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, todos los mensajes enviados a la organización pasan a través de EOP antes de que los trabajadores los vean.</span><span class="sxs-lookup"><span data-stu-id="37b34-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="37b34-105">Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enruten a sus buzones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37b34-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="37b34-106">Trabajar con mensajes y opciones de acceso de mensajes</span><span class="sxs-lookup"><span data-stu-id="37b34-106">Working with messages and message access options</span></span>

<span data-ttu-id="37b34-107">EOP ofrece flexibilidad en el modo en que se enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="37b34-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="37b34-108">Los temas siguientes explican los pasos del proceso de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="37b34-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="37b34-109">[Usar bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica de bloqueo perimetral basado en directorios que permite rechazar mensajes para destinatarios no válidos en el perímetro de la red de servicio.</span><span class="sxs-lookup"><span data-stu-id="37b34-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="37b34-110">[Ver o editar dominios administrados en EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.</span><span class="sxs-lookup"><span data-stu-id="37b34-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="37b34-111">Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos.</span><span class="sxs-lookup"><span data-stu-id="37b34-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="37b34-112">Obtenga más información sobre subdominios en [enable mail Flow for Subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="37b34-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="37b34-113">[Configurar el flujo de correo mediante conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta los conectores y muestra cómo se pueden usar para personalizar el enrutamiento de correo.</span><span class="sxs-lookup"><span data-stu-id="37b34-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="37b34-114">Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.</span><span class="sxs-lookup"><span data-stu-id="37b34-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="37b34-115">El [filtrado mejorado para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.</span><span class="sxs-lookup"><span data-stu-id="37b34-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="37b34-116">En las organizaciones independientes de EOP, debe realizar un par de pasos de configuración para asegurarse de que el correo no deseado se enruta correctamente a la carpeta de correo electrónico no deseado de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="37b34-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="37b34-117">Se describen en [Configure Standalone EOP para entregar el correo no deseado a la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="37b34-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="37b34-118">Si no desea mover mensajes a la carpeta de correo electrónico no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido).</span><span class="sxs-lookup"><span data-stu-id="37b34-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="37b34-119">Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="37b34-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="37b34-120">Comprobar el flujo de correo</span><span class="sxs-lookup"><span data-stu-id="37b34-120">Verify mail flow</span></span>

<span data-ttu-id="37b34-p106">Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="37b34-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="37b34-123">[Probar el flujo de correo mediante la validación de los conectores de 365 de Microsoft](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) proporciona instrucciones para probar que el flujo de correo está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="37b34-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
