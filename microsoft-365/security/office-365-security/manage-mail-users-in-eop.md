---
title: Administrar usuarios de correo en EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP).
ms.openlocfilehash: 065fdae30dea49220c10fd455b7ac346e70c18de
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871776"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="58d8e-103">Administrar usuarios de correo en EOP</span><span class="sxs-lookup"><span data-stu-id="58d8e-103">Manage mail users in EOP</span></span>

<span data-ttu-id="58d8e-p101">La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP). Hay varios métodos para administrar usuarios en EOP:</span><span class="sxs-lookup"><span data-stu-id="58d8e-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>

- <span data-ttu-id="58d8e-p102">**Usar la sincronización de directorios para administrar usuarios de correo**: si su empresa tiene cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizarlas con Azure Active Directory (AD), donde se almacena una copia de las cuentas en la nube. Cuando sincroniza las cuentas de usuario existentes con Azure Active Directory, puede ver esos usuarios en el panel **Destinatarios** del Centro de administración de Exchange (EAC). Se recomienda usar la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="58d8e-p102">**Use directory synchronization to manage mail users**: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud. When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC). Using directory synchronization is recommended.</span></span>

- <span data-ttu-id="58d8e-p103">**Usar el EAC para administrar usuarios de correo**: agregar y administrar usuarios de correo directamente en el EAC. Es la manera más fácil de agregar usuarios de correo y resulta útil para agregar un usuario cada vez.</span><span class="sxs-lookup"><span data-stu-id="58d8e-p103">**Use the EAC to manage mail users**: Add and manage mail users directly in the EAC. This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="58d8e-111">**Usar PowerShell para administrar usuarios de correo**: agregar y administrar usuarios de correo mediante PowerShell de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="58d8e-111">**Use PowerShell to manage mail users**: Add and manage mail users by in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="58d8e-112">Este método es útil para agregar varios registros y crear scripts.</span><span class="sxs-lookup"><span data-stu-id="58d8e-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="58d8e-113">Puede Agregar usuarios en el centro de administración de Microsoft 365, pero estos usuarios no se pueden usar como destinatarios de correo.</span><span class="sxs-lookup"><span data-stu-id="58d8e-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="58d8e-114">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="58d8e-114">Before you begin</span></span>

- <span data-ttu-id="58d8e-115">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="58d8e-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="58d8e-p105">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="58d8e-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="58d8e-118">Tenga en cuenta que al crear usuarios de correo mediante los cmdlets de PowerShell de Exchange Online Protection, es posible que se encuentre con limitaciones.</span><span class="sxs-lookup"><span data-stu-id="58d8e-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="58d8e-119">Los comandos de PowerShell de este tema usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="58d8e-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="58d8e-120">Para aprender a usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Conectarse a Exchange Online Protection con PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="58d8e-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="58d8e-121">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="58d8e-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="58d8e-122">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="58d8e-122">Having problems?</span></span> <span data-ttu-id="58d8e-123">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="58d8e-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="58d8e-124">Usar la sincronización de directorios para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="58d8e-125">En esta sección se proporciona información sobre cómo administrar usuarios de correo mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="58d8e-125">This section provides information about managing email users by using directory synchronization.</span></span>

<span data-ttu-id="58d8e-126">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="58d8e-126">**Notes**:</span></span>

- <span data-ttu-id="58d8e-127">Si usa la sincronización de directorios para administrar los destinatarios, puede seguir agregando y administrando usuarios en el centro de administración de Microsoft 365, pero no se sincronizarán con Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="58d8e-127">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="58d8e-128">Esto se debe **a que** la sincronización de directorios solo sincroniza los destinatarios **de** Active Directory local con la nube.</span><span class="sxs-lookup"><span data-stu-id="58d8e-128">This is because directory synchronization only syncs recipients **from** your on-premises Active Directory **to** the cloud.</span></span>

