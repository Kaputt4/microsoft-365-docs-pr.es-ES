---
title: Solución de problemas de barreras de información
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use este artículo como guía para solucionar problemas con las barreras de la información.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f4e6087d0e1886d833a6cf0472ed467f8577c5d0
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307933"
---
# <a name="troubleshooting-information-barriers"></a>Solución de problemas de barreras de información

Las [barreras de información](information-barriers.md) pueden ayudar a su organización a permanecer conforme con los requisitos legales y las regulaciones del sector. Por ejemplo, con barreras de información, puede restringir la comunicación entre grupos de usuarios específicos para evitar un conflicto de intereses u otros problemas. (Para obtener más información sobre cómo configurar las barreras de la información, consulte [definir directivas para las barreras de información](information-barriers-policies.md)).

En el caso de que los usuarios se encuentren en problemas inesperados después de que entren en vigor las barreras de la información, hay algunos pasos que puede seguir para resolverlos. Use este artículo como guía.

> [!IMPORTANT]
> Para llevar a cabo las tareas descritas en este artículo, debe tener asignada una función adecuada, como una de las siguientes:<br/>-Administrador global de Microsoft 365 Enterprise<br/>-administrador global<br/>-Administrador de cumplimiento<br/>-IB Compliance Management (este es un nuevo rol).<p>Para obtener más información sobre los requisitos previos para las barreras de información, vea [requisitos previos (para las directivas de barrera de información)](information-barriers-policies.md#prerequisites).<p>Asegúrese de [conectarse al centro de seguridad & PowerShell del centro de cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: se impide que los usuarios se comuniquen de forma inesperada con otras personas en Microsoft Teams 

En este caso, los usuarios están notificando problemas inesperados que se comunican con otros usuarios de Microsoft Teams. Ejemplos:
- Un usuario busca, pero no encuentra, otro usuario en Microsoft Teams.
- Un usuario puede encontrar, pero no puede seleccionar, otro usuario en Microsoft Teams.
- Un usuario puede ver a otro usuario, pero no puede enviar mensajes a ese otro usuario en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

Determinar si los usuarios están afectados por una directiva de barrera de información. En función de cómo estén configuradas las directivas, es posible que las barreras de información funcionen según lo esperado. O bien, es posible que tenga que refinar las directivas de la organización.

1. Use el cmdlet **Get-InformationBarrierRecipientStatus** con el parámetro Identity. 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>Puede usar cualquier valor de identidad que identifique de forma exclusiva a cada destinatario, como el nombre, el alias, el nombre distintivo (DN), el DN canónico, la dirección de correo electrónico o el GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>En este ejemplo, se usa un alias (*meganb*) para el parámetro Identity. Este cmdlet devolverá información que indica si el usuario está afectado por una directiva de barrera de información. (Busque * ExoPolicyId: \<GUID> .)         |

    **Si los usuarios no se incluyen en las directivas de barrera de información, póngase en contacto con el soporte técnico**. En caso contrario, continúe con el paso siguiente.

2. Averigüe qué segmentos se incluyen en una directiva de barrera de información. Para ello, use el `Get-InformationBarrierPolicy` cmdlet con el parámetro Identity. 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>Use los detalles, como el GUID de directiva (ExoPolicyId) que ha recibido durante el paso anterior, como un valor de identidad.     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>En este ejemplo, se obtiene información detallada sobre la Directiva de barrera de información que tiene ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.         |

    Después de ejecutar el cmdlet, en los resultados, busque los valores de **AssignedSegment**, **SegmentsAllowed**y **SegmentsBlocked** .

    Por ejemplo, después de ejecutar el `Get-InformationBarrierPolicy` cmdlet, vimos lo siguiente en nuestra lista de resultados:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    En este caso, podemos ver que una directiva de barrera de información afecta a las personas que están en los segmentos de ventas y de investigación. En este caso, se impide que las personas de ventas se comuniquen con personas en investigación. 
    
    Si esto parece correcto, las barreras de la información funcionan como se esperaba. Si no es así, vaya al paso siguiente.

4. Asegúrese de que los segmentos se han definido correctamente. Para ello, use el `Get-OrganizationSegment` cmdlet y revise la lista de resultados. 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>Use este cmdlet con un parámetro Identity.     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>En este ejemplo, se obtiene información acerca del segmento que tiene el GUID *c96e0837-c232-4a8a-841E-ef45787d8fcd*.         |

    Revise los detalles del segmento. Si es necesario, [edite un segmento](information-barriers-edit-segments-policies.md#edit-a-segment)y, a continuación, vuelva a usar el `Start-InformationBarrierPoliciesApplication` cmdlet.

    **Si sigue teniendo problemas con la Directiva de barrera de información, póngase en contacto con el soporte técnico**.

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: se permiten las comunicaciones entre usuarios que deben estar bloqueados en Microsoft Teams

En este caso, a pesar de que las barreras de la información están definidas, activas y aplicadas, los usuarios que deben evitar comunicarse entre sí pueden chatear y realizar llamadas entre sí en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

Compruebe que los usuarios en cuestión se incluyen en una directiva de barrera de información. 

1. Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity.

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como el nombre, el alias, el nombre distintivo, el nombre de dominio canónico, la dirección de correo electrónico o el GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>En este ejemplo, se hace referencia a dos cuentas de usuario en Office 365: *meganb* para *Nuria*y *alexw* para *Alex*.          |

    
    > [!TIP]
    > También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. Revise las conclusiones. El cmdlet **Get-InformationBarrierRecipientStatus** devuelve información acerca de los usuarios, como los valores de atributo y las directivas de barrera de información que se aplican. 

    Revise los resultados y, a continuación, realice los pasos siguientes, como se describe en la tabla siguiente:
    
    |Resultados  |Qué hacer a continuación  |
    |---------|---------|
    |No se enumeran segmentos para el usuario o usuarios seleccionados     |Realiza una de las siguientes acciones:<br/>-Asignar usuarios a un segmento existente editando sus perfiles de usuario en Azure Active Directory. (Consulte [configurar las propiedades de las cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)).<br/>-Definir un segmento mediante un [atributo compatible con barreras de información](information-barriers-attributes.md). A continuación, puede [definir una nueva Directiva](information-barriers-policies.md#part-2-define-information-barrier-policies) o [editar una directiva existente](information-barriers-edit-segments-policies.md#edit-a-policy) para incluir ese segmento.  |
    |Se enumeran los segmentos pero no se asigna ninguna directiva de barrera de información a dichos segmentos.     |Realiza una de las siguientes acciones:<br/>- [Definir una nueva Directiva de barrera de información](information-barriers-policies.md#part-2-define-information-barrier-policies) para cada segmento en cuestión<br/>- [Editar una directiva de barrera de información existente](information-barriers-edit-segments-policies.md#edit-a-policy) para asignarla al segmento correcto         |
    |Se enumeran los segmentos y cada uno de ellos se incluye en una directiva de barrera de información     |-Ejecute el `Get-InformationBarrierPolicy` cmdlet para comprobar que las directivas de barrera de información están activas<br/>-Ejecute el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet para confirmar que se aplican las directivas.<br/>-Ejecute el `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas las directivas activas de barrera de información          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: necesito quitar un solo usuario de una directiva de barrera de información

En este caso, las directivas de barrera de información están en vigor y se impide que uno o más usuarios se comuniquen de forma inesperada con otras personas en Microsoft Teams. En lugar de quitar completamente las directivas de barrera de información, puede quitar uno o más usuarios individuales de las directivas de barrera de información. 

### <a name="what-to-do"></a>Qué hacer

Las directivas de barrera de información se asignan a segmentos de usuarios. Los segmentos se definen mediante determinados [atributos en perfiles de cuenta de usuario](information-barriers-attributes.md). Si debe quitar una directiva de un solo usuario, considere la posibilidad de editar el perfil del usuario en Azure Active Directory de modo que el usuario ya no se incluya en un segmento afectado por las barreras de información.

1. Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity. Este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de barrera de información que se aplican.

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como el nombre, el alias, el nombre distintivo, el nombre de dominio canónico, la dirección de correo electrónico o el GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>En este ejemplo, se hace referencia a dos cuentas de usuario en Office 365: *meganb* para *Nuria*y *alexw* para *Alex*.          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>Puede usar cualquier valor que identifique de forma exclusiva al usuario, como el nombre, el alias, el nombre distintivo, el nombre de dominio canónico, la dirección de correo electrónico o el GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>En este ejemplo, se hace referencia a una única cuenta en Office 365: *jeanp*. |

2. Revise los resultados para ver si se asignan directivas de barrera de información y a qué segmentos pertenecen los usuarios. 

3. Para quitar a un usuario de un segmento afectado por barreras de información, [actualice la información de perfil del usuario en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

4. Espere unos 30 minutos para que se produzca el FwdSync. O bien, ejecute el `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas las directivas de barrera de información activa.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: el proceso de aplicación de la barrera de información está tardando mucho

Después de ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication** , el proceso toma un tiempo muy largo para finalizar.

### <a name="what-to-do"></a>Qué hacer

Tenga en cuenta que, al ejecutar el cmdlet de aplicación de Directiva, se aplican (o quitan) directivas de barrera de información, usuario por usuario, para todas las cuentas de la organización. Si tiene muchos usuarios, tardará un rato en procesarse. (Como regla general, tarda aproximadamente una hora en procesar las cuentas de usuario de 5.000).

1. Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para comprobar el estado de la aplicación de directivas más reciente.

    |Para ver la aplicación de directivas más reciente  |Para ver el estado de todas las aplicaciones de Directiva  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    Esto mostrará información sobre si la aplicación de la Directiva se completó, produjo un error o está en curso.

2. Según los resultados del paso anterior, realice uno de los siguientes pasos:
  
    |Estado  |Paso siguiente  |
    |---------|---------|
    |**No iniciado**     |Si ha transcurrido más de 45 minutos desde que se ejecutó el cmdlet **Start-InformationBarrierPoliciesApplication** , revise el registro de auditoría para ver si hay errores en las definiciones de directiva o alguna otra razón por la que la aplicación no se ha iniciado. |
    |**Failed**     |Si se ha producido un error en la aplicación, revise el registro de auditoría. Revise también sus segmentos y directivas. ¿Hay algún usuario asignado a más de un segmento? ¿Hay algún segmento asignado a más de un poliicy? Si es necesario, [modifique los segmentos](information-barriers-edit-segments-policies.md#edit-a-segment) o [edite las directivas](information-barriers-edit-segments-policies.md#edit-a-policy)y, a continuación, vuelva a ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication** .  |
    |**En curso**     |Si la aplicación sigue en curso, permita más tiempo para completarse. Si ha transcurrido varios días, reúna los registros de auditoría y, a continuación, póngase en contacto con el soporte técnico. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: no se aplican las directivas de barrera de información en absoluto

En este caso, ha definido los segmentos, las directivas de barrera de información definidas y ha tratado de aplicar dichas directivas. Sin embargo, al ejecutar el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, puede ver que la aplicación de la Directiva ha generado un error.

### <a name="what-to-do"></a>Qué hacer

Asegúrese de que su organización no tiene [directivas de libreta de direcciones de Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) en su lugar. Dichas directivas impedirán que se apliquen las directivas de barrera de información.

1. Conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps). 

2. Ejecute el cmdlet [Get-AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/get-addressbookpolicy?view=exchange-ps) y revise los resultados.

    |Resultados  |Paso siguiente  |
    |---------|---------|
    |Las directivas de la libreta de direcciones de Exchange aparecen     |[Quitar directivas de la libreta de direcciones](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |No existen directivas de libreta de direcciones |Revisar los registros de auditoría para averiguar por qué se produce un error en la aplicación de Directiva |

3. [Ver el estado de las cuentas de usuario, los segmentos, las directivas o la aplicación de directivas](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: la Directiva de barrera de información no se aplica a todos los usuarios designados

Una vez que haya definido los segmentos, las directivas de barrera de información definidas y haya intentado aplicar dichas directivas, es posible que la Directiva se aplique a algunos destinatarios, pero no a otros.
Cuando ejecute el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, busque texto como este en la salida.

> Identifica `<application guid>`
>
> Total de destinatarios: 81527
>
> Destinatarios erróneos: 2
>
> Categoría de error: ninguna
>
> Estado: completo

### <a name="what-to-do"></a>Qué hacer

1. Busque en el registro de auditoría de `<application guid>` . Puede copiar este código de PowerShell y modificarlo para sus variables.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Compruebe el resultado detallado del registro de auditoría para los valores de los `"UserId"` `"ErrorDetails"` campos y. Esto le dará el motivo del error. Puede copiar este código de PowerShell y modificarlo para sus variables.

```powershell
   $DetailedLogs[1] |fl
```
 Por ejemplo:

> "UserId": usuario1
> 
>"ErrorDetails": "status: IBPolicyConflict. Error: el segmento de IB "segmento ID1" y el segmento IB "ID2" tienen conflicto y no se pueden asignar al destinatario. 

3. Normalmente, observará que un usuario se ha incluido en más de un segmento. Para solucionarlo, actualice el `-UserGroupFilter` valor de `OrganizationSegments` .

4. Volver a aplicar directivas de barrera de información mediante estos procedimientos [directivas de obstáculos](information-barriers-policies.md#part-3-apply-information-barrier-policies)para la información.

## <a name="related-topics"></a>Temas relacionados

[Definir directivas para las barreras de información en Microsoft Teams](information-barriers-policies.md)

[Barreras de información](information-barriers.md)
