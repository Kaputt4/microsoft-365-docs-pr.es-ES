---
title: Atributos para las directivas de barreras de información
description: Este artículo es una referencia para los atributos de cuenta de usuario de Azure Active Directory que puede usar para definir segmentos de barrera de información.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919736"
---
# <a name="attributes-for-information-barrier-policies"></a>Atributos para las directivas de barreras de información

Algunos atributos de Azure Active Directory se pueden usar para segmentar usuarios. Una vez definidos los segmentos, estos segmentos se pueden usar como filtros para las directivas de barrera de información. Por ejemplo, puede usar **Department** para definir segmentos de usuarios por departamento dentro de su organización (suponiendo que ningún empleado trabaje para dos departamentos al mismo tiempo).

En este artículo se describe cómo usar atributos con barreras de información y se proporciona una lista de atributos que se pueden usar. Para obtener más información sobre las barreras de información, vea los siguientes recursos:

- [Barreras de información](information-barriers.md)
- [Definir directivas para barreras de información en Microsoft Teams](information-barriers-policies.md)
- [Editar (o quitar) directivas de barrera de información](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Cómo usar atributos en directivas de barrera de información

Los atributos enumerados en este artículo se pueden usar para definir o editar segmentos de usuarios. Los segmentos definidos sirven como parámetros *(denominados valores UserGroupFilter)* en las [directivas de barrera de información.](information-barriers-policies.md)

1. Determine qué atributo desea usar para definir segmentos. (Vea la [sección Referencia](#reference) de este artículo).

2. Asegúrese de que las cuentas de usuario tienen valores rellenados para los atributos seleccionados en el paso 1. Vea los detalles de la cuenta de usuario y, si es necesario, edite las cuentas de usuario para incluir valores de atributo. 

    - Para editar varias cuentas (o usar PowerShell para editar una sola cuenta), vea [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

    - Para editar una sola cuenta, vea Agregar o actualizar la información de perfil de un usuario [con Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Defina segmentos con PowerShell](information-barriers-policies.md#define-segments-using-powershell), de forma similar a los ejemplos siguientes:

    |**Ejemplo**|**Cmdlet**|
    |:----------|:---------|
    | Definir un segmento denominado Segment1 mediante el atributo Department | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Definir un segmento denominado SegmentA mediante el atributo MemberOf (supongamos que este atributo contiene nombres de grupo, como "BlueGroup") | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Definir un segmento denominado DayTraders mediante ExtensionAttribute1 (supongamos que este atributo contiene títulos de trabajo, como "DayTrader") | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Al definir segmentos, use el mismo atributo para todos los segmentos. Por ejemplo, si define algunos segmentos mediante *Department*, defina todos los segmentos mediante *Department*. No defina algunos segmentos con *Department* y otros con *MemberOf*. Asegúrese de que los segmentos no se superponen; cada usuario debe estar asignado exactamente a un segmento.

## <a name="reference"></a>Referencia

En la tabla siguiente se enumeran los atributos que puede usar con barreras de información.

|**Nombre de la propiedad de Azure Active Directory <br/> (nombre para mostrar ldap)**|**Nombre de la propiedad Exchange**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
| Department | Department |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| Correo | WindowsEmailAddress |
| Descripción | Descripción |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>Recursos

- [Definir directivas para barreras de información en Microsoft Teams](information-barriers-policies.md)
- [Solución de problemas de barreras de información](information-barriers-troubleshooting.md)
- [Barreras de información](information-barriers.md)