---
title: Definir directivas de barreras de información
description: Obtenga información sobre cómo definir directivas para barreras de información en Microsoft Teams.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80123674644b47c76becb92fa08c21f4668614b2
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980063"
---
# <a name="define-information-barrier-policies"></a>Definir directivas de barreras de información

Con las barreras de información, puede definir directivas diseñadas para impedir que determinados segmentos de usuarios se comuniquen entre sí, o permitir que segmentos específicos se comuniquen solo con ciertos otros segmentos. Las directivas de barreras de información pueden ayudar a su organización a mantener el cumplimiento de normas y normativas relevantes del sector, y evitar posibles conflictos de interés. Para obtener más información, vea [Barreras de información.](information-barriers.md)

En este artículo se describe cómo planear, definir, implementar y administrar directivas de barreras de información. Hay varios pasos necesarios y el flujo de trabajo se divide en varias partes. Asegúrese de leer los [requisitos previos y](#prerequisites) todo el proceso antes de empezar a definir (o editar) directivas de barreras de información.

> [!TIP]
> En este artículo se incluye un [escenario de ejemplo](#example-contosos-departments-segments-and-policies) y un libro descargable de [Excel](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) para ayudarle a planear y definir las directivas de barreras de información.

## <a name="concepts-of-information-barrier-policies"></a>Conceptos de directivas de barreras de información

Al definir directivas para barreras de información, trabajará con atributos de cuenta de usuario, segmentos, directivas de "bloqueo" o "permitir" y aplicación de directiva.

- Los atributos de cuenta de usuario se definen en Azure Active Directory (o Exchange Online). Estos atributos pueden incluir departamento, puesto, ubicación, nombre del equipo y otros detalles del perfil del trabajo. 
- Los segmentos son conjuntos de usuarios que se definen en el Centro de seguridad & cumplimiento mediante un atributo de **cuenta de usuario seleccionado.** (Vea la [lista de atributos admitidos).](information-barriers-attributes.md)
- Las directivas de barreras de información determinan límites o restricciones de comunicación. Al definir directivas de barreras de información, puede elegir entre dos tipos de directivas:
    - Las directivas de "bloqueo" impiden que un segmento se comunique con otro segmento.
    - Las directivas "Permitir" permiten que un segmento se comunique solo con ciertos otros segmentos.
- La aplicación de directiva se realiza una vez definidas todas las directivas de barreras de información y está listo para aplicarlas en su organización.

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

|**Fase**|**Lo que implica**|
|:--------|:------------------|
| [Asegurarse de que se cumplen los requisitos previos](#prerequisites) | - Comprobar que tiene las licencias y permisos [necesarios](information-barriers.md#required-licenses-and-permissions)<br/>- Comprobar que el directorio incluye datos para segmentar usuarios<br/>- Habilitar la búsqueda de directorios con ámbito para Microsoft Teams<br/>- Asegúrese de que el registro de auditoría esté activado<br/>- Asegúrese de que no haya directivas de libreta de direcciones de Exchange<br/>- Usar PowerShell (se proporcionan ejemplos)<br/>- Proporcionar el consentimiento del administrador para Microsoft Teams (se incluyen pasos) |
| [Parte 1: Segmentar usuarios de la organización](#part-1-segment-users) | - Determinar qué directivas son necesarias<br/>- Crear una lista de segmentos para definir<br/>- Identificar qué atributos usar<br/>- Definir segmentos en términos de filtros de directiva |
| [Parte 2: Definir directivas de barreras de información](#part-2-define-information-barrier-policies) | - Definir las directivas (no aplicar todavía)<br/>- Elegir entre dos tipos (bloquear o permitir) |
| [Parte 3: Aplicar directivas de barreras de información](#part-3-apply-information-barrier-policies) | - Establecer directivas en estado activo<br/>- Ejecutar la aplicación de directiva<br/>- Ver el estado de la directiva |
| (Según sea necesario) [Editar un segmento o una directiva](information-barriers-edit-segments-policies.md) | - Editar un segmento<br/>- Editar o quitar una directiva<br/>- Volver a ejecutar la aplicación de directiva<br/>- Ver el estado de la directiva |
| (Según sea necesario) [Solución de problemas](information-barriers-troubleshooting.md)| - Tomar medidas cuando las cosas no funcionen como se esperaba|

## <a name="prerequisites"></a>Requisitos previos

Además de los [permisos y licencias necesarios,](information-barriers.md#required-licenses-and-permissions)asegúrese de que se cumplen los siguientes requisitos:

- Datos de directorio: asegúrese de que la estructura de su organización se refleja en los datos del directorio. Para realizar esta acción, asegúrese de que los atributos de la cuenta de usuario, como la pertenencia a grupos, el nombre del departamento, etc., se rellenan correctamente en Azure Active Directory (o Exchange Online). Para obtener más información, consulte los siguientes recursos:
  - [Atributos para las directivas de barreras de información](information-barriers-attributes.md)
  - [Agregar o actualizar la información de perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurar las propiedades de la cuenta de usuario con Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- Búsqueda de directorios con ámbito: antes de definir la primera directiva de barreras de información de su organización, debe habilitar la búsqueda de directorios con ámbito [en Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search) Espere al menos 24 horas después de habilitar la búsqueda en directorios con ámbito antes de configurar o definir directivas de barreras de información.

- Licencia EXO: las directivas DEC solo funcionan si se ha asignado una licencia EXO a los usuarios de destino.

- Registro de auditoría: para buscar el estado de una aplicación de directiva, el registro de auditoría debe estar activado. Se recomienda habilitar la auditoría antes de empezar a definir segmentos o directivas. Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría.](turn-audit-log-search-on-or-off.md)

- Sin directivas de libreta de direcciones: antes de definir y aplicar directivas de barreras de información, asegúrese de que no haya directivas de libreta de direcciones de Exchange. Las barreras de información se basan en directivas de libreta de direcciones, pero los dos tipos de directivas no son compatibles. Si tiene estas directivas, asegúrese de quitar primero las directivas de [la libreta de](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) direcciones. Una vez habilitadas las directivas de barreras de información y tiene habilitada la libreta [](https://docs.microsoft.com/exchange/address-books/hierarchical-address-books/hierarchical-address-books) jerárquica de direcciones, todos los usuarios *_*_* que no estén incluidos en un segmento de barreras de información verán la libreta jerárquica de direcciones en Exchange Online.

- PowerShell: actualmente, las directivas de barreras de información se definen y administran en el Centro de seguridad & cumplimiento de Office 365 mediante cmdlets de PowerShell. Aunque en este artículo se proporcionan varios ejemplos, deberá familiarizarse con los cmdlets y parámetros de PowerShell. También necesitará el módulo de Azure PowerShell.
    - [Conectarse a PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    - [Instalar el módulo de Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- Consentimiento de administrador para barreras de información en Microsoft Teams: cuando las directivas están en su lugar, las barreras de información pueden quitar a las personas de las sesiones de chat en las que no se supone que estén. Esta configuración ayuda a garantizar que la organización cumpla con las directivas y normativas. Use el siguiente procedimiento para permitir que las directivas de barreras de información funcionen según lo esperado en Microsoft Teams.

   1. Ejecute los siguientes cmdlets de PowerShell:

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. Cuando se le solicite, inicie sesión con su cuenta de trabajo o escuela para Office 365.

   3. En el cuadro de diálogo _ *Permisos solicitados** , revise la información y, a continuación, **elija Aceptar**.

Cuando se cumplan todos los requisitos previos, vaya a la siguiente sección.

> [!TIP]
> Para ayudarle a preparar su plan, se incluye un escenario de ejemplo en este artículo. [Vea los departamentos, segmentos y directivas de Contoso.](#example-contosos-departments-segments-and-policies)<p>Además, hay disponible un libro descargable de Excel para ayudarle a planear y definir los segmentos y directivas (y crear los cmdlets de PowerShell). [Obtener el libro](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).

## <a name="part-1-segment-users"></a>Parte 1: Segmentar usuarios

Durante esta fase, se determinan las directivas de barreras de información que se necesitan, se realiza una lista de segmentos para definir y, a continuación, se definen los segmentos.

### <a name="determine-what-policies-are-needed"></a>Determinar qué directivas son necesarias

Teniendo en cuenta las normativas legales y del sector, ¿quiénes son los grupos de su organización que necesitarán directivas de barreras de información? Crear una lista. ¿Hay algún grupo al que se le impida comunicarse con otro grupo? ¿Hay algún grupo que tenga permiso para comunicarse solo con uno o dos grupos? Piense en las directivas que necesita como pertenecientes a uno de los dos grupos:

- Las directivas de "bloqueo" impiden que un grupo se comunique con otro.
- Las directivas "Permitir" permiten a un grupo comunicarse solo con determinados otros grupos específicos.

Cuando tenga la lista inicial de grupos y directivas, continúe con la identificación de los segmentos que necesitará.

### <a name="identify-segments"></a>Identificar segmentos

Además de la lista inicial de directivas, haga una lista de segmentos para su organización. Los usuarios que se incluirán en las directivas de barreras de información deben pertenecer a un segmento. Planee los segmentos cuidadosamente, ya que un usuario solo puede estar en un segmento. Cada segmento solo puede tener aplicada una directiva de barreras de información.

> [!IMPORTANT]
> Un usuario solo puede estar en un segmento.

Determine qué atributos de los datos de directorio de su organización usará para definir segmentos. Puede usar *Department*, *MemberOf* o cualquiera de los atributos admitidos. Asegúrese de que tiene valores en el atributo que seleccione para los usuarios. [Vea la lista de atributos admitidos para barreras de información.](information-barriers-attributes.md)

> [!IMPORTANT]
> **Antes de continuar con la siguiente sección, asegúrese** de que los datos del directorio tienen valores para los atributos que puede usar para definir segmentos. Si los datos del directorio no tienen valores para los atributos que desea usar, las cuentas de usuario deben actualizarse para incluir esa información antes de continuar con las barreras de información. Para obtener ayuda con esto, vea los siguientes recursos:<br/>- [Configurar las propiedades de la cuenta de usuario con PowerShell de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [Agregar o actualizar la información de perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definir segmentos con PowerShell

La definición de segmentos no afecta a los usuarios; simplemente establece la fase para que se definan y se apliquen las directivas de barreras de información.

1. Use el cmdlet **New-OrganizationSegment** con el parámetro **UserGroupFilter** que corresponde al [atributo](information-barriers-attributes.md) que desea usar.

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>En este ejemplo, se define un segmento denominado *HR* mediante *HR*, un valor en el *atributo Department.* La **parte -eq** del cmdlet hace referencia a "igual a". (Como alternativa, puedes usar **-ne** para significar "no es igual a". Consulta [Usar "es igual a" y "no es igual a" en las definiciones de segmento).](#using-equals-and-not-equals-in-segment-definitions) |

    Después de ejecutar cada cmdlet, debería ver una lista de detalles sobre el nuevo segmento. Los detalles incluyen el tipo del segmento, quién lo creó o modificó por última vez, y así sucesivamente. 

2. Repita este proceso para cada segmento que desee definir.

    > [!IMPORTANT]
    > **Asegúrese de que los segmentos no se superpongan.** Cada usuario que se verá afectado por las barreras de información debe pertenecer a un segmento (y solo uno). Ningún usuario debe pertenecer a dos o más segmentos. (Vea [el ejemplo: segmentos definidos de Contoso](#contosos-defined-segments) en este artículo).

Después de definir los segmentos, continúe con la definición [de directivas de barreras de información.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Usar "es igual a" y "no es igual" en definiciones de segmento

En el siguiente ejemplo, estamos definiendo un segmento como "Department equals HR". 

|**Ejemplo**|**Nota**|
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Observe que en este ejemplo, la definición de segmento incluye un parámetro "equals" que se indica **como -eq**. |

También puede definir segmentos con un parámetro "no es igual a", indicado como **-ne**, como se muestra en la tabla siguiente:

|**Sintaxis**|**Ejemplo**|
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | En este ejemplo, definimos un segmento denominado *NotSales* que incluye a todos los usuarios que no están en *Ventas.* La **parte -ne** del cmdlet hace referencia a "no es igual a". |

Además de definir segmentos con "igual a" o "no es igual a", puedes definir un segmento usando los parámetros "iguales" y "no es igual a". También puede definir filtros de grupo complejos mediante operadores *lógicos AND* *y OR.*

|**Sintaxis**|**Ejemplo**|
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | En este ejemplo, definimos un segmento denominado *LocalFTE* que incluye personas ubicadas localmente y cuyas posiciones no se enumeran como *Temporales*. |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| En este ejemplo, definimos un segmento denominado *Segment1* que incluye personas que son miembros de group1@contoso.com y no miembros de group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | En este ejemplo, definimos un segmento denominado *Segment2* que incluye personas que son miembros de group2@contoso.com y no miembros de group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| En este ejemplo, definimos un segmento denominado *Segment1and2* que incluye miembros de group1@contoso.com y group2@contoso.com y no miembros de group3@contoso.com. |

> [!TIP]
> Si es posible, use definiciones de segmento que incluyan "-eq" o "-ne". Intente no definir definiciones de segmento complejas.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: Definir directivas de barreras de información

Determine si necesita impedir las comunicaciones entre ciertos segmentos o limitar las comunicaciones a determinados segmentos. Lo ideal es usar el número mínimo de directivas para garantizar que su organización cumple con los requisitos legales y del sector.

Con su lista de segmentos de usuario y las directivas de barreras de información que desea definir, seleccione un escenario y, a continuación, siga los pasos.

- [Escenario 1: Bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments)
- [Escenario 2: Permitir que un segmento se comunique solo con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Asegúrese de que, al definir directivas,** no asigne más de una directiva a un segmento. Por ejemplo, si define una directiva para un segmento denominado *Ventas*, no defina una directiva adicional para *Ventas*.<p> Además, al definir directivas de barreras de información, asegúrese de establecer esas directivas en estado inactivo hasta que esté listo para aplicarlas. La definición (o edición) de directivas no afecta a los usuarios hasta que dichas directivas se establecen en estado activo y, a continuación, se aplican.

(Vea [el ejemplo: directivas de barreras de información de Contoso](#contosos-information-barrier-policies) en este artículo).

### <a name="scenario-1-block-communications-between-segments"></a>Escenario 1: Bloquear las comunicaciones entre segmentos

Cuando desee bloquear la comunicación entre segmentos, defina dos directivas: una para cada dirección. Cada directiva bloquea la comunicación solo de un modo.

Por ejemplo, supongamos que desea bloquear las comunicaciones entre el segmento A y el segmento B. En este caso, se define una directiva que impide que el segmento A se comunique con el segmento B y, a continuación, se define una segunda directiva para evitar que el segmento B se comunique con el segmento A.

1. Para definir la primera directiva de bloqueo, use el cmdlet **New-InformationBarrierPolicy** con el **parámetro SegmentsBlocked.**

    |**Sintaxis** | **Ejemplo**| |**--------|:----------| |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> En este ejemplo, definimos una directiva denominada *Sales-Research* para un segmento denominado *Sales*. Cuando está activa y se aplica, esta directiva impide que los usuarios de *Ventas* se comuniquen con personas de un segmento denominado *Investigación.* |

2. Para definir el segundo segmento de bloqueo, use el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsBlocked** de nuevo, esta vez con los segmentos invertidos.

    |**Ejemplo**|**Nota**|
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | En este ejemplo, definimos una directiva denominada *Research-Sales* para evitar que *Research* se comunique con *Sales*. |

3. Continúe con una de las siguientes acciones:

   - (Si es necesario) [Definir una directiva para permitir que un segmento se comunique solo con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Una vez definidas todas las directivas) [Aplicar directivas de barreras de información](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Escenario 2: Permitir que un segmento se comunique solo con otro segmento

1. Para permitir que un segmento se comunique solo con otro segmento, use el cmdlet **New-InformationBarrierPolicy** con el **parámetro SegmentsAllowed.**

    |**Sintaxis**|**Ejemplo**|
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> En este ejemplo, definimos una directiva denominada *Manufacturing-HR* para un segmento denominado *Manufacturing*. Cuando está activa y se aplica, esta directiva permite que los usuarios de fabricación *se* comuniquen solo con personas de un segmento denominado *RECURSOS HUMANOS.* (En este caso, la *fabricación no* se puede comunicar con usuarios que no forman parte de *RR. H.* |

    **Si es necesario, puede especificar varios segmentos con este cmdlet, como se muestra en el ejemplo siguiente.**

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> En este ejemplo, definimos una directiva que permite que el segmento *investigación* se comunique solo con *RR. UU.* y *Fabricación.* |

    Repite este paso para cada directiva que quieras definir para permitir que segmentos específicos se comuniquen solo con determinados segmentos específicos.

2. Continúe con una de las siguientes acciones:

   - (Si es necesario) [Definir una directiva para bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments) 
   - (Una vez definidas todas las directivas) [Aplicar directivas de barreras de información](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: Aplicar directivas de barreras de información

Las directivas de barreras de información no están en vigor hasta que las establezca en estado activo y, a continuación, aplique las directivas.

1. Use el cmdlet **Get-InformationBarrierPolicy** para ver una lista de directivas que se han definido. Tenga en cuenta el estado y la identidad (GUID) de cada directiva.

    Sintaxis: `Get-InformationBarrierPolicy`

2. Para establecer una directiva en estado activo, use el cmdlet **Set-InformationBarrierPolicy** con un parámetro **Identity** y el parámetro **State** establecido en **Active**. 

    |**Sintaxis**|**Ejemplo**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> En este ejemplo, establecemos una directiva de barreras de información que tiene el GUID *43c37853-ea10-4b90-a23d-ab8c93772471* en estado activo. |

    Repita este paso según corresponda para cada directiva.

3. Cuando haya terminado de establecer las directivas de barreras de información en estado activo, use el cmdlet **Start-InformationBarrierPoliciesApplication** en el Centro de seguridad & cumplimiento.

    Sintaxis: `Start-InformationBarrierPoliciesApplication`

    Después de ejecutar `Start-InformationBarrierPoliciesApplication` , espere 30 minutos para que el sistema empiece a aplicar las directivas. El sistema aplica directivas usuario por usuario. El sistema procesa unas 5.000 cuentas de usuario por hora.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Ver el estado de cuentas de usuario, segmentos, directivas o aplicación de directiva

Con PowerShell, puede ver el estado de las cuentas de usuario, los segmentos, las directivas y la aplicación de directiva, como se muestra en la tabla siguiente.

|**Para ver esta información**|**Realizar esta acción**|
|:---------------|:----------|
| Cuentas de usuario | Use el **cmdlet Get-InformationBarrierRecipientStatus con** parámetros Identity. <p> Sintaxis: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. <p> Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*. <p> (También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> Este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de barreras de información que se aplican.|
| Segmentos | Use el cmdlet **Get-OrganizationSegment.**<p> Sintaxis: `Get-OrganizationSegment` <p> Este cmdlet mostrará una lista de todos los segmentos definidos para su organización. |
| Directivas de barreras de información | Use el cmdlet **Get-InformationBarrierPolicy.** <p> Sintaxis: `Get-InformationBarrierPolicy` <p> Este cmdlet mostrará una lista de directivas de barreras de información definidas y su estado. |
| La aplicación de directiva de barreras de información más reciente | Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus.** <p> Sintaxis: `Get-InformationBarrierPoliciesApplicationStatus`<p> Este cmdlet mostrará información sobre si la aplicación de directiva se ha completado, ha fallado o está en curso. |
| Todas las aplicaciones de directivas de barreras de información|Use `Get-InformationBarrierPoliciesApplicationStatus -All`<p> Este cmdlet mostrará información sobre si la aplicación de directiva se ha completado, ha fallado o está en curso.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>¿Qué ocurre si necesito quitar o cambiar directivas?

Hay recursos disponibles para ayudarle a administrar las directivas de barreras de información.

- Si algo va mal con las barreras de información, consulte [Solución de problemas de barreras de información.](information-barriers-troubleshooting.md)
- Para impedir que se apliquen directivas, vea [Detener una aplicación de directiva.](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- Para quitar una directiva de barreras de información, [vea Quitar una directiva.](information-barriers-edit-segments-policies.md#remove-a-policy)
- Para realizar cambios en segmentos o directivas, vea [Editar (o quitar) directivas de barreras de información.](information-barriers-edit-segments-policies.md)

## <a name="example-contosos-departments-segments-and-policies"></a>Ejemplo: departamentos, segmentos y directivas de Contoso

Para ver cómo una organización puede aproximarse a la definición de segmentos y directivas, tenga en cuenta el siguiente ejemplo.

### <a name="contosos-departments-and-plan"></a>Departamentos y planes de Contoso

Contoso tiene cinco departamentos: RR. UU., Ventas, Marketing, Investigación y Fabricación. Para cumplir con las normativas del sector, se supone que las personas de algunos departamentos no deben comunicarse con otros departamentos, como se muestra en la tabla siguiente:

|**Segmento**|**Puede hablar con**|**No se puede hablar con**|
|:----------|:--------------|:-----------------|
| HR | Todos | (sin restricciones) |
| Ventas | RECURSOS HUMANOS, Marketing, Fabricación | Referencia |
| Marketing | Todos | (sin restricciones) |
| Referencia | RECURSOS HUMANOS, Marketing, Fabricación | Ventas |
| Industria | RECURSOS HUMANOS, Marketing | Cualquier persona que no sea RRHH o Marketing |

Para esta estructura, el plan de Contoso incluye tres directivas de barreras de información:

1. Una directiva diseñada para impedir que Ventas se comunique con Investigación (y otra directiva para evitar que Research se comunique con Ventas).
2. Una directiva diseñada para permitir que la fabricación se comunique solo con recursos humanos y marketing.

Para este escenario, no es necesario definir directivas para recursos humanos o marketing.

### <a name="contosos-defined-segments"></a>Segmentos definidos de Contoso

Contoso usará el atributo Department en Azure Active Directory para definir segmentos, como se muestra a continuación:

|**Departamento**|**Definición de segmento**|
|:-------------|:---------------------|
| HR | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Ventas | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Referencia | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Industria | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Con los segmentos definidos, Contoso procede a definir directivas.

### <a name="contosos-information-barrier-policies"></a>Directivas de barreras de información de Contoso

Contoso define tres directivas, como se describe en la tabla siguiente:

|**Directiva**|**Definición de directiva**|
|:---------|:--------------------|
| **Directiva 1: Impedir que las ventas se comuniquen con Research** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> En este ejemplo, la directiva de barreras de información se denomina *Sales-Research*. Cuando esta directiva está activa y se aplica, ayudará a impedir que los usuarios que se encuentran en el segmento ventas se comuniquen con los usuarios del segmento Investigación. Esta directiva es una directiva un solo sentido; no impedirá que Research se comunique con Ventas. Para ello, se necesita la directiva 2. |
| **Directiva 2: Impedir que La investigación se comunique con Ventas** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> En este ejemplo, la directiva de barreras de información se denomina *Research-Sales*. Cuando esta directiva está activa y se aplica, ayudará a impedir que los usuarios que están en el segmento investigación se comuniquen con los usuarios del segmento ventas. |
| **Directiva 3: Permitir que la fabricación se comunique solo con recursos humanos y marketing** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> En este caso, la directiva de barreras de información se denomina *Manufacturing-HRMarketing*. Cuando esta directiva está activa y se aplica, la fabricación solo puede comunicarse con recursos humanos y marketing. Los recursos humanos y el marketing no tienen restricciones para comunicarse con otros segmentos. |

Con los segmentos y directivas definidos, Contoso aplica las directivas ejecutando el cmdlet **Start-InformationBarrierPoliciesApplication.**

Cuando finaliza el cmdlet, Contoso cumple con los requisitos legales y del sector.

## <a name="resources"></a>Recursos

- [Obtener información general sobre las barreras de información](information-barriers.md)
- [Barreras de información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
