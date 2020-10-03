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
description: Use este artículo para obtener más información sobre cómo habilitar y configurar la administración del acceso con privilegios en Office 365.
ms.openlocfilehash: d75a8944cdacb6df2d6ee6570c0ce327d0e7ae00
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341208"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="426ac-103">Introducción a la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="426ac-103">Get started with privileged access management</span></span>

<span data-ttu-id="426ac-104">Este tema le guiará a través de la habilitación y configuración de la administración del acceso con privilegios en su organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="426ac-105">Puede usar tanto el centro de administración de Microsoft 365 como PowerShell de administración de Exchange para administrar y usar el acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="426ac-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="426ac-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="426ac-106">Before you begin</span></span>

<span data-ttu-id="426ac-107">Antes de empezar con la administración de acceso con privilegios, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y los complementos.</span><span class="sxs-lookup"><span data-stu-id="426ac-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="426ac-108">Para acceder a la administración del acceso con privilegios y usarla, su organización debe tener una de las siguientes suscripciones o complementos:</span><span class="sxs-lookup"><span data-stu-id="426ac-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="426ac-109">Suscripción a Microsoft 365 E5 (versión de pago o de prueba)</span><span class="sxs-lookup"><span data-stu-id="426ac-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="426ac-110">Suscripción a Microsoft 365 E3 (o suscripción de Office 365 E3 + suscripción Enterprise Mobility y Security E3) + el complemento de cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="426ac-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="426ac-111">Cualquier suscripción a Microsoft 365, Office 365, Exchange, SharePoint o OneDrive para la empresa + el complemento de administración de riesgos de Insider de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="426ac-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="426ac-112">Suscripción a Microsoft 365 A5 (versión de pago o de prueba)</span><span class="sxs-lookup"><span data-stu-id="426ac-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="426ac-113">Suscripción a Microsoft 365 a3 (o suscripción de Office 365 a3 + suscripción de seguridad y movilidad empresarial a3) + el complemento de cumplimiento de Microsoft A5</span><span class="sxs-lookup"><span data-stu-id="426ac-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="426ac-114">Cualquier suscripción a Microsoft 365, Office 365, Exchange, SharePoint o OneDrive para la educación + el complemento de administración de riesgos de Insider de Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="426ac-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="426ac-115">Suscripción a Office 365 Enterprise E5 (versión de pago o de prueba)</span><span class="sxs-lookup"><span data-stu-id="426ac-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="426ac-116">Office 365 Enterprise E3 subscription + el complemento Office 365 Advanced Compliance (ya no está disponible para las nuevas suscripciones, vea note)</span><span class="sxs-lookup"><span data-stu-id="426ac-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="426ac-117">Los usuarios que envían y responden a solicitudes de administración de acceso privilegiadas deben tener asignada una de las licencias anteriores.</span><span class="sxs-lookup"><span data-stu-id="426ac-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="426ac-118">Office 365 Advanced Compliance ya no se vende como una suscripción independiente.</span><span class="sxs-lookup"><span data-stu-id="426ac-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="426ac-119">Cuando expiren las suscripciones actuales, los clientes deben pasar a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o más.</span><span class="sxs-lookup"><span data-stu-id="426ac-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="426ac-120">Si no tiene un plan de Office 365 Enterprise E5 existente y desea probar la administración de acceso privilegiada, puede [Agregar microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) a su suscripción existente de Office 365 o [registrarse para obtener una versión de prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="426ac-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="426ac-121">Habilitación y configuración de la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="426ac-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="426ac-122">Siga estos pasos para configurar y usar el acceso con privilegios en su organización:</span><span class="sxs-lookup"><span data-stu-id="426ac-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="426ac-123">Paso 1: crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="426ac-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="426ac-124">Antes de empezar a usar el acceso de privilegios, determine quién necesita autoridad de aprobación para el acceso a las tareas elevadas y privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="426ac-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="426ac-125">Cualquier usuario que forme parte del grupo de aprobadores puede aprobar solicitudes de acceso.</span><span class="sxs-lookup"><span data-stu-id="426ac-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="426ac-126">Para habilitar este grupo, cree un grupo de seguridad habilitado para correo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="426ac-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="426ac-127">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="426ac-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="426ac-128">El acceso con privilegios debe estar habilitado explícitamente en Office 365 con el grupo de aprobador predeterminado, incluido un conjunto de cuentas del sistema que desea excluir del control de acceso privilegiado de la administración de acceso.</span><span class="sxs-lookup"><span data-stu-id="426ac-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="426ac-129">Paso 3: crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="426ac-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="426ac-130">La creación de una directiva de aprobación permite definir los requisitos de aprobación específicos en el ámbito de tareas individuales.</span><span class="sxs-lookup"><span data-stu-id="426ac-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="426ac-131">Las opciones de tipo de aprobación son **auto** o **manual**.</span><span class="sxs-lookup"><span data-stu-id="426ac-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="426ac-132">Paso 4: enviar o aprobar solicitudes de acceso privilegiadas</span><span class="sxs-lookup"><span data-stu-id="426ac-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="426ac-133">Una vez habilitado, el acceso con privilegios requiere aprobaciones para cualquier tarea que tenga definida una directiva de aprobación asociada.</span><span class="sxs-lookup"><span data-stu-id="426ac-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="426ac-134">Para las tareas incluidas en una directiva de aprobación, los usuarios deben solicitar y recibir la aprobación de acceso para disponer de los permisos necesarios para ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="426ac-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="426ac-135">Una vez que se haya concedido la aprobación, el usuario que realiza la solicitud puede ejecutar la tarea deseada y el acceso privilegiado autorizará y ejecutará la tarea en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="426ac-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="426ac-136">La aprobación sigue siendo válida durante la duración solicitada (la duración predeterminada es de 4 horas), durante el cual el solicitante puede ejecutar la tarea deseada varias veces.</span><span class="sxs-lookup"><span data-stu-id="426ac-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="426ac-137">Todas estas ejecuciones se registran y están disponibles para la auditoría de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="426ac-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="426ac-138">Si desea usar PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos descritos en [Connect to Exchange Online PowerShell Using multi-factor Authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) para conectarse a Exchange Online PowerShell con sus credenciales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="426ac-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="426ac-139">No es necesario habilitar la autenticación multifactor para que su organización use los pasos para habilitar el acceso privilegiado mientras se conecta a PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="426ac-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="426ac-140">La conexión con la autenticación multifactor crea un token de OAuth que se usa en el acceso con privilegios para firmar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="426ac-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="426ac-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="426ac-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="426ac-142">Paso 1: crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="426ac-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="426ac-143">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="426ac-144">En el centro de administración, vaya a **grupos**  >  **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="426ac-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="426ac-145">Seleccione **grupo de seguridad habilitado para correo** y, a continuación, complete los campos **nombre**, **dirección de correo electrónico de grupo**y **Descripción** para el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="426ac-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="426ac-146">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="426ac-146">Save the group.</span></span> <span data-ttu-id="426ac-147">Puede tardar unos minutos para que el grupo esté totalmente configurado y aparezca en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="426ac-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="426ac-148">Seleccione el grupo del nuevo aprobador y seleccione **Editar** para agregar usuarios al grupo.</span><span class="sxs-lookup"><span data-stu-id="426ac-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="426ac-149">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="426ac-149">Save the group.</span></span>

