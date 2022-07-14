---
title: Introducción a las barreras de información
description: Obtenga información sobre cómo empezar a trabajar con las barreras de información en Microsoft Purview.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, barreras de información
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
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d2f2eb77dd143f82ced98f8fce424cc729e26df7
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787812"
---
# <a name="get-started-with-information-barriers"></a>Introducción a las barreras de información

En este artículo se describe cómo configurar directivas de barreras de información (IB) en su organización. Hay varios pasos implicados, por lo que asegúrese de revisar todo el proceso antes de empezar a configurar las directivas de IB.

Configurará IB en su organización mediante el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) o mediante [Office 365 PowerShell de seguridad y cumplimiento](/powershell/exchange/scc-powershell). Para las organizaciones que configuran IB por primera vez, se recomienda usar la solución **Barreras de información** en el portal de cumplimiento. Si está administrando una configuración de IB existente y se siente cómodo con PowerShell, todavía tiene esta opción.

Para obtener más información sobre los escenarios y características de IB, consulte [Más información sobre las barreras de información](information-barriers.md).

> [!TIP]
> Para ayudarle a preparar el plan, en este artículo se incluye un [escenario de ejemplo](#example-scenario-contosos-departments-segments-and-policies) .

## <a name="required-subscriptions-and-permissions"></a>Suscripciones y permisos necesarios

Antes de empezar a trabajar con IB, debe confirmar su suscripción a Microsoft 365 y cualquier complemento. Para acceder y usar IB, su organización debe tener una de las siguientes suscripciones o complementos:

- suscripción Microsoft 365 E5/A5 (versión de pago o de prueba)
- suscripción Office 365 E5/A5/A3/A1 (versión de pago o de prueba)
- Cumplimiento avanzado de Office 365 complemento (ya no está disponible para nuevas suscripciones)
- suscripción Microsoft 365 E3/A3/A1 + el complemento de cumplimiento de Microsoft 365 E5/A5
- suscripción Microsoft 365 E3/A3/A1 + el complemento Microsoft 365 E5/A5 Insider Risk Management

Para obtener más información, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

Para [administrar las directivas de IB](information-barriers-policies.md), se le debe asignar uno de los siguientes roles:

- Administrador global de Microsoft 365
- Administrador global de Office 365
- Administrador de cumplimiento
- Administración de cumplimiento IB

Para obtener más información acerca de roles y permisos, consulte [Permisos del Centro de seguridad y cumplimiento de Office 365](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="configuration-concepts"></a>Conceptos de configuración

Al configurar IB, trabajará con varios objetos y conceptos.

- **Los atributos de cuenta de usuario** están definidos en Azure Active Directory (o Exchange Online). Estos atributos pueden incluir departamento, puesto, ubicación, nombre del equipo y otros detalles del perfil de trabajo. Asignará usuarios o grupos a segmentos con estos atributos.
- **Los segmentos son conjuntos** de grupos o usuarios definidos en el portal de cumplimiento o mediante PowerShell que usan atributos de cuenta de usuario o grupo seleccionados. Consulte la lista de [atributos admitidos por IB](information-barriers-attributes.md) para obtener más información.
- **Las directivas de IB** determinan límites o restricciones de comunicación. Al definir directivas de IB, puede elegir entre dos tipos de directivas:
  - Las directivas de *bloqueo* impiden que un segmento se comunique con otro segmento.
  - Las directivas de *permiso* permiten que un segmento se comunique solo con otros segmentos determinados.

    > [!NOTE]
    > En el caso de las directivas *permitidas* , los usuarios y grupos que no son del IB no serán visibles para los usuarios incluidos en los segmentos y directivas de IB. Si necesita que los grupos y usuarios que no son de IB sean visibles para los usuarios incluidos en los segmentos y directivas de IB, debe usar directivas de *bloque* .

- **La aplicación de directivas** se realiza una vez definidas todas las directivas de IB y está listo para aplicarlas en su organización.
- **Visibilidad de usuarios y grupos que no son de IB**. Los usuarios y grupos que no son del IB son usuarios y grupos excluidos de los segmentos y directivas de IB. En función del tipo de directivas de IB (bloquear o permitir), el comportamiento de estos usuarios y grupos variará en Microsoft Teams, SharePoint, OneDrive y en la lista global de direcciones. Para los usuarios definidos en las directivas *allow* , los grupos y usuarios que no son del IB no serán visibles para los usuarios incluidos en los segmentos y directivas de IB. Para los usuarios definidos en las directivas de *bloque* , los grupos y los usuarios que no son de IB serán visibles para los usuarios incluidos en los segmentos y directivas de IB.
- **Compatibilidad con grupos**. Actualmente, solo los grupos modernos se admiten en IB y las listas de distribución o los grupos de seguridad se tratan como grupos que no son del IB.
- **Cuentas de usuario ocultas o deshabilitadas**. En el caso de las cuentas ocultas o deshabilitadas de la organización, el parámetro *HiddenFromAddressListEnabled* se establece automáticamente en *True* cuando las cuentas de los usuarios están ocultas o deshabilitadas. En las organizaciones habilitadas para IB, se impide que estas cuentas se comuniquen con todas las demás cuentas de usuario. En Microsoft Teams, todos los chats, incluidas estas cuentas, están bloqueados o los usuarios se quitan automáticamente de las conversaciones.

## <a name="configuration-overview"></a>Descripción general de la configuración

| **Pasos** | **Lo que implica** |
|:------|:----------------|
| **Paso 1**: [Asegúrese de que se cumplen los requisitos previos](#step-1-make-sure-prerequisites-are-met) | : compruebe que tiene las suscripciones y permisos necesarios. <br/>- Comprobar que el directorio incluye datos para segmentar usuarios<br/>- Habilitación [de la búsqueda por nombre para Microsoft Teams](/microsoftteams/teams-scoped-directory-search)<br/>- Asegurarse de que el registro de auditoría está activado<br/>- Asegurarse de que no se han aplicado directivas de libreta de direcciones de Exchange <br/>- Proporcionar consentimiento de administrador para Microsoft Teams (se incluyen los pasos) |
| **Paso 2**: [Segmentar usuarios de la organización](#step-2-segment-users-in-your-organization) | - Determinar qué directivas se necesitan<br/>- Crear una lista de segmentos que definir<br/>- Identificar qué atributos usar<br/>- Definir segmentos en términos de filtros de directiva |
| **Paso 3**: [Crear directivas de barreras de información](#step-3-create-ib-policies) | - Crear las directivas (aún no se aplican)<br/>- Elegir entre dos tipos (bloquear o permitir) |
| **Paso 4**: [Aplicación de directivas de barreras de información](#step-4-apply-ib-policies) | - Establecer directivas en estado activo<br/>- Ejecutar la aplicación de la directiva<br/>- Ver el estado de la directiva |
| **Paso 5**: [Configuración de barreras de información en SharePoint y OneDrive (opcional)](#step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive) | - Configuración de IB para SharePoint y OneDrive |
| **Paso 6**: [Modos de barreras de información (opcional)](#step-6-information-barriers-modes) | - Actualización de los modos de IB si procede |

## <a name="step-1-make-sure-prerequisites-are-met"></a>Paso 1: Asegúrese de que se cumplen los requisitos previos

Además de las suscripciones y permisos necesarios, asegúrese de que se cumplen los siguientes requisitos antes de configurar IB:

- **Datos del directorio**: asegúrese de que la estructura de su organización se refleja en los datos del directorio. Para realizar esta acción, asegúrese de que los atributos de la cuenta de usuario (como la pertenencia a grupos, el nombre del departamento, etc.) se rellenan correctamente en Azure Active Directory (o Exchange Online). Para obtener más información, consulte los siguientes recursos:
  - [Atributos para directivas de barreras de información](information-barriers-attributes.md)
  - [Adición o actualización de la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurar las propiedades de la cuenta de usuario con Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- **Búsqueda de directorios con ámbito**: antes de definir la primera directiva de IB de su organización, debe [habilitar la búsqueda de directorios con ámbito en Microsoft Teams](/MicrosoftTeams/teams-scoped-directory-search). Espere al menos 24 horas después de habilitar la búsqueda de directorios con ámbito antes de configurar o definir directivas de IB.

- **Comprobar que el registro de auditoría está habilitado**: para buscar el estado de una aplicación de directiva de IB, se debe activar el registro de auditoría. La auditoría está habilitada para organizaciones de Microsoft 365 de forma predeterminada. Algunas organizaciones pueden haber deshabilitado la auditoría por motivos específicos. Si la auditoría está deshabilitada para su organización, puede deberse a que otro administrador la ha desactivado. Se recomienda confirmar que es correcto volver a activar la auditoría al completar este paso. Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría](turn-audit-log-search-on-or-off.md).

- **Quitar directivas de libreta de direcciones Exchange Online existentes**: antes de definir y aplicar directivas de IB, debe quitar todas las directivas de libreta de direcciones Exchange Online existentes en su organización. Las directivas de IB se basan en directivas de libreta de direcciones y las directivas ABP existentes no son compatibles con los AAP creados por IB. Para quitar las directivas de libreta de direcciones existentes, consulte [Quitar una directiva de libreta de direcciones en Exchange Online](/exchange/address-books/address-book-policies/remove-an-address-book-policy). Para obtener más información sobre las directivas y Exchange Online de IB, consulte [Barreras de información y Exchange Online](information-barriers.md#information-barriers-and-exchange-online).

- **Administrar mediante PowerShell (opcional):** los segmentos y las directivas de IB se pueden definir y administrar en Office 365 Security & Compliance PowerShell. Aunque en este artículo se proporcionan varios ejemplos, deberá estar familiarizado con los cmdlets y parámetros de PowerShell si decide usar PowerShell para configurar y administrar segmentos y directivas de IB. También necesitará el módulo de PowerShell de Azure Active Directory si elige esta opción de configuración.
  - [Conectarse a Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell)
  - [Instalación de PowerShell de Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2)

- **Administración consentimiento para IB en Microsoft Teams**: cuando se aplican las directivas de IB, pueden quitar usuarios de cumplimiento no IB de grupos (por ejemplo, canales de Teams, que se basan en grupos). Esta configuración ayuda a garantizar que su organización siga siendo compatible con las directivas y las regulaciones. Use el procedimiento siguiente para permitir que las directivas de IB funcionen según lo esperado en Microsoft Teams.

   1. Requisito previo: [instalación de PowerShell de Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2).

   2. Ejecute los siguientes cmdlets de PowerShell:

      ```powershell
      Connect-AzureAD -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzureAD -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureADServicePrincipal -Filter "appid eq '$($appid)'"
      if ($sp -eq $null) { New-AzureADServicePrincipal -AppId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   3. Cuando se le pida, inicie sesión con su cuenta de profesional o educativa de Office 365.

   4. En el cuadro de diálogo **Permisos solicitados** , revise la información y elija **Aceptar**.

Cuando se cumplan todos los requisitos previos, continúe con el paso siguiente.

## <a name="step-2-segment-users-in-your-organization"></a>Paso 2: Segmentar usuarios de la organización

En este paso, determinará qué directivas de IB son necesarias, creará una lista de segmentos para definir y definirá los segmentos. La definición de segmentos no afecta a los usuarios, sino que simplemente establece la fase para que se definan y se apliquen las directivas de IB.

### <a name="determine-what-policies-are-needed"></a>Determinar qué directivas son necesarias

Teniendo en cuenta las necesidades de su organización, determine los grupos de la organización que necesitarán directivas de IB. Pregúntese lo siguiente:

- ¿Existen regulaciones internas, legales o del sector que requieran la restricción de la comunicación y la colaboración entre grupos y usuarios de su organización?
- ¿Hay algún grupo o usuario al que se le impida comunicarse con otro grupo de usuarios?
- ¿Hay algún grupo o usuario que tenga permiso para comunicarse solo con uno o dos otros grupos de usuarios?

Piense en las directivas que necesita como pertenecientes a uno de los dos tipos:

- Las directivas de *bloqueo* impiden que un grupo se comunique con otro grupo.
- *Permitir que* las directivas permitan que un grupo se comunique solo con grupos específicos.

Cuando tenga la lista inicial de grupos y directivas necesarios, continúe con la identificación de los segmentos que necesitará para las directivas de IB.

### <a name="identify-segments"></a>Identificar segmentos

Además de la lista inicial de directivas, haga una lista de segmentos para su organización. Los usuarios que se incluirán en las directivas de IB deben pertenecer a un segmento. Planee cuidadosamente los segmentos, ya que un usuario solo puede estar en un segmento. Cada segmento solo puede tener aplicada una directiva de IB.

> [!IMPORTANT]
> Un usuario solo puede estar en un segmento.

Determine qué atributos de los datos de directorio de la organización usará para definir segmentos. Puede usar *Department*, *MemberOf* o cualquiera de los atributos de IB admitidos. Asegúrese de que tiene valores en el atributo que seleccione para los usuarios. Para obtener más información, consulte los [atributos admitidos para IB](information-barriers-attributes.md).

> [!IMPORTANT]
> **Antes de continuar con la sección siguiente, asegúrese de que los datos de directorio tienen valores para los atributos que puede usar para definir segmentos**. Si los datos de directorio no tienen valores para los atributos que desea usar, las cuentas de usuario deben actualizarse para incluir esa información antes de continuar con la configuración de IB. Para obtener ayuda con esto, consulte los siguientes recursos:<br/>- [Configuración de las propiedades de la cuenta de usuario con Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Adición o actualización de la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-the-compliance-portal"></a>Definición de segmentos mediante el portal de cumplimiento

Para definir segmentos en el portal de cumplimiento, siga estos pasos:

1. Inicie sesión en el [portal de cumplimiento](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su organización.
2. En el portal de cumplimiento, seleccione **Segmentos de barreras** >  de información.
3. En la página **Segmentos** , seleccione **Nuevo segmento** para crear y configurar un nuevo segmento.
4. En la página **Nombre** , escriba un nombre para el segmento. No se puede cambiar el nombre de un segmento una vez creado.
5. Seleccione **Siguiente**.
6. En la página **Filtro de grupo de** usuarios, seleccione **Agregar** para configurar los atributos de grupo y usuario para el segmento. Elija un atributo para el segmento de la lista de atributos disponibles.
7. Para el atributo seleccionado, seleccione *Igual* o *No igual* y, a continuación, escriba el valor del atributo. Por ejemplo, si seleccionó *Department* como atributo e *Equals*, podría escribir *Marketing* como *departamento definido para* esta condición de segmento. Para agregar condiciones adicionales para un atributo, seleccione **Agregar condición**. Si necesita eliminar un atributo o una condición de atributo, seleccione el icono de eliminación para el atributo o la condición.
8. Agregue atributos adicionales según sea necesario en la página **Filtro de grupo** de usuarios y, a continuación, seleccione **Siguiente**.
9. En la página **Revisar la configuración** , revise la configuración que ha elegido para el segmento y las sugerencias o advertencias de las selecciones. Seleccione **Editar** para cambiar cualquiera de los atributos y condiciones del segmento o seleccione **Enviar** para crear el segmento.

    > [!IMPORTANT]
    > **Asegúrese de que los segmentos no se superpongan**. Cada usuario que se verá afectado por las directivas de IB debe pertenecer a un segmento (y solo a uno). Ningún usuario debe pertenecer a dos o más segmentos. Consulte [Ejemplo: Segmentos definidos por Contoso](#contosos-defined-segments) en este artículo para ver un escenario de ejemplo.

### <a name="define-segments-using-powershell"></a>Definición de segmentos mediante PowerShell

Para definir segmentos con PowerShell, complete los pasos siguientes:

1. Use el cmdlet **New-OrganizationSegment** con el parámetro **UserGroupFilter** que corresponde al [atributo](information-barriers-attributes.md) que desea usar.

    | Sintaxis | Ejemplo |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>En este ejemplo, un segmento denominado *RR. HH* . se define mediante *RR. HH*., un valor en el atributo *Department* . La parte **-eq** del cmdlet hace referencia a "equals". (Como alternativa, puede usar **-ne** para significar "no es igual". Consulte [Uso de "equals" y "not equals" en las definiciones de segmento).](#using-equals-and-not-equals-in-powershell-segment-definitions) |

    Después de ejecutar cada cmdlet, debería ver una lista de detalles sobre el nuevo segmento. Los detalles incluyen el tipo del segmento, quién lo creó o modificó por última vez, etc. 

2. Repita este proceso para cada segmento que desee definir.

    > [!IMPORTANT]
    > **Asegúrese de que los segmentos no se superpongan**. Cada usuario que se verá afectado por las directivas de IB debe pertenecer a un segmento (y solo a uno). Ningún usuario debe pertenecer a dos o más segmentos. Consulte [Ejemplo: Segmentos definidos por Contoso](#contosos-defined-segments) en este artículo para ver un escenario de ejemplo.

Después de definir los segmentos, vaya al [Paso 3: Crear directivas de IB](#step-3-create-ib-policies).

### <a name="using-equals-and-not-equals-in-powershell-segment-definitions"></a>Uso de "equals" y "not equals" en las definiciones de segmento de PowerShell

En el ejemplo siguiente, estamos configurando segmentos ib mediante PowerShell y definiendo un segmento como "Department equals HR".

| Ejemplo | Nota: |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Observe que en este ejemplo, la definición de segmento incluye un parámetro "equals" que se indica como **-eq**. |

También puede definir segmentos mediante un parámetro "not equals", denominado **-ne**, como se muestra en la tabla siguiente:

| Sintaxis | Ejemplo |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | En este ejemplo, definimos un segmento denominado *NotSales* que incluye a todos los usuarios que no están en *Ventas*. La parte **-ne** del cmdlet hace referencia a "no es igual". |

Además de definir segmentos con "equals" o "not equals", puede definir un segmento con los parámetros "equals" y "not equals". También puede definir filtros de grupo complejos mediante operadores *lógicos AND* y *OR* .

| Sintaxis | Ejemplo |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | En este ejemplo, definimos un segmento denominado *LocalFTE* que incluye los usuarios que se encuentran localmente y cuyas posiciones no aparecen como *Temporales*. |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| En este ejemplo, definimos un segmento denominado *Segment1* que incluye usuarios que son miembros de group1@contoso.com y no miembros de group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | En este ejemplo, definimos un segmento denominado *Segment2* que incluye usuarios que son miembros de group2@contoso.com y no miembros de group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| En este ejemplo, definimos un segmento denominado *Segment1and2* que incluye usuarios en group1@contoso.com y group2@contoso.com y no miembros de group3@contoso.com. |

> [!TIP]
> Si es posible, use definiciones de segmento que incluyan "-eq" o "-ne". Intente no definir definiciones de segmento complejas.

## <a name="step-3-create-ib-policies"></a>Paso 3: Creación de directivas de IB

Al crear las directivas de IB, determinará si necesita impedir las comunicaciones entre determinados segmentos o limitar las comunicaciones con determinados segmentos. Idealmente, usará el número mínimo de directivas de IB para asegurarse de que su organización cumple los requisitos internos, legales y del sector. Puede usar el portal de cumplimiento o PowerShell para crear y aplicar directivas de IB.

> [!TIP]
> Para la coherencia de la experiencia del usuario, se recomienda usar directivas de bloque para la mayoría de los escenarios si es posible.

Con la lista de segmentos de usuario y las directivas de IB que desea definir, seleccione un escenario y, a continuación, siga los pasos.

- [Escenario 1: Bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments)
- [Escenario 2: Permitir que un segmento solo se comunique con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Asegúrese de que, a medida que defina directivas, no asigne más de una directiva a un segmento**. Por ejemplo, si define una directiva para un segmento denominado *Ventas*, no defina una directiva adicional para el segmento *Ventas* .<br> Además, a medida que defina las directivas de IB, asegúrese de establecer esas directivas en estado inactivo hasta que esté listo para aplicarlas. La definición (o edición) de directivas no afecta a los usuarios hasta que esas directivas se establecen en estado activo y, a continuación, se aplican.

### <a name="scenario-1-block-communications-between-segments"></a>Escenario 1: Bloquear las comunicaciones entre segmentos

Si desea impedir que los segmentos se comuniquen entre sí, defina dos directivas: una para cada dirección. Cada directiva bloquea la comunicación solo en una dirección.

Por ejemplo, supongamos que desea bloquear las comunicaciones entre el segmento A y el segmento B. En este caso, definiría dos directivas:

- Una directiva que impide que el segmento A se comunique con el segmento B
- Una segunda directiva para evitar que el segmento B se comunique con el segmento A

#### <a name="create-policies-using-the-compliance-portal-for-scenario-1"></a>Creación de directivas mediante el portal de cumplimiento para el escenario 1

Para definir directivas en el portal de cumplimiento, siga estos pasos:

1. Inicie sesión en el [portal de cumplimiento](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su organización.
2. En el portal de cumplimiento, seleccione **Directivas de barreras** > **de** información.
3. En la página **Directivas** , seleccione **Crear directiva** para crear y configurar una nueva directiva de IB.
4. En la página **Nombre** , escriba un nombre para la directiva y, a continuación, seleccione **Siguiente**.
5. En la página **Segmento asignado** , seleccione **Elegir segmento**. Use el cuadro de búsqueda para buscar un segmento por nombre o desplazarse para seleccionar el segmento de la lista mostrada. Seleccione **Agregar** para agregar el segmento seleccionado a la directiva. Solo puede seleccionar un segmento.
6. Seleccione **Siguiente**.
7. En la página **Comunicación y colaboración** , seleccione el tipo de directiva en el campo **Comunicación y colaboración** . Las opciones de directiva son *Permitido* o *Bloqueado*. En este escenario de ejemplo, Se seleccionaría *Bloqueado* para la primera directiva.

    >[!IMPORTANT]
    >El estado Permitido y Bloqueado de los segmentos no se puede cambiar después de crear una directiva. Para cambiar el estado después de crear una directiva, debe eliminarla y crear una nueva.

8. Seleccione **Elegir segmento** para definir las acciones del segmento de destino. Puede asignar más de un segmento en este paso. Por ejemplo, si quisiera impedir que los usuarios de un segmento denominado *Ventas* se comunicaran con los usuarios de un segmento denominado *Investigación*, habría definido el segmento *Ventas* en el paso 5 y asignaría *Investigación* en la opción **Elegir segmento** en este paso.
9. Seleccione **Siguiente**.
10. En la página **Estado de** la directiva, cambie el estado de la directiva activa a **Activado**. Seleccione **Siguiente** para continuar.
11. En la página **Revisar la configuración** , revise la configuración que ha elegido para la directiva y las sugerencias o advertencias de las selecciones. Seleccione **Editar** para cambiar cualquiera de los segmentos y el estado de la directiva o seleccione **Enviar** para crear la directiva.

En este ejemplo, repetiría los pasos anteriores para crear una segunda directiva *de bloque* para impedir que los usuarios de un segmento denominado *Investigación* se comuniquen con los usuarios de un segmento denominado *Ventas*. Habría definido el segmento *De investigación* en el paso 5 y asignaría *Ventas* (o varios segmentos) en la opción **Elegir segmento** .

#### <a name="create-policies-using-powershell-for-scenario-1"></a>Creación de directivas mediante PowerShell para el escenario 1

Para definir directivas con PowerShell, complete los pasos siguientes:

1. Para definir la primera directiva de bloqueo, use el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsBlocked** .

    | Sintaxis | Ejemplo |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> En este ejemplo, definimos una directiva denominada *Sales-Research* para un segmento denominado *Sales*. Cuando está activo y aplicado, esta directiva impide que los usuarios de *Ventas* se comuniquen con los usuarios de un segmento denominado *Investigación*. |

2. Para definir el segundo segmento de bloqueo, use de nuevo el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsBlocked** , esta vez con los segmentos invertidos.

    | Ejemplo | Nota: |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | En este ejemplo, definimos una directiva denominada *Research-Sales* para evitar que *Research* se comunique con *Sales*. |

3. Continúe con una de las siguientes acciones:

   - (Si es necesario) [Definición de una directiva para permitir que un segmento se comunique solo con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Una vez definidas todas las directivas) [Aplicación de directivas de IB](#step-4-apply-ib-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Escenario 2: Permitir que un segmento solo se comunique con otro segmento

Si desea permitir que un segmento se comunique solo con otro segmento, defina solo una directiva para ese segmento. El segmento con el que se comunica no requiere una directiva direccional similar (porque pueden comunicarse y colaborar con todos de forma predeterminada).

#### <a name="create-a-policy-using-the-compliance-portal-for-scenario-2"></a>Creación de una directiva mediante el portal de cumplimiento para el escenario 2

Para definir directivas en el portal de cumplimiento, siga estos pasos:

1. Inicie sesión en el [portal de cumplimiento](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su organización.
2. En el portal de cumplimiento, seleccione **Directivas de barreras** > **de** información.
3. En la página **Directivas** , seleccione **Crear directiva** para crear y configurar una nueva directiva de IB.
4. En la página **Nombre** , escriba un nombre para la directiva y, a continuación, seleccione **Siguiente**.
5. En la página **Segmento asignado** , seleccione **Elegir segmento**. Use el cuadro de búsqueda para buscar un segmento por nombre o desplazarse para seleccionar el segmento de la lista mostrada. Seleccione **Agregar** para agregar el segmento seleccionado a la directiva. Solo puede seleccionar un segmento.
6. Seleccione **Siguiente**.
7. En la página **Comunicación y colaboración** , seleccione el tipo de directiva en el campo **Comunicación y colaboración** . Las opciones de directiva son *Permitido* o *Bloqueado*. En este escenario de ejemplo, Se seleccionaría *Permitido* para la directiva.

    >[!IMPORTANT]
    >El estado Permitido y Bloqueado de los segmentos no se puede cambiar después de crear una directiva. Para cambiar el estado después de crear una directiva, debe eliminarla y crear una nueva.

8. Seleccione **Elegir segmento** para definir las acciones del segmento de destino. Puede asignar más de un segmento en este paso. Por ejemplo, si quisiera permitir que los usuarios de un segmento denominado *Fabricación* se comunicaran con los usuarios de un segmento denominado *RR. HH*., habría definido el segmento *De fabricación* en el paso 5 y asignaría *RR. HH* . en la opción **Elegir segmento** de este paso.
9. Seleccione **Siguiente**.
10. En la página **Estado de** la directiva, cambie el estado de la directiva activa a **Activado**. Seleccione **Siguiente** para continuar.
11. En la página **Revisar la configuración** , revise la configuración que ha elegido para la directiva y las sugerencias o advertencias de las selecciones. Seleccione **Editar** para cambiar cualquiera de los segmentos y el estado de la directiva o seleccione **Enviar** para crear la directiva.

#### <a name="create-a-policy-using-powershell-for-scenario-2"></a>Creación de una directiva mediante PowerShell para el escenario 2

Para definir directivas con PowerShell, complete los pasos siguientes:

1. Para permitir que un segmento se comunique solo con otro segmento, use el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsAllowed** .

    | Sintaxis | Ejemplo |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> En este ejemplo, definimos una directiva denominada *Manufacturing-HR* para un segmento denominado *Fabricación*. Cuando está activo y aplicado, esta directiva permite a los usuarios de *Fabricación* comunicarse solo con los usuarios de un segmento denominado *RR. HH*. En este caso, *la fabricación* no puede comunicarse con los usuarios que no forman parte de *RR. HH*. |

    **Si es necesario, puede especificar varios segmentos con este cmdlet, como se muestra en el ejemplo siguiente.**

    | Sintaxis | Ejemplo |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> En este ejemplo, definimos una directiva que permite que el segmento *De investigación* se comunique solo con *RR. HH* . y *Fabricación*. |

    Repita este paso para cada directiva que quiera definir para permitir que segmentos específicos se comuniquen solo con otros segmentos específicos.

2. Continúe con una de las siguientes acciones:

   - (Si es necesario) [Definición de una directiva para bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments) 
   - (Una vez definidas todas las directivas) [Aplicación de directivas de IB](#step-4-apply-ib-policies)

## <a name="step-4-apply-ib-policies"></a>Paso 4: Aplicar directivas de IB

Las directivas de IB no están en vigor hasta que las establezca en estado activo y aplique las directivas.

### <a name="apply-policies-using-the-compliance-portal"></a>Aplicación de directivas mediante el portal de cumplimiento

Para aplicar directivas en el portal de cumplimiento, siga estos pasos:

1. Inicie sesión en el [portal de cumplimiento](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su organización.
2. En el portal de cumplimiento, seleccione **Aplicación de directiva de barreras** > **de** información.
3. En la página **aplicación Directivas** , seleccione **Aplicar todas las directivas** para aplicar todas las directivas de IB de su organización.

    >[!NOTE]
    >Espere 30 minutos para que el sistema empiece a aplicar las directivas. El sistema aplica las directivas usuario por usuario. El sistema procesa unas 5 000 cuentas de usuario por hora.

### <a name="apply-policies-using-powershell"></a>Aplicación de directivas mediante PowerShell

Para aplicar directivas mediante PowerShell, complete los pasos siguientes:

1. Use el cmdlet **Get-InformationBarrierPolicy** para ver una lista de las directivas que se han definido. Tenga en cuenta el estado y la identidad (GUID) de cada directiva.

    Sintaxis: `Get-InformationBarrierPolicy`

2. Para establecer una directiva en estado activo, use el cmdlet **Set-InformationBarrierPolicy** con un parámetro **Identity** y el parámetro **State** establecido en **Active**. 

    | Sintaxis | Ejemplo |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> En este ejemplo, establecemos una directiva ib que tiene el GUID *43c37853-ea10-4b90-a23d-ab8c93772471* en estado activo. |

    Repita este paso según corresponda para cada directiva.

3. Cuando haya terminado de establecer las directivas de IB en estado activo, use el cmdlet **Start-InformationBarrierPoliciesApplication** en PowerShell de seguridad & cumplimiento.

    Sintaxis: `Start-InformationBarrierPoliciesApplication`

    Después de ejecutar `Start-InformationBarrierPoliciesApplication`, debe dejar 30 minutos para que el sistema empiece a aplicar las directivas. El sistema aplica las directivas usuario por usuario. El sistema procesa unas 5 000 cuentas de usuario por hora.

### <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Visualización del estado de cuentas de usuario, segmentos, directivas o aplicación de directiva

Con PowerShell, puede ver el estado de las cuentas de usuario, los segmentos, las directivas y la aplicación de directivas, como se muestra en la tabla siguiente.

| Para ver esta información | Realizar esta acción |
|:---------------|:----------|
| Cuentas de usuario | Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros identity. <p> Sintaxis: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Puede usar cualquier valor que identifique de forma única a cada usuario, como nombre, alias, nombre distintivo, nombre de dominio canónico, dirección de correo electrónico o GUID. <p> Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> En este ejemplo, nos referimos a dos cuentas de usuario en Office 365: *meganb* para *Megan* y *alexw* para *Alex*. <p> (También puede usar este cmdlet para un único usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`) <p> Este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de IB que se aplican.|
| Segmentos | Use el cmdlet **Get-OrganizationSegment** .<p> Sintaxis: `Get-OrganizationSegment` <p> Este cmdlet mostrará una lista de todos los segmentos definidos para su organización. |
| Directivas de IB | Use el cmdlet **Get-InformationBarrierPolicy** . <p> Sintaxis: `Get-InformationBarrierPolicy` <p> Este cmdlet mostrará una lista de las directivas de IB que se definieron y su estado. |
| La aplicación de directiva de IB más reciente | Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** . <p> Sintaxis: `Get-InformationBarrierPoliciesApplicationStatus`<p> Este cmdlet mostrará información sobre si la aplicación de directiva se completó, produjo un error o está en curso. |
| Todas las aplicaciones de directivas de IB|Use `Get-InformationBarrierPoliciesApplicationStatus -All`<p> Este cmdlet mostrará información sobre si la aplicación de directiva se completó, produjo un error o está en curso.|

### <a name="what-if-i-need-to-remove-or-change-policies"></a>¿Qué ocurre si necesito quitar o cambiar directivas?

Los recursos están disponibles para ayudarle a administrar las directivas de IB.

- Para editar, detener o quitar directivas de IB, consulte [Administración de directivas de barreras de información](information-barriers-edit-segments-policies.md).
- Si algo va mal con IB, consulte [Solución de problemas de barreras de información](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting).

## <a name="step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive"></a>Paso 5: Configuración de barreras de información en SharePoint y OneDrive

Si va a configurar IB para SharePoint y OneDrive, deberá habilitar IB en estos servicios. También tendrá que habilitar IB en estos servicios si va a configurar IB para Microsoft Teams. Cuando se crea un equipo en el equipo de Microsoft Teams, se crea automáticamente un sitio de SharePoint y se asocia a Microsoft Teams para la experiencia de archivos. Las directivas de IB no se respetan en este nuevo sitio y archivos de SharePoint de forma predeterminada.

Para habilitar IB en SharePoint y OneDrive, siga las instrucciones y los pasos del artículo [Uso de barreras de información con SharePoint](/sharepoint/information-barriers) .

## <a name="step-6-information-barriers-modes"></a>Paso 6: Modos de barreras de información

Los modos pueden ayudar a reforzar el acceso, el uso compartido y la pertenencia a un recurso de Microsoft 365 en función del modo IB del recurso. Los modos se admiten en Grupos de Microsoft 365, Microsoft Teams, OneDrive y sitios de SharePoint y se habilitan automáticamente en la configuración de IB nueva o existente.

Los siguientes modos ib son compatibles con los recursos de Microsoft 365:

| **Mode** | **Descripción** | **Ejemplo** |
|:-----|:------------|:--------|
| **Abrir** | No hay directivas o segmentos de IB asociados al recurso de Microsoft 365. Se puede invitar a cualquier persona a ser miembro del recurso. | Un sitio de equipo creado para un evento de picnic para su organización. |
| **Moderado por el propietario (versión preliminar)** | La directiva ib del recurso de Microsoft 365 se determina a partir de la directiva ib del propietario del recurso. Los propietarios de recursos pueden invitar a cualquier usuario al recurso en función de sus directivas de IB. Este modo es útil cuando la empresa quiere permitir la colaboración entre usuarios de segmentos incompatibles moderados por el propietario. Solo el propietario del recurso puede agregar nuevos miembros según su directiva de IB. | El vicepresidente de RR. HH. quiere colaborar con los VPs de Ventas e Investigación. Un nuevo sitio de SharePoint que se establece con el modo IB *Propietario moderado* para agregar usuarios de segmento de ventas e investigación al mismo sitio. Es responsabilidad del propietario asegurarse de que se agregan miembros adecuados al recurso. |
| **Implícita** | La directiva de IB o los segmentos del recurso de Microsoft 365 se heredan de la directiva ib de los miembros del recurso. El propietario puede agregar miembros siempre que sean compatibles con los miembros existentes del recurso. Este modo es el modo IB predeterminado para Microsoft Teams. | El usuario del segmento Ventas crea un equipo de Microsoft Teams para colaborar con otros segmentos compatibles de la organización. |
| **Explicit** | La directiva ib del recurso de Microsoft 365 se realiza según los segmentos asociados al recurso. El propietario del recurso o el administrador de SharePoint tiene la capacidad de administrar los segmentos del recurso. | Un sitio creado solo para que los miembros del segmento Ventas colaboren asociando el segmento Ventas con el sitio. |
| **Mixto (versión preliminar)** | Solo se aplica a OneDrive. La directiva ib de OneDrive se realiza según los segmentos asociados a OneDrive. El propietario del recurso o el administrador de OneDrive tiene la capacidad de administrar los segmentos del recurso. | Un OneDrive creado para que los miembros del segmento Sales colaboren puede compartirse con usuarios noegmentados. |

Para obtener más información sobre los modos de IB y cómo se configuran entre servicios, consulte los artículos siguientes:

- [Modos de barreras de información y Microsoft Teams](/microsoftteams/information-barriers-in-teams)
- [Modos de barreras de información y OneDrive](/onedrive/information-barriers)
- [Modos de barreras de información y SharePoint](/sharepoint/information-barriers)

## <a name="example-scenario-contosos-departments-segments-and-policies"></a>Escenario de ejemplo: departamentos, segmentos y directivas de Contoso

Para ver cómo una organización podría abordar la definición de segmentos y directivas, tenga en cuenta el siguiente escenario de ejemplo.

### <a name="contosos-departments-and-plan"></a>Planes y departamentos de Contoso

Contoso tiene cinco departamentos: *RR. HH*., *Ventas*, *Marketing*, *Investigación* y *Fabricación*. Para seguir siendo conformes con las regulaciones del sector, se supone que los usuarios de algunos departamentos no deben comunicarse con otros departamentos, como se muestra en la tabla siguiente:

| **Segmento** | **Puede comunicarse con** | **No se puede comunicar con** |
|:------------|:-------------------------|:---------------------------|
| HR | Todos | (sin restricciones) |
| Ventas | RR. HH., Marketing, Fabricación | Referencia |
| Marketing | Todos | (sin restricciones) |
| Referencia | RR. HH., Marketing, Fabricación | Ventas |
| Industria | RR. HH., Marketing | Cualquier persona que no sea RR. HH. o Marketing |

Para esta estructura, el plan de Contoso incluye tres directivas de IB:

1. Una directiva de IB diseñada para impedir que las ventas se comuniquen con Research
2. Otra directiva de IB para evitar que Research se comunique con Sales.
3. Una directiva de IB diseñada para permitir que la fabricación se comunique solo con RR. HH. y marketing.

En este escenario, no es necesario definir directivas de IB para *RR. HH* . o *Marketing*.

### <a name="contosos-defined-segments"></a>Segmentos definidos de Contoso

Contoso usará el atributo Department en Azure Active Directory para definir segmentos, como se indica a continuación:

| Departamento | Definición de segmento |
|:-------------|:---------------------|
| RR. HH. | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Ventas | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Referencia | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Industria | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Con los segmentos definidos, Contoso continúa definiendo las directivas de IB.

### <a name="contosos-ib-policies"></a>Directivas de IB de Contoso

Contoso define tres directivas de IB, como se describe en la tabla siguiente:

| Policy | Definición de directiva |
|:---------|:--------------------|
| **Directiva 1: impedir que Ventas se comunique con Investigación** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> En este ejemplo, la directiva de IB se denomina *Sales-Research*. Cuando esta directiva esté activa y se aplique, le ayudará a evitar que los usuarios que se encuentran en el segmento Ventas se comuniquen con usuarios en el segmento Investigación. Esta directiva es una directiva unidireccional; no impedirá que Research se comunique con Sales. Para eso, es necesaria la directiva 2. |
| **Directiva 2: impedir que Investigación se comunique con Ventas** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> En este ejemplo, la directiva de IB se denomina *Research-Sales*. Cuando esta directiva esté activa y se aplique, le ayudará a evitar que los usuarios que se encuentran en el segmento Investigación se comuniquen con usuarios en el segmento Ventas. |
| **Directiva 3: Permitir que la fabricación se comunique solo con RR. HH. y marketing** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> En este caso, la directiva de IB se denomina *Manufacturing-HRMarketing*. Cuando esta directiva está activa y se aplica, Industria solo puede comunicarse con RR. HH. y Marketing. RR. HH. y Marketing no están restringidos a comunicarse con otros segmentos. |

Con los segmentos y las directivas definidos, Contoso aplica las directivas mediante la ejecución del cmdlet **Start-InformationBarrierPoliciesApplication** .

Cuando finaliza el cmdlet, Contoso cumple los requisitos del sector.

## <a name="resources"></a>Recursos

- [Más información acerca de las barreras de información](information-barriers.md)
- [Más información sobre las barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Más información sobre las barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Más información sobre las barreras de información en OneDrive](/onedrive/information-barriers)
