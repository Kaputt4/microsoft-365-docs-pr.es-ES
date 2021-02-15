---
title: Solución de problemas de barreras de información
description: Use este artículo como guía para solucionar problemas de barreras de información.
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
ms.openlocfilehash: 3810dd977ef0d25642ba86a2b62a036c9a4ace06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126567"
---
# <a name="troubleshooting-information-barriers"></a>Solución de problemas de barreras de información

[Las barreras de información](information-barriers.md) pueden ayudar a su organización a cumplir con los requisitos legales y las normativas del sector. Por ejemplo, con las barreras de información, puede restringir la comunicación entre grupos específicos de usuarios para evitar un conflicto de intereses u otros problemas. (Para obtener más información sobre cómo configurar barreras de información, vea [Definir directivas para barreras de información).](information-barriers-policies.md)

En caso de que los usuarios se tomen problemas inesperados después de que haya barreras de información, hay algunos pasos que puede realizar para resolver esos problemas. Use este artículo como guía.

> [!IMPORTANT]
> Para realizar las tareas descritas en este artículo, se le debe asignar un rol adecuado, como uno de los siguientes:<br/>- Administrador global de Microsoft 365 Enterprise<br/>- administrador global<br/>- Administrador de cumplimiento<br/>- Administración de cumplimiento de LAC (este es un nuevo rol)<p>Para obtener más información acerca de los requisitos previos para las barreras de información, consulte [Requisitos previos (para directivas de barreras de información).](information-barriers-policies.md#prerequisites)<p>Asegúrese de [conectarse a PowerShell del Centro & seguridad](/powershell/exchange/connect-to-scc-powershell)y cumplimiento.

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: Se bloquea inesperadamente a los usuarios para que no se comuniquen con otros usuarios en Microsoft Teams 

En este caso, los usuarios están informando de problemas inesperados de comunicación con otros usuarios de Microsoft Teams. Por ejemplo:

- Un usuario busca, pero no puede encontrar, otro usuario en Microsoft Teams.
- Un usuario puede buscar, pero no seleccionar, otro usuario en Microsoft Teams.
- Un usuario puede ver a otro usuario, pero no puede enviar mensajes a ese otro usuario en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

Determinar si los usuarios se ven afectados por una directiva de barreras de información. En función de cómo se configuren las directivas, es posible que las barreras de información funcionen según lo esperado. O bien, es posible que tenga que refinar las directivas de su organización.

1. Use el **cmdlet Get-InformationBarrierRecipientStatus** con el parámetro Identity. 

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> Puede usar cualquier valor de identidad que identifique de forma exclusiva a cada destinatario, como Nombre, Alias, Nombre distintivo (DN), DN canónico, Dirección de correo electrónico o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> En este ejemplo, estamos usando un alias (*meganb*) para el parámetro Identity. Este cmdlet devolverá información que indica si el usuario se ve afectado por una directiva de barreras de información. (Busque *ExoPolicyId: \<GUID> .) |

    **Si los usuarios no están incluidos en las directivas de barreras de información, póngase en contacto con el soporte técnico.** De lo contrario, continúe con el paso siguiente.

2. Descubra qué segmentos se incluyen en una directiva de barreras de información. Para ello, use el `Get-InformationBarrierPolicy` cmdlet con el parámetro Identity. 

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Use detalles, como el GUID de directiva (ExoPolicyId) que recibió durante el paso anterior, como un valor de identidad. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> En este ejemplo, vamos a obtener información detallada sobre la directiva de barreras de información que tiene ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*. |

    Después de ejecutar el cmdlet, en los resultados, busque los valores **AssignedSegment**, **SegmentsAllowed** y **SegmentsBlocked.**

    Por ejemplo, después de ejecutar el `Get-InformationBarrierPolicy` cmdlet, vimos lo siguiente en nuestra lista de resultados:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    En este caso, podemos ver que una directiva de barreras de información afecta a las personas que están en los segmentos ventas e investigación. En este caso, se impide que los usuarios de Ventas se comuniquen con personas de Investigación.

    Si esto parece correcto, las barreras de información funcionan según lo esperado. Si no es así, vaya al paso siguiente.

3. Asegúrese de que los segmentos están definidos correctamente. Para ello, use el `Get-OrganizationSegment` cmdlet y revise la lista de resultados.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Use este cmdlet con un parámetro Identity. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> En este ejemplo, estamos obteniendo información sobre el segmento que tiene GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Revisa los detalles del segmento. Si es [necesario, edite un segmento](information-barriers-edit-segments-policies.md#edit-a-segment)y, a continuación, vuelva a usar el `Start-InformationBarrierPoliciesApplication` cmdlet.

    Si sigue teniendo problemas con la directiva de barreras **de información, póngase en contacto con el soporte técnico.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: se permiten las comunicaciones entre los usuarios que deben bloquearse en Microsoft Teams

En este caso, aunque las barreras de información están definidas, activas y aplicadas, las personas a las que se les debe impedir comunicarse entre sí pueden chatear y llamarse entre sí en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

Compruebe que los usuarios en cuestión están incluidos en una directiva de barreras de información. 

1. Use el **cmdlet Get-InformationBarrierRecipientStatus con** parámetros Identity.

    |**Sintaxis** _|_ *Example**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*. |

    > [!TIP]
    > También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Revise los resultados. El cmdlet **Get-InformationBarrierRecipientStatus** devuelve información acerca de los usuarios, como los valores de atributo y las directivas de barreras de información que se aplican.

    Revise los resultados y, a continuación, siga los pasos siguientes, como se describe en la tabla siguiente:

    |**Resultados**|**Qué hacer a continuación**|
    |:----------|:------------------|
    | No se muestran segmentos para los usuarios seleccionados | Realice una de las acciones siguientes:<br/>- Asignar usuarios a un segmento existente editando sus perfiles de usuario en Azure Active Directory. (Vea [Configurar las propiedades de la cuenta de usuario con PowerShell de Office 365).](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- Definir un segmento con un atributo [admitido para barreras de información.](information-barriers-attributes.md) A continuación, [defina una nueva directiva o](information-barriers-policies.md#part-2-define-information-barrier-policies) [edite una directiva existente](information-barriers-edit-segments-policies.md#edit-a-policy) para incluir ese segmento. |
    | Los segmentos se enumeran pero no se asignan directivas de barreras de información a esos segmentos | Realice una de las acciones siguientes:<br/>- [Definir una nueva directiva de barreras de información](information-barriers-policies.md#part-2-define-information-barrier-policies) para cada segmento en cuestión <br/>- [Editar una directiva de barreras de información](information-barriers-edit-segments-policies.md#edit-a-policy) existente para asignarla al segmento correcto |
    | Los segmentos se enumeran y se incluyen en una directiva de barreras de información | - Ejecute el `Get-InformationBarrierPolicy` cmdlet para comprobar que las directivas de barreras de información están activas<br/>- Ejecutar el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet para confirmar que se aplican las directivas<br/>- Ejecutar el `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas las directivas de barreras de información activas |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: Necesito quitar un solo usuario de una directiva de barreras de información

En este caso, las directivas de barreras de información están en vigor y se bloquea inesperadamente a uno o más usuarios para que no se comuniquen con otros usuarios de Microsoft Teams. En lugar de eliminar las directivas de barreras de información por completo, puede quitar uno o más usuarios individuales de las directivas de barreras de información.

### <a name="what-to-do"></a>Qué hacer

Las directivas de barreras de información se asignan a segmentos de usuarios. Los segmentos se definen mediante el uso de [determinados atributos en los perfiles de cuenta de usuario.](information-barriers-attributes.md) Si debe quitar una directiva de un solo usuario, considere la posibilidad de editar el perfil de ese usuario en Azure Active Directory de modo que el usuario ya no se incluya en un segmento afectado por barreras de información.

1. Use el **cmdlet Get-InformationBarrierRecipientStatus con** parámetros Identity. Este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de barreras de información que se aplican.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva al usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> En este ejemplo, nos referimos a una sola cuenta en Office 365: *juanp*. |

2. Revise los resultados para ver si se asignan directivas de barreras de información y a qué segmentos pertenecen los usuarios.

3. Para quitar un usuario de un segmento afectado por barreras de información, actualice la información de perfil del usuario [en Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. Espere unos 30 minutos para que se produzca FwdSync. O bien, ejecute el cmdlet para aplicar todas las directivas de `Start-InformationBarrierPoliciesApplication` barreras de información activas.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: el proceso de aplicación de barreras de información tarda demasiado tiempo

Después de ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication,** el proceso tarda mucho tiempo en finalizar.

### <a name="what-to-do"></a>Qué hacer

Tenga en cuenta que al ejecutar el cmdlet de la aplicación de directiva, las directivas de barreras de información se aplican (o quitan), usuario por usuario, para todas las cuentas de la organización. Si tiene una gran cantidad de usuarios, el proceso llevará un tiempo. (Como regla general, se tarda aproximadamente una hora en procesar 5.000 cuentas de usuario).

1. Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para comprobar el estado de la aplicación de directiva más reciente.

    |**Para ver la aplicación de directiva más reciente**|**Para ver el estado de todas las aplicaciones de directiva**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Esto mostrará información sobre si la aplicación de directiva se ha completado, ha fallado o está en curso.

2. Según los resultados del paso anterior, siga uno de estos pasos:
  
    |**Estado**|**Paso siguiente**|
    |:---------|:------------|
    | **No iniciado** | Si han pasado más de 45 minutos desde que se ha ejecutado el cmdlet **Start-InformationBarrierPoliciesApplication,** revise el registro de auditoría para ver si hay errores en las definiciones de directiva o algún otro motivo por el que la aplicación no se haya iniciado. |
    | **Failed** | Si se ha dado un error en la aplicación, revise el registro de auditoría. Revise también los segmentos y directivas. ¿Hay usuarios asignados a más de un segmento? ¿Hay segmentos asignados a más de una poliica? Si es necesario, [edite segmentos](information-barriers-edit-segments-policies.md#edit-a-segment) o [directivas](information-barriers-edit-segments-policies.md#edit-a-policy)de edición y, a continuación, ejecute el cmdlet **Start-InformationBarrierPoliciesApplication** de nuevo. |
    | **En curso** | Si la aplicación aún está en curso, deje más tiempo para que se complete. Si han pasado varios días, recopila los registros de auditoría y, a continuación, póngase en contacto con el soporte técnico. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: las directivas de barreras de información no se aplican en absoluto

En este caso, ha definido segmentos, ha definido directivas de barreras de información y ha intentado aplicar esas directivas. Sin embargo, al ejecutar el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, puede ver que la aplicación de directiva ha fallado.

### <a name="what-to-do"></a>Qué hacer

Asegúrese de que su organización no tiene directivas de libreta de direcciones [de Exchange](/exchange/address-books/address-book-policies/address-book-policies) en su lugar. Estas directivas impedirán que se apliquen directivas de barreras de información.

1. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) y revise los resultados.

    |**Resultados**|**Paso siguiente**|
    |:----------|:------------|
    | Se enumeran las directivas de la libreta de direcciones de Exchange | [Quitar directivas de libreta de direcciones](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | No existen directivas de libreta de direcciones |Revise los registros de auditoría para averiguar por qué se está fallando la aplicación de directiva |

3. [Ver el estado de las cuentas de usuario, segmentos, directivas o aplicación de directiva.](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: la directiva de barreras de información no se aplica a todos los usuarios designados

Después de definir segmentos, definir directivas de barreras de información e intentar aplicar esas directivas, es posible que la directiva se aplique a algunos destinatarios, pero no a otros.
Cuando ejecute el cmdlet, busque texto como este en `Get-InformationBarrierPoliciesApplicationStatus` el resultado.

> Identidad: `<application guid>`
>
> Total de destinatarios: 81527
>
> Destinatarios con errores: 2
>
> Categoría de error: ninguno
>
> Estado: Completado

### <a name="what-to-do"></a>Qué hacer

1. Busque en el registro de auditoría `<application guid>` . Puede copiar este código de PowerShell y modificar las variables.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Compruebe los valores de los campos y los resultados detallados del registro `"UserId"` de `"ErrorDetails"` auditoría. Esto le dará la razón del error. Puede copiar este código de PowerShell y modificar las variables.

```powershell
   $DetailedLogs[1] |fl
```

Por ejemplo:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. Error: el segmento DE "id. de segmento1" y el segmento DE LAC "id2" tienen conflicto y no se pueden asignar al destinatario.

3. Por lo general, verá que un usuario se ha incluido en más de un segmento. Puede corregir esto actualizando el `-UserGroupFilter` valor en `OrganizationSegments` .

4. Vuelva a aplicar las directivas de barreras de información mediante estos [procedimientos: directivas de barreras de información.](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="resources"></a>Recursos

- [Definir directivas para barreras de información en Microsoft Teams](information-barriers-policies.md)
- [Barreras de información](information-barriers.md)