<span data-ttu-id="426ac-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="426ac-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="426ac-151">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="426ac-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="426ac-152">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="426ac-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="426ac-153">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="426ac-154">En el centro de administración, vaya a **configuración**  >  **org Settings**  >  **Security &**  >  **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="426ac-155">Habilite el control **requerir aprobaciones para las tareas privilegiadas** .</span><span class="sxs-lookup"><span data-stu-id="426ac-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="426ac-156">Asigne el grupo de aprobador que ha creado en el paso 1 como el **Grupo aprobadores predeterminados**.</span><span class="sxs-lookup"><span data-stu-id="426ac-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="426ac-157">**Guarde** y **cierre**.</span><span class="sxs-lookup"><span data-stu-id="426ac-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="426ac-158">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="426ac-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="426ac-159">Para habilitar el acceso privilegiado y asignar el grupo del aprobador, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="426ac-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="426ac-160">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="426ac-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="426ac-161">La característica cuentas del sistema está disponible para garantizar que determinadas automatización de las organizaciones puedan funcionar sin dependencia en el acceso con privilegios, pero se recomienda que dichas exclusiones sean excepcionales y que las permitidas se puedan aprobar y auditar con regularidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="426ac-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="426ac-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="426ac-163">Paso 3: crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="426ac-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="426ac-164">Puede crear y configurar hasta 30 directivas de acceso privilegiadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="426ac-165">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="426ac-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="426ac-166">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="426ac-167">En el centro de administración, vaya a **configuración**  >  **org Settings**  >  **Security &**  >  **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="426ac-168">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="426ac-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="426ac-169">Seleccione **configurar directivas** y seleccione **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="426ac-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="426ac-170">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="426ac-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="426ac-171">**Tipo de directiva**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="426ac-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="426ac-172">**Ámbito de directiva**: Exchange</span><span class="sxs-lookup"><span data-stu-id="426ac-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="426ac-173">**Nombre de directiva**: Seleccione una de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="426ac-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="426ac-174">**Tipo de aprobación**: manual o automático</span><span class="sxs-lookup"><span data-stu-id="426ac-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="426ac-175">**Grupo de aprobación**: seleccione el grupo aprobadores creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="426ac-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="426ac-176">Seleccione **crear** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="426ac-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="426ac-177">La Directiva puede tardar unos minutos en estar totalmente configurada y habilitada.</span><span class="sxs-lookup"><span data-stu-id="426ac-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="426ac-178">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="426ac-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="426ac-179">Para crear y definir una directiva de aprobación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="426ac-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="426ac-180">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="426ac-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="426ac-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="426ac-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="426ac-182">Paso 4: enviar o aprobar solicitudes de acceso privilegiadas</span><span class="sxs-lookup"><span data-stu-id="426ac-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="426ac-183">Solicitar autorización de elevación para ejecutar tareas privilegiadas</span><span class="sxs-lookup"><span data-stu-id="426ac-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="426ac-184">Las solicitudes de acceso con privilegios son válidas durante un máximo de 24 horas después de que se envíe la solicitud.</span><span class="sxs-lookup"><span data-stu-id="426ac-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="426ac-185">Si no se aprueba o se rechaza, las solicitudes expiran y el acceso no se aprueba.</span><span class="sxs-lookup"><span data-stu-id="426ac-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="426ac-186">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="426ac-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="426ac-187">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="426ac-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="426ac-188">En el centro de administración, vaya a **configuración**  >  **org Settings**  >  **Security &**  >  **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="426ac-189">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="426ac-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="426ac-190">Seleccione **nueva solicitud**.</span><span class="sxs-lookup"><span data-stu-id="426ac-190">Select **New request**.</span></span> <span data-ttu-id="426ac-191">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="426ac-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="426ac-192">**Tipo de solicitud**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="426ac-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="426ac-193">**Ámbito de solicitud**: Exchange</span><span class="sxs-lookup"><span data-stu-id="426ac-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="426ac-194">**Solicitud de**: Seleccione una de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="426ac-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="426ac-195">**Duración (horas)**: número de horas de acceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="426ac-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="426ac-196">No hay un límite en el número de horas que se puede solicitar.</span><span class="sxs-lookup"><span data-stu-id="426ac-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="426ac-197">**Comentarios**: campo de texto para comentarios relacionados con la solicitud de acceso</span><span class="sxs-lookup"><span data-stu-id="426ac-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="426ac-198">Seleccione **Guardar** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="426ac-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="426ac-199">La solicitud se enviará al grupo del aprobador a través del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="426ac-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="426ac-200">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="426ac-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="426ac-201">Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:</span><span class="sxs-lookup"><span data-stu-id="426ac-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="426ac-202">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="426ac-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="426ac-203">Ver el estado de las solicitudes de elevación</span><span class="sxs-lookup"><span data-stu-id="426ac-203">View status of elevation requests</span></span>

