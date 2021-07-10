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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362551"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="57e6f-103">Configuración del Planificador para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57e6f-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="57e6f-104">Para configurar el Programador para Microsoft 365, a continuación se indican los requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="57e6f-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="57e6f-105">¿Qué necesito?</span><span class="sxs-lookup"><span data-stu-id="57e6f-105">What do I need?</span></span> | <span data-ttu-id="57e6f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="57e6f-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="57e6f-107">Cortana buzón de correo</span><span class="sxs-lookup"><span data-stu-id="57e6f-107">Cortana mailbox</span></span> |<span data-ttu-id="57e6f-108">Los administradores de inquilinos tendrán que establecer un buzón para que sirva como buzón de correo "Cortana" (es decir, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="57e6f-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="57e6f-109">Buzón de correo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="57e6f-109">Exchange Online mailbox</span></span> |<span data-ttu-id="57e6f-110">Los usuarios deben tener un Exchange Online correo electrónico y un calendario</span><span class="sxs-lookup"><span data-stu-id="57e6f-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="57e6f-111">Licencia del programador</span><span class="sxs-lookup"><span data-stu-id="57e6f-111">Scheduler license</span></span> |<span data-ttu-id="57e6f-112">Para obtener información sobre licencias y precios, vea [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="57e6f-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="57e6f-113">Crear un buzón para Cortana</span><span class="sxs-lookup"><span data-stu-id="57e6f-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="57e6f-114">Un Exchange en el espacio empresarial actúa como el buzón de correo Cortana para que el inquilino envíe y reciba correos electrónicos desde y hacia Cortana.</span><span class="sxs-lookup"><span data-stu-id="57e6f-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="57e6f-115">Todos los correos electrónicos enviados Cortana se conservan en el buzón de correo Cortana del inquilino en función de la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="57e6f-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="57e6f-116">Use el Centro de administración de Microsoft 365 para crear un buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="57e6f-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="57e6f-117">Se recomienda una directiva de retención de 30 días.</span><span class="sxs-lookup"><span data-stu-id="57e6f-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="57e6f-118">Use el nombre Cortana en la dirección SMTP principal del buzón.</span><span class="sxs-lookup"><span data-stu-id="57e6f-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="57e6f-119">Nombres como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana. Scheduler@yourdomain.com' se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="57e6f-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="57e6f-120">Designar el buzón como asistente del programador</span><span class="sxs-lookup"><span data-stu-id="57e6f-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="57e6f-121">Después de crear un buzón único para Cortana scheduler, debe designar el buzón Microsoft 365 forma formal.</span><span class="sxs-lookup"><span data-stu-id="57e6f-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="57e6f-122">Después de designar el buzón Cortana programador, estará disponible para programar reuniones en nombre de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="57e6f-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="57e6f-123">Para designar el buzón Cortana Scheduler, un administrador autorizado debe ejecutar un comando de PowerShell de una línea.</span><span class="sxs-lookup"><span data-stu-id="57e6f-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="57e6f-124">Conectar para Microsoft 365 espacio de ejecución remoto de PowerShell para la organización.</span><span class="sxs-lookup"><span data-stu-id="57e6f-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="57e6f-125">Ejecute el siguiente script de PowerShell para designar el buzón para scheduler:</span><span class="sxs-lookup"><span data-stu-id="57e6f-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="57e6f-126">Después de ejecutar este comando "set" en el buzón del Programador de Cortana, se establece un nuevo "PersistedCapability" en el buzón para tener en cuenta que este buzón es el "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="57e6f-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="57e6f-127">Siga estos pasos para conectar su organización a PowerShell si no lo ha hecho anteriormente: Conectar a [Microsoft 365 con PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="57e6f-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="57e6f-128">Para descubrir qué buzón de correo de la organización está configurado actualmente como asistente Cortana programador, ejecute la función get:</span><span class="sxs-lookup"><span data-stu-id="57e6f-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="57e6f-129">El buzón del programador puede tardar hasta dos horas en completar el aprovisionamiento completo para establecer la funcionalidad SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="57e6f-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="57e6f-130">Buzón de correo Exchange Online</span><span class="sxs-lookup"><span data-stu-id="57e6f-130">Exchange Online mailbox</span></span>
<span data-ttu-id="57e6f-131">Una licencia de Programador es un complemento para Microsoft 365, que permite al organizador de la reunión delegar sus tareas de programación de reuniones en su asistente programador.</span><span class="sxs-lookup"><span data-stu-id="57e6f-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="57e6f-132">Para que el Programador funcione, normalmente Microsoft 365 licencia, los organizadores de reuniones requieren los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="57e6f-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="57e6f-133">Un buzón designado como buzón de asistente del programador</span><span class="sxs-lookup"><span data-stu-id="57e6f-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="57e6f-134">Licencia del programador</span><span class="sxs-lookup"><span data-stu-id="57e6f-134">Scheduler license</span></span>
- <span data-ttu-id="57e6f-135">Exchange Online buzón y calendario</span><span class="sxs-lookup"><span data-stu-id="57e6f-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="57e6f-136">Los asistentes a la reunión no requieren programador ni Microsoft 365 licencia.</span><span class="sxs-lookup"><span data-stu-id="57e6f-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="57e6f-137">Requisitos de licencia de usuario final del programador</span><span class="sxs-lookup"><span data-stu-id="57e6f-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="57e6f-138">Una licencia de programador requiere una de las siguientes licencias:</span><span class="sxs-lookup"><span data-stu-id="57e6f-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="57e6f-139">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="57e6f-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="57e6f-140">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="57e6f-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="57e6f-141">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="57e6f-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="57e6f-142">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="57e6f-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="57e6f-143">Exchange Online Licencia del Plan 1 o plan 2.</span><span class="sxs-lookup"><span data-stu-id="57e6f-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="57e6f-144">El programador Microsoft 365 está disponible en entornos multiinquilino en todo el mundo solo en inglés.</span><span class="sxs-lookup"><span data-stu-id="57e6f-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="57e6f-145">**El programador Microsoft 365** no está disponible para los usuarios de:</span><span class="sxs-lookup"><span data-stu-id="57e6f-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="57e6f-146">Microsoft 365 operado por 21Vianet en China</span><span class="sxs-lookup"><span data-stu-id="57e6f-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="57e6f-147">Microsoft 365 con la nube alemana que usa el administrador de datos German Telekom</span><span class="sxs-lookup"><span data-stu-id="57e6f-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="57e6f-148">Nube de gobierno, GCC, Consumidor, GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="57e6f-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="57e6f-149">El programador admite usuarios en Alemania cuya ubicación de datos no está en el centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="57e6f-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
