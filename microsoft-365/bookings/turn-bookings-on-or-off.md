---
title: Activa o desactiva Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Obtenga información sobre cómo obtener acceso a Microsoft Bookings en Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126605"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="17bc8-103">Activa o desactiva Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="17bc8-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="17bc8-104">Bookings puede estar activado o desactivado para toda la organización o para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="17bc8-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="17bc8-105">Cuando activa Bookings para los usuarios, pueden crear una página de Bookings, crear un calendario y permitir que otras personas reserven tiempo con ellos.</span><span class="sxs-lookup"><span data-stu-id="17bc8-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="17bc8-106">Los controles de administración descritos en estas secciones no están disponibles para los clientes de Office 365 Operado por 21Vianet (China).</span><span class="sxs-lookup"><span data-stu-id="17bc8-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="17bc8-107">Activar o desactivar Bookings para su organización mediante el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="17bc8-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="17bc8-108">Inicie sesión en el Centro de administración de Microsoft 365 como administrador global.</span><span class="sxs-lookup"><span data-stu-id="17bc8-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="17bc8-109">En el centro de administración, vaya  **a** Configuración de la organización   \> **y** seleccione **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="17bc8-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="17bc8-110">Active la casilla permitir **que su organización use Bookings** para habilitar o deshabilitar Bookings para su organización.</span><span class="sxs-lookup"><span data-stu-id="17bc8-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="17bc8-111">Al desactivar Bookings, se deshabilitará todo el acceso al servicio, incluida la creación y administración de páginas de Bookings.</span><span class="sxs-lookup"><span data-stu-id="17bc8-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="17bc8-112">Seleccione **Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="17bc8-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="17bc8-113">Activar o desactivar Bookings para su organización con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17bc8-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="17bc8-114">Para activar o desactivar Bookings para su organización con el cmdlet de PowerShell [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="17bc8-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="17bc8-115">Activar o desactivar Bookings para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="17bc8-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="17bc8-116">Puede deshabilitar Bookings para usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="17bc8-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="17bc8-117">Vaya al Centro de administración de Microsoft 365 y, a continuación, seleccione **Usuarios** \> **activos.**</span><span class="sxs-lookup"><span data-stu-id="17bc8-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="17bc8-118">Seleccione el usuario deseado y, a continuación, **seleccione Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="17bc8-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="17bc8-119">Expanda **Aplicaciones** y desactive la casilla de Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="17bc8-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="17bc8-120">Requerir aprobaciones del personal antes de compartir información de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="17bc8-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="17bc8-121">Los administradores pueden requerir que los empleados de su organización puedan participar antes de que su información de disponibilidad se comparta a través de Bookings y antes de que se puedan reservar a través de una página de reserva.</span><span class="sxs-lookup"><span data-stu-id="17bc8-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="17bc8-122">Esta configuración está disponible en el Centro de administración de Microsoft 365 en **Configuración** \>  \> **de Bookings.**</span><span class="sxs-lookup"><span data-stu-id="17bc8-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="17bc8-123">Cuando esta configuración está habilitada, los empleados agregados como personal en los calendarios de reserva encontrarán un vínculo Aprobar o Rechazar en la notificación por correo electrónico que reciben.</span><span class="sxs-lookup"><span data-stu-id="17bc8-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="17bc8-124">Esta característica se está implementando gradualmente en todo el mundo para los clientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17bc8-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="17bc8-125">Si no ve esta opción en el Centro de administración de Microsoft 365, vuelva a consultarlo pronto.</span><span class="sxs-lookup"><span data-stu-id="17bc8-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="17bc8-126">Bloquear opciones de uso compartido social</span><span class="sxs-lookup"><span data-stu-id="17bc8-126">Block social sharing options</span></span>

<span data-ttu-id="17bc8-127">Los administradores pueden controlar cómo se comparten las páginas de reserva en las redes sociales.</span><span class="sxs-lookup"><span data-stu-id="17bc8-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="17bc8-128">Esta configuración está disponible en el Centro de administración de Microsoft 365 en **Configuración** \>  \> **de Bookings.**</span><span class="sxs-lookup"><span data-stu-id="17bc8-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="17bc8-129">Esta característica se está implementando gradualmente en todo el mundo para los clientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17bc8-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="17bc8-130">Si no ve esta opción en el Centro de administración de Microsoft 365, vuelva a consultarlo pronto.</span><span class="sxs-lookup"><span data-stu-id="17bc8-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="17bc8-131">Permitir que solo los usuarios seleccionados creen calendarios de Bookings</span><span class="sxs-lookup"><span data-stu-id="17bc8-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="17bc8-132">Mediante el uso de restricciones de directiva, puede restringir a los usuarios con licencia la posibilidad de crear calendarios de Bookings.</span><span class="sxs-lookup"><span data-stu-id="17bc8-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="17bc8-133">Primero debe habilitar Bookings para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="17bc8-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="17bc8-134">Todos los usuarios de su organización tendrán licencias de Bookings, pero solo los incluidos en la directiva pueden crear calendarios de Bookings y tener control total sobre quién puede acceder a los calendarios que crean.</span><span class="sxs-lookup"><span data-stu-id="17bc8-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="17bc8-135">Los usuarios que se incluyen en esta directiva pueden crear nuevos calendarios de Bookings y pueden agregarse como personal en cualquier capacidad (incluido el rol de administrador) a los calendarios de Bookings existentes.</span><span class="sxs-lookup"><span data-stu-id="17bc8-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="17bc8-136">Los usuarios que no se incluyan en esta directiva no podrán crear nuevos calendarios de Bookings y recibirán un mensaje de error si intentan hacerlo.</span><span class="sxs-lookup"><span data-stu-id="17bc8-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="17bc8-137">Deberá ejecutar los siguientes comandos con Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17bc8-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="17bc8-138">Para obtener más información sobre cómo ejecutar cmdlets de Exchange Online, consulte [Conectarse a Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="17bc8-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17bc8-139">En los pasos siguientes se supone que no se han creado otras directivas de buzón de Outlook Web App (OWA) en su organización.</span><span class="sxs-lookup"><span data-stu-id="17bc8-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="17bc8-140">Cree una nueva directiva de buzón para los usuarios que deberían tener permiso para crear calendarios de Bookings.</span><span class="sxs-lookup"><span data-stu-id="17bc8-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="17bc8-141">(La creación de calendario de Bookings está permitida de forma predeterminada por las nuevas directivas de buzón).</span><span class="sxs-lookup"><span data-stu-id="17bc8-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="17bc8-142">Para obtener más información, [vea New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="17bc8-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="17bc8-143">Para asignar esta directiva a los usuarios relevantes, ejecute este comando para cada usuario que desee conceder permiso para crear calendarios de Bookings.</span><span class="sxs-lookup"><span data-stu-id="17bc8-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="17bc8-144">Para obtener más información, vea [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="17bc8-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="17bc8-145">Opcional: ejecute este comando si desea deshabilitar Bookings para todos los demás usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="17bc8-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="17bc8-146">Para más información, vea [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="17bc8-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="17bc8-147">Para obtener más información sobre las directivas de buzón de OWA, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="17bc8-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="17bc8-148">Crear una directiva de buzón de Outlook en la Web en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="17bc8-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="17bc8-149">Aplicar o quitar una directiva de buzón de Outlook en la Web en un buzón en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="17bc8-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