<span data-ttu-id="426ac-204">Después de crear una solicitud de aprobación, el estado de la solicitud de elevación se puede revisar en el centro de administración o en PowerShell de administración de Exchange con el identificador de solicitud asociado.</span><span class="sxs-lookup"><span data-stu-id="426ac-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="426ac-205">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="426ac-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="426ac-206">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="426ac-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="426ac-207">En el centro de administración, vaya a **configuración**  >  **org Settings**  >  **Security &**  >  **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="426ac-208">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="426ac-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="426ac-209">Seleccione **Ver** para filtrar las solicitudes enviadas por estado **pendiente**, **aprobado**, **denegado**o de **caja de caja del cliente** .</span><span class="sxs-lookup"><span data-stu-id="426ac-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="426ac-210">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="426ac-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="426ac-211">Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de la solicitud de aprobación de un identificador de solicitud específico:</span><span class="sxs-lookup"><span data-stu-id="426ac-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="426ac-212">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="426ac-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="426ac-213">Aprobación de una solicitud de autorización de elevación</span><span class="sxs-lookup"><span data-stu-id="426ac-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="426ac-214">Cuando se crea una solicitud de aprobación, los miembros del grupo aprobador relevante reciben una notificación por correo electrónico y pueden aprobar la solicitud asociada con el identificador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="426ac-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="426ac-215">El solicitante recibe la notificación de la aprobación o la denegación de la solicitud mediante un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="426ac-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="426ac-216">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="426ac-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="426ac-217">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="426ac-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="426ac-218">En el centro de administración, vaya a **configuración**  >  **org Settings**  >  **Security &**  >  **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="426ac-219">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="426ac-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="426ac-220">Seleccione una solicitud de la lista para ver los detalles y realizar la acción en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="426ac-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="426ac-221">Seleccione **aprobar** para aprobar la solicitud o seleccione **denegar** para denegar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="426ac-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="426ac-222">Las solicitudes aprobadas anteriormente pueden revocar el acceso mediante la selección de **REVOKE**.</span><span class="sxs-lookup"><span data-stu-id="426ac-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="426ac-223">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="426ac-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="426ac-224">Para aprobar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="426ac-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="426ac-225">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="426ac-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="426ac-226">Para denegar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="426ac-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="426ac-227">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="426ac-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="426ac-228">Eliminar una directiva de acceso privilegiada en Office 365</span><span class="sxs-lookup"><span data-stu-id="426ac-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="426ac-229">Si ya no es necesario en su organización, puede eliminar una directiva de acceso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="426ac-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="426ac-230">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="426ac-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="426ac-231">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="426ac-232">En el centro de administración, vaya a **configuración**  >  **org Settings**  >  **Security &**  >  **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="426ac-233">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="426ac-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="426ac-234">Seleccione **configurar directivas**.</span><span class="sxs-lookup"><span data-stu-id="426ac-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="426ac-235">Seleccione la Directiva que desea eliminar y, a continuación, seleccione **quitar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="426ac-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="426ac-236">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="426ac-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="426ac-237">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="426ac-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="426ac-238">Para eliminar una directiva de acceso privilegiada, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="426ac-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="426ac-239">Deshabilitar el acceso privilegiado en Office 365</span><span class="sxs-lookup"><span data-stu-id="426ac-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="426ac-240">Si es necesario, puede deshabilitar la administración del acceso con privilegios para su organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="426ac-241">La deshabilitación del acceso con privilegios no elimina ninguna directiva de aprobación o grupo de aprobador asociado.</span><span class="sxs-lookup"><span data-stu-id="426ac-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="426ac-242">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="426ac-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="426ac-243">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="426ac-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="426ac-244">En el centro de administración, vaya a **configuración**  >  **org Settings**  >  **Security &**  >  **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="426ac-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="426ac-245">Habilite el control **de acceso requerir aprobaciones para privilegios** .</span><span class="sxs-lookup"><span data-stu-id="426ac-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="426ac-246">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="426ac-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="426ac-247">Para deshabilitar el acceso privilegiado, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="426ac-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
