---
title: Administración de acceso con privilegios para su entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
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
description: Use esta guía del entorno de pruebas para habilitar la administración de acceso con privilegios en el entorno de pruebas de Microsoft 365 para empresas.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126422"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ec346-103">Administración de acceso con privilegios para su entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ec346-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ec346-104">*Esta Guía del entorno de pruebas se puede usar tanto para entornos de prueba de Microsoft 365 para empresas como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ec346-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ec346-105">En este artículo se describe cómo configurar la administración del acceso con privilegios para aumentar la seguridad en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="ec346-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="ec346-106">La configuración de la administración de accesos privilegiados consta de tres fases:</span><span class="sxs-lookup"><span data-stu-id="ec346-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="ec346-107">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ec346-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ec346-108">Fase 2: Configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ec346-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="ec346-109">Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios elevados y elevados</span><span class="sxs-lookup"><span data-stu-id="ec346-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ec346-111">Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="ec346-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ec346-112">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ec346-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ec346-113">Si desea configurar la administración de acceso con privilegios de forma ligera con los requisitos mínimos, siga las instrucciones de [la configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="ec346-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ec346-114">Si desea configurar la administración de acceso con privilegios en una empresa simulada, siga las instrucciones de autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="ec346-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="ec346-115">Las pruebas de administración de acceso con privilegios no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ec346-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="ec346-116">Se proporciona aquí como una opción para que pueda probar la administración de acceso con privilegios y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="ec346-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="ec346-117">Fase 2: Configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ec346-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="ec346-118">En esta fase, configure un grupo de aprobadores y habilite la administración del acceso con privilegios para su entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="ec346-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="ec346-119">Para obtener más información y una introducción a la administración del acceso con privilegios, consulte [Privileged access management](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec346-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="ec346-120">Para configurar y usar el acceso con privilegios en la organización, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ec346-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="ec346-121">Paso 1: Crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="ec346-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="ec346-122">Antes de empezar a usar el acceso con privilegios, determine quién tendrá autoridad de aprobación para las solicitudes entrantes de acceso a tareas con privilegios elevados y con privilegios.</span><span class="sxs-lookup"><span data-stu-id="ec346-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="ec346-123">Todos los usuarios que forman parte del grupo aprobadores pueden aprobar solicitudes de acceso.</span><span class="sxs-lookup"><span data-stu-id="ec346-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="ec346-124">Para usar el acceso con privilegios, debe crear un grupo de seguridad habilitado para correo en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec346-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="ec346-125">En el entorno de prueba, asigne al nuevo grupo de seguridad el nombre "Aprobadores de acceso con privilegios" y agregue el "Usuario 3" que se creó anteriormente en los pasos de guía del entorno de pruebas anteriores.</span><span class="sxs-lookup"><span data-stu-id="ec346-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="ec346-126">Paso 2: Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ec346-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="ec346-127">El acceso con privilegios debe estar activado explícitamente en Microsoft 365 con el grupo de aprobadores predeterminado y debe incluir un conjunto de cuentas del sistema que desea excluir del control de acceso de administración de acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="ec346-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="ec346-128">Asegúrese de habilitar el acceso con privilegios en su organización antes de iniciar la fase 3 de esta guía.</span><span class="sxs-lookup"><span data-stu-id="ec346-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="ec346-129">Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios elevados y elevados</span><span class="sxs-lookup"><span data-stu-id="ec346-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="ec346-130">En esta fase, compruebe que la directiva de acceso con privilegios funciona y que los usuarios necesitan la aprobación para ejecutar tareas definidas con privilegios elevados y con privilegios.</span><span class="sxs-lookup"><span data-stu-id="ec346-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ec346-131">Probar la capacidad de ejecutar una tarea NO definida en una directiva de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ec346-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="ec346-132">En primer lugar, conéctese a PowerShell de administración de Exchange con las credenciales de un usuario configurado como administrador global en su entorno de prueba e intente crear una nueva regla de diario.</span><span class="sxs-lookup"><span data-stu-id="ec346-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="ec346-133">La [tarea New-JournalRule](/powershell/module/exchange/new-journalrule) no está definida actualmente en una directiva de acceso con privilegios para su organización.</span><span class="sxs-lookup"><span data-stu-id="ec346-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="ec346-134">En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto de PowerShell con la cuenta de administrador global para su entorno  >   de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec346-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="ec346-135">En Exchange Management PowerShell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="ec346-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="ec346-136">Ver que la nueva regla de diario se creó correctamente en Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec346-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="ec346-137">Crear una nueva directiva de acceso con privilegios para la New-JournalRule de acceso</span><span class="sxs-lookup"><span data-stu-id="ec346-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="ec346-138">Si aún no ha completado los pasos 1 y 2 de la fase 2 de esta guía, asegúrese de seguir los pasos para crear un grupo de aprobadores denominado "Aprobadores de acceso con privilegios" para habilitar el acceso con privilegios en el entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec346-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="ec346-139">Inicie sesión en el Centro [de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de la cuenta de administrador global del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec346-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ec346-140">En el Centro de administración, vaya **a** Configuración  >  **de seguridad & acceso con**  >  **privilegios de privacidad.**</span><span class="sxs-lookup"><span data-stu-id="ec346-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ec346-141">Seleccione **Administrar directivas de acceso y solicitudes.**</span><span class="sxs-lookup"><span data-stu-id="ec346-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ec346-142">Seleccione **Configurar directivas** y, a continuación, seleccione Agregar una **directiva.**</span><span class="sxs-lookup"><span data-stu-id="ec346-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="ec346-143">En los campos desplegables, seleccione o escriba los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ec346-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="ec346-144">**Tipo de directiva**: tarea</span><span class="sxs-lookup"><span data-stu-id="ec346-144">**Policy type**: Task</span></span>

    <span data-ttu-id="ec346-145">**Ámbito de directiva:** Exchange</span><span class="sxs-lookup"><span data-stu-id="ec346-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="ec346-146">**Nombre de directiva:** nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="ec346-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="ec346-147">**Tipo de aprobación:** Manual</span><span class="sxs-lookup"><span data-stu-id="ec346-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="ec346-148">**Grupo de aprobación:** Aprobadores de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ec346-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="ec346-149">Seleccione **Crear** y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec346-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="ec346-150">La directiva puede tardar unos minutos en configurarse y habilitarse completamente.</span><span class="sxs-lookup"><span data-stu-id="ec346-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="ec346-151">Asegúrese de dejar tiempo para que la directiva esté completamente habilitada antes de probar el requisito de aprobación en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="ec346-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ec346-152">Requisito de aprobación de prueba para New-JournalRule tarea definida en una directiva de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ec346-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="ec346-153">En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto  >  **de PowerShell** con una cuenta de administrador global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec346-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ec346-154">En Exchange Management PowerShell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="ec346-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="ec346-155">Vea el error "Permisos insuficientes" en PowerShell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="ec346-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="ec346-156">Solicitar acceso para crear una nueva regla de diario mediante la New-JournalRule tarea</span><span class="sxs-lookup"><span data-stu-id="ec346-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="ec346-157">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec346-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ec346-158">En el Centro de administración, vaya **a** Configuración  >  **de seguridad & acceso con**  >  **privilegios de privacidad.**</span><span class="sxs-lookup"><span data-stu-id="ec346-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ec346-159">Seleccione **Administrar directivas de acceso y solicitudes.**</span><span class="sxs-lookup"><span data-stu-id="ec346-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ec346-160">Seleccione **Nueva solicitud.**</span><span class="sxs-lookup"><span data-stu-id="ec346-160">Select **New request**.</span></span> <span data-ttu-id="ec346-161">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="ec346-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="ec346-162">**Tipo de solicitud**: tarea</span><span class="sxs-lookup"><span data-stu-id="ec346-162">**Request type**: Task</span></span>

    <span data-ttu-id="ec346-163">**Ámbito de solicitud:** Exchange</span><span class="sxs-lookup"><span data-stu-id="ec346-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="ec346-164">**Solicitud de**: Nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="ec346-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="ec346-165">**Duración (horas):** 2</span><span class="sxs-lookup"><span data-stu-id="ec346-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="ec346-166">**Comentarios:** solicitar permiso para crear una nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="ec346-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="ec346-167">Seleccione **Guardar** y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec346-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="ec346-168">Su solicitud se enviará al grupo del aprobador por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ec346-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="ec346-169">Aprobar la solicitud de acceso con privilegios para la creación de una nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="ec346-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="ec346-170">Inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con las credenciales del usuario 3 del entorno de prueba (miembro del grupo de seguridad "Aprobadores de acceso con privilegios" en el entorno de prueba).</span><span class="sxs-lookup"><span data-stu-id="ec346-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="ec346-171">En el Centro de administración, vaya **a** Configuración  >  **de seguridad & acceso con**  >  **privilegios de privacidad.**</span><span class="sxs-lookup"><span data-stu-id="ec346-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ec346-172">Seleccione **Administrar directivas de acceso y solicitudes.**</span><span class="sxs-lookup"><span data-stu-id="ec346-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ec346-173">Seleccione la solicitud pendiente y, a continuación, seleccione **Aprobar** para conceder acceso a la cuenta de administrador global para crear una nueva regla de diario.</span><span class="sxs-lookup"><span data-stu-id="ec346-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="ec346-174">La cuenta de administrador global (el usuario solicitante) recibirá una confirmación por correo electrónico de que se ha concedido la aprobación.</span><span class="sxs-lookup"><span data-stu-id="ec346-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="ec346-175">Probar la creación de una nueva regla de diario con acceso con privilegios aprobado para la New-JournalRule tarea</span><span class="sxs-lookup"><span data-stu-id="ec346-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="ec346-176">En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto de PowerShell con la cuenta de administrador global para su entorno  >   de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec346-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="ec346-177">En Exchange Management PowerShell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="ec346-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="ec346-178">Ver que la nueva regla de diario se creó correctamente en Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec346-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="ec346-179">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="ec346-179">Next step</span></span>

<span data-ttu-id="ec346-180">Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec346-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec346-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec346-181">See also</span></span>

[<span data-ttu-id="ec346-182">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ec346-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ec346-183">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec346-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ec346-184">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec346-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
