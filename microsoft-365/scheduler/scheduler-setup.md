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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809196"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="65016-103">Configuración del programador para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65016-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="65016-104">Para configurar el Programador para Microsoft 365, a continuación se indican los requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="65016-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="65016-105">**¿Qué necesito?**</span><span class="sxs-lookup"><span data-stu-id="65016-105">**What do I need?**</span></span> |<span data-ttu-id="65016-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="65016-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="65016-107">Buzón de Cortana</span><span class="sxs-lookup"><span data-stu-id="65016-107">Cortana mailbox</span></span> |<span data-ttu-id="65016-108">Los administradores de inquilinos tendrán que establecer un buzón para que sirva como buzón "Cortana" (es decir, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="65016-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="65016-109">Buzón de correo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="65016-109">Exchange Online mailbox</span></span> |<span data-ttu-id="65016-110">Los usuarios deben tener un Exchange Online correo electrónico y un calendario</span><span class="sxs-lookup"><span data-stu-id="65016-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="65016-111">Licencia del programador</span><span class="sxs-lookup"><span data-stu-id="65016-111">Scheduler license</span></span> |<span data-ttu-id="65016-112">Para obtener información sobre licencias y precios, vea [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="65016-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="65016-113">Crear un buzón para Cortana</span><span class="sxs-lookup"><span data-stu-id="65016-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="65016-114">Un Exchange en el inquilino actúa como el buzón de Cortana para que el inquilino envíe y reciba correos electrónicos desde y hacia Cortana.</span><span class="sxs-lookup"><span data-stu-id="65016-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="65016-115">Todos los correos electrónicos enviados a Cortana se conservan en el buzón de Cortana del inquilino en función de la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="65016-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="65016-116">Use el centro Microsoft 365 administración para crear un buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="65016-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="65016-117">Se recomienda una directiva de retención de 30 días.</span><span class="sxs-lookup"><span data-stu-id="65016-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="65016-118">Use el nombre Cortana en la dirección SMTP principal del buzón.</span><span class="sxs-lookup"><span data-stu-id="65016-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="65016-119">Se recomiendan nombres como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana.Scheduler@yourdomain.com".</span><span class="sxs-lookup"><span data-stu-id="65016-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="65016-120">Designar el buzón como asistente del programador</span><span class="sxs-lookup"><span data-stu-id="65016-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="65016-121">Después de crear un buzón único para El programador de Cortana, debe designar el buzón para que Microsoft 365 formalmente.</span><span class="sxs-lookup"><span data-stu-id="65016-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="65016-122">Después de designar el buzón programador de Cortana, estará disponible para programar reuniones en nombre de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="65016-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="65016-123">Para designar el buzón del Programador de Cortana, un administrador autorizado debe ejecutar un comando de PowerShell de una línea.</span><span class="sxs-lookup"><span data-stu-id="65016-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="65016-124">Conectar para Microsoft 365 espacio de ejecución remoto de PowerShell para la organización.</span><span class="sxs-lookup"><span data-stu-id="65016-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="65016-125">Ejecute el siguiente script de PowerShell para designar el buzón para scheduler:</span><span class="sxs-lookup"><span data-stu-id="65016-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="65016-126">Después de ejecutar este comando "set" en el buzón del Programador de Cortana, se establece un nuevo "PersistedCapability" en el buzón para tener en cuenta que este buzón es el "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="65016-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="65016-127">Siga estos pasos para conectar su organización a PowerShell si no lo ha hecho anteriormente: Conectar a Microsoft 365 [PowerShell : Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="65016-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="65016-128">Para descubrir qué buzón de correo de la organización está establecido actualmente como asistente programador de Cortana, ejecute la función get:</span><span class="sxs-lookup"><span data-stu-id="65016-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> <span data-ttu-id="65016-129">El buzón del programador puede tardar hasta dos horas en completar el aprovisionamiento completo para establecer la funcionalidad SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="65016-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="65016-130">Buzón de correo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="65016-130">Exchange Online mailbox</span></span>
<span data-ttu-id="65016-131">Scheduler es un complemento para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65016-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="65016-132">Los organizadores de reuniones deben tener un Exchange Online y un calendario para que el Programador funcione.</span><span class="sxs-lookup"><span data-stu-id="65016-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="65016-133">Requisitos de Exchange</span><span class="sxs-lookup"><span data-stu-id="65016-133">Exchange requirements</span></span>

<span data-ttu-id="65016-134">Además del Programador de licencias, debe tener una de las siguientes licencias:</span><span class="sxs-lookup"><span data-stu-id="65016-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="65016-135">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="65016-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="65016-136">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="65016-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="65016-137">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="65016-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="65016-138">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="65016-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="65016-139">Exchange Online Licencia del Plan 1 o plan 2.</span><span class="sxs-lookup"><span data-stu-id="65016-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="65016-140">**El programador Microsoft 365** no está disponible para usuarios de Office 365 operado por 21Vianet en China.</span><span class="sxs-lookup"><span data-stu-id="65016-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="65016-141">Tampoco está disponible para los usuarios de Microsoft 365 con la nube alemana que usa el administrador de datos German Telekom.</span><span class="sxs-lookup"><span data-stu-id="65016-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="65016-142">Sin embargo, es compatible con los usuarios de Alemania cuya ubicación de datos no se encuentre en el centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="65016-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="65016-143">Esta característica tampoco es compatible con los usuarios de la nube para administración pública, incluidos GCC, Consumidor, GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="65016-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
