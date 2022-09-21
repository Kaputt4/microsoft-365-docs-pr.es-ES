---
title: Configuración del filtrado de permisos para eDiscovery
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
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
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Use el filtrado de permisos de búsqueda para permitir que los administradores de eDiscovery busquen solo un subconjunto de buzones y sitios de la organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6a1441a10b1331c8a2d48d6e22e7a39132a5cd5d
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851554"
---
# <a name="configure-permissions-filtering-for-ediscovery"></a>Configuración del filtrado de permisos para eDiscovery

Puede usar el filtrado de permisos de búsqueda para permitir que un administrador de exhibición de documentos electrónicos busque solo un subconjunto de buzones y sitios de su organización. También puede utilizar el filtrado de permisos para permitir que ese mismo administrador de exhibición de documentos electrónicos busque solo contenido de los buzones o los sitios que cumpla unos criterios concretos de búsqueda. Por ejemplo, puede permitir que un administrador de exhibición de documentos electrónicos busque solo en los buzones de usuarios de un departamento o una ubicación en concreto. Para ello, cree un filtro que use un filtro de destinatario compatible para limitar qué buzones puede buscar un usuario o grupo de usuarios específicos. También puede crear un filtro que especifique qué contenido de buzón de correo puede buscar un usuario. Para ello, debe crear un filtro que utilice una propiedad de mensaje que pueda buscarse. De forma similar, puede permitir que un administrador de exhibición de documentos electrónicos busque solo sitios específicos de SharePoint en su organización. Para hacerlo, debe crear un filtro que limite en qué sitio puede buscarse. También puede crear un filtro que especifique qué contenido del sitio puede buscarse. Para ello, debe crear un filtro que utilice una propiedad de sitio que pueda buscarse.

Los filtros de permisos de búsqueda se aplican al buscar contenido mediante búsqueda de contenido, Microsoft Purview eDiscovery (estándar) y Microsoft Purview eDiscovery (Premium) en el portal de cumplimiento Microsoft Purview. Cuando se aplica un filtro de permisos de búsqueda a un usuario específico, ese usuario puede realizar las siguientes acciones relacionadas con la búsqueda:

- Buscar contenido
- Vista previa de los resultados de búsqueda
- Exportar resultados de búsqueda
- Purgar elementos devueltos por una búsqueda

También puede usar el filtrado de permisos de búsqueda para crear límites lógicos ( _denominados límites de cumplimiento_) dentro de una organización que controle las ubicaciones de contenido del usuario (como buzones, sitios de SharePoint y cuentas de OneDrive) que pueden buscar determinados administradores de eDiscovery. Para obtener más información, vea [Configurar límites de cumplimiento para las investigaciones de eDiscovery](set-up-compliance-boundaries.md).

Los cuatro cmdlets siguientes de Security & Compliance PowerShell permiten configurar y administrar filtros de permisos de búsqueda:

