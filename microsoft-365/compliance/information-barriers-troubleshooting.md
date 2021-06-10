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
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928010"
---
# <a name="troubleshooting-information-barriers"></a>Solución de problemas de barreras de información

[Las barreras de información](information-barriers.md) pueden ayudar a su organización a cumplir con los requisitos legales y las normativas del sector. Por ejemplo, con las barreras de información, puede restringir la comunicación entre grupos específicos de usuarios para evitar conflictos de interés u otros problemas. (Para obtener más información sobre cómo configurar barreras de información, vea [Definir directivas para barreras de información).)](information-barriers-policies.md)

En caso de que las personas se tomen problemas inesperados después de que haya barreras de información, hay algunos pasos que puede seguir para resolver esos problemas. Use este artículo como guía.

> [!IMPORTANT]
> Para realizar las tareas descritas en este artículo, se le debe asignar un rol adecuado, como uno de los siguientes:<br/>- Microsoft 365 Enterprise administrador global<br/>- Administrador global<br/>- Administrador de cumplimiento<br/>- Administración de cumplimiento de IB (este es un nuevo rol!<p>Para obtener más información sobre los requisitos previos para las barreras de información, vea [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).<p>Asegúrese de [conectarse a PowerShell & centro de seguridad y cumplimiento.](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: Los usuarios se bloquean inesperadamente para que no se comuniquen con otros usuarios en Microsoft Teams 

En este caso, las personas informan de problemas inesperados que se comunican con otros usuarios en Microsoft Teams. Por ejemplo:

- Un usuario busca, pero no puede encontrar, otro usuario en Microsoft Teams.
- Un usuario puede encontrar, pero no seleccionar, otro usuario en Microsoft Teams.
- Un usuario puede ver a otro usuario, pero no puede enviar mensajes a ese otro usuario en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

Determine si los usuarios se ven afectados por una directiva de barrera de información. Según cómo se configuren las directivas, las barreras de información podrían funcionar según lo esperado. O bien, es posible que tenga que refinar las directivas de su organización.

1. Use el cmdlet **Get-InformationBarrierRecipientStatus** con el parámetro Identity. 

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> Puede usar cualquier valor de identidad que identifique de forma exclusiva a cada destinatario, como Name, Alias, Distinguished name (DN), Canonical DN, Email address o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> En este ejemplo, estamos usando un alias (*meganb*) para el parámetro Identity. Este cmdlet devolverá información que indica si el usuario se ve afectado por una directiva de barrera de información. (Busque *ExoPolicyId: \<GUID> .) |

    **Si los usuarios no están incluidos en las directivas de barrera de información, póngase en contacto con el soporte técnico**. De lo contrario, continúe con el paso siguiente.

2. Descubra qué segmentos se incluyen en una directiva de barrera de información. Para ello, use el `Get-InformationBarrierPolicy` cmdlet con el parámetro Identity. 

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Use detalles, como el GUID de directiva (ExoPolicyId) que recibió durante el paso anterior, como un valor de identidad. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> En este ejemplo, vamos a obtener información detallada sobre la directiva de barrera de información que tiene ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*. |

    Después de ejecutar el cmdlet, en los resultados, busque los valores **AssignedSegment**, **SegmentsAllowed** y **SegmentsBlocked.**

    Por ejemplo, después de ejecutar el `Get-InformationBarrierPolicy` cmdlet, vimos lo siguiente en nuestra lista de resultados:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    En este caso, podemos ver que una directiva de barrera de información afecta a las personas que están en los segmentos ventas e investigación. En este caso, se impide que los usuarios de Ventas se comuniquen con personas de Investigación.

    Si esto parece correcto, las barreras de información funcionan según lo esperado. Si no es así, vaya al paso siguiente.

3. Asegúrese de que los segmentos están definidos correctamente. Para ello, use el `Get-OrganizationSegment` cmdlet y revise la lista de resultados.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Use este cmdlet con un parámetro Identity. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> En este ejemplo, vamos a obtener información sobre el segmento que tiene GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Revise los detalles del segmento. Si es necesario, [edite un segmento](information-barriers-edit-segments-policies.md#edit-a-segment)y vuelva a usar el `Start-InformationBarrierPoliciesApplication` cmdlet.

    Si sigue teniendo problemas con la directiva de barrera **de información, póngase en contacto con el soporte técnico**.

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: las comunicaciones se permiten entre usuarios que deben bloquearse en Microsoft Teams

En este caso, aunque las barreras de información están definidas, activas y aplicadas, las personas a las que se les debe impedir comunicarse entre sí pueden chatear y llamarse mutuamente en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

Compruebe que los usuarios en cuestión están incluidos en una directiva de barrera de información. 

1. Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity.

    |**Sintaxis** _|_ *Ejemplo**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*. |

    > [!TIP]
    > También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Revise los resultados. El cmdlet **Get-InformationBarrierRecipientStatus** devuelve información sobre los usuarios, como los valores de atributo y las directivas de barrera de información que se aplican.

    Revise los resultados y, a continuación, siga los pasos siguientes, como se describe en la tabla siguiente:

    |**Resultados**|**Qué hacer a continuación**|
    |:----------|:------------------|
    | No se enumeran segmentos para los usuarios seleccionados | Realiza una de las siguientes acciones:<br/>- Asignar usuarios a un segmento existente editando sus perfiles de usuario en Azure Active Directory. (Vea [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).)<br/>- Definir un segmento mediante un [atributo admitido para las barreras de información](information-barriers-attributes.md). A continuación, [defina una nueva directiva](information-barriers-policies.md#part-2-define-information-barrier-policies) o [edite una directiva existente](information-barriers-edit-segments-policies.md#edit-a-policy) para incluir ese segmento. |
    | Los segmentos se enumeran pero no se asignan directivas de barrera de información a esos segmentos | Realiza una de las siguientes acciones:<br/>- [Definir una nueva directiva de barrera de información](information-barriers-policies.md#part-2-define-information-barrier-policies) para cada segmento en cuestión <br/>- [Editar una directiva de barrera de información existente](information-barriers-edit-segments-policies.md#edit-a-policy) para asignarla al segmento correcto |
    | Los segmentos se enumeran y cada uno se incluye en una directiva de barrera de información | - Ejecute el `Get-InformationBarrierPolicy` cmdlet para comprobar que las directivas de barrera de información están activas<br/>- Ejecutar el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet para confirmar que se aplican las directivas<br/>- Ejecutar el `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas las directivas de barrera de información activas |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: necesito quitar un solo usuario de una directiva de barrera de información

En este caso, las directivas de barrera de información están en vigor y uno o varios usuarios se bloquean inesperadamente para que no se comuniquen con otros usuarios en Microsoft Teams. En lugar de quitar las directivas de barrera de información por completo, puede quitar uno o más usuarios individuales de las directivas de barrera de información.

### <a name="what-to-do"></a>Qué hacer

Las directivas de barrera de información se asignan a segmentos de usuarios. Los segmentos se definen mediante el uso de [determinados atributos en perfiles de cuenta de usuario.](information-barriers-attributes.md) Si debe quitar una directiva de un solo usuario, considere la posibilidad de editar el perfil de ese usuario en Azure Active Directory de modo que el usuario ya no esté incluido en un segmento afectado por las barreras de información.

1. Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity. Este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de barrera de información que se aplican.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva al usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> En este ejemplo, nos referimos a una sola cuenta en Office 365: *juana*. |

2. Revise los resultados para ver si se asignan directivas de barrera de información y a qué segmentos pertenecen los usuarios.

3. Para quitar un usuario de un segmento afectado por barreras de información, actualice la información de perfil del usuario [en Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

4. Espere unos 30 minutos para que se produzca FwdSync. O bien, ejecute el `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas las directivas de barrera de información activas.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: el proceso de aplicación de barrera de información tarda demasiado tiempo

Después de ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication,** el proceso tarda mucho tiempo en finalizar.

### <a name="what-to-do"></a>Qué hacer

Tenga en cuenta que al ejecutar el cmdlet de aplicación de directiva, las directivas de barrera de información se aplican (o quitan), usuario por usuario, para todas las cuentas de la organización. Si tiene muchos usuarios, llevará un tiempo procesarlo. (Como directriz general, se tarda aproximadamente una hora en procesar 5.000 cuentas de usuario).

1. Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para comprobar el estado de la aplicación de directiva más reciente.

    |**Para ver la aplicación de directiva más reciente**|**Para ver el estado de todas las aplicaciones de directiva**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Esto mostrará información sobre si la aplicación de directiva se ha completado, ha fallado o está en curso.

2. Según los resultados del paso anterior, siga uno de los pasos siguientes:
  
    |**Estado**|**Paso siguiente**|
    |:---------|:------------|
    | **No iniciado** | Si han pasado más de 45 minutos desde que se ha ejecutado el cmdlet **Start-InformationBarrierPoliciesApplication,** revise el registro de auditoría para ver si hay algún error en las definiciones de directiva o algún otro motivo por el que la aplicación no se haya iniciado. |
    | **Failed** | Si la aplicación ha fallado, revise el registro de auditoría. Revise también los segmentos y directivas. ¿Hay usuarios asignados a más de un segmento? ¿Hay segmentos asignados a más de una poliicidad? Si es necesario, [edite](information-barriers-edit-segments-policies.md#edit-a-segment) segmentos o [directivas](information-barriers-edit-segments-policies.md#edit-a-policy)de edición y vuelva a ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication.** |
    | **En curso** | Si la aplicación aún está en curso, dé más tiempo para que se complete. Si han pasado varios días, recopila los registros de auditoría y, a continuación, póngase en contacto con el soporte técnico. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: las directivas de barrera de información no se aplican en absoluto

En este caso, ha definido segmentos, ha definido directivas de barrera de información y ha intentado aplicar esas directivas. Sin embargo, al ejecutar el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, puede ver que la aplicación de directiva ha fallado.

### <a name="what-to-do"></a>Qué hacer

Asegúrese de que su organización no tiene Exchange [directivas de libreta de direcciones](/exchange/address-books/address-book-policies/address-book-policies) en su lugar. Estas directivas impedirán la aplicación de directivas de barrera de información.

1. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) y revise los resultados.

    |**Resultados**|**Paso siguiente**|
    |:----------|:------------|
    | Exchange se enumeran las directivas de libreta de direcciones | [Quitar directivas de libreta de direcciones](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | No existen directivas de libreta de direcciones |Revisar los registros de auditoría para averiguar por qué se está fallando la aplicación de directiva |

3. [Ver el estado de cuentas de usuario, segmentos, directivas o aplicación de directiva](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: La directiva de barrera de información no se aplica a todos los usuarios designados

Después de definir segmentos, definir directivas de barrera de información e intentar aplicar esas directivas, es posible que la directiva se aplique a algunos destinatarios, pero no a otros.
Cuando ejecute el cmdlet, busque texto como este en el `Get-InformationBarrierPoliciesApplicationStatus` resultado.

> Identidad: `<application guid>`
>
> Total de destinatarios: 81527
>
> Destinatarios con errores: 2
>
> Categoría de error: Ninguno
>
> Estado: Completado

### <a name="what-to-do"></a>Qué hacer

1. Busque en el registro de auditoría `<application guid>` . Puede copiar este código de PowerShell y modificar para las variables.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Compruebe los valores de los campos y en el resultado detallado del registro `"UserId"` de `"ErrorDetails"` auditoría. Esto le dará la razón del error. Puede copiar este código de PowerShell y modificar para las variables.

```powershell
   $DetailedLogs[1] |fl
```

Por ejemplo:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. Error: el segmento IB "segment id1" y el segmento IB "segment id2" tienen conflicto y no se pueden asignar al destinatario.

3. Por lo general, encontrará que un usuario se ha incluido en más de un segmento. Puede corregir esto actualizando el `-UserGroupFilter` valor en `OrganizationSegments` .

4. Volver a aplicar directivas de barrera de información mediante estos [procedimientos Directivas de barreras de información](information-barriers-policies.md#part-3-apply-information-barrier-policies).

## <a name="resources"></a>Recursos

- [Definir directivas para las barreras de información en Microsoft Teams](information-barriers-policies.md)
- [Barreras de información](information-barriers.md)