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
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>Usar el Bloqueo de conservación para restringir los cambios en las directivas de retención y en las directivas de las etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

El Bloqueo de conservación bloquea una directiva de retención o directiva de etiquetas de retención de manera que ningún usuario, ni siquiera un administrador global, pueda desactivarla, eliminarla o hacer que sea menos restrictiva. Esta configuración podría ser necesaria para los requisitos normativos y puede ayudar a protegerse frente a administradores no autorizados.

Cuando una directiva de retención está bloqueada:

- Nadie puede deshabilitar la directiva ni eliminarla
- Las ubicaciones se pueden agregar pero no quitar
- Puede ampliar el período de retención, pero no disminuirlo

Cuando una directiva de etiquetas de retención está bloqueada:

- Nadie puede deshabilitar la directiva ni eliminarla
- Las ubicaciones se pueden agregar pero no quitar
- Las etiquetas se pueden agregar pero no quitar

En resumen, una directiva bloqueada se puede incrementar o ampliar, pero no se puede reducir ni desactivar.

> [!IMPORTANT]
> Antes de bloquear una directiva de retención o una directiva de etiquetas de retención, es importante que comprenda el impacto y confirme si es necesario para la organización. Por ejemplo, es posible que se necesite para cumplir los requisitos normativos. Los administradores no podrán deshabilitar ni eliminar esas directivas cuando se haya aplicado el Bloqueo de conservación.

Configure el Bloqueo de conservación después de crear una [directiva de retención](create-retention-policies.md)o una directiva de etiquetas de retención que se vaya a [publicar](create-apply-retention-labels.md) o [aplicar automáticamente](apply-retention-labels-automatically.md). 

> [!NOTE]
> El bloqueo de una directiva no impide que un administrador pueda reducir el período de retención de una etiqueta que esté incluida en la directiva bloqueada. Ese requisito, con otras restricciones, puede satisfacerse si se configura una etiqueta para marcar elementos como un [registro normativo](records-management.md#records).

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>Cómo bloquear una directiva de retención o una directiva de etiquetas de retención

Si necesita usar el Bloqueo de conservación, debe usar PowerShell. Los administradores no pueden deshabilitar ni eliminar una directiva de retención una vez que se aplica el Bloqueo de conservación, por lo que la habilitación de esta característica no está disponible en la interfaz del usuario con el fin de evitar una configuración accidental.

Todas las directivas de retención, con cualquier configuración, admiten el Bloqueo de conservación.

1. [Conéctese a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

2. Busque el nombre de la directiva que quiere bloquear ejecutando [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy). Por ejemplo:
    
   ![Lista de las directivas de retención en PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. Para colocar un Bloqueo de preservación en la directiva, ejecute el cmdlet [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) con el nombre de la directiva, y con el parámetro *RestrictiveRetention* establecido en true:
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    Por ejemplo:
    
    ![Parámetro RestrictiveRetention de PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     Cuando se le solicite, lea y acepte las restricciones que se incluyen en esta configuración y elija **Sí**:
    
   ![Preguntar para confirmar que desea bloquear una directiva de retención en PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Ahora, se coloca un Bloqueo de preservación en la directiva. Para confirmar, vuelva a ejecutar `Get-RetentionCompliancePolicy`, pero especifique el nombre de la directiva y muestre los parámetros de la directiva:

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

Debería ver que **RestrictiveRetention** esté establecida en **True**. Por ejemplo:

![Directiva bloqueada con todos los parámetros visibles en PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>Consulte también

[Recursos para ayudarle a cumplir los requisitos normativos para la gobernanza de información y la administración de registros](retention-regulatory-requirements.md)