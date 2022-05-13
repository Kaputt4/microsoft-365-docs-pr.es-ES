---
title: Administración de directivas de barreras de información
description: Obtenga información sobre cómo editar o quitar directivas para barreras de información.
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
ms.openlocfilehash: a4962ba35ef2a66067acdf2676dbe34e63de99c5
ms.sourcegitcommit: 99494a5530ad64802f341573ad42796134190296
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65396238"
---
# <a name="manage-information-barriers-policies"></a>Administración de directivas de barreras de información

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Después de [definir directivas de barreras de información (IB](information-barriers-policies.md)), es posible que tenga que realizar cambios en esas directivas o en los segmentos de usuario, como parte de [la solución de problemas](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting) o como mantenimiento normal.

## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

|**Action**|**Descripción**|
|:---------|:--------------|
| [Editar atributos de cuenta de usuario](#edit-user-account-attributes) | Rellene los atributos en Azure Active Directory que se pueden usar para definir segmentos. <br> Edite los atributos de la cuenta de usuario cuando los usuarios no estén incluidos en los segmentos en los que deben estar, para cambiar en qué segmentos están los usuarios o para definir segmentos con atributos diferentes. |
| [Editar un segmento](#edit-a-segment) | Edite segmentos cuando desee cambiar la forma en que se define un segmento. <br> Por ejemplo, es posible que haya definido originalmente segmentos mediante *Department* y ahora quiera usar otro atributo, como *MemberOf*. |
| [Editar una directiva](#edit-a-policy) | Edite una directiva de barreras de información cuando desee cambiar el funcionamiento de una directiva.<br> Por ejemplo, en lugar de bloquear las comunicaciones entre dos segmentos, puede decidir permitir que las comunicaciones se produzcan solo entre determinados segmentos. |
| [Establecer una directiva en estado inactivo](#set-a-policy-to-inactive-status) |Establezca una directiva en estado inactivo cuando quiera realizar cambios en una directiva o cuando no desee que una directiva esté en vigor. |
| [Eliminación de una directiva](#remove-a-policy) | Quite una directiva de barreras de información cuando ya no necesite una directiva determinada. |
| [Eliminación de un segmento](#remove-a-segment) | Quite un segmento de barreras de información cuando ya no necesite un segmento determinado. |
| [Eliminación de una directiva y un segmento](#remove-a-policy-and-segment) | Quite una directiva de barreras de información y un segmento al mismo tiempo. |
| [Detener una aplicación de directiva](#stop-a-policy-application) | Realice esta acción cuando desee detener el proceso de aplicación de directivas de barreras de información. <br> Detener una aplicación de directiva no es instantáneo y no deshace las directivas que ya se aplican a los usuarios. |
| [Definir directivas de barreras de información](information-barriers-policies.md) | Defina una directiva de barreras de información cuando aún no tenga dichas directivas en su lugar y debe restringir o limitar las comunicaciones entre grupos específicos de usuarios. |
| [Solución de problemas de barreras de información](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting) | Consulte este artículo cuando tenga problemas inesperados con las barreras de información. |

>[!IMPORTANT]
>Para realizar las tareas descritas en este artículo, se le debe asignar un rol adecuado, como una de las siguientes:<br>- administrador global de Microsoft 365 Enterprise<br>- Administrador global<br>- Administrador de cumplimiento<br>- Ib Compliance Management (¡este es un nuevo rol!)<br><br>Para obtener más información sobre los requisitos previos para las barreras de información, consulte [Requisitos previos (para directivas de barreras de información).](information-barriers-policies.md#step-1-make-sure-prerequisites-are-met)<br><br> Asegúrese de [conectarse a PowerShell del Centro de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell).

## <a name="edit-user-account-attributes"></a>Editar atributos de cuenta de usuario

Use este procedimiento para editar los atributos que se usan para segmentar usuarios. Por ejemplo, si usa un atributo Department y una o varias cuentas de usuario no tienen actualmente ningún valor enumerado para Department, debe editar esas cuentas de usuario para incluir información del departamento. Los atributos de cuenta de usuario se usan para definir segmentos de modo que se puedan asignar directivas de barreras de información.

1. Para ver los detalles de una cuenta de usuario específica, como los valores de atributo y los segmentos asignados, use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros identity.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <br> Puede usar cualquier valor que identifique de forma única a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. <br> (También puede usar este cmdlet para un único usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`) |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <br> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*. |

2. Determine qué atributo desea editar para los perfiles de cuenta de usuario. Para obtener más información, vea [Atributos para directivas de barreras de información](information-barriers-attributes.md).

3. Edite una o varias cuentas de usuario para incluir valores para el atributo seleccionado en el paso anterior. Para realizar esta acción, use uno de los procedimientos siguientes:

    - Para editar una sola cuenta, consulte [Agregar o actualizar la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

    - Para editar varias cuentas (o usar PowerShell para editar una sola cuenta), consulte [Configuración de propiedades de cuenta de usuario con Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

## <a name="edit-a-segment"></a>Editar un segmento

Use este procedimiento para editar la definición de un segmento de usuario. Por ejemplo, puede cambiar el nombre de un segmento o el filtro que se usa para determinar quién se incluye en el segmento.

1. Para ver todos los segmentos existentes, use el cmdlet **Get-OrganizationSegment** .

    Sintaxis: `Get-OrganizationSegment`

    Verá una lista de segmentos y detalles para cada uno, como el tipo de segmento, su valor UserGroupFilter, quién lo creó o modificó por última vez, GUID, etc.

    > [!TIP]
    > Imprima o guarde la lista de segmentos como referencia más adelante. Por ejemplo, si desea editar un segmento, deberá conocer su nombre o identificar el valor (se usa con el parámetro Identity).

2. Para editar un segmento, use el cmdlet **Set-OrganizationSegment** con el parámetro **Identity** y los detalles pertinentes.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <br> En este ejemplo, hemos actualizado el nombre del departamento a *HRDept* para el segmento con GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

3. Cuando haya terminado de editar segmentos para su organización, puede [definir](information-barriers-policies.md#step-3-create-ib-policies) o [editar](#edit-a-policy) directivas de barreras de información.

## <a name="edit-a-policy"></a>Editar una directiva

1. Para ver una lista de las directivas de barreras de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .

    Sintaxis: `Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la directiva que desea cambiar. Anote el GUID y el nombre de la directiva.

2. Use el cmdlet **Set-InformationBarrierPolicy** con un parámetro **Identity** y especifique los cambios que desea realizar.

    Ejemplo: Supongamos que se definió una directiva para impedir que el segmento *De investigación* se comunique con los segmentos *Ventas* y *Marketing* . La directiva se definió mediante este cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Supongamos que queremos cambiarlo para que los usuarios del segmento *Investigación* solo puedan comunicarse con personas del segmento *de RR. HH* . Para realizar este cambio, usamos este cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    En este ejemplo, cambiamos *SegmentBlocked* a *SegmentsAllowed* y especificamos el segmento *de RR. HH* .

3. Cuando haya terminado de editar una directiva, asegúrese de aplicar los cambios. (Consulte [Aplicar directivas de barreras de información](information-barriers-policies.md#step-4-apply-ib-policies)).

## <a name="set-a-policy-to-inactive-status"></a>Establecer una directiva en estado inactivo

1. Para ver una lista de las directivas de barreras de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .

    Sintaxis: `Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la directiva que desea cambiar (o quitar). Anote el GUID y el nombre de la directiva.

2. Para establecer el estado de la directiva en inactivo, use el cmdlet **Set-InformationBarrierPolicy** con un parámetro *Identity* y el parámetro *State* establecido en *Inactivo*.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <br> En este ejemplo, la directiva de barreras de información que tiene GUID *43c37853-ea10-4b90-a23d-ab8c9377247* se establece en un estado inactivo. |

3. Para aplicar los cambios, use el cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintaxis: `Start-InformationBarrierPoliciesApplication`

    Los cambios se aplican de usuario a usuario para su organización. Si su organización es grande, este proceso puede tardar 24 horas (o más). Como guía general, se tarda aproximadamente una hora en procesar 5000 cuentas de usuario.

4. En este momento, una o varias directivas de barreras de información se establecen en estado inactivo. Desde aquí, puede realizar cualquiera de las siguientes acciones:

    - Manténgalo tal y como está (una directiva establecida en estado inactivo no tiene ningún efecto en los usuarios)
    - [Editar una directiva](#edit-a-policy) 
    - [Eliminación de una directiva](#remove-a-policy)

## <a name="remove-a-policy"></a>Eliminación de una directiva

1. Para ver una lista de las directivas de barreras de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .

    Sintaxis: `Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la directiva que desea quitar. Anote el GUID y el nombre de la directiva. 

2. Asegúrese de que la directiva está establecida en estado inactivo. Para establecer el estado de la directiva en inactivo, use el cmdlet Set-InformationBarrierPolicy con un parámetro Identity y el parámetro State establecido en Inactivo.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive`  | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <br> En este ejemplo, establecemos una directiva de barreras de información que tiene GUID *43c37853-ea10-4b90-a23d-ab8c9377247* en un estado inactivo. |

3. Para aplicar los cambios en la directiva, use el cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintaxis: `Start-InformationBarrierPoliciesApplication`

    Los cambios se aplican de usuario a usuario para su organización. Si su organización es grande, este proceso puede tardar 24 horas (o más). Como guía general, se tarda aproximadamente una hora en procesar 5000 cuentas de usuario.

4. Use el cmdlet **Remove-InformationBarrierPolicy** con un parámetro Identity.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <br> En este ejemplo, vamos a quitar la directiva que tiene GUID *43c37853-ea10-4b90-a23d-ab8c93772471*. |

    Cuando se le solicite, confirme el cambio.

## <a name="remove-a-segment"></a>Eliminación de un segmento

1. Para ver todos los segmentos existentes, use el cmdlet **Get-OrganizationSegment** .

    Sintaxis: `Get-OrganizationSegment`

    Verá una lista de segmentos y detalles para cada uno, como el tipo de segmento, su valor UserGroupFilter, quién lo creó o modificó por última vez, GUID, etc.

    >[!TIP]
    >Imprima o guarde la lista de segmentos como referencia más adelante. Por ejemplo, si desea editar un segmento, deberá conocer su nombre o identificar el valor (se usa con el parámetro Identity).

2. Identifique el segmento que se va a quitar y asegúrese de que se ha quitado la directiva de IB asociada al segmento. Consulte el procedimiento [Quitar una directiva](#remove-a-policy) para obtener más información.

3. Edite el segmento que se quitará para quitar la relación de los usuarios con ese segmento. Esta acción actualiza la definición de segmento y quita todos los usuarios del segmento. Usará el parámetro UserGroupFilter para desasociar a los usuarios del segmento antes de la eliminación.

    Para editar un segmento, use el cmdlet **Set-OrganizationSegment** con el parámetro *Identity* y los detalles pertinentes.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` | `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'FakeDept'"` <br> En este ejemplo, para el segmento que tiene el GUID c96e0837-c232-4a8a-841e-ef45787d8fcd, definimos el nombre del departamento como *FakeDept* para quitar usuarios del segmento. En este ejemplo se usa el atributo *Department* , pero puede usar otros atributos según corresponda. En el ejemplo se usa *FakeDept* porque esto no existe y es seguro que no contiene ningún usuario. |

4. Para aplicar los cambios, use el cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintaxis: `Start-InformationBarrierPoliciesApplication -CleanupGroupSegmentLink`

    >[!NOTE]
    >El atributo *CleanupGroupSegmentLink* quita las asociaciones de grupo con el segmento sin asociaciones de usuario.

    Los cambios se aplican de usuario a usuario para su organización. Si su organización es grande, este proceso puede tardar 24 horas (o más). Como guía general, se tarda aproximadamente una hora en procesar 5000 cuentas de usuario.

5. Para quitar un segmento, use el cmdlet **Remove-OrganizationSegment** con el parámetro *Identity* y los detalles pertinentes.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Remove-OrganizationSegment -Identity GUID` | `Remove-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <br> En este ejemplo, se quitó el segmento que tiene el GUID c96e0837-c232-4a8a-841e-ef45787d8fcd. |

## <a name="remove-a-policy-and-segment"></a>Eliminación de una directiva y un segmento

1. Para ver una lista de las directivas de barreras de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .

    Sintaxis: `Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la directiva que desea quitar. Anote el GUID y el nombre de la directiva.

2. Para ver todos los segmentos existentes, use el cmdlet **Get-OrganizationSegment** .

    Sintaxis: `Get-OrganizationSegment`

    Verá una lista de segmentos y detalles para cada uno, como el tipo de segmento, su valor de parámetro *UserGroupFilter* , quién lo creó o modificó por última vez, GUID, etc.

    >[!TIP]
    >Imprima o guarde la lista de segmentos como referencia más adelante. Por ejemplo, si desea editar un segmento, deberá conocer su nombre o identificar el valor (se usa con el parámetro Identity).

3. Para establecer el estado de la directiva que se va a quitar en inactivo, use el cmdlet **Set-InformationBarrierPolicy** con un parámetro *Identity* y el parámetro *State* establecido en *Inactivo*.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Inactive` <br> En este ejemplo, establecemos una directiva de barreras de información que tiene GUID 43c37853-ea10-4b90-a23d-ab8c9372471 en un estado inactivo. |

4. Edite el segmento que se quitará para quitar la relación de los usuarios con ese segmento. Esta acción actualiza la definición de segmento y quita todos los usuarios del segmento. Usará el parámetro *UserGroupFilter* para desasociar a los usuarios del segmento antes de la eliminación.

    Para editar un segmento, use el cmdlet **Set-OrganizationSegment** con el parámetro *Identity* y los detalles pertinentes.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` | `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'FakeDept'"` <br> En este ejemplo, para el segmento que tiene el GUID c96e0837-c232-4a8a-841e-ef45787d8fcd, actualizamos el nombre del departamento a *FakeDept* para quitar usuarios del segmento. En este ejemplo se usa el atributo *Department* , pero puede usar otros atributos según corresponda. En el ejemplo se usa *FakeDept* porque esto no existe y es seguro que no contiene usuarios. |

5. Para aplicar los cambios, use el cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintaxis: `Start-InformationBarrierPoliciesApplication -CleanupGroupSegmentLink`

    >[!NOTE]
    >El atributo *CleanupGroupSegmentLink* quita las asociaciones de grupo con el segmento sin asociaciones de usuario.

    Los cambios se aplican de usuario a usuario para su organización. Si su organización es grande, este proceso puede tardar 24 horas (o más). Como guía general, se tarda aproximadamente una hora en procesar 5000 cuentas de usuario.

6. Use el cmdlet **Remove-InformationBarrierPolicy** con un parámetro *Identity* .

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <br> En este ejemplo, se quita la directiva que tiene GUID *43c37853-ea10-4b90-a23d-ab8c93772471* . |

    Cuando se le solicite, confirme el cambio.

7. Para quitar un segmento, use el cmdlet **Remove-OrganizationSegment** con el parámetro *Identity* y los detalles pertinentes.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Remove-OrganizationSegment -Identity GUID` | `Remove-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <br> En este ejemplo, se quitó el segmento con GUID c96e0837-c232-4a8a-841e-ef45787d8fcd. |

## <a name="stop-a-policy-application"></a>Detener una aplicación de directiva

Después de empezar a aplicar directivas de barreras de información, si desea impedir que se apliquen esas directivas, use el procedimiento siguiente. El proceso tardará aproximadamente entre 30 y 35 minutos en comenzar.

1. Para ver el estado de la aplicación de directiva de barreras de información más reciente, use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** .

    Sintaxis: `Get-InformationBarrierPoliciesApplicationStatus`

    Anote el GUID de la aplicación.

2. Use el cmdlet **Stop-InformationBarrierPoliciesApplication** con un parámetro Identity.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> En este ejemplo, vamos a impedir que se apliquen directivas de barreras de información. |

## <a name="resources"></a>Recursos

- [Obtener información general sobre las barreras de información](information-barriers.md)
- [Definir directivas de barreras de información](information-barriers-policies.md)
- [Más información sobre las barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Más información sobre las barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Más información sobre las barreras de información en OneDrive](/onedrive/information-barriers)
- [Atributos para directivas de IB](information-barriers-attributes.md)
- [Solución de problemas de barreras de información](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)
