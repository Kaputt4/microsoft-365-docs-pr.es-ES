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
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Obtenga información sobre cómo administrar usuarios de correo en Exchange Online Protection (EOP), incluido el uso de la sincronización de directorios, EAC y PowerShell para administrar usuarios.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910623"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="c4f94-103">Administrar usuarios de correo en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="c4f94-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c4f94-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c4f94-104">**Applies to**</span></span>
-  [<span data-ttu-id="c4f94-105">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="c4f94-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="c4f94-106">En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los usuarios de correo son el tipo fundamental de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c4f94-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="c4f94-107">Un usuario de correo tiene credenciales de cuenta en la organización independiente de EOP y puede tener acceso a recursos (tener permisos asignados).</span><span class="sxs-lookup"><span data-stu-id="c4f94-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="c4f94-108">La dirección de correo electrónico de un usuario de correo es externa (por ejemplo, en el entorno de correo electrónico local).</span><span class="sxs-lookup"><span data-stu-id="c4f94-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="c4f94-109">Al crear un usuario de correo, la cuenta de usuario correspondiente está disponible en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f94-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c4f94-110">Al crear una cuenta de usuario en el Centro de administración de Microsoft 365, no puede usar esa cuenta para crear un usuario de correo.</span><span class="sxs-lookup"><span data-stu-id="c4f94-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="c4f94-111">El método recomendado para crear y administrar usuarios de correo en [](#use-directory-synchronization-to-manage-mail-users) EOP independiente es usar la sincronización de directorios como se describe en la sección Usar sincronización de directorios para administrar usuarios de correo más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c4f94-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="c4f94-112">Para organizaciones EOP independientes con un número reducido de usuarios, puede agregar y administrar usuarios de correo en el Centro de administración de Exchange (EAC) o en PowerShell de EOP independiente, como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c4f94-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c4f94-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="c4f94-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c4f94-114">Para abrir el Centro de administración de Exchange (EAC), vea Centro de [administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c4f94-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c4f94-115">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="c4f94-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c4f94-116">Al crear usuarios de correo en PowerShell de EOP, es posible que encuentre limitación.</span><span class="sxs-lookup"><span data-stu-id="c4f94-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="c4f94-117">Además, los cmdlets de PowerShell de EOP usan un método de procesamiento por lotes que da como resultado un retraso de propagación de unos minutos antes de que los resultados de los comandos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="c4f94-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="c4f94-118">Debe tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c4f94-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="c4f94-119">En concreto, necesita los roles Creación de destinatarios de correo **(crear)** y Destinatarios de correo **(modificar),** que se asignan a los grupos de roles Administración de la organización **(administradores** globales) y Administración de destinatarios de forma predeterminada. </span><span class="sxs-lookup"><span data-stu-id="c4f94-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="c4f94-120">Para obtener más información, vea [Permissions in standalone EOP](feature-permissions-in-eop.md) y [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="c4f94-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="c4f94-121">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, vea [Métodos abreviados](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="c4f94-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c4f94-122">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="c4f94-122">Having problems?</span></span> <span data-ttu-id="c4f94-123">Solicite ayuda en los foros de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4f94-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="c4f94-124">Visite el foro [de Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="c4f94-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="c4f94-125">Usar el Centro de administración de Exchange para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="c4f94-126">Usar el EAC para crear usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="c4f94-127">En el EAC, vaya a **Contactos de** \> **destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c4f94-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="c4f94-128">Haga **clic en Nuevo** icono Nuevo ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="c4f94-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c4f94-129">En la **página Nuevo usuario de** correo que se abre, configure las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="c4f94-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="c4f94-130">Se requiere una configuración <sup>\*</sup> marcada con una.</span><span class="sxs-lookup"><span data-stu-id="c4f94-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="c4f94-131">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c4f94-131">**First name**</span></span>

   - <span data-ttu-id="c4f94-132">**Iniciales:** inicial media de la persona.</span><span class="sxs-lookup"><span data-stu-id="c4f94-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="c4f94-133">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="c4f94-133">**Last name**</span></span>

   - <span data-ttu-id="c4f94-134"><sup>\*</sup>**Nombre para** mostrar: De forma predeterminada, este cuadro muestra los valores de los cuadros **Nombre,** **Iniciales** y **Apellidos.**</span><span class="sxs-lookup"><span data-stu-id="c4f94-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="c4f94-135">Puede aceptar este valor o cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="c4f94-135">You can accept this value or change it.</span></span> <span data-ttu-id="c4f94-136">El valor debe ser único y tiene una longitud máxima de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="c4f94-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="c4f94-137"><sup>\*</sup>**Alias:** escriba un alias único, con hasta 64 caracteres, para el usuario</span><span class="sxs-lookup"><span data-stu-id="c4f94-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="c4f94-138">**Dirección de correo electrónico externa:** escriba la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="c4f94-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="c4f94-139">El dominio debe ser externo a la organización basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="c4f94-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="c4f94-140"><sup>\*</sup>**Id. de** usuario: escriba la cuenta que usará la persona para iniciar sesión en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c4f94-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="c4f94-141">El identificador de usuario consta de un nombre de usuario en el lado izquierdo del símbolo at (@) (@) y un dominio en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="c4f94-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="c4f94-142"><sup>\*</sup>**Nueva contraseña y** <sup>\*</sup> **Confirmar contraseña:** escriba y vuelva a escribir la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c4f94-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="c4f94-143">Compruebe que la contraseña cumple con los requisitos de longitud, complejidad e historial de la contraseña de su organización.</span><span class="sxs-lookup"><span data-stu-id="c4f94-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="c4f94-144">Cuando haya terminado, haga clic en **Guardar** para crear el usuario de correo.</span><span class="sxs-lookup"><span data-stu-id="c4f94-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="c4f94-145">Usar el EAC para modificar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="c4f94-146">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="c4f94-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="c4f94-147">Seleccione el usuario de correo que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="c4f94-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="c4f94-148">En la página de propiedades de usuario de correo que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c4f94-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="c4f94-149">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c4f94-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="c4f94-150">General</span><span class="sxs-lookup"><span data-stu-id="c4f94-150">General</span></span>

<span data-ttu-id="c4f94-151">Use la **pestaña General** para ver o cambiar la información básica sobre el usuario de correo.</span><span class="sxs-lookup"><span data-stu-id="c4f94-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="c4f94-152">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c4f94-152">**First name**</span></span>

- <span data-ttu-id="c4f94-153">**Iniciales**</span><span class="sxs-lookup"><span data-stu-id="c4f94-153">**Initials**</span></span>

- <span data-ttu-id="c4f94-154">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="c4f94-154">**Last name**</span></span>

- <span data-ttu-id="c4f94-155">**Nombre para** mostrar: este nombre aparece en la libreta de direcciones de la organización, en las líneas Para: y De: en el correo electrónico y en la lista de contactos del EAC.</span><span class="sxs-lookup"><span data-stu-id="c4f94-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="c4f94-156">Este nombre no puede contener espacios en blanco antes o después del nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="c4f94-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="c4f94-157">**Id. de** usuario: esta es la cuenta del usuario en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f94-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="c4f94-158">No puede modificar este valor aquí.</span><span class="sxs-lookup"><span data-stu-id="c4f94-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="c4f94-159">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="c4f94-159">Contact information</span></span>

<span data-ttu-id="c4f94-160">Use la **pestaña Información de** contacto para ver o cambiar la información de contacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="c4f94-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="c4f94-161">La información de esta página se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="c4f94-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="c4f94-162">**Calle**</span><span class="sxs-lookup"><span data-stu-id="c4f94-162">**Street**</span></span>
- <span data-ttu-id="c4f94-163">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="c4f94-163">**City**</span></span>
- <span data-ttu-id="c4f94-164">**Estado o provincia**</span><span class="sxs-lookup"><span data-stu-id="c4f94-164">**State/Province**</span></span>
- <span data-ttu-id="c4f94-165">**CÓDIGO POSTAL/POSTAL**</span><span class="sxs-lookup"><span data-stu-id="c4f94-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="c4f94-166">**País o región**</span><span class="sxs-lookup"><span data-stu-id="c4f94-166">**Country/Region**</span></span>
- <span data-ttu-id="c4f94-167">**Teléfono de trabajo**</span><span class="sxs-lookup"><span data-stu-id="c4f94-167">**Work phone**</span></span>
- <span data-ttu-id="c4f94-168">**Teléfono móvil**</span><span class="sxs-lookup"><span data-stu-id="c4f94-168">**Mobile phone**</span></span>
- <span data-ttu-id="c4f94-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="c4f94-169">**Fax**</span></span>
- <span data-ttu-id="c4f94-170">**Más opciones**</span><span class="sxs-lookup"><span data-stu-id="c4f94-170">**More options**</span></span>

  - <span data-ttu-id="c4f94-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="c4f94-171">**Office**</span></span>
  - <span data-ttu-id="c4f94-172">**Teléfono principal**</span><span class="sxs-lookup"><span data-stu-id="c4f94-172">**Home phone**</span></span>
  - <span data-ttu-id="c4f94-173">**Página web**</span><span class="sxs-lookup"><span data-stu-id="c4f94-173">**Web page**</span></span>
  - <span data-ttu-id="c4f94-174">**Notas**</span><span class="sxs-lookup"><span data-stu-id="c4f94-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="c4f94-175">Organización</span><span class="sxs-lookup"><span data-stu-id="c4f94-175">Organization</span></span>

<span data-ttu-id="c4f94-176">Use la **pestaña Organización** para registrar información detallada sobre el rol del usuario en la organización.</span><span class="sxs-lookup"><span data-stu-id="c4f94-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="c4f94-177">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="c4f94-177">**Title**</span></span>
- <span data-ttu-id="c4f94-178">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="c4f94-178">**Department**</span></span>
- <span data-ttu-id="c4f94-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="c4f94-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="c4f94-180">Usar el EAC para quitar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="c4f94-181">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="c4f94-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="c4f94-182">Seleccione el usuario de correo que desea quitar y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="c4f94-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="c4f94-183">Usar PowerShell para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="c4f94-184">Usar PowerShell de EOP independiente para ver usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="c4f94-185">Para devolver una lista resumida de todos los usuarios de correo en PowerShell de EOP independiente, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c4f94-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="c4f94-186">Para ver información detallada sobre un usuario de correo específico, reemplace por el nombre, alias o nombre de cuenta del usuario de correo \<MailUserIdentity\> y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="c4f94-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="c4f94-187">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-Recipient](/powershell/module/exchange/get-recipient) y [Get-User](/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="c4f94-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="c4f94-188">Usar PowerShell de EOP independiente para crear usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="c4f94-189">Para crear usuarios de correo en PowerShell de EOP independiente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c4f94-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="c4f94-190">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="c4f94-190">**Notes**:</span></span>

- <span data-ttu-id="c4f94-191">El _parámetro Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="c4f94-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="c4f94-192">Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="c4f94-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="c4f94-193">Si no usa el parámetro _Alias,_ se usa el lado izquierdo del parámetro _MicrosoftOnlineServicesID_ para el alias.</span><span class="sxs-lookup"><span data-stu-id="c4f94-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="c4f94-194">Si no usa el parámetro _ExternalEmailAddress,_ se usará el valor _MicrosoftOnlineServicesID_ para la dirección de correo electrónico externa.</span><span class="sxs-lookup"><span data-stu-id="c4f94-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="c4f94-195">En este ejemplo se crea un usuario de correo con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="c4f94-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="c4f94-196">El nombre es JeffreyZeng y el nombre para mostrar es Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="c4f94-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="c4f94-197">El nombre es Jeffrey y el apellido es Zeng.</span><span class="sxs-lookup"><span data-stu-id="c4f94-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="c4f94-198">El alias es jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="c4f94-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="c4f94-199">La dirección de correo electrónico externa es jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="c4f94-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="c4f94-200">El nombre de cuenta es jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="c4f94-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="c4f94-201">La contraseña es Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="c4f94-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="c4f94-202">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="c4f94-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="c4f94-203">Usar PowerShell de EOP independiente para modificar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="c4f94-204">Para modificar los usuarios de correo existentes en PowerShell de EOP independiente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c4f94-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="c4f94-205">Este ejemplo establece la dirección de correo electrónico externa de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="c4f94-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="c4f94-206">Este ejemplo establece la propiedad de la empresa para todos los usuarios de correo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="c4f94-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="c4f94-207">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="c4f94-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="c4f94-208">Usar PowerShell de EOP independiente para quitar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="c4f94-209">Para quitar usuarios de correo en PowerShell de EOP independiente, reemplace por el nombre, alias o nombre de cuenta del usuario de correo \<MailUserIdentity\> y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c4f94-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="c4f94-210">En este ejemplo se quita el usuario de correo de Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="c4f94-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="c4f94-211">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="c4f94-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c4f94-212">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="c4f94-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="c4f94-213">Para comprobar que ha creado, modificado o quitado correctamente usuarios de correo en EOP independiente, use cualquiera de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c4f94-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="c4f94-214">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="c4f94-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="c4f94-215">Compruebe que el usuario de correo aparece (o no aparece).</span><span class="sxs-lookup"><span data-stu-id="c4f94-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="c4f94-216">Seleccione el usuario de correo y vea la información en el panel Detalles o haga clic **en Editar** icono Editar para ver ![ la ](../../media/ITPro-EAC-AddIcon.png) configuración.</span><span class="sxs-lookup"><span data-stu-id="c4f94-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="c4f94-217">En PowerShell de EOP independiente, ejecute el siguiente comando para comprobar que el usuario de correo aparece (o no aparece):</span><span class="sxs-lookup"><span data-stu-id="c4f94-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="c4f94-218">Reemplace por el nombre, alias o nombre de cuenta del usuario de correo \<MailUserIdentity\> y ejecute los siguientes comandos para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="c4f94-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="c4f94-219">Usar la sincronización de directorios para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="c4f94-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="c4f94-220">En EOP independiente, la sincronización de directorios está disponible para clientes con Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="c4f94-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="c4f94-221">Puede sincronizar esas cuentas con Azure Active Directory (Azure AD), donde las copias de las cuentas se almacenan en la nube.</span><span class="sxs-lookup"><span data-stu-id="c4f94-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="c4f94-222">Al sincronizar las cuentas de usuario existentes con Azure  Active Directory, puede ver esos usuarios en el panel Destinatarios del Centro de administración de Exchange (EAC) o en PowerShell independiente de EOP.</span><span class="sxs-lookup"><span data-stu-id="c4f94-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="c4f94-223">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="c4f94-223">**Notes**:</span></span>

- <span data-ttu-id="c4f94-224">Si usa la sincronización de directorios para administrar los destinatarios, todavía puede agregar y administrar usuarios en el Centro de administración de Microsoft 365, pero no se sincronizarán con su Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="c4f94-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="c4f94-225">Esto se debe a que la sincronización de directorios solo sincroniza destinatarios de su Active Directory local con la nube.</span><span class="sxs-lookup"><span data-stu-id="c4f94-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="c4f94-226">Se recomienda usar la sincronización de directorios para su uso con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="c4f94-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="c4f94-227">**Listas de remitentes seguros de Outlook** y listas de remitentes bloqueados: cuando se sincronizan con el servicio, estas listas tendrán prioridad sobre el filtrado de correo no deseado en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c4f94-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="c4f94-228">Esto permite a los usuarios administrar su propia lista de remitentes seguros y la lista de remitentes bloqueados con entradas individuales de remitente y dominio.</span><span class="sxs-lookup"><span data-stu-id="c4f94-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="c4f94-229">Para más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="c4f94-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="c4f94-230">**Bloqueo perimetral basado en directorios (DBEB):** para obtener más información acerca de DBEB, vea Usar el bloqueo perimetral basado en directorios para rechazar mensajes [enviados a destinatarios no válidos.](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="c4f94-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="c4f94-231">**Acceso de usuario final** a cuarentena: para obtener acceso a sus mensajes en cuarentena, los destinatarios deben tener un identificador de usuario y una contraseña válidos en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c4f94-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="c4f94-232">Para obtener más información acerca de la cuarentena, vea Buscar y liberar mensajes [en cuarentena como usuario.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="c4f94-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="c4f94-233">Reglas de flujo de correo (también conocidas como reglas de **transporte):** al usar la sincronización de directorios, los usuarios y grupos de Active Directory existentes se cargan automáticamente en la nube y, a continuación, puede crear reglas de flujo de correo destinadas a usuarios o grupos específicos sin tener que agregarlos manualmente al servicio.</span><span class="sxs-lookup"><span data-stu-id="c4f94-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="c4f94-234">Tenga en cuenta que los [grupos de distribución dinámicos](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) no se pueden sincronizar mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="c4f94-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="c4f94-235">Obtenga los permisos necesarios y prepárese para la sincronización de directorios, como se describe en ¿Qué es la identidad [híbrida con Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="c4f94-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="c4f94-236">Sincronizar directorios con Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="c4f94-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="c4f94-237">Activar la sincronización de directorios como se describe en [Sincronización de Azure AD Connect: Comprender y personalizar la sincronización.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="c4f94-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="c4f94-238">Instale y configure un equipo local para ejecutar AAD Connect como se describe en [Requisitos previos para Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c4f94-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="c4f94-239">[Seleccione el tipo de instalación que se va a usar para Azure AD Connect:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="c4f94-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="c4f94-240">Express</span><span class="sxs-lookup"><span data-stu-id="c4f94-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="c4f94-241">Personalizados</span><span class="sxs-lookup"><span data-stu-id="c4f94-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="c4f94-242">Autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="c4f94-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="c4f94-p121">Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory. Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local. Para que la sincronización de directorios se realice correctamente, debe asegurarse de que el TCP 443 esté abierto en el servidor de sincronización de directorios local.</span><span class="sxs-lookup"><span data-stu-id="c4f94-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="c4f94-246">Después de configurar la sincronización, asegúrese de comprobar que AAD Connect se está sincronizando correctamente.</span><span class="sxs-lookup"><span data-stu-id="c4f94-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="c4f94-247">En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.</span><span class="sxs-lookup"><span data-stu-id="c4f94-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>