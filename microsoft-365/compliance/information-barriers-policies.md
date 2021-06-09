---
title: Definir directivas de barreras de información
description: Obtenga información sobre cómo definir directivas para las barreras de información en Microsoft Teams.
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
ms.openlocfilehash: ce387799a2f9e6d6cdffe063d3adf7310d7e7757
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842727"
---
# <a name="define-information-barrier-policies"></a>Definir directivas de barreras de información

Con las barreras de información, puede definir directivas diseñadas para impedir que determinados segmentos de usuarios se comuniquen entre sí o permitir que segmentos específicos se comuniquen solo con otros segmentos. Las directivas de barrera de información pueden ayudar a su organización a mantener el cumplimiento de los estándares y normativas relevantes del sector y evitar posibles conflictos de interés. Para obtener más información, vea [Information barriers](information-barriers.md).

En este artículo se describe cómo planear, definir, implementar y administrar directivas de barrera de información. Hay varios pasos implicados y el flujo de trabajo se divide en varias partes. Asegúrese de leer los [requisitos previos](#prerequisites) y todo el proceso antes de empezar a definir (o editar) directivas de barrera de información.

> [!TIP]
> En este artículo se incluye un [escenario](#example-contosos-departments-segments-and-policies) de ejemplo y un libro de Excel [para](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) ayudarle a planear y definir las directivas de barrera de información.

## <a name="concepts-of-information-barrier-policies"></a>Conceptos de las directivas de barrera de información

Al definir directivas para barreras de información, trabajará con atributos de cuenta de usuario, segmentos, directivas de "bloquear" o "permitir" y aplicación de directiva.

- Los atributos de cuenta de usuario están definidos en Azure Active Directory (o Exchange Online). Estos atributos pueden incluir departamento, puesto, ubicación, nombre del equipo y otros detalles del perfil de trabajo. 
- Los segmentos son conjuntos de usuarios que se definen en el Centro de seguridad & cumplimiento mediante un atributo **de cuenta de usuario seleccionado.** (Consulte la[ lista de atributos admitidos](information-barriers-attributes.md)).
- Las directivas de barrera de información determinan los límites o restricciones de comunicación. Al definir directivas de barrera de información, puede elegir entre dos tipos de directivas:
    - Las directivas de "bloqueo" impiden que un segmento se comunique con otro segmento.
    - Las directivas de "permitir" permiten que un segmento se comunique solo con ciertos otros segmentos.
- La administración de directivas se realiza después de definir todas las directivas de barrera de información y está listo para aplicarlas en su organización.

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

| Fase | Lo que implica |
|:--------|:------------------|
| [Asegurarse de que se cumplen los requisitos previos](#prerequisites) | - Compruebe que tiene las licencias y permisos [necesarios](information-barriers.md#required-licenses-and-permissions)<br/>- Comprobar que el directorio incluye datos para segmentar usuarios<br/>- Habilitar la búsqueda de directorios con ámbito para Microsoft Teams<br/>- Asegúrese de que el registro de auditoría está activado<br/>- Asegúrese de que no Exchange directivas de libreta de direcciones están en su lugar<br/>- Usar PowerShell (se proporcionan ejemplos)<br/>- Proporcionar consentimiento de administrador para Microsoft Teams (se incluyen pasos) |
| [Parte 1: Segmentar usuarios de la organización](#part-1-segment-users) | - Determinar qué directivas son necesarias<br/>- Crear una lista de segmentos para definir<br/>- Identificar qué atributos usar<br/>- Definir segmentos en términos de filtros de directivas |
| [Parte 2: Definir directivas de barrera de información](#part-2-define-information-barrier-policies) | - Definir las directivas (aún no se aplican)<br/>- Elegir entre dos tipos (bloquear o permitir) |
| [Parte 3: Aplicar directivas de barrera de información](#part-3-apply-information-barrier-policies) | - Establecer directivas en estado activo<br/>- Ejecutar la aplicación de directiva<br/>- Ver el estado de la directiva |
| (Según sea necesario) [Editar un segmento o una directiva](information-barriers-edit-segments-policies.md) | - Editar un segmento<br/>- Editar o quitar una directiva<br/>- Volver a ejecutar la aplicación de directiva<br/>- Ver el estado de la directiva |
| (Según sea necesario) [Solución de problemas](information-barriers-troubleshooting.md)| - Tomar medidas cuando las cosas no funcionen como se esperaba|

## <a name="prerequisites"></a>Requisitos previos

Además de las licencias y permisos [necesarios,](information-barriers.md#required-licenses-and-permissions)asegúrese de que se cumplen los siguientes requisitos:

- Datos de directorio: asegúrese de que la estructura de su organización se refleja en los datos de directorio. Para realizar esta acción, asegúrese de que los atributos de cuenta de usuario, como la pertenencia a grupos, el nombre del departamento, etc., se rellenan correctamente en Azure Active Directory (o Exchange Online). Para obtener más información, consulte los siguientes recursos:
  - [Atributos para las directivas de barreras de información](information-barriers-attributes.md)
  - [Agregar o actualizar la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurar las propiedades de la cuenta de usuario con Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- Búsqueda de directorios con ámbito: antes de definir la primera directiva de barrera de información de la [organización,](/MicrosoftTeams/teams-scoped-directory-search)debe habilitar la búsqueda de directorios con ámbito en Microsoft Teams . Espere al menos 24 horas después de habilitar la búsqueda de directorios con ámbito antes de configurar o definir directivas de barrera de información.

- Licencia exo: las directivas de IB funcionan solo si se ha asignado una licencia EXO a los usuarios de destino.

- Registro de auditoría: para buscar el estado de una aplicación de directiva, el registro de auditoría debe estar activado. Se recomienda habilitar la auditoría antes de empezar a definir segmentos o directivas. Para obtener más información, vea Activar o desactivar la búsqueda del [registro de auditoría.](turn-audit-log-search-on-or-off.md)

- Sin directivas de libreta de direcciones: antes de definir y aplicar directivas de barrera de información, asegúrese de que no Exchange directivas de libreta de direcciones. Las barreras de información se basan en las directivas de libreta de direcciones, pero los dos tipos de directivas no son compatibles. Si tiene estas directivas, asegúrese de quitar primero [las directivas de la libreta de direcciones.](/exchange/address-books/address-book-policies/remove-an-address-book-policy) Una vez habilitadas las directivas de barrera de  información y habilitada la libreta jerárquica [](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) de direcciones, todos los usuarios que no estén incluidos en un segmento de barrera de información verán la libreta jerárquica de direcciones en Exchange en línea.

- PowerShell: actualmente, las directivas de barrera de información se definen y administran en el Centro de Office 365 seguridad & cumplimiento con cmdlets de PowerShell. Aunque en este artículo se proporcionan varios ejemplos, deberá familiarizarse con los cmdlets y parámetros de PowerShell. También necesitará el módulo Azure PowerShell.
    - [Conectarse a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)
    - [Instalar el Azure PowerShell módulo](/powershell/azure/install-az-ps?view=azps-2.3.2)

- Consentimiento de los administradores para las barreras de información en Microsoft Teams: cuando las directivas del IB están en su lugar, pueden quitar usuarios que no son del IB de grupos (es decir, canales Teams, que se basan en grupos). Esta configuración ayuda a garantizar que la organización cumpla con las directivas y las normativas. Use el siguiente procedimiento para permitir que las directivas de barrera de información funcionen según lo esperado en Microsoft Teams.

   1. Requisito previo: Instalar Azure PowerShell [desde Instalar Azure PowerShell](/powershell/azure/install-az-ps).

   1. Ejecute los siguientes cmdlets de PowerShell:

      ```powershell
      Connect-AzAccount -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzAccount -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. Cuando se le pida, inicie sesión con su cuenta de trabajo o escuela para Office 365.

   1. En el **cuadro de diálogo Permisos solicitados,** revise la información y, a continuación, elija **Aceptar**. Los permisos solicitados por la aplicación se indican a continuación.
      
      > [!div class="mx-imgBorder"]
      > ![imagen](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)


Cuando se cumplan todos los requisitos previos, continúe con la siguiente sección.

> [!TIP]
> Para ayudarle a preparar el plan, se incluye un escenario de ejemplo en este artículo. [Vea Departamentos, segmentos](#example-contosos-departments-segments-and-policies)y directivas de Contoso.<p>Además, hay disponible un Excel de datos descargable para ayudarle a planear y definir sus segmentos y directivas (y crear los cmdlets de PowerShell). [Obtener el libro](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).

## <a name="part-1-segment-users"></a>Parte 1: Segmentar usuarios

Durante esta fase, se determina qué directivas de barrera de información se necesitan, se hace una lista de segmentos para definir y, a continuación, se definen los segmentos.

### <a name="determine-what-policies-are-needed"></a>Determinar qué directivas son necesarias

Teniendo en cuenta las normativas legales y del sector, ¿quiénes son los grupos de su organización que necesitarán directivas de barreras de información? Hacer una lista. ¿Hay algún grupo al que se le impida comunicarse con otro grupo? ¿Hay algún grupo al que se le debería permitir comunicarse solo con uno o dos grupos más? Piense en las directivas que necesita como pertenecientes a uno de los dos grupos:

- Las directivas de "bloquear" impiden que un grupo se comunique con otro grupo.
- Las directivas de "permitir" permiten a un grupo comunicarse solo con otros grupos específicos.

Cuando tenga la lista inicial de grupos y directivas, proceda a identificar los segmentos que necesitará.

### <a name="identify-segments"></a>Identificar segmentos

Además de la lista inicial de directivas, haga una lista de segmentos para su organización. Los usuarios que se incluirán en directivas de barrera de información deben pertenecer a un segmento. Planear los segmentos cuidadosamente como un usuario solo puede estar en un segmento. Cada segmento solo puede tener aplicada una directiva de barrera de información.

> [!IMPORTANT]
> Un usuario solo puede estar en un segmento.

Determine qué atributos de los datos de directorio de la organización usará para definir segmentos. Puede usar *Department*, *MemberOf* o cualquiera de los atributos admitidos. Asegúrese de que tiene valores en el atributo que seleccione para los usuarios. [Vea la lista de atributos admitidos para ver las barreras de información](information-barriers-attributes.md).

> [!IMPORTANT]
> **Antes de continuar con la siguiente sección, asegúrese** de que los datos de directorio tienen valores para los atributos que puede usar para definir segmentos . Si los datos de directorio no tienen valores para los atributos que desea usar, las cuentas de usuario deben actualizarse para incluir esa información antes de continuar con las barreras de información. Para obtener ayuda con esto, consulte los siguientes recursos:<br/>- [Configurar propiedades de cuenta de usuario Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Agregar o actualizar la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definir segmentos con PowerShell

La definición de segmentos no afecta a los usuarios; simplemente establece la fase para que las directivas de barrera de información se definan y, a continuación, se apliquen.

1. Use el cmdlet **New-OrganizationSegment** con el parámetro **UserGroupFilter** que corresponde al [atributo](information-barriers-attributes.md) que desea usar.

    | Sintaxis | Ejemplo |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>En este ejemplo, se define un segmento denominado *HR* mediante *HR*, un valor en el *atributo Department.* La **parte -eq** del cmdlet hace referencia a "equals". (Alternativamente, puede usar **-ne** para significar "no es igual". Vea [Using "equals" and "not equals" in segment definitions](#using-equals-and-not-equals-in-segment-definitions).) |

    Después de ejecutar cada cmdlet, debería ver una lista de detalles sobre el nuevo segmento. Los detalles incluyen el tipo del segmento, quién lo creó o modificó por última vez, y así sucesivamente. 

2. Repita este proceso para cada segmento que desee definir.

    > [!IMPORTANT]
    > **Asegúrese de que los segmentos no se superponen**. Cada usuario que se verá afectado por las barreras de información debe pertenecer a un segmento (y solo uno). Ningún usuario debe pertenecer a dos o más segmentos. (Vea [el ejemplo: segmentos definidos de Contoso](#contosos-defined-segments) en este artículo).

Después de definir los segmentos, continúe con la [definición de directivas de barrera de información](#part-2-define-information-barrier-policies).

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Usar "iguales" y "no es igual" en definiciones de segmento

En el siguiente ejemplo, estamos definiendo un segmento de modo que "Department es igual a HR". 

| Ejemplo: | Nota |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Observe que en este ejemplo, la definición de segmento incluye un parámetro "igual" que se indica como **-eq**. |

También puede definir segmentos mediante un parámetro "no igual a", que se indica como **-ne**, como se muestra en la tabla siguiente:

| Sintaxis | Ejemplo |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | En este ejemplo, definimos un segmento denominado *NotSales* que incluye a todos los usuarios que no están en *Sales*. La **parte -ne** del cmdlet hace referencia a "no es igual". |

Además de definir segmentos con "iguales" o "no iguales", puede definir un segmento con parámetros "iguales" y "no iguales". También puede definir filtros de grupo complejos mediante operadores *AND* y *OR* lógicos.

| Sintaxis | Ejemplo |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | En este ejemplo, definimos un segmento denominado *LocalFTE* que incluye personas que están ubicadas localmente y cuyas posiciones no se enumeran como *Temporales*. |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| En este ejemplo, definimos un segmento denominado *Segment1* que incluye personas que son miembros de group1@contoso.com y no miembros de group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | En este ejemplo, definimos un segmento denominado *Segment2* que incluye personas que son miembros de group2@contoso.com y no miembros de group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| En este ejemplo, definimos un segmento denominado *Segment1and2* que incluye a los miembros de group1@contoso.com y group2@contoso.com miembros de group3@contoso.com. |

> [!TIP]
> Si es posible, use definiciones de segmento que incluyan "-eq" o "-ne". Intente no definir definiciones de segmento complejas.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: Definir directivas de barrera de información

Determine si necesita impedir las comunicaciones entre ciertos segmentos o limitar las comunicaciones a determinados segmentos. Lo ideal es usar el número mínimo de directivas para garantizar que su organización cumple con los requisitos legales y del sector.

Con la lista de segmentos de usuario y las directivas de barrera de información que desea definir, seleccione un escenario y, a continuación, siga los pasos.

- [Escenario 1: Bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments)
- [Escenario 2: Permitir que un segmento solo se comunique con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Asegúrese de que, al definir directivas,** no asigne más de una directiva a un segmento . Por ejemplo, si define una directiva para un segmento denominado *Ventas*, no defina una directiva adicional para *Sales*.<p> Además, al definir directivas de barrera de información, asegúrese de establecer dichas directivas en estado inactivo hasta que esté listo para aplicarlas. La definición (o edición) de directivas no afecta a los usuarios hasta que estas directivas se establecen en estado activo y, a continuación, se aplican.

(Vea [el ejemplo: directivas de barrera](#contosos-information-barrier-policies) de información de Contoso en este artículo).

### <a name="scenario-1-block-communications-between-segments"></a>Escenario 1: Bloquear las comunicaciones entre segmentos

Cuando desea bloquear segmentos para que no se comuniquen entre sí, defina dos directivas: una para cada dirección. Cada directiva bloquea la comunicación en un solo sentido.

Por ejemplo, supongamos que desea bloquear las comunicaciones entre el segmento A y el segmento B. En este caso, se define una directiva que impide que el segmento A se comunique con el segmento B y, a continuación, se define una segunda directiva para impedir que el segmento B se comunique con el segmento A.

1. Para definir la primera directiva de bloqueo, use el cmdlet **New-InformationBarrierPolicy** con el **parámetro SegmentsBlocked.**

    | Sintaxis | Ejemplo |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> En este ejemplo, definimos una directiva denominada *Sales-Research* para un segmento denominado *Sales*. Cuando se activa y se aplica, esta directiva impide que los usuarios de *Ventas* se comuniquen con personas de un segmento denominado *Investigación*. |

2. Para definir el segundo segmento de bloqueo, use de nuevo el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsBlocked,** esta vez con los segmentos invertidos.

    | Ejemplo: | Nota |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | En este ejemplo, definimos una directiva denominada *Research-Sales* para impedir que *Research* se comunique con *Sales*. |

3. Continúe con una de las siguientes acciones:

   - (Si es necesario) [Definir una directiva para permitir que un segmento se comunique solo con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Después de definir todas las directivas) [Aplicar directivas de barrera de información](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Escenario 2: Permitir que un segmento solo se comunique con otro segmento

1. Para permitir que un segmento se comunique solo con otro segmento, use el cmdlet **New-InformationBarrierPolicy** con el **parámetro SegmentsAllowed.**

    | Sintaxis | Ejemplo |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> En este ejemplo, definimos una directiva denominada *Manufacturing-HR* para un segmento denominado *Manufacturing*. Cuando se activa y se aplica, esta directiva permite a los usuarios de *La* fabricación comunicarse solo con personas de un segmento denominado *HR*. (En este caso, *la fabricación no* puede comunicarse con usuarios que no forman parte de recursos *humanos).* |

    **Si es necesario, puede especificar varios segmentos con este cmdlet, como se muestra en el ejemplo siguiente.**

    | Sintaxis | Ejemplo |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> En este ejemplo, definimos una  directiva que permite al segmento de investigación comunicarse solo con *recursos humanos* y *fabricación.* |

    Repita este paso para cada directiva que desee definir para permitir que segmentos específicos se comuniquen solo con ciertos otros segmentos específicos.

2. Continúe con una de las siguientes acciones:

   - (Si es necesario) [Definir una directiva para bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments) 
   - (Después de definir todas las directivas) [Aplicar directivas de barrera de información](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: Aplicar directivas de barrera de información

Las directivas de barrera de información no están en vigor hasta que las establezca en estado activo y, a continuación, aplique las directivas.

1. Use el cmdlet **Get-InformationBarrierPolicy** para ver una lista de directivas que se han definido. Tenga en cuenta el estado y la identidad (GUID) de cada directiva.

    Sintaxis: `Get-InformationBarrierPolicy`

2. Para establecer una directiva en estado activo, use el cmdlet **Set-InformationBarrierPolicy** con un parámetro **Identity** y el parámetro **State** establecido en **Active**. 

    | Sintaxis | Ejemplo |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> En este ejemplo, establecemos una directiva de barrera de información que tiene el GUID *43c37853-ea10-4b90-a23d-ab8c93772471* en estado activo. |

    Repita este paso según corresponda para cada directiva.

3. Cuando haya terminado de establecer las directivas de barrera de información en estado activo, use el cmdlet **Start-InformationBarrierPoliciesApplication** en el Centro de seguridad & cumplimiento.

    Sintaxis: `Start-InformationBarrierPoliciesApplication`

    Después de ejecutar `Start-InformationBarrierPoliciesApplication` , espere 30 minutos para que el sistema empiece a aplicar las directivas. El sistema aplica directivas usuario por usuario. El sistema procesa unas 5.000 cuentas de usuario por hora.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Ver el estado de cuentas de usuario, segmentos, directivas o aplicación de directiva

Con PowerShell, puede ver el estado de cuentas de usuario, segmentos, directivas y aplicación de directivas, como se muestra en la tabla siguiente.

| Para ver esta información | Realizar esta acción |
|:---------------|:----------|
| Cuentas de usuario | Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity. <p> Sintaxis: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. <p> Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*. <p> (También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> Este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de barrera de información que se aplican.|
| Segmentos | Use el cmdlet **Get-OrganizationSegment.**<p> Sintaxis: `Get-OrganizationSegment` <p> Este cmdlet mostrará una lista de todos los segmentos definidos para su organización. |
| Directivas de barreras de información | Use el cmdlet **Get-InformationBarrierPolicy.** <p> Sintaxis: `Get-InformationBarrierPolicy` <p> Este cmdlet mostrará una lista de directivas de barrera de información definidas y su estado. |
| La aplicación de directiva de barrera de información más reciente | Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus.** <p> Sintaxis: `Get-InformationBarrierPoliciesApplicationStatus`<p> Este cmdlet mostrará información sobre si la aplicación de directiva se ha completado, ha fallado o está en curso. |
| Todas las aplicaciones de directiva de barrera de información|Use `Get-InformationBarrierPoliciesApplicationStatus -All`<p> Este cmdlet mostrará información sobre si la aplicación de directiva se ha completado, ha fallado o está en curso.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>¿Qué ocurre si necesito quitar o cambiar las directivas?

Los recursos están disponibles para ayudarle a administrar sus directivas de barrera de información.

- Si algo sale mal con las barreras de información, vea [Troubleshooting information barriers](information-barriers-troubleshooting.md).
- Para impedir que se apliquen directivas, vea [Stop a policy application](information-barriers-edit-segments-policies.md#stop-a-policy-application).
- Para quitar una directiva de barrera de información, vea [Remove a policy](information-barriers-edit-segments-policies.md#remove-a-policy).
- Para realizar cambios en segmentos o directivas, vea [Editar (o quitar) directivas de](information-barriers-edit-segments-policies.md)barrera de información .

## <a name="example-contosos-departments-segments-and-policies"></a>Ejemplo: departamentos, segmentos y directivas de Contoso

Para ver cómo una organización puede enfocar la definición de segmentos y directivas, tenga en cuenta el ejemplo siguiente.

### <a name="contosos-departments-and-plan"></a>Planes y departamentos de Contoso

Contoso tiene cinco departamentos: Recursos Humanos, Ventas, Marketing, Investigación y Fabricación. Para cumplir con las normativas del sector, se supone que los usuarios de algunos departamentos no deben comunicarse con otros departamentos, como se muestra en la tabla siguiente:

| Segmento | Puede hablar con | No puede hablar con |
|:----------|:--------------|:-----------------|
| RR. HH. | Todos | (sin restricciones) |
| Ventas | RECURSOS HUMANOS, Marketing, Fabricación | Referencia |
| Marketing | Todos | (sin restricciones) |
| Referencia | RECURSOS HUMANOS, Marketing, Fabricación | Ventas |
| Industria | RECURSOS HUMANOS, Marketing | Cualquier persona que no sea RRHH o Marketing |

Para esta estructura, el plan de Contoso incluye tres directivas de barrera de información:

1. Una directiva diseñada para impedir que Sales se comunique con Research (y otra directiva para impedir que Research se comunique con Ventas).

2. Una directiva diseñada para permitir que la fabricación se comunique solo con recursos humanos y marketing.

Para este escenario, no es necesario definir directivas para recursos humanos o marketing.

### <a name="contosos-defined-segments"></a>Segmentos definidos de Contoso

Contoso usará el atributo Department en Azure Active Directory para definir segmentos, como se muestra a continuación:

| Departamento | Definición de segmento |
|:-------------|:---------------------|
| RR. HH. | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Ventas | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Referencia | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Industria | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Con los segmentos definidos, Contoso continúa con la definición de directivas.

### <a name="contosos-information-barrier-policies"></a>Directivas de barreras de información de Contoso

Contoso define tres directivas, como se describe en la tabla siguiente:

| Directiva | Definición de directiva |
|:---------|:--------------------|
| **Directiva 1: impedir que Ventas se comunique con Investigación** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> En este ejemplo, la directiva de barrera de información se denomina *Ventas-Investigación*. Cuando esta directiva esté activa y se aplique, le ayudará a evitar que los usuarios que se encuentran en el segmento Ventas se comuniquen con usuarios en el segmento Investigación. Esta directiva es una directiva uni-way; no impedirá que Research se comunique con Sales. Para eso, es necesaria la directiva 2. |
| **Directiva 2: impedir que Investigación se comunique con Ventas** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> En este ejemplo, la directiva de barrera de información se denomina *Investigación-Ventas*. Cuando esta directiva esté activa y se aplique, le ayudará a evitar que los usuarios que se encuentran en el segmento Investigación se comuniquen con usuarios en el segmento Ventas. |
| **Directiva 3: Permitir que la fabricación se comunique solo con recursos humanos y marketing** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> En este caso, la directiva de barrera de información se denomina *Industria-RR.HH.Marketing*. Cuando esta directiva está activa y se aplica, Industria solo puede comunicarse con RR. HH. y Marketing. Los recursos humanos y el marketing no están restringidos para comunicarse con otros segmentos. |

Con segmentos y directivas definidos, Contoso aplica las directivas ejecutando el cmdlet **Start-InformationBarrierPoliciesApplication.**

Cuando el cmdlet finaliza, Contoso cumple los requisitos legales y del sector.

## <a name="resources"></a>Recursos

- [Obtener información general sobre las barreras de información](information-barriers.md)
- [Obtenga más información sobre las barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Obtenga más información sobre las barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Obtenga más información sobre las barreras de información en OneDrive](/onedrive/information-barriers)