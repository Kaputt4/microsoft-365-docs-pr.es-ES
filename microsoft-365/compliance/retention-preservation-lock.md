---
title: Usar el Bloqueo de conservación para restringir los cambios en las directivas de retención y en las directivas de las etiquetas de retención
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Use el Bloqueo de conservación con las directivas de retención y las directivas de etiquetas de retención para ayudar a cumplir los requisitos normativos y protegerse frente a administradores no autorizados.
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922534"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="c67f8-103">Usar el Bloqueo de conservación para restringir los cambios en las directivas de retención y en las directivas de las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="c67f8-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="c67f8-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="c67f8-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="c67f8-105">El Bloqueo de conservación bloquea una directiva de retención o directiva de etiquetas de retención de manera que ningún usuario, ni siquiera un administrador global, pueda desactivarla, eliminarla o hacer que sea menos restrictiva.</span><span class="sxs-lookup"><span data-stu-id="c67f8-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="c67f8-106">Esta configuración podría ser necesaria para los requisitos normativos y puede ayudar a protegerse frente a administradores no autorizados.</span><span class="sxs-lookup"><span data-stu-id="c67f8-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="c67f8-107">Cuando una directiva de retención está bloqueada:</span><span class="sxs-lookup"><span data-stu-id="c67f8-107">When a retention policy is locked:</span></span>

- <span data-ttu-id="c67f8-108">Nadie puede deshabilitar la directiva ni eliminarla</span><span class="sxs-lookup"><span data-stu-id="c67f8-108">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="c67f8-109">Las ubicaciones se pueden agregar pero no quitar</span><span class="sxs-lookup"><span data-stu-id="c67f8-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="c67f8-110">Puede ampliar el período de retención, pero no disminuirlo</span><span class="sxs-lookup"><span data-stu-id="c67f8-110">You can extend the retention period but not decrease it</span></span>

<span data-ttu-id="c67f8-111">Cuando una directiva de etiquetas de retención está bloqueada:</span><span class="sxs-lookup"><span data-stu-id="c67f8-111">When a retention label policy is locked:</span></span>

- <span data-ttu-id="c67f8-112">Nadie puede deshabilitar la directiva ni eliminarla</span><span class="sxs-lookup"><span data-stu-id="c67f8-112">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="c67f8-113">Las ubicaciones se pueden agregar pero no quitar</span><span class="sxs-lookup"><span data-stu-id="c67f8-113">Locations can be added but not removed</span></span>
- <span data-ttu-id="c67f8-114">Las etiquetas se pueden agregar pero no quitar</span><span class="sxs-lookup"><span data-stu-id="c67f8-114">Labels can be added but not removed</span></span>

<span data-ttu-id="c67f8-115">En resumen, una directiva bloqueada se puede incrementar o ampliar, pero no se puede reducir ni desactivar.</span><span class="sxs-lookup"><span data-stu-id="c67f8-115">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c67f8-116">Antes de bloquear una directiva de retención o una directiva de etiquetas de retención, es importante que comprenda el impacto y confirme si es necesario para la organización.</span><span class="sxs-lookup"><span data-stu-id="c67f8-116">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="c67f8-117">Por ejemplo, es posible que se necesite para cumplir los requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="c67f8-117">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="c67f8-118">Los administradores no podrán deshabilitar ni eliminar esas directivas cuando se haya aplicado el Bloqueo de conservación.</span><span class="sxs-lookup"><span data-stu-id="c67f8-118">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="c67f8-119">Configure el Bloqueo de conservación después de crear una [directiva de retención](create-retention-policies.md)o una directiva de etiquetas de retención que se vaya a [publicar](create-apply-retention-labels.md) o [aplicar automáticamente](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="c67f8-119">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="c67f8-120">El bloqueo de una directiva no impide que un administrador pueda reducir el período de retención de una etiqueta que esté incluida en la directiva bloqueada.</span><span class="sxs-lookup"><span data-stu-id="c67f8-120">Locking a label policy doesn't prevent an administrator from reducing the retention period in a label that is included in the locked policy.</span></span> <span data-ttu-id="c67f8-121">Ese requisito, con otras restricciones, puede satisfacerse si se configura una etiqueta para marcar elementos como un [registro normativo](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="c67f8-121">That requirement, with other restrictions, can be met when you configure a label to mark items as a [regulatory record](records-management.md#records).</span></span>

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="c67f8-122">Cómo bloquear una directiva de retención o una directiva de etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="c67f8-122">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="c67f8-123">Si necesita usar el Bloqueo de conservación, debe usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c67f8-123">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="c67f8-124">Los administradores no pueden deshabilitar ni eliminar una directiva de retención una vez que se aplica el Bloqueo de conservación, por lo que la habilitación de esta característica no está disponible en la interfaz del usuario con el fin de evitar una configuración accidental.</span><span class="sxs-lookup"><span data-stu-id="c67f8-124">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="c67f8-125">Todas las directivas de retención, con cualquier configuración, admiten el Bloqueo de conservación.</span><span class="sxs-lookup"><span data-stu-id="c67f8-125">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="c67f8-126">[Conéctese a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c67f8-126">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c67f8-127">Busque el nombre de la directiva que quiere bloquear ejecutando [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="c67f8-127">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="c67f8-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c67f8-128">For example:</span></span>
    
   ![Lista de las directivas de retención en PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="c67f8-130">Para colocar un Bloqueo de preservación en la directiva, ejecute el cmdlet [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) con el nombre de la directiva, y con el parámetro *RestrictiveRetention* establecido en true:</span><span class="sxs-lookup"><span data-stu-id="c67f8-130">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="c67f8-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c67f8-131">For example:</span></span>
    
    ![Parámetro RestrictiveRetention de PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="c67f8-133">Cuando se le solicite, lea y acepte las restricciones que se incluyen en esta configuración y elija **Sí**:</span><span class="sxs-lookup"><span data-stu-id="c67f8-133">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![Preguntar para confirmar que desea bloquear una directiva de retención en PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="c67f8-135">Ahora, se coloca un Bloqueo de preservación en la directiva.</span><span class="sxs-lookup"><span data-stu-id="c67f8-135">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="c67f8-136">Para confirmar, vuelva a ejecutar `Get-RetentionCompliancePolicy`, pero especifique el nombre de la directiva y muestre los parámetros de la directiva:</span><span class="sxs-lookup"><span data-stu-id="c67f8-136">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="c67f8-137">Debería ver que **RestrictiveRetention** esté establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="c67f8-137">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="c67f8-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c67f8-138">For example:</span></span>

![Directiva bloqueada con todos los parámetros visibles en PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="c67f8-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c67f8-140">See also</span></span>

[<span data-ttu-id="c67f8-141">Recursos para ayudarle a cumplir los requisitos normativos para la gobernanza de información y la administración de registros</span><span class="sxs-lookup"><span data-stu-id="c67f8-141">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)