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
localization_priority: Normal
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
ms.openlocfilehash: 02e2e2f048ab521ad5640003cb127ed7bfa19641
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706611"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Configurar límites de cumplimiento para investigaciones de exhibición de documentos electrónicos

Las instrucciones de este artículo se pueden aplicar al usar core eDiscovery o Advanced eDiscovery para administrar investigaciones.

Los límites de cumplimiento crean límites lógicos dentro de una organización que controlan las ubicaciones de contenido de usuario (como buzones, cuentas de OneDrive y sitios SharePoint) que los administradores de exhibición de documentos electrónicos pueden buscar. Además, los límites de cumplimiento controlan quién puede acceder a los casos de exhibición de documentos electrónicos usados para administrar las investigaciones legales, de recursos humanos u otras investigaciones de su organización. La necesidad de límites de cumplimiento suele ser necesaria para las corporaciones multinacionales que tienen que respetar los reglamentos y los miembros de la directiva geográfica, así como para los gobiernos, que a menudo se dividen en diferentes organismos. En Microsoft 365, los límites de cumplimiento le ayudan a cumplir estos requisitos al realizar búsquedas de contenido y administrar investigaciones con casos de exhibición de documentos electrónicos.
  
Usamos el ejemplo de la siguiente ilustración para explicar cómo funcionan los límites de cumplimiento.
  
