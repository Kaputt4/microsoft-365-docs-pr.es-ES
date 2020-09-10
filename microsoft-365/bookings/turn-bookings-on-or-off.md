---
title: Activar o desactivar Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Obtenga información sobre cómo obtener acceso a Microsoft bookings en Microsoft 365.
ms.openlocfilehash: 815aa3a859db15364aa18d3550001a28d085b711
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420105"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="a24ca-103">Activar o desactivar Microsoft bookings</span><span class="sxs-lookup"><span data-stu-id="a24ca-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="a24ca-104">Las reservas pueden activarse o desactivarse para toda la organización o para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="a24ca-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="a24ca-105">Cuando se activan las reservas para los usuarios, se puede crear una página de reservas, crear un calendario y permitir que otras personas dispongan de tiempo con ellos.</span><span class="sxs-lookup"><span data-stu-id="a24ca-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="a24ca-106">Los controles de administración descritos en estas secciones no están disponibles para los clientes de Office 365 operado por 21Vianet (China).</span><span class="sxs-lookup"><span data-stu-id="a24ca-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a24ca-107">Activar o desactivar las reservas para su organización mediante el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a24ca-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a24ca-108">Inicie sesión en el centro de administración de Microsoft 365 como administrador global.</span><span class="sxs-lookup"><span data-stu-id="a24ca-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="a24ca-109">En el centro de administración, vaya **a configuración**   \> **Settings** y seleccione **reservas**.</span><span class="sxs-lookup"><span data-stu-id="a24ca-109">In the admin center, go to **Settings** \> **Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="a24ca-110">Marque la casilla de verificación **permitir a su organización usar reservas** para habilitar o deshabilitar reservas para su organización.</span><span class="sxs-lookup"><span data-stu-id="a24ca-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a24ca-111">La desactivación de reservas deshabilitará todo el acceso al servicio, incluida la creación y la administración de las páginas de reservas.</span><span class="sxs-lookup"><span data-stu-id="a24ca-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="a24ca-112">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a24ca-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="a24ca-113">Activar o desactivar las reservas para su organización mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="a24ca-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="a24ca-114">Para activar o desactivar las reservas para su organización mediante el cmdlet [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)de PowerShell, [Conéctese a PowerShell de Exchange Online]() y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a24ca-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell]() and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="a24ca-115">Activar o desactivar las reservas para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="a24ca-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="a24ca-116">Puede deshabilitar las reservas para usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="a24ca-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="a24ca-117">Vaya al centro de administración de Microsoft 365 **y seleccione usuarios** \> **activos**.</span><span class="sxs-lookup"><span data-stu-id="a24ca-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="a24ca-118">Seleccione el usuario que desee y, a continuación, seleccione **licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a24ca-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="a24ca-119">Expanda **aplicaciones** y desactive la casilla de verificación de Microsoft bookings.</span><span class="sxs-lookup"><span data-stu-id="a24ca-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="a24ca-120">Requerir aprobaciones del personal antes de compartir la información de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="a24ca-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="a24ca-121">Los administradores pueden requerir que los empleados de su organización se puedan suscribir antes de que la información de disponibilidad se comparta a través de reservas y antes de que se puedan bookable a través de una página de reserva.</span><span class="sxs-lookup"><span data-stu-id="a24ca-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="a24ca-122">Esta opción está disponible en el centro de administración de Microsoft **365 en configuración de** \> **Settings** \> **reservas**.</span><span class="sxs-lookup"><span data-stu-id="a24ca-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a24ca-123">Cuando esta configuración está habilitada, los empleados agregados como personal en los calendarios de reserva buscarán un vínculo aprobar o rechazar en la notificación de correo electrónico que reciban.</span><span class="sxs-lookup"><span data-stu-id="a24ca-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="a24ca-124">Esta característica se encuentra gradualmente en todo el mundo a los clientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a24ca-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a24ca-125">Si no ve esta opción en el centro de administración de Microsoft 365, vuelva a consultar pronto.</span><span class="sxs-lookup"><span data-stu-id="a24ca-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="a24ca-126">Bloquear opciones de uso compartido social</span><span class="sxs-lookup"><span data-stu-id="a24ca-126">Block social sharing options</span></span>