- <span data-ttu-id="58d8e-129">Se recomienda usar la sincronización de directorios con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="58d8e-129">Directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="58d8e-130">**Remitente seguro de Outlook y listas de remitentes bloqueados**: cuando se sincronizan con el servicio, estas listas tienen prioridad sobre el filtrado de correo no deseado en el servicio.</span><span class="sxs-lookup"><span data-stu-id="58d8e-130">**Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="58d8e-131">Esto permite a los usuarios administrar sus propias listas de remitentes seguros y remitentes bloqueados por usuario o por dominio.</span><span class="sxs-lookup"><span data-stu-id="58d8e-131">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span>

  - <span data-ttu-id="58d8e-132">**Bloqueo perimetral basado en directorios (DBEB)**: para obtener más información sobre DBEB, vea [use Directory based Edge blocking to Reject messages sent to invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="58d8e-132">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="58d8e-133">**Cuarentena de correo no deseado del usuario final**: para poder obtener acceso a la cuarentena de correo no deseado del usuario final, los usuarios finales deben tener un identificador de usuario y una contraseña válidos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="58d8e-133">**End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="58d8e-134">Los clientes de EOP que protejan los buzones locales deben ser usuarios de correo electrónico válidos.</span><span class="sxs-lookup"><span data-stu-id="58d8e-134">EOP customers protecting on-premises mailboxes must be valid email users.</span></span>

  - <span data-ttu-id="58d8e-135">**Reglas de flujo de correo**: cuando se usa la sincronización de directorios, los usuarios y grupos de Active Directory existentes se cargan automáticamente en la nube y, a continuación, se pueden crear reglas de flujo de correo (también conocidas como reglas de transporte) dirigidas a usuarios o grupos específicos sin tener que agregarlos manualmente a través del EAC o de PowerShell de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="58d8e-135">**Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="58d8e-136">Tenga en cuenta que los [grupos de distribución dinámicos](https://go.microsoft.com/fwlink/?LinkId=507569) no se pueden sincronizar mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="58d8e-136">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="58d8e-137">Obtenga los permisos necesarios y prepárese para la sincronización de directorios, tal como se describe en [Preparar la sincronización de directorios](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span><span class="sxs-lookup"><span data-stu-id="58d8e-137">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="58d8e-138">Para sincronizar los directorios de usuario con Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="58d8e-138">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="58d8e-139">Para sincronizar los usuarios con Azure Active Directory (AAD), primero tiene que **activar la sincronización de directorios**, tal como se describe en activar la sincronización de [directorios](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span><span class="sxs-lookup"><span data-stu-id="58d8e-139">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>

<span data-ttu-id="58d8e-140">A continuación se encuentra la instalación y la configuración de un equipo local para ejecutar AAD Connect (si todavía no tiene una, merece la pena comprobar por adelantado el tiempo).</span><span class="sxs-lookup"><span data-stu-id="58d8e-140">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="58d8e-141">El tema de [configuración de AAD Connect, la forma exprés](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) le indica cómo configurar y sincronizar sus cuentas de local a Azure ad con AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="58d8e-141">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="58d8e-142">Pero, antes de hacerlo, asegúrese de que [cumple los requisitos previos](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)y [Elija el tipo de instalación](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="58d8e-142">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="58d8e-143">El vínculo anterior es un breve artículo para instalaciones rápidas.</span><span class="sxs-lookup"><span data-stu-id="58d8e-143">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="58d8e-144">También puede encontrar artículos en [instalaciones personalizadas](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)o [la autenticación de paso a través](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) si es necesario.</span><span class="sxs-lookup"><span data-stu-id="58d8e-144">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58d8e-p113">Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory. Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local. Para que la sincronización de directorios se realice correctamente, debe asegurarse de que el TCP 443 esté abierto en el servidor de sincronización de directorios local.</span><span class="sxs-lookup"><span data-stu-id="58d8e-p113">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="58d8e-148">Una vez configurada la sincronización, asegúrese de comprobar que EOP se está sincronizando correctamente.</span><span class="sxs-lookup"><span data-stu-id="58d8e-148">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="58d8e-149">En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.</span><span class="sxs-lookup"><span data-stu-id="58d8e-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="58d8e-150">Usar el EAC para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-150">Use the EAC to manage mail users</span></span>

<span data-ttu-id="58d8e-151">En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo electrónico directamente en el EAC.</span><span class="sxs-lookup"><span data-stu-id="58d8e-151">This section provides information about adding and managing email users directly in the EAC.</span></span>

### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="58d8e-152">Usar el EAC para agregar un usuario de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-152">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="58d8e-153">Para crear un usuario de correo electrónico, vaya a **Destinatarios**\> **Contactos** en el EAC y después haga clic en **Nuevo +**.</span><span class="sxs-lookup"><span data-stu-id="58d8e-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="58d8e-154">En la página **Nuevo usuario de correo**, escriba la información del usuario, incluido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="58d8e-154">On the **New mail user** page, enter the user's information, including the following:</span></span>

   ****

   |<span data-ttu-id="58d8e-155">**Propiedad de usuario de correo**</span><span class="sxs-lookup"><span data-stu-id="58d8e-155">**Mail user property**</span></span>|<span data-ttu-id="58d8e-156">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="58d8e-156">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="58d8e-157">**Nombre**, **Iniciales** y **Apellidos**</span><span class="sxs-lookup"><span data-stu-id="58d8e-157">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="58d8e-158">Escriba el nombre completo del usuario en los cuadros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="58d8e-158">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="58d8e-159">**Nombre para mostrar**</span><span class="sxs-lookup"><span data-stu-id="58d8e-159">**Display name**</span></span>|<span data-ttu-id="58d8e-p115">Escriba un nombre con un máximo de 64 caracteres. De manera predeterminada, este cuadro muestra los nombres en los cuadros **Nombre**, **Iniciales** y **Apellidos** si hay alguno. El nombre para mostrar es un campo obligatorio.  </span><span class="sxs-lookup"><span data-stu-id="58d8e-p115">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="58d8e-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="58d8e-163">**Alias**</span></span>|<span data-ttu-id="58d8e-p116">Escriba un alias exclusivo, con un máximo de 64 caracteres, para el usuario. El alias es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="58d8e-p116">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="58d8e-166">**Dirección de correo electrónico externa**</span><span class="sxs-lookup"><span data-stu-id="58d8e-166">**External email address**</span></span>|<span data-ttu-id="58d8e-167">Escriba la dirección de correo electrónico externa del usuario.</span><span class="sxs-lookup"><span data-stu-id="58d8e-167">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="58d8e-168">**Id. de usuario**</span><span class="sxs-lookup"><span data-stu-id="58d8e-168">**User id**</span></span>|<span data-ttu-id="58d8e-p117">Escriba el nombre que el usuario de correo usará para iniciar sesión en el servicio. El nombre de inicio de sesión del usuario consta de un nombre de usuario a la izquierda del símbolo arroba (@) y un sufijo a la derecha. Por lo general, el sufijo es el nombre de dominio en el que reside la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="58d8e-p117">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="58d8e-172">**Contraseña nueva**</span><span class="sxs-lookup"><span data-stu-id="58d8e-172">**New password**</span></span>|<span data-ttu-id="58d8e-p118">Escriba la contraseña que el usuario de correo usará para iniciar sesión en el servicio. Asegúrese de que la contraseña que proporciona cumple los requisitos de longitud, complejidad e historial de la contraseña del dominio en el que va a crear la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="58d8e-p118">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="58d8e-175">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="58d8e-175">**Confirm password**</span></span>|<span data-ttu-id="58d8e-176">Vuelva a escribir la contraseña para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="58d8e-176">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="58d8e-p119">Haga clic en **Guardar** para crear el nuevo usuario de correo. El nuevo usuario debe aparecer en la lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="58d8e-p119">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="58d8e-179">Usar el EAC para editar o quitar un usuario de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-179">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="58d8e-180">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="58d8e-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="58d8e-181">En la lista de usuarios, haga clic en el usuario que desea ver o modificar y, a continuación \*\*\*\* ![, seleccione Editar](../media/ITPro-EAC-EditIcon.gif) icono Editar para actualizar la configuración del usuario según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="58d8e-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="58d8e-182">Puede cambiar el nombre, el alias o la información de contacto del usuario, y puede registrar información detallada sobre el rol del usuario en la organización.</span><span class="sxs-lookup"><span data-stu-id="58d8e-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="58d8e-183">También puede seleccionar un usuario y, a continuación \*\*\*\* ![, elegir quitar](../media/ITPro-EAC-RemoveIcon.gif) icono quitar para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="58d8e-183">You can also select a user and then choose **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span>

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="58d8e-184">Uso de PowerShell de Exchange Online Protection para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-184">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="58d8e-185">En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo mediante Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="58d8e-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>

### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="58d8e-186">Usar PowerShell de EOP para agregar un usuario de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-186">Use EOP PowerShell to add a mail user</span></span>

<span data-ttu-id="58d8e-187">En este ejemplo, se usa el cmdlet [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) para crear una cuenta de usuario habilitada para correo para Jeffrey Zeng en EOP con los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="58d8e-187">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>

- <span data-ttu-id="58d8e-188">El nombre es Jeffrey y el apellido es Zeng.</span><span class="sxs-lookup"><span data-stu-id="58d8e-188">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="58d8e-189">El nombre es Jeffrey y el nombre para mostrar es Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="58d8e-189">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="58d8e-190">El alias es jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="58d8e-190">The alias is jeffreyz.</span></span>

- <span data-ttu-id="58d8e-191">La dirección de correo electrónico externa es jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="58d8e-191">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="58d8e-192">El nombre de inicio de sesión de Office 365 es jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="58d8e-192">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="58d8e-193">La contraseña es Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="58d8e-193">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="58d8e-194">Para comprobar que esto funcionó, ejecute el siguiente comando para mostrar información sobre el nuevo usuario de correo Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="58d8e-194">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="58d8e-195">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span><span class="sxs-lookup"><span data-stu-id="58d8e-195">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="58d8e-196">Uso de PowerShell de EOP para editar las propiedades de un usuario de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-196">Use EOP PowerShell to edit the properties of a mail user</span></span>

<span data-ttu-id="58d8e-197">Use los cmdlets [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) y [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) para ver o cambiar las propiedades de los usuarios de correo.</span><span class="sxs-lookup"><span data-stu-id="58d8e-197">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>

<span data-ttu-id="58d8e-198">Este ejemplo establece la dirección de correo electrónico externa de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="58d8e-198">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="58d8e-199">Este ejemplo establece la propiedad de la empresa para todos los usuarios de correo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="58d8e-199">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="58d8e-200">Para comprobar que esto funcionó, use el cmdlet [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para comprobar los cambios.</span><span class="sxs-lookup"><span data-stu-id="58d8e-200">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="58d8e-201">(Tenga en cuenta que puede ver varias propiedades de varios contactos de correo).</span><span class="sxs-lookup"><span data-stu-id="58d8e-201">(Note that you can view multiple properties for multiple mail contacts.)</span></span>

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="58d8e-202">En el ejemplo anterior, donde la propiedad Empresa estaba configurada para Contoso para todos los usuarios de correo, ejecute el siguiente comando para comprobar los cambios:</span><span class="sxs-lookup"><span data-stu-id="58d8e-202">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="58d8e-203">Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles.</span><span class="sxs-lookup"><span data-stu-id="58d8e-203">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>

### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="58d8e-204">Usar PowerShell de EOP para quitar un usuario de correo</span><span class="sxs-lookup"><span data-stu-id="58d8e-204">Use EOP PowerShell to remove a mail user</span></span>

<span data-ttu-id="58d8e-205">En este ejemplo se usa el cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) para eliminar el usuario Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="58d8e-205">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
<span data-ttu-id="58d8e-206">Para comprobar que esto funcionó, ejecute el cmdlet [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para comprobar que el usuario de correo ya no existe.</span><span class="sxs-lookup"><span data-stu-id="58d8e-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>

```PowerShell
Get-Recipient Jeffrey | Format-List
```
