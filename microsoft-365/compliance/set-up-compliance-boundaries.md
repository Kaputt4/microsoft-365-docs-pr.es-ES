---
title: Configurar límites de cumplimiento para investigaciones de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Obtenga información sobre cómo usar límites de cumplimiento para crear límites lógicos que controlen las ubicaciones de contenido de usuario que un administrador de exhibición de documentos electrónicos puede buscar en Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fe023391823abbde2cb289926863bbcbb98dfb2
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61934518"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Configurar límites de cumplimiento para investigaciones de exhibición de documentos electrónicos

Las instrucciones de este artículo se pueden aplicar al usar core eDiscovery o Advanced eDiscovery para administrar investigaciones.

Los límites de cumplimiento crean límites lógicos dentro de una organización que controlan las ubicaciones de contenido de usuario (como buzones, cuentas de OneDrive y sitios de SharePoint) en las que los administradores de eDiscovery pueden buscar. Además, los límites de cumplimiento controlan quién puede acceder a los casos de exhibición de documentos electrónicos usados para administrar las investigaciones legales, de recursos humanos u otras investigaciones de su organización. La necesidad de límites de cumplimiento suele ser necesaria para las corporaciones multinacionales que tienen que respetar los reglamentos y los miembros de la directiva geográfica, así como para los gobiernos, que a menudo se dividen en diferentes organismos. En Microsoft 365, los límites de cumplimiento le ayudan a cumplir estos requisitos al realizar búsquedas de contenido y administrar investigaciones con casos de exhibición de documentos electrónicos.
  
Usamos el ejemplo de la siguiente ilustración para explicar cómo funcionan los límites de cumplimiento.
  
