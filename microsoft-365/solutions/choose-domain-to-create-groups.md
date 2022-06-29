---
title: Elegir el dominio que se va a usar al crear grupos de Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: Aprenda a elegir el dominio que se va a usar al crear grupos de Microsoft 365 mediante la configuración de directivas de direcciones de correo electrónico mediante PowerShell.
ms.openlocfilehash: bd9fad340d136fe4cac228f94f1904761cff7071
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490905"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Elegir el dominio que se va a usar al crear grupos de Microsoft 365

Algunas organizaciones utilizan dominios de correo electrónico diferentes para segmentar diferentes partes de la empresa. Puede especificar qué dominio debe usarse cuando los usuarios creen grupos de Microsoft 365.
  
Si su organización necesita que los usuarios creen sus grupos en dominios distintos del dominio aceptado predeterminado de su empresa, puede permitirlo configurando directivas de direcciones de correo electrónico (EAP) mediante PowerShell.

Para poder ejecutar los cmdlets de PowerShell, descargue e instale un módulo que le permita comunicarse con su organización. Consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="example-scenarios"></a>Escenarios de ejemplo

Supongamos que el dominio principal de su empresa es Contoso.com. Pero el dominio aceptado predeterminado de la organización es service.contoso.com. Esto significa que se crearán grupos en service.contoso.com (por ejemplo, jimsteam@service.contoso.com).
  
Supongamos que también tiene subdominios configurados en su organización. También quiere que los grupos se creen en estos dominios:
  
- students.contoso.com para estudiantes
    
- faculty.contoso.com para profesores
    
En los dos escenarios siguientes se explica cómo lograría esto.

> [!NOTE]
> Cuando tiene EAP de mulitple, se evalúan en el orden de prioridad. Un valor de 1 significa la prioridad más alta. Una vez que un EAP coincide, no se evalúa ningún EAP más y las direcciones que se marcan en el grupo son según el EAP coincidente. > Si ningún EAP coincide con los criterios especificados, el grupo se aprovisiona en el dominio aceptado predeterminado de la organización. Consulte [Administración de dominios aceptados en Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) para obtener más información sobre cómo agregar un dominio aceptado.
  
### <a name="scenario-1"></a>Escenario 1

En el ejemplo siguiente se muestra cómo aprovisionar todos los grupos de Microsoft 365 de su organización en el dominio groups.contoso.com.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Escenario 2

Supongamos que desea controlar en qué subdominios se crean los grupos de Microsoft 365. Quieres:
  
- Grupos creados por alumnos (usuarios que tienen **department** establecido en **Students**) en el dominio students.groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Los grupos creados por los miembros del profesorado (usuarios que tienen el **departamento** establecido en **Faculty o la dirección de correo electrónico contiene faculty.contoso.com)**) en el dominio faculty.groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Los grupos creados por cualquier otra persona se crean en el dominio groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```
> [!NOTE]
> Este escenario no funciona cuando el registro MX apunta al filtrado de correo no deseado de terceros.
 
## <a name="change-email-address-policies"></a>Cambio de directivas de direcciones de correo electrónico

Para cambiar la prioridad o las plantillas de dirección de correo electrónico para un EAP existente, use el cmdlet Set-EmailAddressPolicy.
  
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

Si su organización está configurada en un escenario híbrido, consulte [Configuración de grupos de Microsoft 365 con exchange híbrido local](/exchange/hybrid-deployment/set-up-microsoft-365-groups) para asegurarse de que su organización cumple los requisitos para crear grupos de Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Información adicional sobre el uso de grupos de directivas de direcciones de correo electrónico:

Hay algunas cosas más que saber:
  
- La rapidez con la que se crean los grupos depende del número de EAP configurados en la organización.
    
- Los administradores y los usuarios también pueden modificar dominios cuando crean grupos.
    
- El grupo de usuarios se determina mediante las consultas estándar (propiedades de usuario) que ya están disponibles. Consulte [Propiedades filtrables del parámetro -RecipientFilter](/powershell/exchange/recipientfilter-properties) para ver las propiedades filtrables admitidas. 
    
- Si no configura ningún EAP para grupos, se selecciona el dominio aceptado predeterminado para la creación de grupos.
    
- Si quita un dominio aceptado, primero debe actualizar los EAP; de lo contrario, el aprovisionamiento de grupos se verá afectado.
    
- Se puede configurar un límite máximo de 100 directivas de direcciones de correo electrónico para una organización.
    
## <a name="related-content"></a>Contenido relacionado

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations) (artículo)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md) (artículo)

[Creación de un grupo de Microsoft 365 en el Centro de administración](../admin/create-groups/create-groups.md) (artículo)
