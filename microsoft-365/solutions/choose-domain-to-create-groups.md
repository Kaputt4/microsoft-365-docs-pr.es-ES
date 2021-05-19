---
title: Elegir el dominio que se usará al crear Microsoft 365 grupos
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
recommendations: false
description: Aprenda a elegir el dominio que se va a usar al crear Microsoft 365 mediante la configuración de directivas de direcciones de correo electrónico mediante PowerShell.
ms.openlocfilehash: a0142ea5f5aa088c4be79fc8699a616d9cdd9390
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538224"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Elegir el dominio que se usará al crear Microsoft 365 grupos

Algunas organizaciones utilizan dominios de correo electrónico diferentes para segmentar diferentes partes de la empresa. Puede especificar qué dominio debe usarse cuando los usuarios creen Microsoft 365 grupos.
  
Si su organización necesita que los usuarios creen sus grupos en dominios distintos del dominio aceptado predeterminado de su empresa, puede permitirlo configurando directivas de direcciones de correo electrónico (APE) con PowerShell.

Antes de poder ejecutar los cmdlets de PowerShell, descargue e instale un módulo que le permitirá hablar con su organización. Consulte Conectar [para Exchange Online con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="example-scenarios"></a>Escenarios de ejemplo

Supongamos que el dominio principal de su empresa es Contoso.com. Pero el dominio aceptado predeterminado de la organización es service.contoso.com. Esto significa que los grupos se crearán en service.contoso.com (por ejemplo, jimsteam@service.contoso.com).
  
Supongamos que también tiene subdominios configurados en su organización. También desea que los grupos se creen en estos dominios:
  
- students.contoso.com para estudiantes
    
- faculty.contoso.com para profesores
    
Los dos escenarios siguientes explican cómo lograr esto.

> [!NOTE]
> Cuando se tienen EAP de mulitple, se evalúan en el orden de prioridad. Un valor de 1 significa la prioridad más alta. Una vez que un EAP coincide, no se evalúa ningún EAP más y las direcciones que se marcan en el grupo son según el EAP coincidente. > Si ningún AED coincide con los criterios especificados, el grupo se aprovisiona en el dominio aceptado predeterminado de la organización. Consulte [Administrar dominios aceptados en Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) para obtener más información sobre cómo agregar un dominio aceptado.
  
### <a name="scenario-1"></a>Escenario 1

En el ejemplo siguiente se muestra cómo aprovisionar todos los Microsoft 365 de la organización en el dominio groups.contoso.com usuario.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Escenario 2

Supongamos que desea controlar en qué subdominios Microsoft 365 se crean los grupos. Quieres:
  
- Grupos creados por alumnos (usuarios que tienen **Departamento** establecido en **Estudiantes)** en el students.groups.contoso.com de correo. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupos creados por miembros del  profesorado (usuarios que tienen departamento establecido en Profesor o dirección de correo electrónico contiene **faculty.contoso.com)**) en el faculty.groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Los grupos creados por cualquier otra persona se crean en el groups.contoso.com usuario. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Cambiar directivas de direcciones de correo electrónico

Para cambiar las plantillas de prioridad o dirección de correo electrónico para un EAP existente, use el cmdlet Set-EmailAddressPolicy correo electrónico.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Cambiar un EAP no tiene ningún impacto en los grupos que ya se han aprovisionado.
  
## <a name="delete-email-address-policies"></a>Eliminar directivas de direcciones de correo electrónico

Para eliminar un EAP, use el cmdlet Remove-EmailAddressPolicy.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Cambiar un EAP no tiene ningún impacto en los grupos que ya se han aprovisionado.
  
## <a name="hybrid-requirements"></a>Requisitos híbridos

Si la organización está configurada en un escenario híbrido, consulte [Configure Microsoft 365 groups with on-premises Exchange hybrid para](/exchange/hybrid-deployment/set-up-microsoft-365-groups) asegurarse de que la organización cumple los requisitos para crear Microsoft 365 grupos. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Información adicional sobre cómo usar grupos de directivas de direcciones de correo electrónico:

Hay que saber algunas cosas más:
  
- La forma en que se crean los grupos rápidos depende del número de EPE configurados en la organización.
    
- Los administradores y los usuarios también pueden modificar dominios al crear grupos.
    
- El grupo de usuarios se determina mediante las consultas estándar (propiedades de usuario) que ya están disponibles. Consulte [Propiedades filtrables para el parámetro -RecipientFilter](/powershell/exchange/recipientfilter-properties) para las propiedades filtrables admitidas. 
    
- Si no configura ningún EAP para grupos, se selecciona el dominio aceptado predeterminado para la creación de grupos.
    
- Si quita un dominio aceptado, primero debe actualizar los EPE, de lo contrario, el aprovisionamiento de grupos se verá afectado.
    
- Se puede configurar un límite máximo de 100 directivas de direcciones de correo electrónico para una organización.
    
## <a name="related-articles"></a>Artículos relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Crear un grupo Microsoft 365 en el Centro de administración](../admin/create-groups/create-groups.md)