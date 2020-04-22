---
title: Preguntas más frecuentes sobre administración delegada
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: En este tema se proporcionan preguntas frecuentes y respuestas a los partners y revendedores de Microsoft que quieren realizar tareas de administración delegada, incluida la capacidad de administrar Exchange Online Protection (EOP) para otros inquilinos (empresas).
ms.openlocfilehash: b79c0aba026a8d59aac338ceac0f1c4a60d71c4d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637657"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="37aa7-103">Preguntas más frecuentes sobre administración delegada</span><span class="sxs-lookup"><span data-stu-id="37aa7-103">Delegated administration FAQ</span></span>

<span data-ttu-id="37aa7-104">En este tema se proporcionan preguntas frecuentes y respuestas a los partners y revendedores de Microsoft que quieren realizar tareas de administración delegada, incluida la capacidad de administrar Exchange Online Protection (EOP) para otros inquilinos (empresas).</span><span class="sxs-lookup"><span data-stu-id="37aa7-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

<span data-ttu-id="37aa7-105">**P. Soy distribuidor y necesito administrar los inquilinos de mis clientes. ¿Cómo funciona?**</span><span class="sxs-lookup"><span data-stu-id="37aa7-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>

<span data-ttu-id="37aa7-106">A.</span><span class="sxs-lookup"><span data-stu-id="37aa7-106">A.</span></span> <span data-ttu-id="37aa7-107">Si es un distribuidor o un partner de Microsoft y se ha registrado para ser un asesor de Microsoft, puede solicitar permiso para administrar su inquilino dentro del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="37aa7-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="37aa7-108">Esto se conoce como administración delegada y le permite administrar su inquilino de Microsoft 365 (incluida la configuración de EOP) como si fuera un administrador de su organización.</span><span class="sxs-lookup"><span data-stu-id="37aa7-108">This is known as delegated administration, and it allows you to manage their Microsoft 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="37aa7-109">Los pasos para llevar a cabo la administración delegada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="37aa7-109">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="37aa7-110">Regístrese para ser un [asesor de Microsoft Office 365](https://aka.ms/cloudbenefits).</span><span class="sxs-lookup"><span data-stu-id="37aa7-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="37aa7-111">Regístrese para obtener una administración delegada.</span><span class="sxs-lookup"><span data-stu-id="37aa7-111">Sign up for delegated administration.</span></span> <span data-ttu-id="37aa7-112">Antes de que pueda comenzar a administrar la cuenta de un cliente, este debe autorizarlo como administrador delegado.</span><span class="sxs-lookup"><span data-stu-id="37aa7-112">Before you can start administering a customer's account, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="37aa7-113">Para obtener su aprobación, primero debe [enviarle una oferta de administración delegada](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e).</span><span class="sxs-lookup"><span data-stu-id="37aa7-113">To obtain their approval, you first [send them an offer for delegated administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="37aa7-114">(También puede ofrecerle administración delegada a su cliente más adelante).</span><span class="sxs-lookup"><span data-stu-id="37aa7-114">(You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="37aa7-115">Cree la cuenta de administrador delegado mediante los pasos descritos en [Agregar, cambiar o eliminar un partner Asesor de suscripción](https://docs.microsoft.com/office365/admin/misc/add-partner).</span><span class="sxs-lookup"><span data-stu-id="37aa7-115">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/office365/admin/misc/add-partner).</span></span>

<span data-ttu-id="37aa7-116">Visite [Partners: cree su empresa y administre la suscripción de Partner](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) para obtener más información acerca de cómo configurar la administración delegada.</span><span class="sxs-lookup"><span data-stu-id="37aa7-116">Visit [Partners: Build your business and administer partner subscription](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

<span data-ttu-id="37aa7-117">**P. Soy un cliente, no un distribuidor, ¿cómo puedo configurar un administrador delegado para mis inquilinos?**</span><span class="sxs-lookup"><span data-stu-id="37aa7-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>

<span data-ttu-id="37aa7-p103">R. En este momento, la administración delegada solo está disponible para los distribuidores y socios. Sin embargo, hemos incluido un script de ejemplo de Windows PowerShell que le ayudará a aplicar directivas a sus subinquilinos (empresas). Para obtener más información, consulte [Script de ejemplo para aplicar la configuración de EOP a varios inquilinos](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="37aa7-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

<span data-ttu-id="37aa7-122">**P. ¿Puedo evitar que mi administrador de subinquilinos modifique la directiva?**</span><span class="sxs-lookup"><span data-stu-id="37aa7-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>

<span data-ttu-id="37aa7-123">A.</span><span class="sxs-lookup"><span data-stu-id="37aa7-123">A.</span></span> <span data-ttu-id="37aa7-124">Microsoft 365 no tiene actualmente esta capacidad.</span><span class="sxs-lookup"><span data-stu-id="37aa7-124">Microsoft 365 does not currently have this capability.</span></span>

<span data-ttu-id="37aa7-125">**P. ¿Puedo obtener informes consolidados en todos mis subinquilinos?**</span><span class="sxs-lookup"><span data-stu-id="37aa7-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>

<span data-ttu-id="37aa7-126">R.</span><span class="sxs-lookup"><span data-stu-id="37aa7-126">A.</span></span> <span data-ttu-id="37aa7-127">La generación de informes consolidados en las empresas que administra no está disponible para los informes del centro de administración de Microsoft 365 en este momento.</span><span class="sxs-lookup"><span data-stu-id="37aa7-127">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="37aa7-128">Sin embargo, puede hacerlo con [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="37aa7-128">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