![Los límites de cumplimiento constan de filtros de permisos de búsqueda que controlan el acceso a agencias y grupos de roles de administración que controlan el acceso a casos de exhibición de documentos electrónicos](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
En este ejemplo, Contoso LTD es una organización formada por dos subsidiarias, Fourth Coffee y Coho Winery. La empresa requiere que los administradores e investigadores de exhibición de documentos electrónicos solo puedan buscar en los buzones de correo Exchange, las cuentas OneDrive y los SharePoint de su agencia. Además, los administradores e investigadores de exhibición de documentos electrónicos solo pueden ver casos de exhibición de documentos electrónicos en su agencia y solo pueden acceder a los casos de los que son miembros. Además, en este escenario, los investigadores no pueden poner ubicaciones de contenido en espera ni exportar contenido de un caso. Este es el modo en que los límites de cumplimiento cumplen estos requisitos.
  
- La funcionalidad de filtrado de permisos de búsqueda en búsqueda de contenido controla las ubicaciones de contenido que pueden buscar los administradores e investigadores de exhibición de documentos electrónicos. Esto significa que los gerentes e investigadores de eDiscovery en la agencia Fourth Coffee solo pueden buscar ubicaciones de contenido en la subsidiaria Fourth Coffee. La misma restricción se aplica a la subsidiaria Coho Winery.

- Los grupos de roles proporcionan las siguientes funciones para los límites de cumplimiento:

  - Controle quién puede ver los casos de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento. Esto quiere decir que los administradores y gestores de eDiscovery solo pueden ver los casos de eDiscovery en su organismo.

  - Controle quién puede asignar miembros a un caso de exhibición de documentos electrónicos. Esto significa que los administradores y administradores de eDiscovery solo pueden asignar miembros a los casos de los que ellos mismos sean miembros.

  - Controle las tareas relacionadas con la exhibición de documentos electrónicos que los miembros pueden realizar agregando o quitando roles que asignan permisos específicos.

Este es el proceso para configurar límites de cumplimiento:
  
[Paso 1: Identificar un atributo de usuario para definir las agencias](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Paso 2: Presentar una solicitud con el soporte técnico de Microsoft para sincronizar el atributo de usuario con OneDrive cuentas](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Paso 3: Crear un grupo de roles para cada agencia](#step-3-create-a-role-group-for-each-agency)

[Paso 4: Crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Paso 5: Crear un caso de exhibición de documentos electrónicos para investigaciones dentro de la agencia](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Antes de configurar los límites de cumplimiento

Debe cumplir los siguientes requisitos previos antes de que el atributo Azure Active Directory (Azure AD) que se identidade (en el paso 1) se pueda sincronizar correctamente con la cuenta de OneDrive de un usuario (en el paso 2):

- A los usuarios se les debe asignar una Exchange Online y una licencia SharePoint online.

- Los buzones de usuario deben tener un tamaño mínimo de 10 MB. Si el buzón de un usuario es inferior a 10 MB, el atributo que se usa para definir las agencias no se sincronizará con la cuenta de OneDrive usuario.

- Los límites de cumplimiento y los atributos usados para crear filtros de permisos de búsqueda requieren que los Azure Active Directory (Azure AD) se sincronicen con los buzones de usuario. Para comprobar que los atributos que desea usar se han sincronizado, ejecute el cmdlet [Get-User](/powershell/module/exchange/get-user) en Exchange Online PowerShell. El resultado de este cmdlet muestra los atributos de Azure AD sincronizados con Exchange Online.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Paso 1: Identificar un atributo de usuario para definir las agencias

El primer paso es elegir un atributo de Azure AD que se usará para definir las agencias. Este atributo se usa para crear el filtro de permisos de búsqueda que limita a un administrador de exhibición de documentos electrónicos para buscar solo las ubicaciones de contenido de los usuarios a los que se asigna un valor específico para este atributo. Por ejemplo, supongamos que Contoso decide usar el **atributo Department.** El valor de este atributo para los usuarios de la subsidiaria Fourth Coffee sería y el valor para los usuarios de la subsidiaria  `FourthCoffee`  Coho Winery sería `CohoWinery` . En el paso 4, se usa este  `attribute:value`  par (por ejemplo, *Department:FourthCoffee*) para limitar las ubicaciones de contenido de usuario en las que los administradores de exhibición de documentos electrónicos pueden buscar. 
  
Esta es una lista de atributos de usuario de Azure AD que puede usar para los límites de cumplimiento:
  
- Empresa

- CustomAttribute1 - CustomAttribute15

- Departamento

- Oficina

- C (código de país de dos letras) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup>Este atributo se asigna a la propiedad CountryOrRegion que se devuelve ejecutando el cmdlet **Get-User** en Exchange Online PowerShell. El cmdlet devuelve el nombre de país localizado, que se traduce a partir del código de país de dos letras. Para obtener más información, vea la descripción del parámetro CountryOrRegion en el artículo de referencia del cmdlet [Set-User.](/powershell/module/exchange/set-user)

Aunque hay más atributos de usuario disponibles, especialmente para Exchange buzones de correo, los atributos enumerados anteriormente son los únicos admitidos actualmente por OneDrive.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Paso 2: Presentar una solicitud con el soporte técnico de Microsoft para sincronizar el atributo de usuario con OneDrive cuentas

El siguiente paso es presentar una solicitud con el soporte técnico de Microsoft para sincronizar el atributo de Azure AD que eligió en el paso 1 con todas las OneDrive de la organización. Después de que se produzca esta sincronización, el atributo (y su valor) que eligió en el paso 1 se asignará a una propiedad administrada oculta denominada `ComplianceAttribute` . Este atributo se usa para crear el filtro de permisos de búsqueda OneDrive en el paso 4.
  
Incluya la siguiente información al enviar la solicitud al soporte técnico de Microsoft:
  
- El nombre de dominio predeterminado de la organización

- Nombre del atributo de Azure AD (del paso 1)

- El siguiente título o descripción del propósito de la solicitud de soporte técnico: "Habilitar OneDrive para la Empresa sincronización con Azure AD para filtros de seguridad de cumplimiento". Esto ayuda a enrutar la solicitud al equipo de ingeniería de exhibición de documentos electrónicos que implementa la solicitud.

Después de realizar el cambio de ingeniería y de sincronizar el atributo con OneDrive, el soporte técnico de Microsoft le enviará el número de compilación en el que se realizó el cambio y una fecha de implementación estimada. El proceso de implementación suele demorar entre 4 y 6 semanas después de enviar la solicitud de soporte técnico.
  
> [!IMPORTANT]
> Puede completar el paso 3 al paso 5 antes de implementar este cambio de atributo. Pero la ejecución de búsquedas de contenido no devolverá documentos de OneDrive que se especifican en un filtro de permisos de búsqueda hasta después de implementar la sincronización de atributos.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Paso 3: Crear un grupo de roles para cada agencia

El siguiente paso es crear los grupos de roles en el Centro de seguridad & cumplimiento que se alineará con las agencias. Le recomendamos que cree un grupo de funciones copiando el grupo de administradores de exhibición de documentos electrónicos integrado, agregando los miembros adecuados y eliminando las funciones que pueden no ser aplicables a sus necesidades. Para obtener más información acerca de los roles relacionados con la exhibición de documentos electrónicos, vea [Asignar permisos de exhibición de documentos electrónicos.](assign-ediscovery-permissions.md)
  
Para crear los grupos de roles, vaya a la página **Permisos** del Centro de seguridad y cumplimiento y cree un grupo de roles para cada equipo de cada organismo que usará los límites de cumplimiento y los casos de eDiscovery para administrar investigaciones.
  
Con el escenario de límites de cumplimiento de Contoso, se deben crear cuatro grupos de roles y agregar los miembros adecuados a cada uno.
  
- Administradores de eDiscovery de Fourth Coffee

- Investigadores de Fourth Coffee

- Administradores de eDiscovery de Coho Winery

- Investigadores de Coho Winery
  
Para cumplir los requisitos del escenario de límites  de cumplimiento de Contoso, también quitaría los **roles** de retención y exportación de los grupos de roles de investigadores para impedir que los investigadores coloquen retenciones en ubicaciones de contenido y exporten contenido de un caso.

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Paso 4: Crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento

Después de crear grupos de roles para cada agencia, el siguiente paso es crear los filtros de permisos de búsqueda que asocian cada grupo de roles a su agencia específica y definen el propio límite de cumplimiento. Debe crear un filtro de permisos de búsqueda para cada agencia. Para obtener más información acerca de la creación de filtros de permisos de seguridad, vea [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).
  
Esta es la sintaxis que se usa para crear un filtro de permisos de búsqueda usado para los límites de cumplimiento.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Esta es una descripción de cada parámetro del comando:
  
- `FilterName`: especifica el nombre del filtro. Use un nombre que describa o identifique la agencia en la que se usa el filtro.

- `Users`: especifica los usuarios o grupos que obtienen este filtro aplicado a las acciones de búsqueda que realizan. Para los límites de cumplimiento, este parámetro especifica los grupos de roles (que creó en el paso 3) en la agencia para la que está creando el filtro. Tenga en cuenta que se trata de un parámetro de varios valores, por lo que puede incluir uno o varios grupos de roles, separados por comas.

- `Filters`: especifica los criterios de búsqueda para el filtro. Para los límites de cumplimiento, defina los filtros siguientes. Cada uno se aplica a una ubicación de contenido. 

    - `Mailbox`: especifica los buzones que pueden buscar los grupos de roles definidos en  `Users` el parámetro. Para los límites de cumplimiento,  *ComplianceAttribute*  es el mismo atributo que identificó en el paso 1 y  *AttributeValue*  especifica la agencia. Este filtro permite a los miembros del grupo de roles buscar solo los buzones de una agencia específica; por ejemplo, `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: especifica las cuentas OneDrive que pueden buscar los grupos de roles definidos en `Users` el parámetro. Para el OneDrive, use la cadena real `ComplianceAttribute` . Esto se asigna al mismo atributo que identificó en el paso 1 y que se sincroniza con las cuentas de OneDrive como resultado de la solicitud de soporte técnico que envió en el paso 2; *AttributeValue* especifica la agencia. Este filtro permite a los miembros del grupo de roles buscar solo las OneDrive en una agencia específica; por ejemplo, `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: especifica los SharePoint que pueden buscar los grupos de roles definidos en `Users` el parámetro. *SharePointURL* especifica los sitios de la agencia en los que pueden buscar los miembros del grupo de roles. Por ejemplo, `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Observe que `Site` los filtros y están conectados por un operador `Site_Path` **-or.**

     > [!NOTE]
     > La sintaxis del `Filters` parámetro incluye una lista de *filtros*. Una lista de filtros es un filtro que incluye un filtro de buzón de correo y un filtro de sitio separado por una coma. En el ejemplo anterior, observe que una coma separa **Mailbox_ComplianceAttribute** y **Site_ComplianceAttribute**: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` . Cuando este filtro se procesa durante la ejecución de una búsqueda de contenido, se crean dos filtros de permisos de búsqueda a partir de la lista de filtros: un filtro de buzones y un filtro de sitio. Una alternativa al uso de una lista de filtros sería crear dos filtros de permisos de búsqueda independientes para cada agencia: un filtro de permisos de búsqueda para el atributo de buzón y un filtro para los atributos del sitio. En cualquier caso, los resultados serán los mismos. El uso de una lista de filtros o la creación de filtros de permisos de búsqueda independientes es una cuestión de preferencia.

- `Action`: especifica el tipo de acción de búsqueda a la que se aplica el filtro. Por ejemplo, solo aplicaría el filtro cuando los miembros del grupo de roles  `-Action Search` definidos en `Users` el parámetro ejecuten una búsqueda. En este caso, el filtro no se aplicaría al exportar resultados de búsqueda. Para los límites de cumplimiento, úselo  `-Action All` para que el filtro se aplique a todas las acciones de búsqueda. 

    Para obtener una lista de las acciones de búsqueda, vea la sección "New-ComplianceSecurityFilter" en [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).

Estos son algunos ejemplos de los dos filtros de permisos de búsqueda que se crearían para admitir el escenario de límites de cumplimiento de Contoso. Estos dos ejemplos incluyen una lista de filtros separados por comas, en la que el buzón y los filtros de sitio se incluyen en el mismo filtro de permisos de búsqueda y se separan con una coma.
  
### <a name="fourth-coffee"></a>Cuarto café

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Paso 5: Crear un caso de exhibición de documentos electrónicos para investigaciones dentro de la agencia

El último paso es crear un caso de exhibición de documentos electrónicos principal o un caso Advanced eDiscovery en el centro de cumplimiento de Microsoft 365 y, a continuación, agregar el grupo de roles que creó en el paso 3 como miembro del caso. Esto da como resultado dos características importantes del uso de límites de cumplimiento:
  
- Solo los miembros del grupo de roles agregados al caso podrán ver y tener acceso al caso en el Centro de seguridad & cumplimiento. Por ejemplo, si el grupo de roles Fourth Coffee Investigators es el único miembro de un caso, los miembros del grupo de roles Fourth Coffee eDiscovery Managers (o miembros de cualquier otro grupo de roles) no podrán ver ni acceder al caso.

- Cuando un miembro del grupo de roles asignado a un caso ejecuta una búsqueda asociada al caso, solo podrá buscar en las ubicaciones de contenido dentro de su agencia (que se define mediante el filtro de permisos de búsqueda que creó en el paso 4).

Para crear un caso y asignar miembros:

1. Vaya a la **página Core eDiscovery** o **Advanced eDiscovery** en el centro de Microsoft 365 de cumplimiento y cree un caso.

2. En la lista de casos, haga clic en el nombre del caso que creó.

3. Agregue grupos de roles como miembros al caso. Para obtener instrucciones, consulte uno de los siguientes artículos:

   - [Agregar miembros a un caso de exhibición de documentos electrónicos principal](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [Agregar miembros a un Advanced eDiscovery caso](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> Al agregar un grupo de roles a un caso, solo puede agregar los grupos de roles de los que es miembro.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Búsqueda y exportación de contenido en entornos multigeómicos

Los filtros de permisos de búsqueda también permiten controlar dónde se enruta el contenido para su exportación y qué centro de datos se puede buscar al buscar ubicaciones de contenido en un [SharePoint Multi-Geo de búsqueda.](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)
  
- **Exportar resultados de búsqueda:** Puede exportar los resultados de la búsqueda Exchange buzones de correo, SharePoint y cuentas OneDrive de un centro de datos específico. Esto significa que puede especificar la ubicación del centro de datos desde la que se exportarán los resultados de la búsqueda.

    Use el **parámetro Region** para los cmdlets **New-ComplianceSecurityFilter** o **Set-ComplianceSecurityFilter** para crear o cambiar el centro de datos por el que se enruta la exportación.
  
    |**Valor del parámetro**|**Ubicación del centro de datos**|
    |:-----|:-----|
    |NAM  <br/> |Norteamérica (los centros de datos están en estados Unidos)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacífico  <br/> |
    |CAN <br/> |Canadá|
    |||

- **Enrutar búsquedas de contenido:** Puede enrutar las búsquedas de contenido de SharePoint sitios y OneDrive cuentas a un centro de datos satélite. Esto significa que puede especificar la ubicación del centro de datos donde se ejecutarán las búsquedas.

    Use uno de los siguientes valores para el parámetro **Region** para controlar la ubicación del centro de datos en la que se ejecutarán las búsquedas al buscar SharePoint sitios y OneDrive cuentas. 
  
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

   Si no especifica el parámetro **Region** para un filtro de permisos de búsqueda, se buscará la región principal SharePoint la organización. Los resultados de la búsqueda se exportan al centro de datos más cercano.

   Para simplificar el concepto, el **parámetro Region** controla el centro de datos que se usa para buscar contenido en SharePoint y OneDrive. Esto no se aplica a la búsqueda de contenido en Exchange porque Exchange búsquedas de contenido no están vinculadas por la ubicación geográfica de los centros de datos. Además, el mismo **valor de parámetro Region** también puede dictar el centro de datos por el que se enrutan las exportaciones. Esto suele ser necesario para controlar el movimiento de datos a través de los tableros geográficos.

> [!NOTE]
> Si usa Advanced eDiscovery, el parámetro **Region** no controla la región desde la que se exportan los datos. Los datos se exportan desde el centro de datos principal de la organización. Además, la búsqueda de contenido en SharePoint y OneDrive no está enlazada por la ubicación geográfica de los centros de datos. Se buscan todos los centros de datos. Para obtener más información sobre Advanced eDiscovery, vea [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).

Estos son ejemplos del uso del **parámetro Region** al crear filtros de permisos de búsqueda para los límites de cumplimiento. Esto supone que la subsidiaria Fourth Coffee se encuentra en Norteamérica y que Coho Winery está en Europa. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Tenga en cuenta lo siguiente al buscar y exportar contenido en entornos multigeómicos.
  
- El parámetro **Region** no controla las búsquedas de los buzones de Exchange. Todos los centros de datos se buscarán al buscar en buzones de correo. Para limitar el ámbito en el que se Exchange los buzones de correo, use el parámetro **Filters** al crear o cambiar un filtro de permisos de búsqueda. 

- Si es necesario que un administrador de exhibición de documentos electrónicos busque en varias regiones de SharePoint, debe crear una cuenta de usuario diferente para que ese administrador de exhibición de documentos electrónicos use en el filtro de permisos de búsqueda para especificar la región donde se encuentran los sitios de SharePoint o las cuentas OneDrive. Para obtener más información acerca de la configuración, vea la sección "Buscar contenido en un entorno SharePoint Multi-Geo" en [Búsqueda de contenido](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment).

- Al buscar contenido en SharePoint y OneDrive, el parámetro **Region** dirige las búsquedas a la ubicación principal o satélite donde el administrador de exhibición de documentos electrónicos llevará a cabo investigaciones de exhibición de documentos electrónicos. Si un administrador de exhibición de documentos electrónicos busca SharePoint y OneDrive fuera de la región especificada en el filtro de permisos de búsqueda, no se devuelven resultados de búsqueda.

- Al exportar resultados de búsqueda, el contenido de todas las ubicaciones de contenido (incluidos Exchange, Skype Empresarial, SharePoint, OneDrive y otros servicios que se pueden buscar mediante la herramienta búsqueda de contenido) se cargan en la ubicación Azure Storage del centro de datos especificada por el **parámetro Region.** Esto ayuda a las organizaciones a mantenerse dentro del cumplimiento al no permitir que el contenido se exporte a través de bordes controlados. Si no se especifica ninguna región en el filtro de permisos de búsqueda, el contenido se carga en el centro de datos principal de la organización.

- Puede editar un filtro de permisos de búsqueda existente para agregar o cambiar la región ejecutando el siguiente comando:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Uso de límites de cumplimiento para SharePoint de concentradores

[SharePoint los sitios centrales](/sharepoint/dev/features/hub-site/hub-site-overview) suelen alinearse con los mismos límites geográficos o de agencia que los límites de cumplimiento de eDiscovery. Esto significa que puede usar la propiedad id. de sitio del sitio concentrador para crear un límite de cumplimiento. Para ello, use el cmdlet [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) de SharePoint Online PowerShell para obtener el SiteId para el sitio central y, a continuación, use este valor para la propiedad id. del departamento para crear un filtro de permisos de búsqueda.

Use la siguiente sintaxis para crear un filtro de permisos de búsqueda para un SharePoint de concentradores:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Este es un ejemplo de creación de un filtro de permisos de búsqueda para un sitio central para la agencia Coho Winery:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Limitaciones de límites de cumplimiento

Tenga en cuenta las siguientes limitaciones al administrar casos e investigaciones de exhibición de documentos electrónicos que usan límites de cumplimiento.
  
- Al crear y ejecutar una búsqueda, puede seleccionar ubicaciones de contenido que estén fuera de su organismo. Sin embargo, debido al filtro de permisos de búsqueda, el contenido de esas ubicaciones no se incluye en los resultados de búsqueda.

- Los límites de cumplimiento no se aplican a las retenciones en casos de exhibición de documentos electrónicos. Eso significa que un administrador de eDiscovery en una agencia puede poner a un usuario en una agencia distinta en espera. Sin embargo, se aplicará el límite de cumplimiento si el administrador de eDiscovery busca las ubicaciones de contenido del usuario que se ha colocado en espera. Esto significa que el administrador de eDiscovery no podrá buscar en las ubicaciones de contenido del usuario, incluso aunque colocaron al usuario en espera.

    Además, las estadísticas de retención solo se aplicarán a las ubicaciones de contenido de la agencia.

- Si se le asigna un filtro de permisos de búsqueda (un buzón o un filtro de sitio) e intenta exportar elementos sin indizar para una búsqueda que incluya todos los sitios de SharePoint de la organización, recibirá el siguiente mensaje de error: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . Si tiene asignado un filtro de permisos de búsqueda y desea exportar elementos sin indizar desde SharePoint, tendrá que volver a ejecutar la búsqueda e incluir sitios de SharePoint específicos para buscar. De lo contrario, solo podrá exportar elementos indizados de una búsqueda que incluya todos los SharePoint web. Para obtener más información acerca de las opciones al exportar resultados de búsqueda, vea [Export Content search results](export-search-results.md#step-1-prepare-search-results-for-export).

- Los filtros de permisos de búsqueda no se aplican a las carpetas públicas de Exchange.

## <a name="more-information"></a>Más información

- Si un buzón está des licenciado o eliminado temporalmente, los atributos de Azure AD ya no se sincronizan con el buzón. Si se colocó una retención en el buzón cuando se eliminó, el contenido conservado en el buzón sigue sujeto a un límite de cumplimiento o a un filtro de permisos de búsqueda en función de la última vez que se sincronizaron los atributos de Azure AD antes de eliminar el buzón. 

    Además, la sincronización entre el buzón del usuario y la cuenta OneDrive dejará de funcionar si el buzón está des licenciado o eliminado temporalmente. El último valor marcado del atributo de cumplimiento para la cuenta OneDrive permanecerá en vigor.

- El atributo de cumplimiento se sincroniza desde el buzón de correo Exchange usuario a su OneDrive cada siete días. Como se ha indicado anteriormente, esta sincronización solo se produce cuando al usuario se le asigna una licencia de Exchange Online y SharePoint Online y el buzón del usuario tiene al menos 10 MB.

- Si los límites de cumplimiento y los filtros de permisos de búsqueda se implementan tanto para el buzón de un usuario como para una cuenta de OneDrive, se recomienda no eliminar el buzón de un usuario y no su cuenta OneDrive usuario. En otras palabras, si elimina el buzón de un usuario, también debe quitar la cuenta OneDrive usuario.

- Hay situaciones (como un empleado que devuelve) en las que un usuario puede tener dos o más OneDrive cuentas. En estos casos, solo se sincronizará OneDrive cuenta principal asociada con el usuario en Azure AD.

- Los límites de cumplimiento y los filtros de permisos de búsqueda dependen de los atributos que se marcan en el contenido de Exchange, OneDrive y SharePoint y de la indización posterior de este contenido marcado. 

- No se recomienda usar filtros de exclusión (como usar en un filtro de permisos de búsqueda) para un límite de cumplimiento `-not()` basado en contenido. El uso de un filtro de exclusión puede tener resultados inesperados si no se ha indizado el contenido con atributos actualizados recientemente. 

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**Quién puede crear y administrar filtros de permisos de búsqueda (con New-ComplianceSecurityFilter y Set-ComplianceSecurityFilter cmdlets)?**
  
Para crear, ver y modificar filtros de permisos de búsqueda, debe ser miembro del grupo de roles Administración de la organización en el Centro de seguridad & cumplimiento.
  
**Si un administrador de exhibición de documentos electrónicos está asignado a más de un grupo de roles que abarca varias agencias, ¿cómo buscan contenido en una agencia u otra?**
  
El administrador de exhibición de documentos electrónicos puede agregar parámetros a su consulta de búsqueda que restringen la búsqueda a una agencia específica. Por ejemplo, si una organización ha especificado la propiedad **CustomAttribute10** para diferenciar las agencias, puede anexar lo siguiente a su consulta de búsqueda para buscar buzones y cuentas OneDrive en una agencia específica: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` .
  
**¿Qué sucede si se cambia el valor del atributo que se usa como atributo de cumplimiento en un filtro de permisos de búsqueda?**
  
Un filtro de permisos de búsqueda tarda hasta tres días en aplicar el límite de cumplimiento si se cambia el valor del atributo que se usa en el filtro. Por ejemplo, en el escenario contoso, supongamos que un usuario de la cuarta agencia de café se transfiere a la agencia Coho Winery. Como resultado, el valor del atributo **Department** en el objeto user se cambia de *FourthCoffee* a *CohoWinery*. En esta situación, fourth coffee eDiscovery and investors will get search results for that user for up three days after the attribute is changed. Del mismo modo, se tarda hasta tres días antes de que los administradores e investigadores de exhibición de documentos electrónicos de Coho Winery obtengan resultados de búsqueda para el usuario.
  
**¿Puede un administrador de exhibición de documentos electrónicos ver contenido desde dos límites de cumplimiento independientes?**
  
Sí, esto se puede hacer al buscar Exchange buzones de correo agregando el administrador de exhibición de documentos electrónicos a los grupos de roles que tienen visibilidad para ambas agencias. Sin embargo, al buscar SharePoint sitios y cuentas OneDrive, un administrador de exhibición de documentos electrónicos solo puede buscar contenido en límites de cumplimiento diferentes si las agencias están en la misma región o ubicación geográfica. **Nota:** Esta limitación para los sitios no se aplica en Advanced eDiscovery porque la búsqueda de contenido en SharePoint y OneDrive no está enlazada por ubicación geográfica.
  
**¿Funcionan los filtros de permisos de búsqueda para las conservaciones de casos de exhibición de documentos electrónicos, Microsoft 365 directivas de retención o DLP?**
  
No, no en este momento.
  
**Si especifico una región para controlar dónde se exporta el contenido, pero no tengo una organización SharePoint en esa región, ¿puedo seguir buscando SharePoint?**
  
Si la región especificada en el filtro de permisos de búsqueda no existe en la organización, se buscará la región predeterminada.
  
**¿Cuál es el número máximo de filtros de permisos de búsqueda que se pueden crear en una organización?**
  
No hay ningún límite en el número de filtros de permisos de búsqueda que se pueden crear en una organización. Sin embargo, el rendimiento de la búsqueda se verá afectado cuando haya más de 100 filtros de permisos de búsqueda. Para mantener el número de filtros de permisos de búsqueda en la organización lo más pequeño posible, cree filtros que combinen reglas para Exchange, SharePoint y OneDrive en un único filtro de permisos de búsqueda siempre que sea posible.