![Los límites de cumplimiento constan de filtros de permisos de búsqueda que controlan el acceso a agencias y grupos de roles de administrador que controlan el acceso a los casos de eDiscovery.](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
En este ejemplo, Contoso LTD es una organización formada por dos subsidiarias, Fourth Coffee y Coho Winery. La empresa requiere que los administradores e investigadores de exhibición de documentos electrónicos solo puedan buscar en los buzones de correo Exchange, las OneDrive y los SharePoint de su agencia. Además, los administradores e investigadores de exhibición de documentos electrónicos solo pueden ver casos de exhibición de documentos electrónicos en su agencia y solo pueden acceder a los casos de los que son miembros. Además, en este escenario, los investigadores no pueden poner ubicaciones de contenido en espera ni exportar contenido de un caso. Este es el modo en que los límites de cumplimiento cumplen estos requisitos.
  
- La funcionalidad de filtrado de permisos de búsqueda para eDiscovery controla las ubicaciones de contenido en las que los administradores e investigadores de exhibición de documentos electrónicos pueden buscar. Esto significa que los gerentes e investigadores de eDiscovery en la agencia Fourth Coffee solo pueden buscar ubicaciones de contenido en la subsidiaria Fourth Coffee. La misma restricción se aplica a la subsidiaria Coho Winery.

- [Los grupos de](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) roles proporcionan las siguientes funciones para los límites de cumplimiento:

  - Controle quién puede ver los casos de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365. Esto quiere decir que los administradores y gestores de eDiscovery solo pueden ver los casos de eDiscovery en su organismo.

  - Controle quién puede asignar miembros a un caso de exhibición de documentos electrónicos. Esto significa que los administradores y administradores de eDiscovery solo pueden asignar miembros a los casos de los que ellos mismos sean miembros.

  - Controle las tareas relacionadas con la exhibición de documentos electrónicos que los miembros pueden realizar agregando o quitando roles que asignan permisos específicos.

- Cuando se aplica un filtro de permisos de búsqueda a un grupo de roles, los miembros del grupo de roles pueden realizar las siguientes acciones relacionadas con la búsqueda siempre que los permisos para realizar una acción se asignen al grupo de roles:

  - Buscar contenido

  - Vista previa de los resultados de búsqueda

  - Exportar resultados de búsqueda

  - Purgar elementos devueltos por una búsqueda

Este es el proceso para configurar límites de cumplimiento:
  
[Paso 1: Identificar un atributo de usuario para definir las agencias](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Paso 2: Crear un grupo de roles para cada agencia](#step-2-create-a-role-group-for-each-agency)

[Paso 3: Crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Paso 4: Crear un caso de exhibición de documentos electrónicos para investigaciones dentro de la agencia](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Antes de configurar los límites de cumplimiento

- A los usuarios se les debe asignar una Exchange Online licencia. Para comprobarlo, use el cmdlet [Get-User](/powershell/module/exchange/get-user) en Exchange Online PowerShell.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Paso 1: Identificar un atributo de usuario para definir las agencias

El primer paso es elegir un atributo que se usará para definir las agencias. Este atributo se usa para crear el filtro de permisos de búsqueda que limita a un administrador de exhibición de documentos electrónicos para buscar solo las ubicaciones de contenido de los usuarios a los que se asigna un valor específico para este atributo. Por ejemplo, supongamos que Contoso decide usar el **atributo Department.** El valor de este atributo para los usuarios de la subsidiaria Fourth Coffee sería y el valor para los usuarios de la subsidiaria  `FourthCoffee`  Coho Winery sería `CohoWinery` . En el paso 3, se usa este  `attribute:value`  par (por ejemplo, *Department:FourthCoffee*) para limitar las ubicaciones de contenido de usuario en las que los administradores de exhibición de documentos electrónicos pueden buscar. 
  
Estos son algunos ejemplos de atributos de usuario que puede usar para los límites de cumplimiento:
  
- Company

- CustomAttribute1 - CustomAttribute15

- Departamento

- Oficina

- CountryOrRegion (código de país de dos letras)

Para obtener una lista completa, vea la lista completa de filtros de [buzones admitidos.](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)

## <a name="step-2-create-a-role-group-for-each-agency"></a>Paso 2: Crear un grupo de roles para cada agencia

El siguiente paso es crear los grupos de roles en el Centro de cumplimiento de Microsoft 365 que se alinearán con las agencias. Le recomendamos que cree un grupo de funciones copiando el grupo de administradores de exhibición de documentos electrónicos integrado, agregando los miembros adecuados y eliminando las funciones que pueden no ser aplicables a sus necesidades. Para obtener más información acerca de los roles relacionados con la exhibición de documentos electrónicos, vea [Asignar permisos de exhibición de documentos electrónicos.](assign-ediscovery-permissions.md)
  
Para crear los grupos de roles, vaya a la página Permisos del Centro de cumplimiento de Microsoft 365 y cree un grupo de roles para cada equipo de cada agencia que usará límites de cumplimiento y **casos** de exhibición de documentos electrónicos para administrar investigaciones.
  
Con el escenario de límites de cumplimiento de Contoso, se deben crear cuatro grupos de roles y agregar los miembros adecuados a cada uno.
  
- Administradores de eDiscovery de Fourth Coffee

- Investigadores de Fourth Coffee

- Administradores de eDiscovery de Coho Winery

- Investigadores de Coho Winery
  
Para cumplir los requisitos del escenario de límites  de cumplimiento de Contoso, también quitaría los **roles** de retención y exportación de los grupos de roles de investigadores para impedir que los investigadores coloquen retenciones en ubicaciones de contenido y exporten contenido de un caso.

> [!IMPORTANT]
> Si se agrega o quita un rol de un grupo de roles que ha agregado como miembro de un caso, el grupo de roles se quitará automáticamente como miembro del caso (o en cualquier caso el grupo de roles es miembro de). El motivo es proteger la organización de proporcionar permisos adicionales a los miembros de un caso de forma involuntaria. Del mismo modo, si se elimina un grupo de roles, se quitará de todos los casos de los que era miembro.

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Paso 3: Crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento

Después de crear grupos de roles para cada agencia, el siguiente paso es crear los filtros de permisos de búsqueda que asocian cada grupo de roles a su agencia específica y definen el propio límite de cumplimiento. Debe crear un filtro de permisos de búsqueda para cada agencia. Para obtener más información acerca de la creación de filtros de permisos de seguridad, vea [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).
  
Esta es la sintaxis que se usa para crear un filtro de permisos de búsqueda usado para los límites de cumplimiento para el escenario de este artículo.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "SiteContent_Path -like '<SharePointURL>' -or SiteContent_Path -like '<OneDriveURL>'"
```

Esta es una descripción de cada parámetro del comando:
  
- `FilterName`: especifica el nombre del filtro. Use un nombre que describa o identifique la agencia en la que se usa el filtro.

- `Users`: especifica los usuarios o grupos que obtienen este filtro aplicado a las acciones de búsqueda que realizan. Para los límites de cumplimiento, este parámetro especifica los grupos de roles (que creó en el paso 3) en la agencia para la que está creando el filtro. Tenga en cuenta que se trata de un parámetro de varios valores, por lo que puede incluir uno o varios grupos de roles, separados por comas.

- `Filters`: especifica los criterios de búsqueda para el filtro. Para los límites de cumplimiento, defina los filtros siguientes. Cada una se aplica a diferentes ubicaciones de contenido.

  - `Mailbox`: especifica los buzones o OneDrive que pueden buscar los grupos de roles definidos en `Users` el parámetro. Este filtro permite a los miembros del grupo de roles buscar solo los buzones o OneDrive cuentas en una agencia específica; por ejemplo, `"Mailbox_Department -eq 'FourthCoffee'"` .

  - `SiteContent`: este filtro incluye dos filtros independientes. El primero especifica los SharePoint de la agencia que pueden buscar los grupos de roles `SiteContent_Path` definidos en `Users` el parámetro. Por ejemplo, `SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee'`. El segundo filtro (conectado al primer filtro por el operador) especifica el dominio OneDrive de la agencia (también denominado `SiteContent_Path` `SiteContent_Path` dominio `or` *MySite).* Por ejemplo, `SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'`. También puede usar el `Site_Path` filtro en lugar del `SiteContent` filtro. Los filtros y son intercambiables y no afectan a los filtros de permisos de búsqueda que se `Site` `SiteContent` describen en este artículo.

    > [!IMPORTANT]
    > ¿Por qué se incluye el filtro OneDrive en el filtro de permisos `SiteContent` de búsqueda anterior? Aunque el filtro se aplica tanto a buzones como a cuentas de OneDrive, la inclusión del filtro de SharePoint excluiría OneDrive cuentas si no incluyera también el filtro `Mailbox`  `Site` OneDrive. Si el filtro de permisos de búsqueda no incluye un filtro de SharePoint, no tendría que incluir un filtro de OneDrive independiente porque el filtro buzón incluiría cuentas OneDrive en el ámbito del límite de cumplimiento. En otras palabras, un filtro de permisos de búsqueda con solo el filtro incluiría `Mailbox` tanto buzones como cuentas OneDrive búsqueda.

Estos son algunos ejemplos de los dos filtros de permisos de búsqueda que se crearían para admitir el escenario de límites de cumplimiento de Contoso. Estos dos ejemplos incluyen una lista de filtros separados por comas, en la que el buzón y los filtros de sitio se incluyen en el mismo filtro de permisos de búsqueda y se separan con una coma.
  
### <a name="fourth-coffee"></a>Cuarto café

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

> [!NOTE]
> La sintaxis de `Filters` los parámetros de los ejemplos anteriores incluye una lista de *filtros*. Una lista de filtros es un filtro que incluye un filtro de buzón de correo y un filtro de ruta de acceso de sitio separados por una coma. En el ejemplo anterior, observe que una coma separa `Mailbox` y `SiteContent` filtra: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "SiteContent_Path -like '<SharePointURL>' -or SiteContent_Path -like '<OneDriveURL>'"` . Cuando este filtro se procesa durante la ejecución de una búsqueda de exhibición de documentos electrónicos, se crean dos filtros de permisos de búsqueda a partir de la lista de filtros: un filtro de buzones y un filtro SharePoint/OneDrive búsqueda. Una alternativa al uso de una lista de filtros sería crear dos filtros de permisos de búsqueda independientes para cada agencia: un filtro de permisos de búsqueda para el atributo de buzón y un filtro para los atributos SharePoint y OneDrive sitio. En cualquier caso, los resultados serán los mismos. El uso de una lista de filtros o la creación de filtros de permisos de búsqueda independientes es una cuestión de preferencia.

### <a name="how-do-the-search-permissions-filters-work-in-this-scenario"></a>¿Cómo funcionan los filtros de permisos de búsqueda en este escenario?

Este es el modo en que se aplican los filtros de permisos de búsqueda para cada agencia en este escenario.

1. El filtro se aplica primero para definir las ubicaciones de contenido en las que los administradores de `Mailbox` exhibición de documentos electrónicos pueden buscar. En este caso, los administradores de exhibición de documentos electrónicos de Coho Winery solo pueden buscar en los buzones y en las cuentas OneDrive de los usuarios cuya propiedad *department* mailbox tiene un valor de **FourthCoffee**; Los administradores de exhibición de documentos electrónicos de Coho Winery solo pueden buscar en los buzones y OneDrive cuentas de usuarios cuya propiedad *de* buzón de departamento tiene un valor de **CohoWinery**. El filtro es un filtro de ubicación de contenido, ya que especifica las ubicaciones de contenido que los administradores de `Mailbox` exhibición de documentos electrónicos pueden buscar.  En ambos filtros, los administradores de exhibición de documentos electrónicos solo pueden buscar ubicaciones de contenido con un valor de propiedad de buzón específico.

2. Una vez definidas las ubicaciones de contenido que se pueden buscar, la siguiente parte del filtro define el contenido que los administradores de exhibición de documentos electrónicos pueden buscar. El primer filtro permite a los administradores de exhibición de documentos electrónicos de cuarto café solo buscar documentos que tengan una propiedad de ruta de acceso de sitio `SiteContent` que contenga (o comience por) `https://contoso.sharepoint.com/sites/FourthCoffee` ; Los administradores de exhibición de documentos electrónicos de Coho Winery solo pueden buscar documentos que tengan una propiedad de ruta de acceso de sitio que contenga (o comience por) `https://contoso.sharepoint.com/sites/CohoWinery` . Por lo tanto, los dos `SiteContent` filtros son filtros *de* contenido porque definen el contenido que se puede buscar. En ambos filtros, los administradores de exhibición de documentos electrónicos solo pueden buscar documentos con un valor de propiedad de documento específico. Todos SharePoint filtros relacionados con el contenido son filtros de contenido porque las propiedades del sitio que se pueden buscar se marcan en todos los documentos. Para obtener más información, vea [Configure permissions filtering for eDiscovery](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).

   > [!NOTE]
   > Aunque el escenario de este artículo no los usa, también puede usar filtros de contenido de buzón para especificar el contenido que los administradores de exhibición de documentos electrónicos pueden buscar. La sintaxis de los filtros de contenido del buzón es `"MailboxContent_<property> -<comparison operator> '<value>'"` . Puede crear filtros de contenido basados en intervalos de fechas, destinatarios y dominios o en cualquier propiedad de correo electrónico que se pueda buscar. Por ejemplo, este filtro permitiría a los administradores de exhibición de documentos electrónicos buscar solo elementos de correo enviados o recibidos por los usuarios del contoso.com: `"MailboxContent_Participants -like 'contoso.com'"` . Para obtener más información acerca de los filtros de contenido de buzones de correo, vea [Configure search permissions filtering](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).

3. El filtro de permisos de búsqueda se une a la consulta de búsqueda mediante el **operador booleano AND.** Esto significa que cuando un administrador de exhibición de documentos electrónicos en una de las agencias ejecuta una búsqueda de exhibición de documentos electrónicos, los elementos devueltos por la búsqueda deben coincidir con la consulta de búsqueda y las condiciones definidas en el filtro de permisos de búsqueda.

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>Paso 4: Crear un caso de exhibición de documentos electrónicos para investigaciones dentro de la agencia

El paso final es crear un caso de exhibición de documentos electrónicos principal o un caso Advanced eDiscovery en el Centro de cumplimiento de Microsoft 365 y, a continuación, agregar el grupo de roles que creó en el paso 2 como miembro del caso. Esto da como resultado dos características importantes del uso de límites de cumplimiento:
  
- Solo los miembros del grupo de roles agregados al caso podrán ver y acceder al caso en el Centro de cumplimiento de Microsoft 365. Por ejemplo, si el grupo de roles Fourth Coffee Investigators es el único miembro de un caso, los miembros del grupo de roles Fourth Coffee eDiscovery Managers (o miembros de cualquier otro grupo de roles) no podrán ver ni acceder al caso.

- Cuando un miembro del grupo de roles asignado a un caso ejecuta una búsqueda asociada al caso, solo podrá buscar en las ubicaciones de contenido dentro de su agencia (que se define mediante el filtro de permisos de búsqueda que creó en el paso 3).

Para crear un caso y asignar miembros:

1. Vaya a la **página Core eDiscovery** o **Advanced eDiscovery** en el Centro de cumplimiento de Microsoft 365 y cree un caso.

2. En la lista de casos, haga clic en el nombre del caso que creó.

3. Agregue grupos de roles como miembros al caso. Para obtener instrucciones, consulte uno de los siguientes artículos:

   - [Agregar miembros a un caso de exhibición de documentos electrónicos principal](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [Agregar miembros a un Advanced eDiscovery caso](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> Al agregar un grupo de roles a un caso, solo puede agregar los grupos de roles de los que es miembro.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Búsqueda y exportación de contenido en entornos multigeómicos

Los filtros de permisos de búsqueda también permiten controlar dónde se enruta el contenido para su exportación y qué centro de datos se puede buscar al buscar ubicaciones de contenido en un [SharePoint Multi-Geo de búsqueda.](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)
  
- **Exportar resultados de búsqueda:** Puede exportar los resultados de la búsqueda Exchange buzones de correo, SharePoint y cuentas OneDrive de un centro de datos específico. Esto significa que puede especificar la ubicación del centro de datos desde la que se exportarán los resultados de la búsqueda.

    Use el *parámetro Region* para los cmdlets **New-ComplianceSecurityFilter** o **Set-ComplianceSecurityFilter** para crear o cambiar el centro de datos por el que se enruta la exportación.
  
    |**Valor del parámetro**|**Ubicación del centro de datos**|
    |:-----|:-----|
    |NAM  <br/> |Norteamérica (los centros de datos están en estados Unidos)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacífico  <br/> |
    |CAN <br/> |Canadá|
    |||

- **Enrutar búsquedas de contenido:** Puede enrutar las búsquedas de contenido de SharePoint sitios y OneDrive cuentas a un centro de datos satélite. Esto significa que puede especificar la ubicación del centro de datos donde se ejecutarán las búsquedas.

    Use uno de los siguientes valores para el parámetro *Region* para controlar la ubicación del centro de datos en la que se ejecutarán las búsquedas al buscar SharePoint sitios y OneDrive cuentas.
  
    |**Valor del parámetro**|**Ubicaciones de enrutamiento de centros de datos para SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |EE. UU.  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacífico  <br/> |
    |CAN  <br/> |EE. UU.  <br/> |
    |AUS  <br/> |Asia Pacífico  <br/> |
    |KOR  <br/> |Centro de datos predeterminado de la organización  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Asia Pacífico  <br/> |
    |IND  <br/> |Asia Pacífico  <br/> |
    |LAM  <br/> |EE. UU.  <br/> |
    |NOR  <br/> |Europa |
    |BRA  <br/> |Centros de datos de Norteamérica |
    |||

   Si no especifica el parámetro *Region* para un filtro de permisos de búsqueda, se buscará la región principal SharePoint la organización. Los resultados de la búsqueda se exportan al centro de datos más cercano.

   Para simplificar el concepto, el *parámetro Region* controla el centro de datos que se usa para buscar contenido en SharePoint y OneDrive. Esto no se aplica a la búsqueda de contenido en Exchange porque Exchange búsquedas de contenido no están vinculadas por la ubicación geográfica de los centros de datos. Además, el mismo *valor de parámetro Region* también puede dictar el centro de datos por el que se enrutan las exportaciones. Esto suele ser necesario para controlar el movimiento de datos a través de los tableros geográficos.

> [!NOTE]
> Si usa Advanced eDiscovery, el parámetro *Region* no controla la región desde la que se exportan los datos. Los datos se exportan desde la ubicación central de la organización. Además, la búsqueda de contenido en SharePoint y OneDrive no está enlazada por la ubicación geográfica de los centros de datos. Se buscan todos los centros de datos. Para obtener más información sobre Advanced eDiscovery, vea [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).

Estos son ejemplos del uso del *parámetro Region* al crear filtros de permisos de búsqueda para los límites de cumplimiento. Esto supone que la subsidiaria Fourth Coffee se encuentra en Norteamérica y que Coho Winery está en Europa.
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'" -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'" -Region EUR
```

Tenga en cuenta lo siguiente al buscar y exportar contenido en entornos multigeómicos.
  
- El parámetro *Region* no controla las búsquedas de los buzones de Exchange. Todos los centros de datos se buscarán al buscar en buzones de correo. Para limitar el ámbito en el que se Exchange los buzones de correo, use el parámetro *Filters* al crear o cambiar un filtro de permisos de búsqueda.

- Si es necesario que un administrador de exhibición de documentos electrónicos busque en varias regiones de SharePoint, debe crear una cuenta de usuario diferente para que ese administrador de exhibición de documentos electrónicos use en el filtro de permisos de búsqueda para especificar la región donde se encuentran los sitios de SharePoint o las cuentas OneDrive. Para obtener más información acerca de la configuración, vea la sección "Buscar contenido en un entorno SharePoint Multi-Geo" en [Búsqueda de contenido](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment).

- Al buscar contenido en SharePoint y OneDrive, el parámetro *Region* dirige las búsquedas a la ubicación principal o satélite donde el administrador de exhibición de documentos electrónicos llevará a cabo investigaciones de exhibición de documentos electrónicos. Si un administrador de exhibición de documentos electrónicos busca SharePoint y OneDrive fuera de la región especificada en el filtro de permisos de búsqueda, no se devuelven resultados de búsqueda.

- Al exportar resultados de búsqueda desde eDiscovery principal, el contenido de todas las ubicaciones de contenido (incluidos Exchange, Skype Empresarial, SharePoint, OneDrive y otros servicios que puede buscar mediante la herramienta búsqueda de contenido) se cargan en el Azure Storage  ubicación en el centro de datos especificado por el *parámetro Region.* Esto ayuda a las organizaciones a mantenerse dentro del cumplimiento al no permitir que el contenido se exporte a través de bordes controlados. Si no se especifica ninguna región en el filtro de permisos de búsqueda, el contenido se carga en el centro de datos principal de la organización.

  Al exportar contenido desde Advanced eDiscovery, no se puede controlar dónde se carga el contenido mediante el *parámetro Region.* El contenido se carga en una Azure Storage en un centro de datos de la ubicación central de la organización. Para obtener una lista de ubicaciones geográficas basadas en la ubicación central, vea Microsoft 365 configuración de exhibición de documentos [electrónicos multigeós.](../enterprise/multi-geo-ediscovery-configuration.md)

- Puede editar un filtro de permisos de búsqueda existente para agregar o cambiar la región ejecutando el siguiente comando:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Uso de límites de cumplimiento para SharePoint de concentradores

[SharePoint los sitios centrales](/sharepoint/dev/features/hub-site/hub-site-overview) suelen alinearse con los mismos límites geográficos o de agencia que los límites de cumplimiento de eDiscovery. Esto significa que puede usar la propiedad id. de sitio del sitio concentrador para crear un límite de cumplimiento. Para ello, use el cmdlet [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) de SharePoint Online PowerShell para obtener el SiteId para el sitio central y, a continuación, use este valor para la propiedad id. del departamento para crear un filtro de permisos de búsqueda.

Use la siguiente sintaxis para crear un filtro de permisos de búsqueda para un SharePoint de concentradores:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'"
```

Este es un ejemplo de creación de un filtro de permisos de búsqueda para un sitio central para la agencia Coho Winery:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'"
```

## <a name="compliance-boundary-limitations"></a>Limitaciones de límites de cumplimiento

Tenga en cuenta las siguientes limitaciones al administrar casos e investigaciones de exhibición de documentos electrónicos que usan límites de cumplimiento.
  
- Al crear y ejecutar una búsqueda, puede seleccionar ubicaciones de contenido que estén fuera de su organismo. Sin embargo, debido al filtro de permisos de búsqueda, el contenido de esas ubicaciones no se incluye en los resultados de búsqueda.

- Los límites de cumplimiento no se aplican a las retenciones en casos de exhibición de documentos electrónicos. Eso significa que un administrador de eDiscovery en una agencia puede poner a un usuario en una agencia distinta en espera. Sin embargo, se aplicará el límite de cumplimiento si el administrador de eDiscovery busca las ubicaciones de contenido del usuario que se ha colocado en espera. Esto significa que el administrador de eDiscovery no podrá buscar en las ubicaciones de contenido del usuario, incluso aunque colocaron al usuario en espera.

    Además, las estadísticas de retención solo se aplicarán a las ubicaciones de contenido de la agencia.

- Si se le asigna un filtro de permisos de búsqueda (un buzón o un filtro de sitio) e intenta exportar elementos sin indizar para una búsqueda que incluya todos los sitios de SharePoint de la organización, recibirá el siguiente mensaje de error: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . Si tiene asignado un filtro de permisos de búsqueda y desea exportar elementos sin indizar desde SharePoint, tendrá que volver a ejecutar la búsqueda e incluir sitios de SharePoint específicos para buscar. De lo contrario, solo podrá exportar elementos indizados de una búsqueda que incluya todos los SharePoint web. Para obtener más información acerca de las opciones al exportar resultados de búsqueda, vea [Export Content search results](export-search-results.md#step-1-prepare-search-results-for-export).

- Los filtros de permisos de búsqueda no se aplican a las carpetas públicas de Exchange.

## <a name="more-information"></a>Más información

- Si un buzón está des licenciado o eliminado temporalmente, el usuario ya no se considerará dentro del límite de cumplimiento. Si se colocó una retención en el buzón cuando se eliminó, el contenido conservado en el buzón sigue sujeto a un límite de cumplimiento o a un filtro de permisos de búsqueda.

- Si los límites de cumplimiento y los filtros de permisos de búsqueda se implementan para un usuario, se recomienda no eliminar el buzón de un usuario y no su cuenta OneDrive usuario. En otras palabras, si elimina el buzón de un usuario, también debe quitar la cuenta de OneDrive del usuario ya que mailbox_RecipientFilter se usa para aplicar el filtro de permisos de búsqueda para OneDrive.

- Los límites de cumplimiento y los filtros de permisos de búsqueda dependen de los atributos que se marcan en el contenido de Exchange, OneDrive y SharePoint y de la indización posterior de este contenido marcado.

- No se recomienda usar filtros de exclusión (como usar en un filtro de permisos de búsqueda) para un límite de cumplimiento `-not()` basado en contenido. El uso de un filtro de exclusión puede tener resultados inesperados si no se ha indizado el contenido con atributos actualizados recientemente.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes.

**Quién puede crear y administrar filtros de permisos de búsqueda (con New-ComplianceSecurityFilter y Set-ComplianceSecurityFilter cmdlets)?**
  
Para crear, ver y modificar filtros de permisos de búsqueda, debe ser miembro del grupo de roles Administración de la organización en el Centro de cumplimiento de Microsoft 365.
  
**Si un administrador de exhibición de documentos electrónicos está asignado a más de un grupo de roles que abarca varias agencias, ¿cómo buscan contenido en una agencia u otra?**
  
El administrador de exhibición de documentos electrónicos puede agregar parámetros a su consulta de búsqueda que restringen la búsqueda a una agencia específica. Por ejemplo, si una organización ha especificado la propiedad **CustomAttribute10** para diferenciar las agencias, puede anexar lo siguiente a su consulta de búsqueda para buscar buzones y cuentas OneDrive en una agencia específica: `CustomAttribute10:<value>` .
  
**¿Qué sucede si se cambia el valor del atributo que se usa como atributo de cumplimiento en un filtro de permisos de búsqueda?**
  
Un filtro de permisos de búsqueda tarda hasta tres días en aplicar el límite de cumplimiento si se cambia el valor del atributo que se usa en el filtro. Por ejemplo, en el escenario contoso, supongamos que un usuario de la cuarta agencia de café se transfiere a la agencia Coho Winery. Como resultado, el valor del atributo **Department** en el objeto user se cambia de *FourthCoffee* a *CohoWinery*. En esta situación, fourth coffee eDiscovery and investors will get search results for that user for up three days after the attribute is changed. Del mismo modo, se tarda hasta tres días antes de que los administradores e investigadores de exhibición de documentos electrónicos de Coho Winery obtengan resultados de búsqueda para el usuario.
  
**¿Puede un administrador de exhibición de documentos electrónicos ver contenido desde dos límites de cumplimiento independientes?**
  
Sí, esto se puede hacer al buscar Exchange buzones de correo agregando el administrador de exhibición de documentos electrónicos a los grupos de roles que tienen visibilidad para ambas agencias. Sin embargo, al buscar SharePoint sitios y cuentas OneDrive, un administrador de exhibición de documentos electrónicos solo puede buscar contenido en límites de cumplimiento diferentes si las agencias están en la misma región o ubicación geográfica. **Nota:** Esta limitación para los sitios no se aplica en Advanced eDiscovery porque la búsqueda de contenido en SharePoint y OneDrive no está enlazada por ubicación geográfica.
  
**¿Funcionan los filtros de permisos de búsqueda para las conservaciones de casos de exhibición de documentos electrónicos, Microsoft 365 directivas de retención o DLP?**
  
De momento, no.
  
**Si especifico una región para controlar dónde se exporta el contenido, pero no tengo una organización SharePoint en esa región, ¿puedo seguir buscando SharePoint?**
  
Si la región especificada en el filtro de permisos de búsqueda no existe en la organización, se buscará la región predeterminada.
  
**¿Cuál es el número máximo de filtros de permisos de búsqueda que se pueden crear en una organización?**
  
No hay ningún límite en el número de filtros de permisos de búsqueda que se pueden crear en una organización. Sin embargo, una consulta de búsqueda puede tener un máximo de 100 condiciones. En este caso, una condición se define como algo que está conectado a la consulta por un operador booleano (como **AND**, **OR** y **NEAR**). El límite del número de condiciones incluye la propia consulta de búsqueda y todos los filtros de permisos de búsqueda que se aplican al usuario que ejecuta la búsqueda. Por lo tanto, cuanto más filtros de permisos de búsqueda tenga (especialmente si estos filtros se aplican al mismo usuario o grupo de usuarios), mayor será la posibilidad de superar el número máximo de condiciones para una búsqueda.

Para comprender cómo funciona este límite, debe comprender que un filtro de permisos de búsqueda se anexa a la consulta de búsqueda cuando se ejecuta una búsqueda. El operador **booleano AND** une un filtro de permisos de búsqueda a la consulta de búsqueda. La lógica de consulta para la consulta de búsqueda y un único filtro de permisos de búsqueda tendría este aspecto:

```text
<SearchQuery> AND <PermissionsFilter>
```

El operador **booleano OR** combina varios filtros de permisos de búsqueda y, a continuación, el operador AND conecta esas condiciones a la **consulta de** búsqueda.

La lógica de consulta para la consulta de búsqueda y varios filtros de permisos de búsqueda tendría este aspecto:

```text
<SearchQuery> AND (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>...)
```

Es posible que la consulta de búsqueda en sí conste de varias condiciones conectadas por operadores booleanos. Cada condición de la consulta de búsqueda también contaría con el límite de 100 condiciones.

Además, el número de filtros de permisos de búsqueda anexados a una consulta depende del usuario que ejecuta la búsqueda. Cuando un usuario específico ejecuta una búsqueda, los filtros de permisos de búsqueda que se aplican al usuario (que se define mediante el parámetro *Users* en el filtro) se anexan a la consulta. Su organización podría tener cientos de filtros de permisos de búsqueda, pero si se aplican más de 100 filtros a los mismos usuarios, es probable que se supere el límite de 100 condiciones cuando esos usuarios ejecuten búsquedas.

Hay una cosa más que tener en cuenta sobre el límite de condición. El número de sitios SharePoint específicos que se incluyen en los filtros de permisos de búsqueda o consulta de búsqueda también cuentan con este límite. 

Para evitar que su organización alcance el límite de condiciones, mantenga el número de filtros de permisos de búsqueda en su organización en pocos minutos como sea posible para cumplir los requisitos de su empresa.
