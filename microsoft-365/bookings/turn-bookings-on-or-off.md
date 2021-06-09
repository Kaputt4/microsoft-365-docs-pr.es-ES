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
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913771"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="488a3-103">Activa o desactiva Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="488a3-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="488a3-104">Las reservas pueden estar activadas o desactivadas para toda la organización o para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="488a3-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="488a3-105">Cuando activas Bookings para los usuarios, pueden crear una página de Bookings, crear un calendario y permitir que otras personas reserven tiempo con ellos.</span><span class="sxs-lookup"><span data-stu-id="488a3-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="488a3-106">Los controles de administración que se describen en estas secciones no están disponibles Office 365 los clientes de 21Vianet (China).</span><span class="sxs-lookup"><span data-stu-id="488a3-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="488a3-107">Activar o desactivar Bookings para su organización mediante el Centro Microsoft 365 administración</span><span class="sxs-lookup"><span data-stu-id="488a3-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="488a3-108">Inicie sesión en el centro Microsoft 365 de administración como administrador global.</span><span class="sxs-lookup"><span data-stu-id="488a3-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="488a3-109">En el Centro de administración, vaya  **a Configuración**   \> **Org Configuración** y seleccione **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="488a3-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="488a3-110">Active la casilla **Permitir que su organización use Bookings** para habilitar o deshabilitar Bookings para su organización.</span><span class="sxs-lookup"><span data-stu-id="488a3-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="488a3-111">Desactivar Bookings deshabilitará todo el acceso al servicio, incluida la creación y administración de páginas de Bookings.</span><span class="sxs-lookup"><span data-stu-id="488a3-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="488a3-112">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="488a3-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="488a3-113">Activar o desactivar Bookings para su organización con PowerShell</span><span class="sxs-lookup"><span data-stu-id="488a3-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="488a3-114">Para activar o desactivar Bookings para su organización con el cmdlet de PowerShell [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), Conectar a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="488a3-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="488a3-115">Activar o desactivar Bookings para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="488a3-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="488a3-116">Puedes deshabilitar Bookings para usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="488a3-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="488a3-117">Vaya al Centro Microsoft 365 administración y, a continuación, seleccione **Usuarios** \> **usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="488a3-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="488a3-118">Seleccione el usuario deseado y, a continuación, **seleccione Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="488a3-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="488a3-119">Expanda **Aplicaciones** y desactive la casilla de Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="488a3-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="488a3-120">Requerir aprobaciones de personal antes de compartir información de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="488a3-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="488a3-121">Los administradores pueden exigir a los empleados de su organización que opten por participar antes de compartir su información de disponibilidad a través de Bookings y antes de poder reservar a través de una página de reserva.</span><span class="sxs-lookup"><span data-stu-id="488a3-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="488a3-122">Esta configuración está disponible en el Centro Microsoft 365 administración en **Configuración** \> **Configuración** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="488a3-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="488a3-123">Cuando esta configuración está habilitada, los empleados agregados como personal en los calendarios de reserva encontrarán un vínculo Aprobar o rechazar en la notificación de correo electrónico que reciben.</span><span class="sxs-lookup"><span data-stu-id="488a3-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="488a3-124">Esta característica se está implementando gradualmente en todo el mundo para Microsoft 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="488a3-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="488a3-125">Si no ve esta opción en el centro de administración de Microsoft 365, vuelva pronto.</span><span class="sxs-lookup"><span data-stu-id="488a3-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="488a3-126">Bloquear opciones de uso compartido social</span><span class="sxs-lookup"><span data-stu-id="488a3-126">Block social sharing options</span></span>

<span data-ttu-id="488a3-127">Los administradores pueden controlar cómo se comparten las páginas de reserva en las redes sociales.</span><span class="sxs-lookup"><span data-stu-id="488a3-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="488a3-128">Esta configuración está disponible en el Centro Microsoft 365 administración en **Configuración** \> **Configuración** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="488a3-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="488a3-129">Esta característica se está implementando gradualmente en todo el mundo para Microsoft 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="488a3-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="488a3-130">Si no ve esta opción en el centro de administración de Microsoft 365, vuelva pronto.</span><span class="sxs-lookup"><span data-stu-id="488a3-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="488a3-131">Permitir que solo los usuarios seleccionados creen calendarios de Bookings</span><span class="sxs-lookup"><span data-stu-id="488a3-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="488a3-132">Al usar restricciones de directiva, puede restringir a los usuarios con licencia la posibilidad de crear calendarios de Bookings.</span><span class="sxs-lookup"><span data-stu-id="488a3-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="488a3-133">Primero debe habilitar Bookings para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="488a3-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="488a3-134">Todos los usuarios de la organización tendrán licencias de Bookings, pero solo los incluidos en la directiva pueden crear calendarios de Bookings y tener control total sobre quién puede acceder a los calendarios que creen.</span><span class="sxs-lookup"><span data-stu-id="488a3-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="488a3-135">Los usuarios incluidos en esta directiva pueden crear nuevos calendarios de Bookings y pueden agregarse como personal con cualquier capacidad (incluido el rol de administrador) a los calendarios de Bookings existentes.</span><span class="sxs-lookup"><span data-stu-id="488a3-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="488a3-136">Los usuarios que no están incluidos en esta directiva no podrán crear nuevos calendarios de Bookings y recibirán un mensaje de error si intentan hacerlo.</span><span class="sxs-lookup"><span data-stu-id="488a3-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="488a3-137">Deberá ejecutar los siguientes comandos con Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="488a3-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="488a3-138">Para obtener más información sobre cómo Exchange Online cmdlets, vea [Conectar to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="488a3-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="488a3-139">Los pasos siguientes suponen que no se han creado otras Outlook Web App de buzones de correo (OWA) en su organización.</span><span class="sxs-lookup"><span data-stu-id="488a3-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="488a3-140">Cree una nueva directiva de buzón de correo para los usuarios que deben tener permiso para crear calendarios de Bookings.</span><span class="sxs-lookup"><span data-stu-id="488a3-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="488a3-141">(La creación de calendario de Bookings está permitida de forma predeterminada por las nuevas directivas de buzón).</span><span class="sxs-lookup"><span data-stu-id="488a3-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="488a3-142">Para obtener más información, [vea New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="488a3-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="488a3-143">Para asignar esta directiva a los usuarios relevantes, ejecute este comando para cada usuario que desee conceder permiso para crear calendarios de Bookings.</span><span class="sxs-lookup"><span data-stu-id="488a3-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="488a3-144">Para obtener más información, vea [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="488a3-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="488a3-145">Opcional: ejecute este comando si desea deshabilitar Bookings para todos los demás usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="488a3-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="488a3-146">Para más información, vea [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="488a3-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="488a3-147">Para obtener más información sobre las directivas de buzones de OWA, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="488a3-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="488a3-148">Crear una Outlook en la directiva de buzón de correo web en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="488a3-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="488a3-149">Aplicar o quitar una Outlook en la directiva de buzón de correo web en un buzón en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="488a3-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)