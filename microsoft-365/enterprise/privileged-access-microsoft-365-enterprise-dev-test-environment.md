---
title: Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Use esta guía de laboratorio de prueba para habilitar la administración con privilegios de acceso a su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871167"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f34f3-103">Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f34f3-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f34f3-104">Con las instrucciones de este artículo, configurar la administración del acceso con privilegios para aumentar la seguridad en su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f34f3-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f34f3-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f34f3-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f34f3-107">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f34f3-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f34f3-108">Si desea configurar la administración de acceso con privilegios en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f34f3-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f34f3-109">Si desea configurar la administración de acceso con privilegios en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f34f3-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f34f3-p101">Prueba de administración con privilegios de acceso no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Aquí se proporciona como una opción para que pueda probar con privilegios de acceso a la administración y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="f34f3-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="f34f3-112">Fase 2: Configuración de administración con privilegios de acceso</span><span class="sxs-lookup"><span data-stu-id="f34f3-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="f34f3-p102">En esta fase, configurar un grupo de aprobadores y habilitar la administración con privilegios de acceso para el entorno de prueba de Microsoft 365 Enterprise. Para obtener más información y una visión general de con privilegios de administración de acceso, consulte [administración de acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="f34f3-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="f34f3-115">Siga estos pasos para configurar y utilizar con privilegios de acceso de la organización de Office 365:</span><span class="sxs-lookup"><span data-stu-id="f34f3-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="f34f3-116">Paso 1: Crear el grupo del aprobador</span><span class="sxs-lookup"><span data-stu-id="f34f3-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="f34f3-p103">Antes de empezar a usar acceso con privilegios, determinar quién tendrá la autoridad de aprobación para las solicitudes entrantes para el acceso a las tareas con privilegios elevados y con privilegios. Cualquier usuario que forma parte del grupo de los aprobadores podrán aprobar las solicitudes de acceso. Esto se habilita mediante la creación de un grupo de seguridad habilitados para correo en Office 365. Crear un nuevo grupo de seguridad denominado "Aprobadores con privilegios de acceso" en su entorno de prueba y agregar el "usuario 3" creado anteriormente en los pasos de guía de laboratorio de prueba anterior.</span><span class="sxs-lookup"><span data-stu-id="f34f3-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="f34f3-121">Paso 2: Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="f34f3-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="f34f3-p104">Acceso con privilegios debe habilitarse explícitamente en Office 365 con el grupo de aprobadores predeterminada y, incluido un conjunto de cuentas del sistema que desea que se deben excluir desde el control de acceso de administración con privilegios de acceso. Asegúrese de habilitar el acceso con privilegios en su organización de Office 365 antes de iniciar la fase 3 de esta guía.</span><span class="sxs-lookup"><span data-stu-id="f34f3-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="f34f3-124">Fase 3: Compruebe que se necesita aprobación para tareas con privilegios elevados y con privilegios</span><span class="sxs-lookup"><span data-stu-id="f34f3-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="f34f3-125">En esta fase, compruebe que funciona la directiva de acceso con privilegios y los usuarios requieren aprobación para ejecutar tareas con privilegios elevados y con privilegios definidas.</span><span class="sxs-lookup"><span data-stu-id="f34f3-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="f34f3-126">Probar la capacidad de ejecutar una tarea no definida en una directiva de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="f34f3-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="f34f3-p105">En primer lugar, conéctese a Exchange Management PowerShell con las credenciales de un usuario configurado como un administrador Global en su entorno de prueba e intenta crear una nueva regla de diario. Actualmente, no se define la tarea de [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) en una directiva de acceso con privilegios para su organización.</span><span class="sxs-lookup"><span data-stu-id="f34f3-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="f34f3-129">En el equipo local, abra e inicie sesión en el la Exchange Online PowerShell módulo remoto en **Microsoft Corporation** > cuenta de**Microsoft Exchange Online PowerShell módulo remoto** con el administrador Global de su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f34f3-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f34f3-130">En Exchange Management Powershell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="f34f3-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="f34f3-131">Vista de que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f34f3-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="f34f3-132">Crear una nueva directiva de acceso con privilegios para la tarea de New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="f34f3-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="f34f3-133">Si aún no ha completado los pasos 1 y 2 de la fase 2 de esta guía, ser asegúrese de seguir los pasos para crear grupo del aprobador denominado "Privilegio acceso aprobadores" y para habilitar el acceso con privilegios en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f34f3-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="f34f3-134">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con las credenciales de la cuenta de administrador Global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f34f3-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f34f3-135">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f34f3-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f34f3-136">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f34f3-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f34f3-137">Seleccione **la configuración de directivas** y seleccione **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="f34f3-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="f34f3-138">En los campos de lista desplegable, seleccione o introduzca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f34f3-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="f34f3-139">**Tipo de directiva**: tarea</span><span class="sxs-lookup"><span data-stu-id="f34f3-139">**Policy type**: Task</span></span>

    <span data-ttu-id="f34f3-140">**Ámbito de directiva**: Exchange</span><span class="sxs-lookup"><span data-stu-id="f34f3-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="f34f3-141">**Nombre de la directiva**: nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="f34f3-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="f34f3-142">**Tipo de aprobación**: Manual</span><span class="sxs-lookup"><span data-stu-id="f34f3-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="f34f3-143">**Grupo de aprobación**: aprobadores con privilegios de acceso</span><span class="sxs-lookup"><span data-stu-id="f34f3-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="f34f3-p106">Seleccione **crear** y, a continuación, en **Cerrar**. Puede tardar unos minutos para la directiva ser totalmente configurado y habilitado. Asegúrese de permitir tiempo para la directiva a habilitarse completamente antes de probar el requisito de aprobación en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="f34f3-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="f34f3-147">Requisito de aprobación de prueba para la tarea de New-JournalRule definida en una directiva de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="f34f3-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="f34f3-148">En el equipo local, abra e inicie sesión en el la Exchange Online PowerShell módulo remoto en **Microsoft Corporation** > cuenta de**Microsoft Exchange Online PowerShell módulo remoto** mediante un uso de la administración Global de la prueba entorno.</span><span class="sxs-lookup"><span data-stu-id="f34f3-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f34f3-149">En Exchange Management Powershell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="f34f3-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="f34f3-150">Ver el error "No hay suficiente permisos" en PowerShell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="f34f3-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="f34f3-151">Solicitud de acceso para crear una nueva regla de diario mediante la tarea de New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="f34f3-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="f34f3-152">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con la cuenta de administrador Global para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f34f3-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f34f3-153">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f34f3-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f34f3-154">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f34f3-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f34f3-p107">Seleccione **nueva solicitud**. En los campos de lista desplegable, seleccione los valores apropiados para su organización:</span><span class="sxs-lookup"><span data-stu-id="f34f3-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="f34f3-157">**Tipo de solicitud**: tarea</span><span class="sxs-lookup"><span data-stu-id="f34f3-157">**Request type**: Task</span></span>

    <span data-ttu-id="f34f3-158">**Ámbito de solicitud**: Exchange</span><span class="sxs-lookup"><span data-stu-id="f34f3-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="f34f3-159">**Solicitud para**: nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="f34f3-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="f34f3-160">**Duración (horas)**: 2</span><span class="sxs-lookup"><span data-stu-id="f34f3-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="f34f3-161">**Comentarios**: solicitar permiso para crear una nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="f34f3-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="f34f3-p108">Seleccione **Guardar** y, a continuación, en **Cerrar**. La solicitud se enviará al grupo del aprobador a través de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f34f3-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="f34f3-164">Aprobar solicitudes de acceso con privilegios para la creación de una nueva regla de diario</span><span class="sxs-lookup"><span data-stu-id="f34f3-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="f34f3-165">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con las credenciales para el usuario 3 en su entorno de prueba (miembros del grupo de seguridad "Aprobadores con privilegios de acceso" en su entorno de prueba).</span><span class="sxs-lookup"><span data-stu-id="f34f3-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="f34f3-166">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f34f3-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f34f3-167">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f34f3-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f34f3-p109">Seleccione la solicitud pendiente y seleccione **Aprobar** para conceder acceso a la cuenta de administrador Global para crear una nueva regla de diario. Se enviará un correo electrónico de notificación que confirma que se ha concedido la aprobación para la cuenta de administrador Global (el usuario solicitante).</span><span class="sxs-lookup"><span data-stu-id="f34f3-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="f34f3-170">Crear una nueva regla de diario con acceso con privilegios aprobado para la tarea de New-JournalRule de prueba</span><span class="sxs-lookup"><span data-stu-id="f34f3-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="f34f3-171">En el equipo local, abra e inicie sesión en el la Exchange Online PowerShell módulo remoto en **Microsoft Corporation** > cuenta de**Microsoft Exchange Online PowerShell módulo remoto** con el administrador Global de su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f34f3-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f34f3-172">En Exchange Management Powershell, cree una nueva regla de diario para su organización:</span><span class="sxs-lookup"><span data-stu-id="f34f3-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="f34f3-173">Vista de que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f34f3-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="f34f3-174">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="f34f3-174">Next step</span></span>

<span data-ttu-id="f34f3-175">Explorar las características adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f34f3-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f34f3-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="f34f3-176">See also</span></span>

[<span data-ttu-id="f34f3-177">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f34f3-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f34f3-178">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f34f3-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f34f3-179">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f34f3-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)