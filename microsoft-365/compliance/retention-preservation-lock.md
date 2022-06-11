---
title: Usar el Bloqueo de conservación para restringir los cambios en las directivas de retención
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
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Use el Bloqueo de conservación con las directivas de retención y las directivas de etiquetas de retención para ayudar a cumplir los requisitos normativos y protegerse frente a administradores no autorizados.
ms.openlocfilehash: 228d4cd1a7778b5352df6d10d31b7e4c25af915f
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016292"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>Usar el Bloqueo de conservación para restringir los cambios en las directivas de retención y en las directivas de las etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

> [!IMPORTANT]
> Actualmente, los [ámbitos de directiva adaptables](retention.md#adaptive-or-static-policy-scopes-for-retention) no admiten el Bloqueo de conservación.

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

Configure el Bloqueo de conservación después de crear una [directiva de retención](create-retention-policies.md) o una directiva de etiquetas de retención que [publique](create-apply-retention-labels.md) y contenga solo etiquetas que [marquen elementos como registros normativos](records-management.md#records).

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>Cómo bloquear una directiva de retención o una directiva de etiquetas de retención

Si necesita usar el Bloqueo de conservación, debe usar PowerShell. Los administradores no pueden deshabilitar ni eliminar una directiva de retención una vez que se aplica el Bloqueo de conservación, por lo que la habilitación de esta característica no está disponible en la interfaz del usuario con el fin de evitar una configuración accidental.

Todas las directivas de retención con cualquier configuración admiten el Bloqueo de conservación. Para aplicar el Bloqueo de conservación en una directiva de etiqueta de retención, solo debe contener etiquetas que marquen elementos como registros normativos.

1. [Conéctese al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)

2. Busque el nombre de la directiva que desea bloquear ejecutando [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy). Por ejemplo:
    
   ![Lista de las directivas de retención en PowerShell.](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. Para colocar un Bloqueo de preservación en la directiva, ejecute el cmdlet [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) con el nombre de la directiva, y con el parámetro *RestrictiveRetention* establecido en true:
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" -RestrictiveRetention $true
    ```
    
    Por ejemplo:
    
    ![Parámetro RestrictiveRetention de PowerShell.](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     Cuando se le solicite, lea y acepte las restricciones que se incluyen en esta configuración y elija **Sí**:
    
   ![Preguntar para confirmar que desea bloquear una directiva de retención en PowerShell.](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Ahora, se coloca un Bloqueo de preservación en la directiva. Para confirmar, vuelva a ejecutar `Get-RetentionCompliancePolicy`, pero especifique el nombre de la directiva y muestre los parámetros de la directiva:

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

Debería ver **restrictRetention** está establecido en **True**. Por ejemplo:

![Directiva bloqueada con todos los parámetros visibles en PowerShell.](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>Consulte también

[Recursos para ayudarle a cumplir los requerimientos reglamentarios para la administración del ciclo de vida de datos y de registros](retention-regulatory-requirements.md)
