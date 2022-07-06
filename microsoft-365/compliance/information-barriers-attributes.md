---
title: Atributos de barreras de información
description: Este artículo es una referencia para los atributos de cuenta de usuario de Azure Active Directory que puede usar para definir segmentos de barreras de información.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, barreras de información
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1549a0cb3bf03056b37a75175c3b24416bec7b5
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66639784"
---
# <a name="information-barriers-attributes"></a>Atributos de barreras de información

Algunos atributos de Azure Active Directory se pueden usar para segmentar usuarios en barreras de información (IB). Una vez definidos los segmentos, esos segmentos se pueden usar como filtros para las directivas de IB. Por ejemplo, puede usar **Departamento** para definir segmentos de usuarios por departamento dentro de su organización (suponiendo que ningún empleado único trabaje para dos departamentos al mismo tiempo).

En este artículo se describe cómo usar atributos con barreras de información y se proporciona una lista de atributos que se pueden usar. Para obtener más información sobre las barreras de información, consulte los siguientes recursos:

- [Barreras de información](information-barriers.md)
- [Definición de directivas para barreras de información en Microsoft Teams](information-barriers-policies.md)
- [Editar (o quitar) directivas de IB](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-ib-policies"></a>Uso de atributos en directivas de IB

Los atributos enumerados en este artículo se pueden usar para definir o editar segmentos de usuarios. Los segmentos definidos sirven como parámetros (denominados valores *UserGroupFilter* ) en [las directivas de IB](information-barriers-policies.md).

1. Determine qué atributo desea usar para definir segmentos. (Consulte la sección [Referencia](#reference) de este artículo).

2. Asegúrese de que las cuentas de usuario tienen valores rellenados para los atributos seleccionados en el paso 1. Vea los detalles de la cuenta de usuario y, si es necesario, edite las cuentas de usuario para incluir valores de atributo. 

    - Para editar varias cuentas (o usar PowerShell para editar una sola cuenta), consulte [Configuración de propiedades de cuenta de usuario con Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

    - Para editar una sola cuenta, consulte [Agregar o actualizar la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Defina segmentos mediante PowerShell](information-barriers-policies.md#define-segments-using-powershell), de forma similar a los ejemplos siguientes:

    |**Ejemplo**|**Cmdlet**|
    |:----------|:---------|
    | Definición de un segmento denominado Segment1 mediante el atributo Department | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Defina un segmento denominado SegmentA mediante el atributo MemberOf (supongamos que este atributo contiene nombres de grupo, como "BlueGroup") | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Defina un segmento denominado DayTraders mediante ExtensionAttribute1 (supongamos que este atributo contiene títulos de trabajo, como "DayTrader") | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Al definir segmentos, use el mismo atributo para todos los segmentos. Por ejemplo, si define algunos segmentos mediante *Department*, defina todos los segmentos mediante *Department*. No defina algunos segmentos mediante *Department* y otros mediante *MemberOf*. Asegúrese de que los segmentos no se superpongan; cada usuario debe asignarse exactamente a un segmento.

## <a name="reference"></a>Referencia

En la tabla siguiente se enumeran los atributos que puede usar con las barreras de información.

|**Nombre<br/> de propiedad de Azure Active Directory (nombre para mostrar LDAP)**|**Nombre de propiedad de Exchange**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Empresa | Empresa |
| Departamento | Departamento |
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
| PhysicalDeliveryOfficeName | Oficina |
| PostalCode | PostalCode |
| Proxyaddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| Correo | WindowsEmailAddress |
| Descripción | Descripción |
| Miembro | MemberOfGroup |

## <a name="resources"></a>Recursos

- [Definición de directivas para barreras de información en Microsoft Teams](information-barriers-policies.md)
- [Solución de problemas de barreras de información](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)
- [Barreras de información](information-barriers.md)