<span data-ttu-id="a24ca-127">Los administradores pueden controlar cómo se comparten las páginas de reserva en las redes sociales.</span><span class="sxs-lookup"><span data-stu-id="a24ca-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="a24ca-128">Esta opción está disponible en el centro de administración de Microsoft **365 en configuración de** \> **Settings** \> **reservas**.</span><span class="sxs-lookup"><span data-stu-id="a24ca-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a24ca-129">Esta característica se encuentra gradualmente en todo el mundo a los clientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a24ca-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a24ca-130">Si no ve esta opción en el centro de administración de Microsoft 365, vuelva a consultar pronto.</span><span class="sxs-lookup"><span data-stu-id="a24ca-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="a24ca-131">Permitir solo a los usuarios seleccionados crear calendarios de reservas</span><span class="sxs-lookup"><span data-stu-id="a24ca-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="a24ca-132">Mediante el uso de restricciones de Directiva, puede restringir que los usuarios con licencia puedan crear calendarios de reservas.</span><span class="sxs-lookup"><span data-stu-id="a24ca-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="a24ca-133">Primero debe habilitar las reservas para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="a24ca-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="a24ca-134">Todos los usuarios de la organización tendrán licencias de reservas, pero solo los que se incluyan en la Directiva pueden crear calendarios de reservas y tener control total sobre quién puede tener acceso a los calendarios que crean.</span><span class="sxs-lookup"><span data-stu-id="a24ca-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="a24ca-135">Los usuarios que se incluyen en esta Directiva pueden crear nuevos calendarios de reservas y se pueden agregar como personal de cualquier capacidad (incluido el rol de administrador) a calendarios de reservas existentes.</span><span class="sxs-lookup"><span data-stu-id="a24ca-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="a24ca-136">Los usuarios que no estén incluidos en esta Directiva no podrán crear calendarios de reservas y recibirán un mensaje de error si intentan hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a24ca-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="a24ca-137">Deberá ejecutar los siguientes comandos con Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a24ca-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="a24ca-138">Para obtener más información sobre cómo ejecutar los cmdlets de Exchange Online, vea [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a24ca-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a24ca-139">En los pasos siguientes se da por sentado que no se ha creado ninguna otra directiva de buzón de Outlook Web App (OWA) en la organización.</span><span class="sxs-lookup"><span data-stu-id="a24ca-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="a24ca-140">Cree una nueva Directiva de buzón para los usuarios a los que se les permitirá crear calendarios de reservas.</span><span class="sxs-lookup"><span data-stu-id="a24ca-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="a24ca-141">(Las nuevas directivas de buzón de correo permiten la creación de calendarios de Books de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="a24ca-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="a24ca-142">Para obtener más información, vea [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="a24ca-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="a24ca-143">Asigne esta directiva a los usuarios pertinentes; para ello, ejecute este comando para cada usuario al que desee conceder permisos para crear calendarios de reservas.</span><span class="sxs-lookup"><span data-stu-id="a24ca-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="a24ca-144">Para obtener más información, vea [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="a24ca-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="a24ca-145">Opcional: ejecute este comando si desea deshabilitar las reservas para todos los demás usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="a24ca-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="a24ca-146">Para más información, vea [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="a24ca-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="a24ca-147">Para obtener más información sobre las directivas de buzón de OWA, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="a24ca-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="a24ca-148">Crear una directiva de buzón de correo de Outlook en la web en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a24ca-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="a24ca-149">Aplicar o quitar una directiva de buzón de Outlook en la web en un buzón de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a24ca-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)