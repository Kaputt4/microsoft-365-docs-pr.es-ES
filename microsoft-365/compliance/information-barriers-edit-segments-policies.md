---
title: Administrar directivas de barreras de información
description: Aprenda a editar o quitar directivas para barreras de información.
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
ms.openlocfilehash: 0d46459f61b29c6bdb457c7e0c82e9147e7709ba
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126145"
---
# <a name="manage-information-barrier-policies"></a>Administrar directivas de barreras de información

Una vez [definidas](information-barriers-policies.md)las directivas de barreras de información, es posible que [](information-barriers-troubleshooting.md) deba realizar cambios en dichas directivas o en los segmentos de usuario, como parte de la solución de problemas o como mantenimiento normal. Use este artículo como guía.

## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

|**Acción**|**Descripción**|
|:---------|:--------------|
| [Editar atributos de cuenta de usuario](#edit-user-account-attributes) | Rellene los atributos de Azure Active Directory que se pueden usar para definir segmentos.<br/>Edite los atributos de cuenta de usuario cuando los usuarios no se incluyan en los segmentos en los que deben estar, para cambiar los segmentos en los que se encuentran los usuarios o para definir segmentos con atributos diferentes. |
| [Editar un segmento](#edit-a-segment) | Edite los segmentos cuando desee cambiar la forma en que se define un segmento. <br/>Por ejemplo, es posible que haya definido segmentos originalmente con *Department* y ahora quiera usar otro atributo, como *MemberOf*. |
| [Editar una directiva](#edit-a-policy) | Edite una directiva de barreras de información cuando desee cambiar el funcionamiento de una directiva.<br/>Por ejemplo, en lugar de bloquear las comunicaciones entre dos segmentos, puede decidir que desea permitir que las comunicaciones solo se produzcan entre ciertos segmentos. |
| [Establecer una directiva en estado inactivo](#set-a-policy-to-inactive-status) |Establece una directiva en estado inactivo cuando quieras realizar cambios en una directiva o cuando no quieras que una directiva esté en vigor. |
| [Quitar una directiva](#remove-a-policy) | Quite una directiva de barreras de información cuando ya no necesite una directiva concreta. |
| [Detener una aplicación de directiva](#stop-a-policy-application) | Tome esta acción cuando desee detener el proceso de aplicación de directivas de barreras de información.<br/> La detención de una aplicación de directiva no es instantánea y no deshace las directivas que ya se han aplicado a los usuarios. |
| [Definir directivas para barreras de información](information-barriers-policies.md) | Defina una directiva de barreras de información cuando aún no tenga dichas directivas en su lugar y debe restringir o limitar las comunicaciones entre grupos de usuarios específicos. |
| [Solución de problemas de barreras de información](information-barriers-troubleshooting.md) | Consulte este artículo cuando se tope con problemas inesperados con barreras de información. |

> [!IMPORTANT]
> Para realizar las tareas descritas en este artículo, se le debe asignar un rol adecuado, como uno de los siguientes:<br/>- Administrador global de Microsoft 365 Enterprise<br/>- Administrador global<br/>- Administrador de cumplimiento<br/>- Administración de cumplimiento de LAC (este es un nuevo rol)<br><br>Para obtener más información acerca de los requisitos previos para las barreras de información, consulte [Requisitos previos (para directivas de barreras de información).](information-barriers-policies.md#prerequisites)<br><br> Asegúrese de [conectarse a PowerShell del Centro & seguridad y cumplimiento.](/powershell/exchange/connect-to-scc-powershell)

## <a name="edit-user-account-attributes"></a>Editar atributos de cuenta de usuario

Use este procedimiento para editar atributos que se usan para segmentar usuarios. Por ejemplo, si usa un atributo Department y una o más cuentas de usuario no tienen actualmente ningún valor enumerado para Department, debe editar esas cuentas de usuario para incluir información de departamento. Los atributos de cuenta de usuario se usan para definir segmentos de modo que se puedan asignar directivas de barreras de información.

1. Para ver los detalles de una cuenta de usuario específica, como los valores de atributo y los segmentos asignados, use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. <p> (También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>` ) |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*. |

2. Determina qué atributo quieres editar para los perfiles de cuenta de usuario. Para obtener más información, vea [Atributos para las directivas de barreras de información.](information-barriers-attributes.md) 

3. Edite una o más cuentas de usuario para incluir valores para el atributo que seleccionó en el paso anterior. Para realizar esta acción, use uno de los siguientes procedimientos:

    - Para editar una sola cuenta, vea Agregar o actualizar la información de perfil de un usuario [con Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

    - Para editar varias cuentas (o usar PowerShell para editar una sola cuenta), vea Configurar las propiedades de la cuenta de usuario [con PowerShell de Office 365.](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

## <a name="edit-a-segment"></a>Editar un segmento

Use este procedimiento para editar la definición de un segmento de usuario. Por ejemplo, puede cambiar el nombre de un segmento o el filtro que se usa para determinar quién está incluido en el segmento.

1. Para ver todos los segmentos existentes, use el cmdlet **Get-OrganizationSegment.**

    Sintaxis: `Get-OrganizationSegment`

    Verá una lista de segmentos y detalles para cada uno, como el tipo de segmento, su valor UserGroupFilter, quién lo creó o modificó por última vez, GUID, y así sucesivamente.

    > [!TIP]
    > Imprimir o guardar la lista de segmentos para su referencia más adelante. Por ejemplo, si desea editar un segmento, necesitará conocer su nombre o su valor de identificación (se usa con el parámetro Identity).

2. Para editar un segmento, use el cmdlet **Set-OrganizationSegment** con el parámetro **Identity** y los detalles relevantes.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> En este ejemplo, para el segmento que tiene el GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd,* actualizamos el nombre del departamento a "HRDept". |

Cuando haya terminado de editar segmentos para su organización, puede definir [o](information-barriers-policies.md#part-2-define-information-barrier-policies) [editar directivas](#edit-a-policy) de barreras de información.

## <a name="edit-a-policy"></a>Editar una directiva

1. Para ver una lista de directivas de barreras de información actuales, use el cmdlet **Get-InformationBarrierPolicy.**

    Sintaxis: `Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la directiva que desea cambiar. Tenga en cuenta el GUID y el nombre de la directiva.

2. Use el cmdlet **Set-InformationBarrierPolicy** con un parámetro **Identity** y especifique los cambios que desea realizar.

    Ejemplo: supongamos que se definió una directiva para impedir que el segmento *investigación* se comunique con los segmentos *ventas* *y marketing.* La directiva se definió con este cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Supongamos que queremos cambiarlo para que los usuarios del segmento *Investigación* solo puedan comunicarse con personas del segmento *de RECURSOS* HUMANOS. Para realizar este cambio, usamos este cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    En este ejemplo, cambiamos "SegmentsBlocked" a "SegmentsAllowed" y especificamos el segmento *hr.*

3. Cuando haya terminado de editar una directiva, asegúrese de aplicar los cambios. (Vea [Aplicar directivas de barreras de información).](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="set-a-policy-to-inactive-status"></a>Establecer una directiva en estado inactivo

1. Para ver una lista de directivas de barreras de información actuales, use el cmdlet **Get-InformationBarrierPolicy.**

    Sintaxis: `Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la directiva que desea cambiar (o quitar). Tenga en cuenta el GUID y el nombre de la directiva.

2. Para establecer el estado de la directiva en inactivo, use el cmdlet **Set-InformationBarrierPolicy** con un parámetro Identity y el parámetro State establecido en Inactivo.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> En este ejemplo, se establece una directiva de barreras de información con GUID *43c37853-ea10-4b90-a23d-ab8c9377247* en estado inactivo. |

3. Para aplicar los cambios, use el cmdlet **Start-InformationBarrierPoliciesApplication.**

    Sintaxis: `Start-InformationBarrierPoliciesApplication`

    Los cambios se aplican, usuario por usuario, a la organización. Si su organización es grande, este proceso puede tardar 24 horas (o más). (Como regla general, se tarda aproximadamente una hora en procesar 5.000 cuentas de usuario).

En este punto, una o más directivas de barreras de información se establecen en estado inactivo. Desde aquí, puede realizar cualquiera de las siguientes acciones:

- Mantenerlo tal como está (una directiva establecida en estado inactivo no tiene ningún efecto en los usuarios)
- [Editar una directiva](#edit-a-policy) 
- [Quitar una directiva](#remove-a-policy)

## <a name="remove-a-policy"></a>Quitar una directiva

1. Para ver una lista de directivas de barreras de información actuales, use el cmdlet **Get-InformationBarrierPolicy.**

    Sintaxis: `Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la directiva que desea quitar. Tenga en cuenta el GUID y el nombre de la directiva. Asegúrese de que la directiva está establecida en estado inactivo.

2. Use el **cmdlet Remove-InformationBarrierPolicy** con un parámetro Identity.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> En este ejemplo, se quita la directiva que tiene GUID *43c37853-ea10-4b90-a23d-ab8c93772471*. |

    Cuando se le solicite, confirme el cambio.

3. Repita los pasos del 1 al 2 para cada directiva que desee quitar.

4. Cuando haya terminado de quitar directivas, aplique los cambios. Para realizar esta acción, use el cmdlet **Start-InformationBarrierPoliciesApplication.**

    Sintaxis: `Start-InformationBarrierPoliciesApplication`

    Los cambios se aplican, usuario por usuario, a la organización. Si su organización es grande, este proceso puede tardar 24 horas (o más).

## <a name="stop-a-policy-application"></a>Detener una aplicación de directiva

Una vez que haya comenzado a aplicar directivas de barreras de información, si desea impedir que se apliquen esas directivas, use el siguiente procedimiento. El proceso tarda aproximadamente entre 30 y 35 minutos en comenzar.

1. Para ver el estado de la aplicación de directiva de barreras de información más reciente, use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus.**

    Sintaxis: `Get-InformationBarrierPoliciesApplicationStatus`

    Tenga en cuenta el GUID de la aplicación.

2. Use el cmdlet **Stop-InformationBarrierPoliciesApplication** con un parámetro Identity.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> En este ejemplo, estamos impidiendo que se apliquen directivas de barreras de información. |

## <a name="resources"></a>Recursos

- [Obtener información general sobre las barreras de información](information-barriers.md)
- [Definir directivas para barreras de información](information-barriers-policies.md)
- [Más información sobre las barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Obtenga más información sobre las barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Más información sobre las barreras de información en OneDrive](/onedrive/information-barriers)
- [Atributos para las directivas de barreras de información](information-barriers-attributes.md)
- [Solución de problemas de barreras de información](information-barriers-troubleshooting.md)
