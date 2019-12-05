---
title: Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Use esta guía del laboratorio de pruebas para habilitar la administración del acceso con privilegios en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 7e6a2ddea341f49c737409d8586bd9e70c9b2b79
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831821"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="62aab-103">Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="62aab-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="62aab-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="62aab-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="62aab-105">Con las instrucciones de este artículo, se configura la administración del acceso con privilegios para aumentar la seguridad en el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="62aab-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="62aab-107">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="62aab-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="62aab-108">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="62aab-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="62aab-109">Si solo quiere configurar la administración del acceso con privilegios de manera ligera con los requisitos mínimos, siga las instrucciones de [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="62aab-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="62aab-110">Si desea configurar la administración del acceso con privilegios en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="62aab-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="62aab-111">La prueba de la administración del acceso con privilegios no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de AD DS.</span><span class="sxs-lookup"><span data-stu-id="62aab-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="62aab-112">Se proporciona aquí como una opción para poder probar la administración de acceso privilegiado y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="62aab-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="62aab-113">Fase 2: configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="62aab-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="62aab-114">En esta fase, configurará un grupo aprobadores y habilitará la administración de acceso privilegiada para el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="62aab-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="62aab-115">Para obtener información adicional y una introducción a la administración del acceso con privilegios, consulte [Administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="62aab-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="62aab-116">Siga estos pasos para configurar y usar el acceso con privilegios en su organización de Office 365:</span><span class="sxs-lookup"><span data-stu-id="62aab-116">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="62aab-117">Paso 1: crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="62aab-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="62aab-118">Antes de empezar a usar el acceso de privilegios, determine quién tendrá autoridad de aprobación para el acceso a las tareas elevadas y privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="62aab-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="62aab-119">Cualquier usuario que forme parte del grupo de aprobadores podrá aprobar solicitudes de acceso.</span><span class="sxs-lookup"><span data-stu-id="62aab-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="62aab-120">Para habilitarlo, cree un grupo de seguridad habilitado para correo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="62aab-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="62aab-121">Cree un nuevo grupo de seguridad denominado "aprobadores de acceso privilegiados" en su entorno de prueba y agregue el "usuario 3" creado anteriormente en los pasos anteriores de la guía del entorno de pruebas.</span><span class="sxs-lookup"><span data-stu-id="62aab-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="62aab-122">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="62aab-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="62aab-123">El acceso privilegiado debe estar activado explícitamente en Office 365 con el grupo de aprobador predeterminado e incluir un conjunto de cuentas del sistema que se desea excluir del control de acceso privilegiado de la administración de acceso.</span><span class="sxs-lookup"><span data-stu-id="62aab-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="62aab-124">Asegúrese de habilitar el acceso con privilegios en su organización de Office 365 antes de iniciar la fase 3 de esta guía.</span><span class="sxs-lookup"><span data-stu-id="62aab-124">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="62aab-125">Fase 3: comprobar que la aprobación es necesaria para las tareas elevadas y privilegiadas</span><span class="sxs-lookup"><span data-stu-id="62aab-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="62aab-126">En esta fase, se comprueba que la Directiva de acceso privilegiado funciona y que los usuarios necesitan aprobación para ejecutar las tareas elevadas y privilegiadas definidas.</span><span class="sxs-lookup"><span data-stu-id="62aab-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="62aab-127">Probar la capacidad de ejecutar una tarea no definida en una directiva de acceso privilegiada</span><span class="sxs-lookup"><span data-stu-id="62aab-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="62aab-128">En primer lugar, conéctese a PowerShell de administración de Exchange con las credenciales de un usuario configurado como administrador global en el entorno de prueba e intente crear una nueva regla de diario.</span><span class="sxs-lookup"><span data-stu-id="62aab-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="62aab-129">La tarea [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) no se define actualmente en una directiva de acceso privilegiada para su organización.</span><span class="sxs-lookup"><span data-stu-id="62aab-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="62aab-130">En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation** > **Microsoft Exchange Online** con la cuenta de administrador global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="62aab-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62aab-131">En Exchange Management PowerShell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="62aab-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="62aab-132">Vista que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62aab-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="62aab-133">Crear una nueva Directiva de acceso con privilegios para la tarea New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="62aab-133">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="62aab-134">Si todavía no ha completado los pasos 1 y 2 de la fase 2 de esta guía, asegúrese de seguir los pasos para crear un grupo de aprobadores denominado "aprobadores de acceso de privilegios" y para habilitar el acceso privilegiado en el entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="62aab-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="62aab-135">Inicie sesión en el [centro de administración de 365 de Microsoft](https://admin.microsoft.com) con las credenciales de la cuenta de administrador global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="62aab-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62aab-136">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="62aab-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62aab-137">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="62aab-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62aab-138">Seleccione **configurar directivas** y seleccione **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="62aab-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="62aab-139">En los campos desplegables, seleccione o escriba los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="62aab-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="62aab-140">**Tipo de directiva**: tarea</span><span class="sxs-lookup"><span data-stu-id="62aab-140">**Policy type**: Task</span></span>

    <span data-ttu-id="62aab-141">**Ámbito de directiva**: Exchange</span><span class="sxs-lookup"><span data-stu-id="62aab-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="62aab-142">**Nombre de directiva**: nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="62aab-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="62aab-143">**Tipo de aprobación**: manual</span><span class="sxs-lookup"><span data-stu-id="62aab-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="62aab-144">**Grupo de aprobación**: aprobadores de acceso privilegiados</span><span class="sxs-lookup"><span data-stu-id="62aab-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="62aab-145">Seleccione **crear** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="62aab-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="62aab-146">La Directiva puede tardar unos minutos en estar totalmente configurada y habilitada.</span><span class="sxs-lookup"><span data-stu-id="62aab-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="62aab-147">Asegúrese de dejar tiempo para que la Directiva esté totalmente habilitada antes de probar el requisito de aprobación en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="62aab-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="62aab-148">Requisito de aprobación de prueba para la tarea New-JournalRule definida en una directiva de acceso privilegiado</span><span class="sxs-lookup"><span data-stu-id="62aab-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="62aab-149">En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation** > **Microsoft Exchange Online** usando un con la cuenta de administrador global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="62aab-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62aab-150">En Exchange Management PowerShell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="62aab-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="62aab-151">Ver el error "permisos insuficientes" en Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="62aab-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="62aab-152">Solicitar acceso para crear una nueva regla de diario mediante la tarea New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="62aab-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="62aab-153">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="62aab-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62aab-154">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="62aab-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62aab-155">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="62aab-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62aab-156">Seleccione **nueva solicitud**.</span><span class="sxs-lookup"><span data-stu-id="62aab-156">Select **New request**.</span></span> <span data-ttu-id="62aab-157">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="62aab-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="62aab-158">**Tipo de solicitud**: tarea</span><span class="sxs-lookup"><span data-stu-id="62aab-158">**Request type**: Task</span></span>

    <span data-ttu-id="62aab-159">**Ámbito de solicitud**: Exchange</span><span class="sxs-lookup"><span data-stu-id="62aab-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="62aab-160">**Solicitud de**: nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="62aab-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="62aab-161">**Duración (horas)**: 2</span><span class="sxs-lookup"><span data-stu-id="62aab-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="62aab-162">**Comentarios**: solicitar permiso para crear una nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="62aab-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="62aab-163">Seleccione **Guardar** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="62aab-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="62aab-164">La solicitud se enviará al grupo del aprobador a través del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="62aab-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="62aab-165">Aprobar la solicitud de acceso con privilegios para la creación de una nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="62aab-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="62aab-166">Inicie sesión en el [centro de administración de 365 de Microsoft](https://admin.microsoft.com) con las credenciales del usuario 3 en su entorno de prueba (miembro del grupo de seguridad "aprobadores de acceso con privilegios" en su entorno de prueba).</span><span class="sxs-lookup"><span data-stu-id="62aab-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="62aab-167">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="62aab-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62aab-168">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="62aab-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62aab-169">Seleccione la solicitud pendiente y seleccione **aprobar** para conceder acceso a la cuenta de administrador global para crear una nueva regla de diario.</span><span class="sxs-lookup"><span data-stu-id="62aab-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="62aab-170">Se enviará un correo electrónico de notificación para confirmar que la aprobación se ha concedido a la cuenta de administrador global (el usuario que realiza la solicitud).</span><span class="sxs-lookup"><span data-stu-id="62aab-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="62aab-171">Prueba de creación de una nueva regla de diario con acceso con privilegios aprobado para la tarea New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="62aab-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="62aab-172">En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation** > **Microsoft Exchange Online** con la cuenta de administrador global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="62aab-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="62aab-173">En Exchange Management PowerShell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="62aab-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="62aab-174">Vista que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62aab-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="62aab-175">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="62aab-175">Next step</span></span>

<span data-ttu-id="62aab-176">Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="62aab-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="62aab-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="62aab-177">See also</span></span>

[<span data-ttu-id="62aab-178">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="62aab-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="62aab-179">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="62aab-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="62aab-180">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="62aab-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)