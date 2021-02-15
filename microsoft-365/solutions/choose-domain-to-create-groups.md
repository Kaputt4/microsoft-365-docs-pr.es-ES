---
title: Elegir el dominio que se usará al crear grupos de Microsoft 365
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
description: Learn to choose the domain to use when creating Microsoft 365 groups by configuring email address policies using PowerShell.
ms.openlocfilehash: 1e56268c3994b1ac822869d154be826326039bfc
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612945"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Elegir el dominio que se usará al crear grupos de Microsoft 365

Algunas organizaciones utilizan dominios de correo electrónico diferentes para segmentar diferentes partes de la empresa. Puede especificar qué dominio debe usarse cuando los usuarios creen grupos de Microsoft 365.
  
Si su organización necesita que los usuarios creen sus grupos en dominios distintos del dominio aceptado predeterminado de su empresa, puede permitir esto configurando directivas de direcciones de correo electrónico (EPE) con PowerShell.

Antes de ejecutar los cmdlets de PowerShell, descargue e instale un módulo que le permitirá hablar con su organización. Consulte [Conectarse a Exchange Online con PowerShell remoto.](https://go.microsoft.com/fwlink/p/?LinkId=785881)

## <a name="example-scenarios"></a>Escenarios de ejemplo

Supongamos que el dominio principal de su empresa es Contoso.com. Pero el dominio aceptado predeterminado de su organización es service.contoso.com. Esto significa que se crearán grupos en service.contoso.com (por ejemplo, jimsteam@service.contoso.com).
  
Supongamos que también tiene subdominios configurados en su organización. También desea que los grupos se cree en estos dominios:
  
- students.contoso.com para estudiantes
    
- faculty.contoso.com para miembros del profesorado
    
Los dos escenarios siguientes explican cómo se lograría esto.

> [!NOTE]
> Cuando tienes EAP de mulas, se evalúan en el orden de prioridad. Un valor de 1 significa la prioridad más alta. Una vez que un EAP coincide, no se evalúa ningún EAP adicional y las direcciones que se marcan en el grupo son según el EAP coincidente. > si no hay EAP que coincidan con los criterios especificados, el grupo se aprovisiona en el dominio aceptado predeterminado de la organización. Consulte [Administrar dominios aceptados en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) para obtener más información sobre cómo agregar un dominio aceptado.
  
### <a name="scenario-1"></a>Escenario 1

En el siguiente ejemplo se muestra cómo aprovisionar todos los grupos de Microsoft 365 de su organización en el groups.contoso.com local.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Escenario 2

Supongamos que desea controlar en qué subdominios se crean los grupos de Microsoft 365. Quieres:
  
- Grupos creados por alumnos (usuarios que tienen **Departamento** establecido en **Estudiantes)** en el students.groups.contoso.com local. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupos creados por miembros del profesorado (usuarios que tienen **Departamento** establecido en Profesores o la dirección de correo electrónico contiene **faculty.contoso.com)** en el faculty.groups.contoso.com principal. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Los grupos creados por cualquier otro usuario se crean en el groups.contoso.com usuario. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Cambiar las directivas de direcciones de correo electrónico

Para cambiar la prioridad o las plantillas de dirección de correo electrónico para un EAP existente, use el cmdlet Set-EmailAddressPolicy.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Cambiar un EAP no afecta a los grupos que ya se han aprovisionado.
  
## <a name="delete-email-address-policies"></a>Eliminar directivas de direcciones de correo electrónico

Para eliminar un EAP, use el cmdlet Remove-EmailAddressPolicy datos.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Cambiar un EAP no afecta a los grupos que ya se han aprovisionado.
  
## <a name="hybrid-requirements"></a>Requisitos híbridos

Si su organización está configurada en un escenario híbrido, consulte Configurar grupos de [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) con Exchange híbrido local para asegurarse de que su organización cumple los requisitos para crear grupos de Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Información adicional sobre el uso de grupos de directivas de direcciones de correo electrónico:

Hay algunas cosas más que debe saber:
  
- La rapidez con la que se crean los grupos depende del número de EPE configurados en la organización.
    
- Los administradores y usuarios también pueden modificar dominios cuando crean grupos.
    
- El grupo de usuarios se determina mediante las consultas estándar (propiedades de usuario) que ya están disponibles. Des check [out Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties. 
    
- Si no configuras ningún EAP para grupos, se selecciona el dominio aceptado predeterminado para la creación de grupos.
    
- Si quitas un dominio aceptado, debes actualizar primero las EPE; de lo contrario, el aprovisionamiento de grupos se verá afectado.
    
- Se puede configurar un límite máximo de 100 directivas de direcciones de correo electrónico para una organización.
    
## <a name="related-articles"></a>Artículos relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear un plan de gobierno de colaboración](collaboration-governance-first.md)

[Crear un grupo de Microsoft 365 en el Centro de administración](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
