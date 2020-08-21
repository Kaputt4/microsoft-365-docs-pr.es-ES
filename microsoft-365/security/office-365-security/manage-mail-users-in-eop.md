---
title: Administrar usuarios de correo en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Obtenga información sobre cómo administrar usuarios de correo en Exchange Online Protection (EOP), incluido el uso de la sincronización de directorios, el EAC y PowerShell para administrar usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827080"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="440f4-103">Administrar usuarios de correo en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="440f4-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="440f4-104">En las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los usuarios de correo son el tipo fundamental de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="440f4-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="440f4-105">Un usuario de correo tiene credenciales de cuenta en su organización de EOP independiente y puede tener acceso a los recursos (tener permisos asignados).</span><span class="sxs-lookup"><span data-stu-id="440f4-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="440f4-106">La dirección de correo electrónico de un usuario de correo es externa (por ejemplo, en su entorno de correo electrónico local).</span><span class="sxs-lookup"><span data-stu-id="440f4-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="440f4-107">Al crear un usuario de correo, la cuenta de usuario correspondiente está disponible en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="440f4-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="440f4-108">Cuando se crea una cuenta de usuario en el centro de administración de Microsoft 365, no se puede usar esa cuenta para crear un usuario de correo.</span><span class="sxs-lookup"><span data-stu-id="440f4-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="440f4-109">El método recomendado para crear y administrar usuarios de correo en EOP independiente es usar la sincronización de directorios, tal como se describe en la sección [usar la sincronización de directorios para administrar usuarios de correo](#use-directory-synchronization-to-manage-mail-users) , más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="440f4-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="440f4-110">Para organizaciones independientes de EOP con un pequeño número de usuarios, puede Agregar y administrar usuarios de correo en el centro de administración de Exchange (EAC) o en PowerShell independiente de EOP, tal y como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="440f4-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="440f4-111">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="440f4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="440f4-112">Para abrir el centro de administración de Exchange (EAC), consulte [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="440f4-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="440f4-113">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="440f4-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="440f4-114">Al crear usuarios de correo en el PowerShell de EOP, es posible que se encuentre con limitaciones.</span><span class="sxs-lookup"><span data-stu-id="440f4-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="440f4-115">Además, los cmdlets de PowerShell de EOP usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="440f4-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="440f4-116">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="440f4-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="440f4-117">En concreto, necesita los roles creación de destinatarios de correo (crear) y destinatarios de correo (modificar), que se asignan a los grupos de roles OrganizationManagement (administradores globales) y RecipientManagement de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="440f4-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="440f4-118">Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="440f4-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="440f4-119">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="440f4-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="440f4-120">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="440f4-120">Having problems?</span></span> <span data-ttu-id="440f4-121">Solicite ayuda en los foros de Exchange.</span><span class="sxs-lookup"><span data-stu-id="440f4-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="440f4-122">Visite el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="440f4-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="440f4-123">Usar el centro de administración de Exchange para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="440f4-124">Usar el EAC para crear usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="440f4-125">En el EAC, vaya a contactos de **destinatarios** \> **Contacts** .</span><span class="sxs-lookup"><span data-stu-id="440f4-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="440f4-126">Haga clic en **nuevo** ![ icono nuevo ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="440f4-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="440f4-127">En la página **nuevo usuario de correo** que se abre, configure las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="440f4-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="440f4-128">La configuración marcada con un <sup>\*</sup> es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="440f4-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="440f4-129">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="440f4-129">**First name**</span></span>

   - <span data-ttu-id="440f4-130">**Iniciales**: inicial del segundo nombre de la persona.</span><span class="sxs-lookup"><span data-stu-id="440f4-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="440f4-131">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="440f4-131">**Last name**</span></span>

   - <span data-ttu-id="440f4-132"><sup>\*</sup>**Nombre para mostrar**: de forma predeterminada, este cuadro muestra los valores de los cuadros **nombre**, **iniciales**y **Apellido** .</span><span class="sxs-lookup"><span data-stu-id="440f4-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="440f4-133">Puede aceptar este valor o cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="440f4-133">You can accept this value or change it.</span></span> <span data-ttu-id="440f4-134">El valor debe ser único y tener una longitud máxima de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="440f4-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="440f4-135"><sup>\*</sup>**Alias**: escriba un alias único, con un máximo de 64 caracteres, para el usuario</span><span class="sxs-lookup"><span data-stu-id="440f4-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="440f4-136">**Dirección de correo electrónico externa**: escriba la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="440f4-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="440f4-137">El dominio debe ser externo a su organización basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="440f4-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="440f4-138"><sup>\*</sup>**Identificador de usuario**: escriba la cuenta que usará la persona para iniciar sesión en el servicio.</span><span class="sxs-lookup"><span data-stu-id="440f4-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="440f4-139">El identificador de usuario consta de un nombre de usuario en el lado izquierdo del símbolo arroba (@) y de un dominio en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="440f4-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="440f4-140"><sup>\*</sup>**Nueva contraseña** y <sup>\*</sup> **Confirmar contraseña**: escriba y vuelva a escribir la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="440f4-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="440f4-141">Compruebe que la contraseña cumple con los requisitos de longitud de la contraseña, complejidad e historial de la organización.</span><span class="sxs-lookup"><span data-stu-id="440f4-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="440f4-142">Cuando haya terminado, haga clic en **Guardar** para crear el usuario de correo.</span><span class="sxs-lookup"><span data-stu-id="440f4-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="440f4-143">Usar el EAC para modificar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="440f4-144">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="440f4-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="440f4-145">Seleccione el usuario de correo que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="440f4-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="440f4-146">En la página de propiedades del usuario de correo que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="440f4-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="440f4-147">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="440f4-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="440f4-148">General</span><span class="sxs-lookup"><span data-stu-id="440f4-148">General</span></span>

<span data-ttu-id="440f4-149">Use la ficha **General** para ver o cambiar la información básica sobre el usuario de correo.</span><span class="sxs-lookup"><span data-stu-id="440f4-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="440f4-150">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="440f4-150">**First name**</span></span>

- <span data-ttu-id="440f4-151">**Iniciales**</span><span class="sxs-lookup"><span data-stu-id="440f4-151">**Initials**</span></span>

- <span data-ttu-id="440f4-152">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="440f4-152">**Last name**</span></span>

- <span data-ttu-id="440f4-153">**Nombre para mostrar**: este nombre aparece en la libreta de direcciones de la organización, en las líneas para: y de: del correo electrónico, y en la lista de contactos del EAC.</span><span class="sxs-lookup"><span data-stu-id="440f4-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="440f4-154">Este nombre no puede contener espacios en blanco antes o después del nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="440f4-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="440f4-155">**User ID**: es la cuenta de usuario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="440f4-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="440f4-156">Este valor no se puede modificar aquí.</span><span class="sxs-lookup"><span data-stu-id="440f4-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="440f4-157">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="440f4-157">Contact information</span></span>

<span data-ttu-id="440f4-158">Use la ficha **información de contacto** para ver o cambiar la información de contacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="440f4-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="440f4-159">La información de esta página se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="440f4-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="440f4-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="440f4-160">**Street**</span></span>
- <span data-ttu-id="440f4-161">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="440f4-161">**City**</span></span>
- <span data-ttu-id="440f4-162">**Estado o provincia**</span><span class="sxs-lookup"><span data-stu-id="440f4-162">**State/Province**</span></span>
- <span data-ttu-id="440f4-163">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="440f4-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="440f4-164">**País o región**</span><span class="sxs-lookup"><span data-stu-id="440f4-164">**Country/Region**</span></span>
- <span data-ttu-id="440f4-165">**Teléfono del trabajo**</span><span class="sxs-lookup"><span data-stu-id="440f4-165">**Work phone**</span></span>
- <span data-ttu-id="440f4-166">**Teléfono móvil**</span><span class="sxs-lookup"><span data-stu-id="440f4-166">**Mobile phone**</span></span>
- <span data-ttu-id="440f4-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="440f4-167">**Fax**</span></span>
- <span data-ttu-id="440f4-168">**Más opciones**</span><span class="sxs-lookup"><span data-stu-id="440f4-168">**More options**</span></span>

  - <span data-ttu-id="440f4-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="440f4-169">**Office**</span></span>
  - <span data-ttu-id="440f4-170">**Teléfono particular**</span><span class="sxs-lookup"><span data-stu-id="440f4-170">**Home phone**</span></span>
  - <span data-ttu-id="440f4-171">**Página web   **</span><span class="sxs-lookup"><span data-stu-id="440f4-171">**Web page**</span></span>
  - <span data-ttu-id="440f4-172">**Notas**</span><span class="sxs-lookup"><span data-stu-id="440f4-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="440f4-173">Organización</span><span class="sxs-lookup"><span data-stu-id="440f4-173">Organization</span></span>

<span data-ttu-id="440f4-174">Use la pestaña **organización** para registrar información detallada sobre el rol del usuario en la organización.</span><span class="sxs-lookup"><span data-stu-id="440f4-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="440f4-175">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="440f4-175">**Title**</span></span>
- <span data-ttu-id="440f4-176">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="440f4-176">**Department**</span></span>
- <span data-ttu-id="440f4-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="440f4-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="440f4-178">Usar el EAC para quitar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="440f4-179">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="440f4-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="440f4-180">Seleccione el usuario de correo que desea quitar y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="440f4-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="440f4-181">Usar PowerShell para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="440f4-182">Usar PowerShell independiente de EOP para ver los usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="440f4-183">Para devolver una lista de Resumen de todos los usuarios de correo en EOP independiente, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="440f4-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="440f4-184">Para ver información detallada sobre un usuario de correo específico, reemplace \<MailUserIdentity\> por el nombre, el alias o el nombre de cuenta del usuario de correo y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="440f4-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="440f4-185">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) y [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="440f4-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="440f4-186">Usar PowerShell independiente de EOP para crear usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="440f4-187">Para crear usuarios de correo en un PowerShell de EOP independiente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="440f4-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="440f4-188">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="440f4-188">**Notes**:</span></span>

- <span data-ttu-id="440f4-189">El parámetro _Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="440f4-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="440f4-190">Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="440f4-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="440f4-191">Si no usa el parámetro _alias_ , el lado izquierdo del parámetro _MicrosoftOnlineServicesID_ se usa para el alias.</span><span class="sxs-lookup"><span data-stu-id="440f4-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="440f4-192">Si no usa el parámetro _ExternalEmailAddress_ , el valor _MicrosoftOnlineServicesID_ se usa para la dirección de correo electrónico externa.</span><span class="sxs-lookup"><span data-stu-id="440f4-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="440f4-193">En este ejemplo se crea un usuario de correo con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="440f4-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="440f4-194">El nombre es JeffreyZeng y el nombre para mostrar es Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="440f4-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="440f4-195">El nombre es Jeffrey y el apellido es Zeng.</span><span class="sxs-lookup"><span data-stu-id="440f4-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="440f4-196">El alias es jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="440f4-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="440f4-197">La dirección de correo electrónico externa es jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="440f4-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="440f4-198">El nombre de la cuenta es jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="440f4-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="440f4-199">La contraseña es Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="440f4-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="440f4-200">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="440f4-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="440f4-201">Usar PowerShell independiente de EOP para modificar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="440f4-202">Para modificar los usuarios de correo existentes en PowerShell de EOP independiente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="440f4-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="440f4-203">Este ejemplo establece la dirección de correo electrónico externa de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="440f4-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="440f4-204">Este ejemplo establece la propiedad de la empresa para todos los usuarios de correo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="440f4-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="440f4-205">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="440f4-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="440f4-206">Usar PowerShell independiente de EOP para quitar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="440f4-207">Para quitar usuarios de correo en un PowerShell de EOP independiente, reemplace \<MailUserIdentity\> por el nombre, el alias o el nombre de cuenta del usuario de correo y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="440f4-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="440f4-208">En este ejemplo se quita el usuario de correo de Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="440f4-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="440f4-209">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="440f4-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="440f4-210">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="440f4-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="440f4-211">Para comprobar que los usuarios de correo se han creado, modificado o quitado correctamente en EOP independiente, use uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="440f4-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="440f4-212">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="440f4-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="440f4-213">Compruebe que el usuario de correo aparece (o no aparece en la lista).</span><span class="sxs-lookup"><span data-stu-id="440f4-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="440f4-214">Seleccione el usuario de correo y vea la información en el panel de detalles o haga clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-AddIcon.png) para ver la configuración.</span><span class="sxs-lookup"><span data-stu-id="440f4-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="440f4-215">En PowerShell independiente de EOP, ejecute el siguiente comando para comprobar que el usuario de correo aparece (o no aparece en la lista):</span><span class="sxs-lookup"><span data-stu-id="440f4-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="440f4-216">Reemplace \<MailUserIdentity\> por el nombre, el alias o el nombre de cuenta del usuario de correo y ejecute los siguientes comandos para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="440f4-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="440f4-217">Usar la sincronización de directorios para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="440f4-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="440f4-218">En EOP independiente, la sincronización de directorios está disponible para los clientes con Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="440f4-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="440f4-219">Puede sincronizar esas cuentas con Azure Active Directory (Azure AD), donde las copias de las cuentas se almacenan en la nube.</span><span class="sxs-lookup"><span data-stu-id="440f4-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="440f4-220">Al sincronizar las cuentas de usuario existentes con Azure Active Directory, puede ver a esos usuarios en el panel **destinatarios** del centro de administración de Exchange (EAC) o en un PowerShell independiente de EOP.</span><span class="sxs-lookup"><span data-stu-id="440f4-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="440f4-221">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="440f4-221">**Notes**:</span></span>

- <span data-ttu-id="440f4-222">Si usa la sincronización de directorios para administrar los destinatarios, puede seguir agregando y administrando usuarios en el centro de administración de Microsoft 365, pero no se sincronizarán con Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="440f4-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="440f4-223">Esto se debe a que la sincronización de directorios solo sincroniza los destinatarios de Active Directory local con la nube.</span><span class="sxs-lookup"><span data-stu-id="440f4-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="440f4-224">Se recomienda usar la sincronización de directorios con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="440f4-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="440f4-225">Listas de remitentes **seguros de Outlook y listas de remitentes bloqueados**: cuando se sincronizan con el servicio, estas listas tienen prioridad sobre el filtrado de correo no deseado en el servicio.</span><span class="sxs-lookup"><span data-stu-id="440f4-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="440f4-226">Esto permite a los usuarios administrar su propia lista de remitentes seguros y la lista de remitentes bloqueados con entradas individuales de remitente y dominio.</span><span class="sxs-lookup"><span data-stu-id="440f4-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="440f4-227">Para más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="440f4-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="440f4-228">**Bloqueo perimetral basado en directorios (DBEB)**: para obtener más información sobre DBEB, vea [use Directory based Edge blocking to Reject messages sent to invalid Recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="440f4-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="440f4-229">**Acceso de usuario final a cuarentena**: para obtener acceso a los mensajes en cuarentena, los destinatarios deben tener un identificador de usuario y una contraseña válidos en el servicio.</span><span class="sxs-lookup"><span data-stu-id="440f4-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="440f4-230">Para obtener más información acerca de la cuarentena, vea [Buscar y liberar mensajes en cuarentena como un usuario](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span><span class="sxs-lookup"><span data-stu-id="440f4-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="440f4-231">**Reglas de flujo de correo (también conocidas como reglas de transporte)**: cuando se usa la sincronización de directorios, los usuarios y grupos existentes de Active Directory se cargan automáticamente en la nube y, a continuación, se pueden crear reglas de flujo de correo dirigidas a usuarios o grupos específicos sin tener que agregarlos manualmente en el servicio.</span><span class="sxs-lookup"><span data-stu-id="440f4-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="440f4-232">Tenga en cuenta que los [grupos de distribución dinámicos](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) no se pueden sincronizar mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="440f4-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="440f4-233">Obtenga los permisos necesarios y prepárese para la sincronización de directorios, tal como se describe en [¿Qué es la identidad híbrida con Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="440f4-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="440f4-234">Sincronización de directorios con Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="440f4-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="440f4-235">Active la sincronización de directorios como se describe en [Azure ad Connect Sync: comprender y personalizar la sincronización](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="440f4-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="440f4-236">Instale y configure un equipo local para ejecutar la conexión de AAD como se describe en [requisitos previos para Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="440f4-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="440f4-237">[Seleccione el tipo de instalación que se va a usar para Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="440f4-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="440f4-238">Exprés</span><span class="sxs-lookup"><span data-stu-id="440f4-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="440f4-239">Personalizados</span><span class="sxs-lookup"><span data-stu-id="440f4-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="440f4-240">Autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="440f4-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="440f4-p121">Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory. Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local. Para que la sincronización de directorios se realice correctamente, debe asegurarse de que el TCP 443 esté abierto en el servidor de sincronización de directorios local.</span><span class="sxs-lookup"><span data-stu-id="440f4-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="440f4-244">Una vez configurada la sincronización, asegúrese de comprobar que AAD Connect se está sincronizando correctamente.</span><span class="sxs-lookup"><span data-stu-id="440f4-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="440f4-245">En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.</span><span class="sxs-lookup"><span data-stu-id="440f4-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
