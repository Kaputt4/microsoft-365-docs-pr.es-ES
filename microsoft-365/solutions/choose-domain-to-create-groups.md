---
title: Elegir el dominio que se va a usar al crear grupos de 365 de Microsoft
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Obtenga información acerca de cómo elegir el dominio que se usará al crear grupos de Microsoft 365 mediante la configuración de directivas de direcciones de correo electrónico con PowerShell.
ms.openlocfilehash: bb6137a3dfce17bc9c94648e5ea9e12ec2776195
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377442"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Elegir el dominio que se va a usar al crear grupos de 365 de Microsoft

Algunas organizaciones utilizan dominios de correo electrónico diferentes para segmentar diferentes partes de la empresa. Puede especificar el dominio que debe usarse cuando los usuarios creen grupos de 365 de Microsoft.
  
Si su organización necesita que los usuarios creen sus grupos en dominios distintos del dominio aceptado predeterminado de su empresa, puede permitir esto mediante la configuración de directivas de direcciones de correo electrónico (EAPs) con PowerShell.

Antes de poder ejecutar los cmdlets de PowerShell, descargue e instale un módulo que le permitirá hablar con su organización. Consulte [conectarse a Exchange online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=785881).

## <a name="example-scenarios"></a>Escenarios de ejemplo

Supongamos que el dominio principal de su empresa es Contoso.com. Pero el dominio aceptado predeterminado de su organización es service.contoso.com. Esto significa que los grupos se crearán en service.contoso.com (por ejemplo, jimsteam@service.contoso.com).
  
Supongamos que también tiene subdominios configurados en la organización. También desea que los grupos se creen en estos dominios:
  
- students.contoso.com para estudiantes
    
- faculty.contoso.com para miembros de profesores
    
En los dos escenarios siguientes, se explica cómo hacerlo.

> [!NOTE]
> Cuando hay varios EAPs, se evalúan en el orden de prioridad. Un valor de 1 indica la prioridad más alta. Una vez que un EAP coincide, no se evalúan más EAP y las direcciones que se marcan en el grupo son las establecidas por el EAP coincidente. > si ningún EAPs coincide con los criterios especificados, el grupo se aprovisiona en el dominio aceptado predeterminado de la organización. Consulte [Manage accepted Domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) para obtener más información sobre cómo agregar un dominio aceptado.
  
### <a name="scenario-1"></a>Escenario 1

En el ejemplo siguiente se muestra cómo aprovisionar todos los grupos de Microsoft 365 de la organización en el dominio groups.contoso.com.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Escenario 2

Supongamos que desea controlar en qué subdominios se crean los grupos de Microsoft 365. Quieres:
  
- Grupos creados por los alumnos (usuarios que tienen el **Departamento** establecido en **alumnos**) en el dominio Students.groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupos creados por los miembros de los profesores (los usuarios que tienen el **Departamento** establecido en **profesora o dirección de correo electrónico contienen Faculty.contoso.com)**) en el dominio Faculty.groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Los grupos creados por cualquier persona se crean en el dominio groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Cambiar las directivas de direcciones de correo electrónico

Para cambiar las plantillas de prioridad o dirección de correo electrónico de un EAP existente, use el cmdlet Set-EmailAddressPolicy.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

El cambio de un EAP no afecta a los grupos que ya se han aprovisionado.
  
## <a name="delete-email-address-policies"></a>Eliminar directivas de direcciones de correo electrónico

Para eliminar un EAP, use el cmdlet Remove-EmailAddressPolicy.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

El cambio de un EAP no afecta a los grupos que ya se han aprovisionado.
  
## <a name="hybrid-requirements"></a>Requisitos de entornos híbridos

Si su organización está configurada en un escenario híbrido, consulte [Configure Microsoft 365 Groups with on-premises Exchange híbrida](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) para asegurarse de que su organización cumple los requisitos para la creación de grupos de Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Información adicional acerca del uso de grupos de directivas de direcciones de correo electrónico:

Hay algunas cosas más que debe saber:
  
- La creación de grupos rápidos depende del número de EAPs configurados en la organización.
    
- Los administradores y los usuarios también pueden modificar los dominios cuando crean grupos.
    
- El grupo de usuarios se determina mediante las consultas estándar (propiedades de usuario) que ya están disponibles. Desproteger [propiedades filtrables para el parámetro-RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) para las propiedades filtrables admitidas. 
    
- Si no configura ningún EAPs para grupos, se seleccionará el dominio aceptado predeterminado para la creación de grupos.
    
- Si quita un dominio aceptado, debe actualizar el EAPs en primer lugar; de lo contrario, el aprovisionamiento de grupos se verá afectado.
    
- Se puede configurar un límite máximo de 100 directivas de direcciones de correo electrónico para una organización.
    
## <a name="related-articles"></a>Artículos relacionados

[Crear un grupo de 365 de Microsoft en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