- [New-ComplianceSecurityFilter](#new-compliancesecurityfilter)
- [Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)
- [Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)
- [Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Requisitos para configurar el filtrado de permisos

- Para ejecutar los cmdlets de filtro de seguridad de cumplimiento, debe ser miembro del grupo de roles Administración de la organización en el portal de cumplimiento. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Tiene que conectarse a PowerShell de cumplimiento de Exchange Online y seguridad & para usar los cmdlets de filtro de seguridad de cumplimiento. Esto es necesario porque estos cmdlets requieren acceso a las propiedades del buzón, por lo que tiene que conectarse a Exchange Online PowerShell. Vea los pasos en la sección siguiente.

- Consulte la sección [More information](#more-information) para obtener información adicional acerca de los filtros de permisos de búsqueda.

- El filtrado de permisos de búsqueda se aplica a los buzones inactivos, lo que significa que puede usar el filtrado de contenido de buzón y buzón para limitar quién puede buscar en un buzón inactivo. Consulte la sección [Más información](#more-information) para obtener información adicional sobre el filtrado de permisos y los buzones inactivos.

- El filtrado de permisos de búsqueda no se puede usar para limitar quién puede buscar en carpetas públicas en Exchange.

- No hay ningún límite en el número de filtros de permisos de búsqueda que se pueden crear en una organización. Sin embargo, una consulta de búsqueda puede tener un máximo de 100 condiciones. En este caso, una condición se define como algo que está conectado a la consulta por un operador booleano (como **AND**, **OR** y **NEAR**). El límite para el número de condiciones incluye la propia consulta de búsqueda y todos los filtros de permisos de búsqueda que se aplican al usuario que ejecuta la búsqueda. Por lo tanto, cuantos más filtros de permisos de búsqueda tenga (especialmente si estos filtros se aplican al mismo usuario o grupo de usuarios), mejor será la posibilidad de superar el número máximo de condiciones para una búsqueda. Para evitar que su organización alcance el límite de condiciones, mantenga el número de filtros de permisos de búsqueda en su organización a la menor cantidad posible para satisfacer sus requisitos empresariales. Para obtener más información, vea [Configurar límites de cumplimiento para las investigaciones de eDiscovery](set-up-compliance-boundaries.md#frequently-asked-questions).

## <a name="connect-to-exchange-online-and-security--compliance-powershell-in-a-single-session"></a>Conexión a PowerShell de cumplimiento de Exchange Online y seguridad & en una sola sesión

Para poder ejecutar correctamente el script en esta sección, debe descargar e instalar el módulo de PowerShell Exchange Online. Para obtener información, consulte [Instalación y mantenimiento del módulo de PowerShell Exchange Online](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-module).

1. Guarde el texto siguiente en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de **.ps1**. Por ejemplo, podría guardarlo en un archivo denominado **ConnectEXO-SCC.ps1**.

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Security & Compliance)"
    ```

2. En el equipo local, abra Windows PowerShell, vaya a la carpeta donde se encuentra el script que creó en el paso anterior y, a continuación, ejecute el script; por ejemplo:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

¿Cómo se sabe si se ha completado correctamente? Después de ejecutar el script, están disponibles los cmdlets de Exchange Online PowerShell y PowerShell de seguridad & cumplimiento. Si no se muestra ningún error, la conexión se habrá establecido correctamente. Una prueba rápida consiste en ejecutar Exchange Online cmdlets de PowerShell y Seguridad & Cumplimiento de PowerShell. Por ejemplo, puede ejecutar **y Get-Mailbox** y **Get-ComplianceSearch**.

Para solucionar problemas de errores de conexión de PowerShell, consulte:

- [Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Conectarse a Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

El cmdlet **New-ComplianceSecurityFilter** se usa para crear un filtro de permisos de búsqueda. Esta es la sintaxis básica de este cmdlet:

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <user or role group> -Filters <filter>
```

En las secciones siguientes se describen los parámetros de este cmdlet. Todos los parámetros son necesarios para crear un filtro de permisos de búsqueda.

### <a name="filtername"></a>FilterName

El parámetro  _FilterName_ especifica el nombre del filtro de permisos. Este nombre sirve para identificar un filtro al utilizar los cmdlets **Get ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** y **Remove-ComplianceSecurityFilter**.

### <a name="filters"></a>Filtros

El parámetro  _Filters_ especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear tres tipos de filtros diferentes:

- **Filtrado de buzón de correo o OneDrive:** Este tipo de filtro especifica los buzones y las cuentas de OneDrive que los usuarios asignados (especificados por el parámetro  _Users_ ) pueden buscar. Este tipo de filtro se denomina filtro de _ubicación de contenido_ porque define las ubicaciones de contenido que un usuario puede buscar. La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde  _MailboxPropertyName_ especifica una propiedad de buzón usada para limitar los buzones y las cuentas de OneDrive que se pueden buscar. Por ejemplo, el filtro  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` de buzón de correo permitiría al usuario asignado a este filtro buscar solo los buzones y las cuentas de OneDrive que tienen el valor "OttawaUsers" en la propiedad CustomAttribute10.

  Cualquier propiedad de destinatario filtrable admitida se puede usar para la propiedad  _MailboxPropertyName_ en un buzón o filtro de OneDrive. En la tabla siguiente se enumeran cuatro propiedades de destinatario usadas habitualmente para crear un buzón de correo o un filtro de OneDrive. La tabla también incluye un ejemplo de uso de la propiedad en un filtro.

  |Nombre de propiedad|Ejemplo|
  |---|---|
  |Alias|`"Mailbox_Alias -like 'v-'"`|
  |Empresa|`"Mailbox_Company -eq 'Contoso'"`|
  |CountryOrRegion|`"Mailbox_CountryOrRegion -eq 'United States'"`|
  |Departamento|`"Mailbox_Department -eq 'Finance'"`|

- **Filtrado de contenido de buzón de correo:** Este tipo de filtro se aplica al contenido que se puede buscar. Este tipo de filtro se denomina _filtro de contenido_ porque especifica el contenido del buzón o las propiedades de correo electrónico que pueden buscar los usuarios asignados. La sintaxis de este tipo de filtro es **MailboxContent_**_SearchablePropertyName_, donde  _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda. Por ejemplo, el filtro `"MailboxContent_Recipients  -like 'contoso.com'"` de contenido del buzón de correo permitiría que el usuario asignado a este filtro solo buscara los mensajes enviados a los destinatarios en el dominio contoso.com. Para obtener una lista de las propiedades de correo electrónico que se pueden buscar, vea [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md#searchable-email-properties).

  > [!IMPORTANT]
  > Un único filtro de búsqueda no puede contener un filtro de buzón y un filtro de contenido de buzón. Para combinarlos en un solo filtro, debe usar una lista de [filtros](#using-a-filters-list-to-combine-filter-types).  Pero un filtro puede contener una consulta más compleja del mismo tipo. Por ejemplo: `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`

- **Filtrado de contenido de sitio y sitio:** Hay dos filtros relacionados con SharePoint y OneDrive que puede usar para especificar qué sitio o contenido de sitio pueden buscar los usuarios asignados.

  - **Site_**_SearchableSiteProperty_

  - **SiteContent_**_SearchableSiteProperty_

   Estos dos filtros son intercambiables. Por ejemplo, `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors'"` y  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors'"` devuelve los mismos resultados. Para obtener una lista de propiedades de sitio que se pueden buscar, vea [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md#searchable-site-properties)  Para obtener una lista más completa, vea [Información general sobre las propiedades rastreadas y administradas en SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Las propiedades marcadas con **sí** en la columna **Consultable** se pueden usar para crear un filtro de contenido de sitio o sitio.

  > [!IMPORTANT]
  > La configuración de un filtro de sitio con una de las propiedades admitidas no significa que la propiedad de sitio del filtro se propagará a todos los documentos de ese sitio. Esto significa que el usuario sigue siendo responsable de rellenar los campos de propiedad específicos asociados a los documentos de ese sitio para que el filtro de sitio funcione y capture el contenido correcto. Por ejemplo, si el usuario tiene aplicado un filtro de seguridad "Site_RefineableString00 -eq 'abc'" y, a continuación, el usuario ejecuta una búsqueda mediante la consulta de palabra clave "xyz". El filtro de seguridad se anexa a la consulta y la consulta real que se ejecuta sería "xyz **AND RefineableString0:'abc'**". El usuario debe asegurarse de que los documentos del sitio tengan valores en el campo RefineableString00 como "abc". Si no es así, la consulta de búsqueda no devolverá ningún resultado.

Tenga en cuenta las siguientes consideraciones al configurar el parámetro _Filters_ para los filtros de permisos de búsqueda:

- A diferencia de los buzones de correo, no hay un filtro de ubicación de contenido para los sitios aunque el filtro _de sitio_ tenga el aspecto de un filtro de ubicación. Todos los filtros para SharePoint y OneDrive son filtros de contenido (por lo que los filtros _Site\__ y _SiteContent\__ son intercambiables) porque las propiedades relacionadas con el sitio, como _Path_ , se marcan directamente en los documentos. ¿Qué significa esto? Es el resultado de la forma en que sharePoint está diseñado. En SharePoint, no hay un "objeto de sitio" con propiedades, como sucede con los buzones de Exchange. Por lo tanto, la propiedad _Path_ se marca en el documento y contiene la dirección URL del sitio donde se encuentra el documento. Esta es la razón por la que un filtro _de sitio_ se considera un filtro de contenido y no un filtro de ubicación de contenido.

- Tiene que crear un filtro de permisos de búsqueda para evitar explícitamente que los usuarios busquen ubicaciones de contenido en un servicio específico (por ejemplo, impedir que un usuario busque en cualquier buzón de Exchange o en cualquier sitio de SharePoint). En otras palabras, la creación de un filtro de permisos de búsqueda que permita a un usuario buscar en todos los sitios de SharePoint de la organización no impide que ese usuario busque buzones de correo. Por ejemplo, para permitir que los administradores de SharePoint solo busquen sitios de SharePoint, tiene que crear un filtro que les impida buscar buzones. De forma similar, para permitir que los administradores de Exchange solo busquen buzones, debe crear un filtro que les impida buscar sitios.

### <a name="users"></a>Usuarios

El parámetro  _Users_ especifica los usuarios que obtienen este filtro aplicado a sus búsquedas. Identifique a los usuarios por su alias o su dirección SMTP principal. Se pueden especificar varios valores separados por comas, o bien puede asignar el filtro a todos los usuarios con el valor **Todos**.

También puede usar el parámetro  _Users_ para especificar un grupo de roles del portal de cumplimiento. Así, podrá crear un grupo de roles personalizado y, a continuación, asignar a ese grupo de roles un filtro de permisos de búsqueda. Por ejemplo, supongamos que tiene un grupo de roles personalizado para los administradores de exhibición de documentos electrónicos de la sede en los Estados Unidos de una compañía multinacional. Puede usar el parámetro  _Users_ para especificar este grupo de roles (mediante la propiedad Name del grupo de roles) y, a continuación, usar el parámetro  _Filter_ para permitir que solo se busquen buzones en LOS EE. UU. No se pueden especificar grupos de distribución con este parámetro.|

### <a name="using-a-filters-list-to-combine-filter-types"></a>Uso de una lista de filtros para combinar tipos de filtro

Una _lista de filtros_ es un filtro que incluye un filtro de buzón y un filtro de sitio separados por una coma. Esta coma también funciona como un operador **OR** . El uso de una lista de filtros es el único método admitido para combinar diferentes tipos de filtros. En el ejemplo siguiente, observe que una coma separa los filtros **Buzón** y **Sitio** :

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors'"
```

Cuando se procesa un filtro que contiene una lista de filtros durante la ejecución de una búsqueda, se crean dos filtros de permisos de búsqueda a partir de la lista de filtros: uno para cada filtro separado por una coma. Por lo tanto, en el ejemplo anterior, se crearía un filtro de permisos de búsqueda de buzón y un filtro de permisos de búsqueda de sitio. Estos filtros están conectados por el operador **OR** .

Una alternativa al uso de una lista de filtros sería crear dos filtros de permisos de búsqueda independientes. Por lo tanto, en el ejemplo anterior, crearía un filtro para el atributo mailbox y un filtro para el atributo de sitio. En cualquier caso, los resultados son los mismos. El uso de una lista de filtros o la creación de filtros de permisos de búsqueda independientes es una cuestión de preferencia.

Tenga en cuenta lo siguiente sobre el uso de una lista de filtros:

- Debe usar una lista de filtros para crear un filtro que incluya un filtro **buzón** y un filtro **MailboxContent** .

- Cada componente de una lista de filtros puede contener una sintaxis de filtro compleja. Por ejemplo, los filtros de buzón y de sitio pueden contener varios filtros separados por un operador **-o** :

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Ejemplos de creación de filtros de permisos de búsqueda

Vea a continuación ejemplos del uso del cmdlet **New-ComplianceSecurityFilter** para crear un filtro de permisos de búsqueda.

Este ejemplo permite a los miembros del grupo de roles "US Discovery Managers" buscar solo los buzones y las cuentas de OneDrive en el Estados Unidos.

```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryOrRegion  -eq 'United States'"
```

Este ejemplo permite al usuario annb@contoso.com realizar acciones de búsqueda solo para buzones y cuentas de OneDrive en Canadá. Este filtro contiene el código de país numérico de tres dígitos correspondiente a Canadá según la ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'"
```

Este ejemplo permite a los usuarios donh y suzanf buscar solo los buzones de correo y las cuentas de OneDrive que tienen el valor "Marketing" para la propiedad de buzón CustomAttribute1.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'"
```

Este ejemplo permite a los miembros del grupo de roles "Fourth Coffee eDiscovery Managers" buscar solo los buzones y las cuentas de OneDrive que tienen el valor "FourthCoffee" para la propiedad de buzón department. El filtro también permite a los miembros del grupo de roles buscar documentos en el sitio de SharePoint Fourth Coffee.

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

> [!NOTE]
> En el ejemplo anterior, se debe incluir un filtro de contenido de sitio adicional (`SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'`) para que los miembros del grupo de roles puedan buscar documentos en cuentas de OneDrive. Si no se incluye este filtro, el filtro solo permitiría a los miembros del grupo de roles buscar documentos ubicados en `https://contoso.sharepoint.com/sites/FourthCoffee`.

Este ejemplo permite a los miembros del grupo de roles administrador de eDiscovery buscar solo los buzones y las cuentas de OneDrive de los miembros del grupo de distribución Usuarios de Ottawa. El cmdlet Get-DistributionGroup de Exchange Online PowerShell se usa para buscar los miembros del grupo Usuarios de Ottawa.

```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"
```

En este ejemplo se impide que cualquier usuario realice acciones de búsqueda en los buzones de correo y las cuentas de OneDrive de los miembros del grupo de distribución del equipo ejecutivo. Esto significa que los usuarios pueden eliminar contenido de estos buzones. El cmdlet Get-DistributionGroup de Exchange Online PowerShell se usa para buscar los miembros del grupo del equipo ejecutivo.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'"
```

En este ejemplo, los miembros del grupo de roles personalizado administradores de exhibición de documentos electrónicos de OneDrive solo pueden buscar contenido en las cuentas de OneDrive de la organización.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

En este ejemplo se restringe al usuario a realizar acciones de búsqueda solo en los mensajes de correo electrónico enviados durante el año natural de 2015.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'"
```

De forma similar al ejemplo anterior, este ejemplo restringe al usuario a realizar acciones de búsqueda solo en documentos que se cambiaron por última vez en algún momento del año natural 2015.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'"
```

En este ejemplo se impide que los miembros del grupo de roles "Administradores de detección de OneDrive" realicen acciones de búsqueda en cualquier buzón de la organización.

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"
```

Este ejemplo impide que cualquier persona de la organización realice acciones de búsqueda en los mensajes de correo electrónico enviados o recibidos por janets o sarad.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'"
```

En este ejemplo se usa una lista de filtros para combinar filtros de buzón y de sitio. En este ejemplo, el filtro de buzón de correo es un filtro de ubicación de contenido y el filtro de sitio es un filtro de contenido.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery'"
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** se usa para devolver una lista de filtros de permisos de búsqueda. Use el parámetro  _FilterName_ para devolver información de un filtro de búsqueda específico.

## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** se usa para modificar un filtro de permisos de búsqueda existente. En las secciones siguientes se describen los parámetros de este cmdlet. El único parámetro necesario es  _FilterName_.

### <a name="filtername"></a>FilterName

El parámetro  _FilterName_ especifica el nombre del filtro de permisos.

### <a name="users"></a>Usuarios

El parámetro  _Users_ especifica los usuarios que obtienen este filtro aplicado a sus búsquedas. Dado que se trata de una propiedad de varios valores, al especificar un usuario o grupo de usuarios con este parámetro se sobrescribe la lista existente de usuarios. Consulte los ejemplos siguientes para obtener la sintaxis para agregar y quitar usuarios seleccionados.

También puede usar el parámetro  _Users_ para especificar un grupo de roles del portal de cumplimiento. Así, podrá crear un grupo de roles personalizado y, a continuación, asignar a ese grupo de roles un filtro de permisos de búsqueda. Por ejemplo, supongamos que tiene un grupo de roles personalizado para los administradores de exhibición de documentos electrónicos de la sede en los Estados Unidos de una compañía multinacional. Puede usar el parámetro  _Users_ para especificar este grupo de roles (mediante la propiedad Name del grupo de roles) y, a continuación, usar el parámetro  _Filter_ para permitir que solo se busquen buzones en LOS EE. UU. Con este parámetro no es posible especificar grupos de distribución.

### <a name="filters"></a>Filtros

El parámetro  _Filters_ especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear tres tipos de filtros diferentes:

- **Filtrado de Buzón y OneDrive:** Este tipo de filtro especifica los buzones y las cuentas de OneDrive que los usuarios asignados (especificados por el parámetro  _Users_ ) pueden buscar. La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde  _MailboxPropertyName_ especifica una propiedad mailbox usada para limitar los buzones que se pueden buscar. Por ejemplo, el filtro  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` de buzón de correo permitiría al usuario asignado este filtro buscar solo los buzones que tienen el valor "OttawaUsers" en la propiedad CustomAttribute10.  Cualquier propiedad de destinatario filtrable compatible se puede usar para la propiedad  _MailboxPropertyName_ . Para obtener una lista de las propiedades admitidas, vea [Propiedades filtrables para el parámetro -RecipientFilter](/powershell/exchange/recipientfilter-properties).

- **Filtrado de contenido de buzón de correo:** Este tipo de filtro se aplica al contenido que se puede buscar. Especifica el contenido del buzón que los usuarios asignados pueden buscar. La sintaxis de este tipo de filtro es **MailboxContent_**_SearchablePropertyName_, donde  _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda. Por ejemplo, el filtro `"MailboxContent_Recipients  -like 'contoso.com'"` de contenido del buzón de correo permitiría que el usuario asignado a este filtro solo buscara los mensajes enviados a los destinatarios en el dominio contoso.com.  Para obtener una lista de las propiedades de correo electrónico que se pueden buscar, vea [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).

- **Filtrado de contenido de sitio y sitio:** Hay dos filtros relacionados con el sitio de SharePoint y OneDrive para la Empresa que puede usar para especificar qué sitio o contenido de sitio pueden buscar los usuarios asignados:

  - **Sitio\_** _SearchableSiteProperty_
  - **SiteContent\_** _SearchableSiteProperty_

  Estos dos filtros son intercambiables. Por ejemplo, `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` y  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` devuelve los mismos resultados. Para obtener una lista de las propiedades de sitio que se pueden buscar, vea [Información general sobre las propiedades rastreadas y administradas en SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Las propiedades marcadas con **sí** en la columna **Consultable** se pueden usar para crear un filtro de contenido de sitio o sitio.

### <a name="examples-of-changing-search-permissions-filters"></a>Ejemplos de cambio de filtros de permisos de búsqueda

En estos ejemplos se muestra cómo usar los cmdlets **Get-ComplianceSecurityFilter** y **Set-ComplianceSecurityFilter** para agregar o quitar un usuario a la lista existente de usuarios a los que está asignado el filtro. Al agregar o quitar usuarios de un filtro, especifique el usuario mediante su dirección SMTP.

En este ejemplo se agrega un usuario al filtro.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

En este ejemplo se quita un usuario del filtro.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter** se usa para eliminar un filtro de búsqueda. Use el parámetro  _FilterName_ para especificar el filtro que desea eliminar.

## <a name="more-information"></a>Más información

- **¿Cómo funciona el filtrado de permisos de búsqueda?** El filtro de permisos se anexa a la consulta de búsqueda cuando se ejecuta una búsqueda. El operador booleano **AND** une el filtro de permisos a la consulta de búsqueda. La lógica de consulta para la consulta de búsqueda y el filtro de permisos tendría este aspecto:

  ```text
  <SearchQuery> AND <PermissionsFilter>
  ```

  Por ejemplo, tiene un filtro de permisos que permite a Bob realizar todas las acciones de búsqueda en los buzones de los miembros del grupo de distribución Trabajadores. A continuación, Bob ejecuta una búsqueda en todos los buzones de la organización con la consulta  `sender:jerry@adatum.com`de búsqueda . Dado que el filtro de permisos y la consulta de búsqueda se combinan lógicamente con un operador **AND** , la búsqueda devuelve cualquier mensaje enviado por jerry@adatum.com a cualquier miembro del grupo de distribución Trabajos.

- **¿Qué ocurre si tiene varios filtros de permisos de búsqueda?** En una consulta de búsqueda, los operadores booleanos **OR** combinan varios filtros de permisos. Por lo tanto, los resultados se devolverán si alguno de los filtros es true. En una búsqueda, el operador **AND** combina todos los filtros (combinados por operadores **OR**) con la consulta de búsqueda.

  ```text
  <SearchQuery> AND  (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>)
  ```

  Tomemos el ejemplo anterior, donde un filtro de búsqueda permite a Bob buscar solo en los buzones de los miembros del grupo de distribución Trabajadores. A continuación, creamos otro filtro que impide que Bob busque en el buzón de Phil ("Mailbox_Alias -ne 'Phil'"). Y supongamos también que Phil es miembro del grupo Trabajadores. Cuando Bob ejecuta una búsqueda (del ejemplo anterior) en todos los buzones de la organización, los resultados de la búsqueda se devuelven para el buzón de Phil aunque haya aplicado el filtro para evitar que Bob busque en el buzón de Phil. Esto se debe a que el primer filtro, que permite a Bob buscar en el grupo Workers, es true. Y como Phil es miembro del grupo Trabajadores, Bob puede buscar en el buzón de Phil.

- **¿Funciona el filtrado de permisos de búsqueda para buzones inactivos?** Sí, puede usar filtros de contenido de buzón y buzón para limitar quién puede buscar buzones inactivos en su organización. Al igual que un buzón normal, un buzón inactivo debe configurarse con la propiedad recipient que se usa para crear un filtro de permisos. Si es necesario, puede usar el comando **Get-Mailbox -InactiveMailboxOnly** para mostrar las propiedades de los buzones inactivos. Para obtener más información, consulte [Creación y administración de buzones inactivos](create-and-manage-inactive-mailboxes.md).

- **¿Funciona el filtrado de permisos de búsqueda para carpetas públicas?** No. Como se explicó anteriormente, el filtrado de permisos de búsqueda no se puede usar para limitar quién puede buscar en carpetas públicas en Exchange. Por ejemplo, los elementos de las ubicaciones de carpetas públicas no se pueden excluir de los resultados de búsqueda mediante un filtro de permisos.

- **¿Permite que un usuario busque en todas las ubicaciones de contenido de un servicio específico también impedir que busque ubicaciones de contenido en un servicio diferente?** No. Como se explicó anteriormente, tiene que crear un filtro de permisos de búsqueda para impedir explícitamente que los usuarios busquen ubicaciones de contenido en un servicio específico (por ejemplo, impedir que un usuario busque en cualquier buzón de Exchange o en cualquier sitio de SharePoint). En otras palabras, la creación de un filtro de permisos de búsqueda que permita a un usuario buscar en todos los sitios de SharePoint de la organización no impide que ese usuario busque buzones de correo. Por ejemplo, para permitir que los administradores de SharePoint solo busquen sitios de SharePoint, tiene que crear un filtro que les impida buscar buzones. De forma similar, para permitir que los administradores de Exchange solo busquen buzones, debe crear un filtro que les impida buscar sitios.

- **¿Cuentan los filtros de permisos de búsqueda con respecto a los límites de caracteres de consulta de búsqueda?** Sí. Los filtros de permisos de búsqueda cuentan con el límite de caracteres para las consultas de búsqueda. Para obtener más información, vea [Límites en eDiscovery (Premium).](limits-ediscovery20.md)

**¿Cuál es el número máximo de filtros de permisos de búsqueda que se pueden crear en una organización?**

No hay ningún límite en el número de filtros de permisos de búsqueda que se pueden crear en una organización. Sin embargo, una consulta de búsqueda puede tener un máximo de 100 condiciones. En este caso, una condición se define como algo que está conectado a la consulta por un operador booleano (como **AND**, **OR** y **NEAR**). El límite del número de condiciones incluye la propia consulta de búsqueda y todos los filtros de permisos de búsqueda que se aplican al usuario que ejecuta la búsqueda. Por lo tanto, cuantos más filtros de permisos de búsqueda tenga (especialmente si estos filtros se aplican al mismo usuario o grupo de usuarios), mejor será la posibilidad de superar el número máximo de condiciones para una búsqueda.

Para comprender cómo funciona este límite, debe comprender que se anexa un filtro de permisos de búsqueda a la consulta de búsqueda cuando se ejecuta una búsqueda. El operador booleano **AND** une un filtro de permisos de búsqueda a la consulta de búsqueda. La lógica de consulta de la consulta de búsqueda y un único filtro de permisos de búsqueda tendrían este aspecto:

```text
<SearchQuery> AND <PermissionsFilter>
```

El operador **booleano OR** combina varios filtros de permisos de búsqueda y, a continuación, el operador **AND** conecta esas condiciones a la consulta de búsqueda.

La lógica de consulta para la consulta de búsqueda y varios filtros de permisos de búsqueda tendría este aspecto:

```text
<SearchQuery> AND (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>...)
```

Es posible que la propia consulta de búsqueda conste de varias condiciones conectadas por operadores booleanos. Cada condición de la consulta de búsqueda también contaría con el límite de 100 condiciones.

Además, el número de filtros de permisos de búsqueda anexados a una consulta depende del usuario que ejecuta la búsqueda. Cuando un usuario específico ejecuta una búsqueda, los filtros de permisos de búsqueda que se aplican al usuario (que se define mediante el parámetro _Users_ en el filtro) se anexan a la consulta. Su organización podría tener cientos de filtros de permisos de búsqueda, pero si se aplican más de 100 filtros a los mismos usuarios, es probable que se supere el límite de 100 condiciones cuando esos usuarios ejecuten búsquedas.

Hay una cosa más que debe tener en cuenta sobre el límite de la condición. El número de sitios de SharePoint específicos que se incluyen en los filtros de permisos de búsqueda o consulta de búsqueda también cuenta con respecto a este límite.

Para evitar que su organización alcance el límite de condiciones, mantenga el número de filtros de permisos de búsqueda en su organización a la menor cantidad posible para satisfacer sus requisitos empresariales.