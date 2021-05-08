---
title: Configuración del Programador para Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Configuración del Programador para Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286253"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="713b9-103">Configuración del programador para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="713b9-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="713b9-104">Para configurar el Programador para Microsoft 365, a continuación se indican los requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="713b9-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="713b9-105">**¿Qué necesito?**</span><span class="sxs-lookup"><span data-stu-id="713b9-105">**What do I need?**</span></span> |<span data-ttu-id="713b9-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="713b9-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="713b9-107">Buzón de Cortana</span><span class="sxs-lookup"><span data-stu-id="713b9-107">Cortana mailbox</span></span> |<span data-ttu-id="713b9-108">Los administradores de inquilinos tendrán que establecer un buzón para que sirva como buzón "Cortana" (es decir, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="713b9-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="713b9-109">Buzón de correo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="713b9-109">Exchange Online mailbox</span></span> |<span data-ttu-id="713b9-110">Los usuarios deben tener un Exchange Online correo electrónico y un calendario</span><span class="sxs-lookup"><span data-stu-id="713b9-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="713b9-111">Licencia del programador</span><span class="sxs-lookup"><span data-stu-id="713b9-111">Scheduler license</span></span> |<span data-ttu-id="713b9-112">Para obtener información sobre licencias y precios, vea [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="713b9-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="713b9-113">Crear un buzón para Cortana</span><span class="sxs-lookup"><span data-stu-id="713b9-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="713b9-114">Un Exchange en el inquilino actúa como el buzón de Cortana para que el inquilino envíe y reciba correos electrónicos desde y hacia Cortana.</span><span class="sxs-lookup"><span data-stu-id="713b9-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="713b9-115">Todos los correos electrónicos enviados a Cortana se conservan en el buzón de Cortana del inquilino en función de la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="713b9-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="713b9-116">Use el centro Microsoft 365 administración para crear un buzón nuevo.</span><span class="sxs-lookup"><span data-stu-id="713b9-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="713b9-117">Se recomienda una directiva de retención de 30 días.</span><span class="sxs-lookup"><span data-stu-id="713b9-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="713b9-118">Use el nombre Cortana en la dirección SMTP principal del buzón.</span><span class="sxs-lookup"><span data-stu-id="713b9-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="713b9-119">Se recomiendan nombres como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana.Scheduler@yourdomain.com".</span><span class="sxs-lookup"><span data-stu-id="713b9-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="713b9-120">Póngase en contacto con Microsoft (scheduler_m365@microsoft.com) para habilitar el buzón de Cortana.</span><span class="sxs-lookup"><span data-stu-id="713b9-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="713b9-121">Debe ponerse en contacto con Microsoft para configurar el buzón de Cortana para que use el servicio Scheduler mediante correo electrónico scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="713b9-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="713b9-122">Habilitar el buzón de Cortana puede tardar hasta dos semanas.</span><span class="sxs-lookup"><span data-stu-id="713b9-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="713b9-123">Buzón de correo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="713b9-123">Exchange Online mailbox</span></span>
<span data-ttu-id="713b9-124">Scheduler es un complemento para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="713b9-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="713b9-125">Los organizadores de reuniones deben tener un Exchange Online y un calendario para que el Programador funcione.</span><span class="sxs-lookup"><span data-stu-id="713b9-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="713b9-126">Requisitos de Exchange</span><span class="sxs-lookup"><span data-stu-id="713b9-126">Exchange requirements</span></span>

<span data-ttu-id="713b9-127">Además del Programador de licencias, debe tener una de las siguientes licencias:</span><span class="sxs-lookup"><span data-stu-id="713b9-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="713b9-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="713b9-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="713b9-129">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="713b9-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="713b9-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="713b9-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="713b9-131">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="713b9-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="713b9-132">Exchange Online Licencia del Plan 1 o plan 2.</span><span class="sxs-lookup"><span data-stu-id="713b9-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="713b9-133">**El programador Microsoft 365** no está disponible para usuarios de Office 365 operado por 21Vianet en China.</span><span class="sxs-lookup"><span data-stu-id="713b9-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="713b9-134">Tampoco está disponible para los usuarios de Microsoft 365 con la nube alemana que usa el administrador de datos German Telekom.</span><span class="sxs-lookup"><span data-stu-id="713b9-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="713b9-135">Sin embargo, es compatible con los usuarios de Alemania cuya ubicación de datos no se encuentre en el centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="713b9-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="713b9-136">Esta característica tampoco es compatible con los usuarios de la nube para administración pública, incluidos GCC, Consumidor, GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="713b9-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
