---
title: Introducción a la administración del acceso con privilegios
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Use este artículo para obtener más información sobre cómo habilitar y configurar la administración de acceso con privilegios en Office 365.
ms.openlocfilehash: 13b600c60e1b9c88285ee58efcf80a7ff5ea17fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226124"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="75560-103">Introducción a la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="75560-103">Get started with privileged access management</span></span>

<span data-ttu-id="75560-104">Este tema le guía a través de la habilitación y configuración de la administración de acceso con privilegios en su organización.</span><span class="sxs-lookup"><span data-stu-id="75560-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="75560-105">Puede usar powerShell de administración Centro de administración de Microsoft 365 o Exchange para administrar y usar el acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="75560-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="75560-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="75560-106">Before you begin</span></span>

<span data-ttu-id="75560-107">Antes de empezar con la administración de acceso con privilegios, debe confirmar la [Microsoft 365 suscripción y](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) los complementos.</span><span class="sxs-lookup"><span data-stu-id="75560-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="75560-108">Para obtener acceso y usar la administración de acceso con privilegios, la organización debe tener una de las siguientes suscripciones o complementos:</span><span class="sxs-lookup"><span data-stu-id="75560-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="75560-109">Microsoft 365 E5 suscripción (versión de pago o de prueba)</span><span class="sxs-lookup"><span data-stu-id="75560-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="75560-110">Microsoft 365 E3 suscripción (o Office 365 E3 + Enterprise de movilidad y seguridad E3) + Cumplimiento de Microsoft 365 E5 complemento</span><span class="sxs-lookup"><span data-stu-id="75560-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="75560-111">Cualquier Microsoft 365, Office 365, Exchange, SharePoint o OneDrive para la Empresa suscripción + el complemento de administración de riesgos Microsoft 365 E5 Insider</span><span class="sxs-lookup"><span data-stu-id="75560-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="75560-112">Microsoft 365 A5 suscripción (versión de pago o de prueba)</span><span class="sxs-lookup"><span data-stu-id="75560-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="75560-113">Microsoft 365 A3 suscripción (o Office 365 A3 suscripción + Enterprise de movilidad y seguridad A3) + el complemento cumplimiento de Microsoft A5</span><span class="sxs-lookup"><span data-stu-id="75560-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="75560-114">Cualquier suscripción Microsoft 365, Office 365, Exchange, SharePoint o OneDrive para Educación + el complemento de administración de riesgos de Microsoft 365 A5 Insider</span><span class="sxs-lookup"><span data-stu-id="75560-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="75560-115">Office 365 Enterprise Suscripción E5 (versión de pago o de prueba)</span><span class="sxs-lookup"><span data-stu-id="75560-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="75560-116">Office 365 Enterprise Suscripción E3 + Cumplimiento avanzado de Office 365 complemento (ya no está disponible para las nuevas suscripciones, vea la nota)</span><span class="sxs-lookup"><span data-stu-id="75560-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="75560-117">Los usuarios que envíen y respondan a solicitudes de administración de acceso con privilegios deben tener asignada una de las licencias anteriores.</span><span class="sxs-lookup"><span data-stu-id="75560-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75560-118">Cumplimiento avanzado de Office 365 ya no se vende como una suscripción independiente.</span><span class="sxs-lookup"><span data-stu-id="75560-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="75560-119">Cuando expiran las suscripciones actuales, los clientes deben realizar la transición a una de las suscripciones anteriores, que contienen las mismas o adicionales características de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="75560-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="75560-120">Si no tiene un plan de Office 365 Enterprise E5 existente y desea probar la administración de acceso con privilegios, [](https://www.microsoft.com/microsoft-365/enterprise) puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a la suscripción Office 365 existente o registrarse para una prueba de Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="75560-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="75560-121">Habilitar y configurar la administración de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="75560-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="75560-122">Siga estos pasos para configurar y usar el acceso con privilegios en su organización:</span><span class="sxs-lookup"><span data-stu-id="75560-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="75560-123">Paso 1: Crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="75560-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="75560-124">Antes de empezar a usar el acceso con privilegios, determine quiénes necesitan la autoridad de aprobaciones para las solicitudes entrantes de acceso a tareas con privilegios o privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="75560-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="75560-125">Cualquier usuario que forme parte del grupo de aprobadores podrá aprobar las solicitudes de acceso.</span><span class="sxs-lookup"><span data-stu-id="75560-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="75560-126">Este grupo se habilita mediante la creación de un grupo de seguridad habilitado para correo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="75560-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="75560-127">Paso 2: Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="75560-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="75560-128">El acceso con privilegios debe habilitarse explícitamente en Office 365 con el grupo predeterminado de aprobadores, incluido el conjunto de cuentas del sistema que desee excluir del control de acceso de Privileged Access Management.</span><span class="sxs-lookup"><span data-stu-id="75560-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="75560-129">Paso 3: Crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="75560-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="75560-130">La creación de una directiva de aprobación le permite definir requisitos de aprobación específicos para cada tarea.</span><span class="sxs-lookup"><span data-stu-id="75560-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="75560-131">Las opciones de tipo de aprobación son **Automática** o **Manual**.</span><span class="sxs-lookup"><span data-stu-id="75560-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="75560-132">Paso 4: Enviar o aprobar solicitudes de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="75560-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="75560-133">Tras habilitar el acceso con privilegios, este requiere la aprobación de toda tarea que tenga una directiva de aprobación definida asociada a ella.</span><span class="sxs-lookup"><span data-stu-id="75560-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="75560-134">En el caso de las tareas incluidas en una directiva de aprobación, los usuarios deberán solicitar y obtener la aprobación de acceso para contar con los permisos necesarios para ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="75560-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="75560-135">Una vez que se concede la aprobación, el usuario que realizó la solicitud puede ejecutar la tarea prevista y el acceso con privilegios autorizará y ejecutará la tarea en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="75560-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="75560-136">La aprobación será válida durante el período de tiempo solicitado (la duración predeterminada es de cuatro horas), a lo largo del cual el solicitante puede ejecutar la tarea prevista varias veces.</span><span class="sxs-lookup"><span data-stu-id="75560-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="75560-137">Todas esas ejecuciones se registran y pasan a estar disponibles para las auditorías de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="75560-137">All such executions are logged and made available for security and compliance auditing.</span></span>

> [!NOTE]
> <span data-ttu-id="75560-138">Si desea usar PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos de Conectar para Exchange Online PowerShell mediante la autenticación [multifactor](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) para conectarse Exchange Online PowerShell con sus credenciales Office 365.</span><span class="sxs-lookup"><span data-stu-id="75560-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="75560-139">No es necesario habilitar la autenticación multifactor para que la organización use los pasos necesarios para habilitar el acceso con privilegios al conectarse Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75560-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="75560-140">La conexión con la autenticación multifactor crea un token de OAuth que usa el acceso con privilegios para firmar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="75560-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="75560-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="75560-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="75560-142">Paso 1: Crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="75560-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="75560-143">Inicie sesión en [el Centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de su organización.</span><span class="sxs-lookup"><span data-stu-id="75560-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="75560-144">En el Centro de administración, vaya a **Grupos**  >  **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="75560-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="75560-145">Seleccione **grupo de seguridad habilitado para correo** y,  a continuación, complete los campos **Nombre,** Dirección de **correo electrónico** del grupo y Descripción del nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="75560-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="75560-146">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="75560-146">Save the group.</span></span> <span data-ttu-id="75560-147"> La configuración completa del grupo y su aparición en el Centro de administración de Microsoft 365 pueden tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="75560-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="75560-148">Seleccione el grupo del nuevo aprobador y **seleccione Editar** para agregar usuarios al grupo.</span><span class="sxs-lookup"><span data-stu-id="75560-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="75560-149">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="75560-149">Save the group.</span></span>

<span data-ttu-id="75560-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="75560-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="75560-151">Paso 2: Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="75560-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="75560-152">En el Centro de Administración de Microsoft 365 de datos</span><span class="sxs-lookup"><span data-stu-id="75560-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="75560-153">Inicie sesión en [el Centro de Administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="75560-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="75560-154">En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="75560-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="75560-155">Habilite el **control Requerir aprobaciones para tareas con privilegios.**</span><span class="sxs-lookup"><span data-stu-id="75560-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="75560-156">Asigne el grupo del aprobador que creó en el paso 1 como **grupo Aprobadores predeterminados.**</span><span class="sxs-lookup"><span data-stu-id="75560-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="75560-157">**Guardar** y **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75560-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="75560-158">En Exchange PowerShell de administración</span><span class="sxs-lookup"><span data-stu-id="75560-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="75560-159">Para habilitar el acceso con privilegios y asignar el grupo del aprobador, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75560-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="75560-160">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75560-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="75560-161">La característica cuentas del sistema está disponible para garantizar que ciertas automatizacións dentro de las organizaciones puedan funcionar sin dependencia del acceso con privilegios, pero se recomienda que estas exclusiones sean excepcionales y que las permitidas se aprueben y audite periódicamente.</span><span class="sxs-lookup"><span data-stu-id="75560-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="75560-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="75560-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="75560-163">Paso 3: Crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="75560-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="75560-164">Puede crear y configurar hasta 30 directivas de acceso con privilegios para su organización.</span><span class="sxs-lookup"><span data-stu-id="75560-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="75560-165">En el Centro de Administración de Microsoft 365 de datos</span><span class="sxs-lookup"><span data-stu-id="75560-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="75560-166">Inicie sesión en [el Centro de Administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="75560-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="75560-167">En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="75560-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="75560-168">Seleccione **Administrar directivas y solicitudes de acceso.**</span><span class="sxs-lookup"><span data-stu-id="75560-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="75560-169">Seleccione **Configurar directivas** y seleccione Agregar una **directiva**.</span><span class="sxs-lookup"><span data-stu-id="75560-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="75560-170">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="75560-170">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="75560-171">**Tipo de directiva**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="75560-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="75560-172">**Ámbito de la directiva**: Exchange</span><span class="sxs-lookup"><span data-stu-id="75560-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="75560-173">**Nombre de la directiva**: seleccionar entre las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="75560-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="75560-174">**Tipo de aprobación**: manual o automática</span><span class="sxs-lookup"><span data-stu-id="75560-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="75560-175">**Grupo de aprobación**: seleccionar el grupo de aprobadores creado en el paso 1</span><span class="sxs-lookup"><span data-stu-id="75560-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="75560-176">Seleccione **Crear** y, a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75560-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="75560-177">La directiva puede tardar unos minutos en estar totalmente configurada y habilitada.</span><span class="sxs-lookup"><span data-stu-id="75560-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="75560-178">En Exchange PowerShell de administración</span><span class="sxs-lookup"><span data-stu-id="75560-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="75560-179">Para crear y definir una directiva de aprobación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75560-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="75560-180">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75560-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="75560-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="75560-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="75560-182">Paso 4: Enviar o aprobar solicitudes de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="75560-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="75560-183">Solicitud de autorización de elevación para ejecutar tareas privilegiadas</span><span class="sxs-lookup"><span data-stu-id="75560-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="75560-184">Las solicitudes de acceso con privilegios son válidas hasta 24 horas después de que se hayan enviado.</span><span class="sxs-lookup"><span data-stu-id="75560-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="75560-185">Si ni se aprueban ni se deniegan, las solicitudes expiran y el acceso no se aprueba.</span><span class="sxs-lookup"><span data-stu-id="75560-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="75560-186">En el Centro de Administración de Microsoft 365 de datos</span><span class="sxs-lookup"><span data-stu-id="75560-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="75560-187">Inicie sesión en [el Centro Administración de Microsoft 365 con](https://admin.microsoft.com) sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="75560-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="75560-188">En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="75560-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="75560-189">Seleccione **Administrar directivas y solicitudes de acceso.**</span><span class="sxs-lookup"><span data-stu-id="75560-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="75560-190">Seleccione **Nueva solicitud**.</span><span class="sxs-lookup"><span data-stu-id="75560-190">Select **New request**.</span></span> <span data-ttu-id="75560-191">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="75560-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="75560-192">**Tipo de solicitud**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="75560-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="75560-193">**Ámbito de la solicitud**: Exchange</span><span class="sxs-lookup"><span data-stu-id="75560-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="75560-194">**Solicitud de**: seleccionar entre las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="75560-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="75560-195">**Duración (horas)**: número de horas del acceso solicitado</span><span class="sxs-lookup"><span data-stu-id="75560-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="75560-196">No hay un límite en el número de horas que se pueden solicitar.</span><span class="sxs-lookup"><span data-stu-id="75560-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="75560-197">**Comentarios:** Campo de texto para los comentarios relacionados con la solicitud de acceso</span><span class="sxs-lookup"><span data-stu-id="75560-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="75560-198">Seleccione **Guardar** y, a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75560-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="75560-199">La solicitud se enviará al grupo del aprobador por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75560-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="75560-200">En Exchange PowerShell de administración</span><span class="sxs-lookup"><span data-stu-id="75560-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="75560-201">Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:</span><span class="sxs-lookup"><span data-stu-id="75560-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="75560-202">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75560-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="75560-203">Ver el estado de las solicitudes de elevación</span><span class="sxs-lookup"><span data-stu-id="75560-203">View status of elevation requests</span></span>

<span data-ttu-id="75560-204">Después de crear una solicitud de aprobación, el estado de la solicitud de elevación se puede revisar en el Centro de administración o en powerShell de administración Exchange mediante el identificador de solicitud asociado.</span><span class="sxs-lookup"><span data-stu-id="75560-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="75560-205">En el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75560-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="75560-206">Inicie sesión en [el Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="75560-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="75560-207">En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="75560-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="75560-208">Seleccione **Administrar directivas y solicitudes de acceso.**</span><span class="sxs-lookup"><span data-stu-id="75560-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="75560-209">Seleccione **Ver** para filtrar las solicitudes enviadas por estado **Pendiente,** **Aprobado,** **Denegado** o **Caja de seguridad del** cliente.</span><span class="sxs-lookup"><span data-stu-id="75560-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="75560-210">En Exchange PowerShell de administración</span><span class="sxs-lookup"><span data-stu-id="75560-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="75560-211">Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de una solicitud de aprobación para un identificador de solicitud específico:</span><span class="sxs-lookup"><span data-stu-id="75560-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="75560-212">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75560-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="75560-213">Aprobar una solicitud de autorización de elevación</span><span class="sxs-lookup"><span data-stu-id="75560-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="75560-214">Cuando se crea una solicitud de aprobación, los miembros del grupo de aprobadores correspondiente reciben una notificación por correo electrónico y pueden aprobar la solicitud asociada con el identificador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="75560-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="75560-215">Se notificará al solicitante de la aprobación o denegación de la solicitud por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75560-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="75560-216">En el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75560-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="75560-217">Inicie sesión en [el Centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="75560-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="75560-218">En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="75560-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="75560-219">Seleccione **Administrar directivas y solicitudes de acceso.**</span><span class="sxs-lookup"><span data-stu-id="75560-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="75560-220">Seleccione una solicitud enumerada para ver los detalles y tomar medidas en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="75560-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="75560-221">Seleccione **Aprobar** para aprobar la solicitud o **seleccione Denegar** para denegar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="75560-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="75560-222">Las solicitudes aprobadas anteriormente pueden tener acceso revocado seleccionando **Revocar**.</span><span class="sxs-lookup"><span data-stu-id="75560-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="75560-223">En Exchange PowerShell de administración</span><span class="sxs-lookup"><span data-stu-id="75560-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="75560-224">Para aprobar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75560-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="75560-225">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75560-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="75560-226">Para denegar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75560-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="75560-227">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75560-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="75560-228">Eliminar una directiva de acceso con privilegios en Office 365</span><span class="sxs-lookup"><span data-stu-id="75560-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="75560-229">Si ya no es necesario en su organización, puede eliminar una directiva de acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="75560-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="75560-230">En el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75560-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="75560-231">Inicie sesión en [el Centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de su organización.</span><span class="sxs-lookup"><span data-stu-id="75560-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="75560-232">En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="75560-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="75560-233">Seleccione **Administrar directivas y solicitudes de acceso.**</span><span class="sxs-lookup"><span data-stu-id="75560-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="75560-234">Seleccione **Configurar directivas**.</span><span class="sxs-lookup"><span data-stu-id="75560-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="75560-235">Seleccione la directiva que desea eliminar y, a continuación, **seleccione Quitar directiva**.</span><span class="sxs-lookup"><span data-stu-id="75560-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="75560-236">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75560-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="75560-237">En Exchange PowerShell de administración</span><span class="sxs-lookup"><span data-stu-id="75560-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="75560-238">Para eliminar una directiva de acceso con privilegios, ejecute el siguiente comando en Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="75560-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="75560-239">Deshabilitar el acceso con privilegios en Office 365</span><span class="sxs-lookup"><span data-stu-id="75560-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="75560-240">Si es necesario, puede deshabilitar la administración de acceso con privilegios para su organización.</span><span class="sxs-lookup"><span data-stu-id="75560-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="75560-241">Deshabilitar el acceso con privilegios no elimina ninguna de las directivas de aprobación o grupos de aprobadores asociados.</span><span class="sxs-lookup"><span data-stu-id="75560-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="75560-242">En el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75560-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="75560-243">Inicie sesión en [el Centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de su organización.</span><span class="sxs-lookup"><span data-stu-id="75560-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="75560-244">En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="75560-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="75560-245">Habilite requerir **aprobaciones para el** control de acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="75560-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="75560-246">En Exchange PowerShell de administración</span><span class="sxs-lookup"><span data-stu-id="75560-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="75560-247">Para deshabilitar el acceso con privilegios, ejecute el siguiente comando en Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="75560-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
