---
title: Configurar el filtrado de permisos para Búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Use el filtrado de permisos de búsqueda de contenido para permitir que un administrador de exhibición de documentos electrónicos busque solo un subconjunto de buzones y sitios de la organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c36263466e103c0401e51b42b5d7ec3f6e2b4f9c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245353"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurar el filtrado de permisos para Búsqueda de contenido

Puede usar el filtrado de permisos de búsqueda para permitir que un administrador de exhibición de documentos electrónicos busque solo un subconjunto de buzones y sitios de la organización. También puede utilizar el filtrado de permisos para permitir que ese mismo administrador de exhibición de documentos electrónicos busque solo contenido de los buzones o los sitios que cumpla unos criterios concretos de búsqueda. Por ejemplo, puede permitir que un administrador de exhibición de documentos electrónicos busque solo en los buzones de usuarios de un departamento o una ubicación en concreto. Para ello, cree un filtro que use un filtro de destinatarios admitido para limitar los buzones que un usuario o grupo de usuarios específicos pueden buscar. También puede crear un filtro que especifique qué contenido de buzón puede buscar un usuario. Para ello, debe crear un filtro que utilice una propiedad de mensaje que pueda buscarse. Del mismo modo, puede permitir que un administrador de exhibición de documentos electrónicos busque solo sitios SharePoint específicos de la organización. Para hacerlo, debe crear un filtro que limite en qué sitio puede buscarse. También puede crear un filtro que especifique qué contenido del sitio puede buscarse. Para ello, debe crear un filtro que utilice una propiedad de sitio que pueda buscarse.

También puede usar el filtrado de permisos de búsqueda para crear límites lógicos (denominados límites de *cumplimiento)* dentro de una organización que controlan las ubicaciones de contenido de usuario (como buzones, sitios de SharePoint y cuentas de OneDrive) que los administradores de exhibición de documentos electrónicos específicos pueden buscar. Para obtener más información, vea [Set up compliance boundaries for eDiscovery investigations in Office 365](tagging-and-assessment-in-advanced-ediscovery.md).
  
El filtrado de permisos de búsqueda es compatible con la característica Búsqueda de contenido en el Centro de seguridad & cumplimiento. Estos cuatro cmdlets permiten configurar y administrar filtros de permisos de búsqueda:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Requisitos para configurar el filtrado de permisos

- Para ejecutar los cmdlets de filtro de seguridad de cumplimiento, debe ser miembro del grupo de roles Administración de la organización en el Centro de seguridad & cumplimiento. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Debe conectarse a PowerShell Exchange Online y security & Compliance Center para usar los cmdlets de filtro de seguridad de cumplimiento. Esto es necesario porque estos cmdlets requieren acceso a las propiedades del buzón de correo, por lo que debe conectarse a Exchange Online PowerShell. Vea los pasos en la sección siguiente.

- Consulte la sección [More information](#more-information) para obtener información adicional acerca de los filtros de permisos de búsqueda.

- El filtrado de permisos de búsqueda se aplica a los buzones inactivos, lo que significa que puede usar el filtrado de contenido de buzones y buzones para limitar quién puede buscar en un buzón inactivo. Vea la [sección Más información](#more-information) para obtener información adicional sobre el filtrado de permisos y los buzones inactivos.

- El filtrado de permisos de búsqueda no se puede usar para limitar quién puede buscar carpetas públicas en Exchange.

- No hay ningún límite en el número de filtros de permisos de búsqueda que se pueden crear en una organización. Pero el rendimiento de la búsqueda se verá afectado cuando haya más de 100 filtros de permisos de búsqueda. Para que el número de filtros de permisos de búsqueda en la organización sea lo más pequeño posible, cree filtros que combinen reglas para Exchange, SharePoint y OneDrive en un único filtro siempre que sea posible.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Conectar powerShell Exchange Online y security & Compliance Center en una sola sesión

Para poder ejecutar correctamente el script en esta sección, debe descargar e instalar el módulo Exchange Online PowerShell V2. Para obtener información, vea [Acerca de Exchange Online módulo de PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

1. Guarde el texto siguiente en un archivo Windows PowerShell script mediante un sufijo de nombre de archivo **de.ps1**. Por ejemplo, puede guardarlo en un archivo denominado **ConnectEXO-SCC.ps1**.

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. En el equipo local, abra Windows PowerShell, vaya a la carpeta donde se encuentra el script que creó en el paso anterior y, a continuación, ejecute el script; por ejemplo:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

¿Cómo se sabe si se ha completado correctamente? Después de ejecutar el script, los cmdlets de Exchange Online y Security & Compliance PowerShell se importan a la sesión Windows PowerShell local. Si no se muestra ningún error, la conexión se habrá establecido correctamente. Una prueba rápida es ejecutar un cmdlet Exchange Online y Security & Compliance Center. Por ejemplo, puede ejecutar y **Get-Mailbox** y **Get-ComplianceSearch**.

Para solucionar errores de conexión de PowerShell, vea:

- [Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Conectarse a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter** se usa para crear un filtro de permisos de búsqueda. En la tabla siguiente se describen los parámetros de este cmdlet. Todos los parámetros son necesarios para crear un filtro de seguridad de cumplimiento.
  
| Parámetro | Descripción |
|:-----|:-----|
| _Action_ <br/> | El  _parámetro Action_ especifica ese tipo de acción de búsqueda a la que se aplica el filtro. Las acciones de Búsqueda de contenido posibles son:  <br/><br/> **Exportar:** El filtro se aplica al exportar resultados de búsqueda.  <br/> **Vista previa:** El filtro se aplica al obtener una vista previa de los resultados de la búsqueda.  <br/> **Purgar:** El filtro se aplica al purgar resultados de búsqueda.  <br/> **Buscar:** El filtro se aplica al ejecutar una búsqueda.  <br/> **Todos:** El filtro se aplica a todas las acciones de búsqueda.  <br/> |
| _FilterName_ <br/> |El  _parámetro FilterName_ especifica el nombre del filtro de permisos. Este nombre sirve para identificar un filtro al utilizar los cmdlets **Get ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** y **Remove-ComplianceSecurityFilter**.  <br/> |
| _Filters_ <br/> | El  _parámetro Filters_ especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear tres tipos de filtros diferentes:  <br/><br/> **Filtrado de buzones:** Este tipo de filtro especifica los buzones que los usuarios asignados (especificados por el  _parámetro Users)_ pueden buscar. La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde  _MailboxPropertyName_ especifica una propiedad de buzón usada para establecer el ámbito de los buzones que se pueden buscar. Por ejemplo, el filtro de buzones de correo permitiría al usuario asignado a este filtro buscar solo los buzones que tienen el valor  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" en la propiedad CustomAttribute10.  <br/>  Cualquier propiedad de destinatario filtrable compatible se puede usar para la _propiedad MailboxPropertyName._ Para obtener una lista de las propiedades admitidas, vea [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties).  <br/><br/> **Filtrado de contenido de buzones:** Este tipo de filtro se aplica al contenido que se puede buscar. Especifica el contenido del buzón que los usuarios asignados pueden buscar. La sintaxis de este tipo de filtro es **MailboxContent_** _SearchablePropertyName: value_, donde  _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda de contenido. Por ejemplo, el filtro de contenido de buzón de correo permitiría al usuario asignado este filtro buscar solo los mensajes enviados a los destinatarios del  `MailboxContent_recipients:contoso.com` contoso.com correo.  <br/>  Para obtener una lista de propiedades de mensaje que se pueden buscar, vea Consultas de palabras clave y condiciones [de búsqueda para Búsqueda de contenido.](keyword-queries-and-search-conditions.md) <br/> <br/> **Importante:**  Un filtro de búsqueda único no puede contener un filtro de buzón y un filtro de contenido de buzón. Para combinarlos en un solo filtro, debe usar una [lista de filtros](#using-a-filters-list-to-combine-filter-types).  Pero un filtro puede contener una consulta más compleja del mismo tipo. Por ejemplo,  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **Filtrado de contenido de sitio y sitio:** Hay dos filtros SharePoint y OneDrive para la Empresa relacionados con el sitio que puede usar para especificar qué sitio o contenido de sitio pueden buscar los usuarios asignados:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Estos dos filtros son intercambiables. Por ejemplo,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` y devuelva los mismos  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` resultados. Pero para ayudarle a identificar lo que hace un filtro, puede usar para especificar propiedades relacionadas con el sitio (como una dirección URL de sitio) y para especificar propiedades relacionadas con el contenido (como tipos de  `Site_`  `SiteContent_` documento). Por ejemplo, el filtro permitiría al usuario que asignó este filtro solo buscar  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` contenido en la colección de https://contoso.sharepoint.com/sites/doctors sitios. El filtro permitiría al usuario que asignó este filtro solo buscar documentos de  `"SiteContent_FileExtension -eq 'docx'"` Word (Word 2007 y versiones posteriores).  <br/><br/>  Para obtener una lista de propiedades de sitio que se pueden buscar, vea [Overview of crawled and managed properties in SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Las propiedades marcadas **con sí** en la **columna** Consultable se pueden usar para crear un filtro de contenido de sitio o sitio.  <br/><br/> **Importante:** Debe crear un filtro de permisos de búsqueda para impedir explícitamente que los usuarios busquen ubicaciones de contenido en un servicio específico (por ejemplo, impedir que un usuario busque en cualquier buzón de Exchange o en cualquier sitio SharePoint). En otras palabras, la creación de un filtro de permisos de búsqueda que permite a un usuario buscar en todos los SharePoint de la organización no impide que ese usuario busque buzones. Por ejemplo, para permitir que SharePoint administradores solo busquen sitios SharePoint, debe crear un filtro que les impida buscar buzones. Del mismo modo, para permitir que Exchange administradores solo busquen buzones de correo, debe crear un filtro que les impida buscar sitios.           |
| _Users_ <br/> |El  _parámetro Users_ especifica los usuarios que obtienen este filtro aplicado a sus búsquedas de contenido. Identifique a los usuarios por su alias o su dirección SMTP principal. Se pueden especificar varios valores separados por comas, o bien puede asignar el filtro a todos los usuarios con el valor **Todos**.  <br/> También puede usar el parámetro  _Users_ para especificar un grupo de roles del Centro de & seguridad. Así, podrá crear un grupo de roles personalizado y, a continuación, asignar a ese grupo de roles un filtro de permisos de búsqueda. Por ejemplo, supongamos que tiene un grupo de roles personalizado para los administradores de exhibición de documentos electrónicos de la sede en los Estados Unidos de una compañía multinacional. Puede usar el parámetro  _Users_ para especificar este grupo de roles (mediante la propiedad Name del grupo de roles) y, a continuación, usar el parámetro  _Filter_ para permitir que solo se busquen buzones en Estados Unidos.  <br/> Con este parámetro no es posible especificar grupos de distribución.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Uso de una lista de filtros para combinar tipos de filtro

Una *lista de filtros* es un filtro que incluye un filtro de buzón de correo y un filtro de sitio separado por una coma. El uso de una lista de filtros es el único método admitido para combinar diferentes tipos de filtros. En el ejemplo siguiente, observe que una coma separa los filtros **Buzón** **y** Sitio:

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Cuando se procesa un filtro que contiene una lista de filtros durante la ejecución de una búsqueda de contenido, se crean dos filtros de permisos de búsqueda a partir de la lista de filtros: uno para cada filtro separado por una coma. Por lo tanto, en el ejemplo anterior, se crearía un filtro de permisos de búsqueda de buzones de correo y un filtro de permisos de búsqueda de sitio. 

Una alternativa al uso de una lista de filtros sería crear dos filtros de permisos de búsqueda independientes. Por lo tanto, en el ejemplo anterior, crearía un filtro para el atributo de buzón y un filtro para el atributo site. En cualquier caso, los resultados son los mismos. El uso de una lista de filtros o la creación de filtros de permisos de búsqueda independientes es una cuestión de preferencia.

Tenga en cuenta lo siguiente sobre cómo usar una lista de filtros:

- Debe usar una lista de filtros para crear un filtro que incluya un filtro **buzón** de correo y un filtro **MailboxContent.** 

- Como se ha sugerido anteriormente, no tiene que usar una lista de filtros para incluir un filtro **Site** y Un filtro **SiteContent** en un único filtro de permisos de búsqueda. Por ejemplo, puede combinar los filtros **Site** y **SiteContent** con **un operador -or.**

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Cada componente de una lista de filtros puede contener una sintaxis de filtro compleja. Por ejemplo, los filtros de buzones y sitios pueden contener varios filtros separados por **un operador -or:**

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Ejemplos de creación de filtros de permisos de búsqueda

Vea a continuación ejemplos del uso del cmdlet **New-ComplianceSecurityFilter** para crear un filtro de permisos de búsqueda. 
  
Este ejemplo permite al usuario annb@contoso.com realizar todas las acciones de búsqueda de contenido solo para buzones de correo en Canadá. Este filtro contiene el código de país numérico de tres dígitos correspondiente a Canadá según la ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

En este ejemplo se permite que los usuarios donh y suzanf busquen solo en los buzones con el valor 'Marketing' para la propiedad de buzón CustomAttribute1.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

En este ejemplo se permite que los miembros del grupo de roles "Administradores de detección de EE. UU." realicen todas las acciones de Búsqueda de contenido solo en los buzones de Estados Unidos. Este filtro contiene el código de país numérico de tres dígitos correspondiente a Estados Unidos según la ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

En este ejemplo se permite a los miembros del grupo de roles administrador de exhibición de documentos electrónicos buscar solo los buzones de los miembros del grupo de distribución Usuarios de Ottawa. El cmdlet Get-DistributionGroup en Exchange Online PowerShell se usa para buscar los miembros del grupo Usuarios de Ottawa.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

En este ejemplo se evita que cualquier usuario elimine contenido de los buzones de los miembros del grupo de distribución Executive Team. El cmdlet Get-DistributionGroup en Exchange Online PowerShell se usa para buscar los miembros del grupo de equipos ejecutivos.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

En este ejemplo, los miembros del OneDrive de roles personalizado de administradores de exhibición de documentos electrónicos solo pueden buscar contenido en OneDrive para la Empresa de la organización.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Para restringir a los usuarios a buscar sitios específicos, use el filtro  `Site_Path` , como se muestra en el ejemplo anterior. El  `Site_Site` uso no funcionará. 
  
En este ejemplo se limita al usuario a realizar todas las acciones de Búsqueda de contenido solo en los mensajes de correo electrónico enviados durante el año natural 2015.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

De forma parecida al ejemplo anterior, este ejemplo limita al usuario a realizar todas las acciones de Búsqueda de contenido solo en los documentos que se modificaron por última vez durante el año natural 2015.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

En este ejemplo se impide que los miembros del grupo de roles "administradores de OneDrive de detección" realicen acciones de búsqueda de contenido en cualquier buzón de la organización. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

En este ejemplo se impide que cualquier persona de la organización busque mensajes de correo electrónico enviados o recibidos por janets o sarad.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

En este ejemplo se usa una lista de filtros para combinar filtros de buzones y sitios.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** se usa para devolver una lista de filtros de permisos de búsqueda. Use el  _parámetro FilterName_ para devolver información de un filtro de búsqueda específico. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** se usa para modificar un filtro de permisos de búsqueda existente. El único parámetro necesario es  _FilterName_. 
  
| Parámetro | Descripción |
|:-----|:-----|
| _Action_| El  _parámetro Action_ especifica ese tipo de acción de búsqueda a la que se aplica el filtro. Las acciones de Búsqueda de contenido posibles son: <br/><br/> **Exportar:** El filtro se aplica al exportar resultados de búsqueda.  <br/> **Vista previa:** El filtro se aplica al obtener una vista previa de los resultados de la búsqueda.  <br/> **Purgar:** El filtro se aplica al purgar resultados de búsqueda.  <br/> **Buscar:** El filtro se aplica al ejecutar una búsqueda.  <br/> **Todos:** El filtro se aplica a todas las acciones de búsqueda.  <br/> |
| _FilterName_|El  _parámetro FilterName_ especifica el nombre del filtro de permisos. |
| _Filters_| El  _parámetro Filters_ especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear dos tipos diferentes de filtros: <br/><br/>**Filtrado de buzones:** Este tipo de filtro especifica los buzones que los usuarios asignados (especificados por el  _parámetro Users)_ pueden buscar. La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde  _MailboxPropertyName_ especifica una propiedad de buzón usada para establecer el ámbito de los buzones que se pueden buscar. Por ejemplo, el filtro de buzones de correo permitiría al usuario asignado a este filtro buscar solo los buzones que tienen el valor  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" en la propiedad CustomAttribute10.  Cualquier propiedad de destinatario filtrable compatible se puede usar para la _propiedad MailboxPropertyName._ Para obtener una lista de las propiedades admitidas, vea [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties). <br/><br/>**Filtrado de contenido de buzones:** Este tipo de filtro se aplica al contenido que se puede buscar. Especifica el contenido del buzón que los usuarios asignados pueden buscar. La sintaxis de este tipo de filtro es **MailboxContent_** _SearchablePropertyName:value_, donde  _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda de contenido. Por ejemplo, el filtro de contenido de buzón de correo permitiría al usuario asignado este filtro buscar solo los mensajes enviados a los destinatarios del  `MailboxContent_recipients:contoso.com` contoso.com correo.  Para obtener una lista de propiedades de mensaje que se pueden buscar, vea [Consultas de palabras clave para búsqueda de contenido](keyword-queries-and-search-conditions.md). <br/><br/>**Filtrado de contenido de sitio y sitio:** Hay dos filtros SharePoint y OneDrive para la Empresa relacionados con el sitio que puede usar para especificar qué sitio o contenido de sitio pueden buscar los usuarios asignados: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>Estos dos filtros son intercambiables. Por ejemplo,  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` y devuelve los mismos  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` resultados. Pero para ayudarle a identificar lo que hace un filtro, puede usar para especificar propiedades relacionadas con el sitio (como una dirección URL de sitio) y para especificar propiedades relacionadas con el contenido (como tipos de  `Site_`  `SiteContent_` documento). Por ejemplo, el filtro permitiría al usuario que asignó este filtro solo buscar  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` contenido en la colección de https://contoso.spoppe.com/sites/doctors sitios. El filtro permitiría al usuario que asignó este filtro solo buscar documentos de  `"SiteContent_FileExtension -eq 'docx'"` Word (Word 2007 y versiones posteriores).  <br/><br/>Para obtener una lista de propiedades de sitio que se pueden buscar, vea [Overview of crawled and managed properties in SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Las propiedades marcadas **con sí** en la **columna** Consultable se pueden usar para crear un filtro de contenido de sitio o sitio. <br/><br/>          |
| _Users_|El  _parámetro Users_ especifica los usuarios que obtienen este filtro aplicado a sus búsquedas de contenido. Dado que se trata de una propiedad de varios valores, la especificación de un usuario o grupo de usuarios con este parámetro sobrescribe la lista de usuarios existente. Vea los ejemplos siguientes para ver la sintaxis para agregar y quitar usuarios seleccionados. <br/><br/>También puede usar el parámetro  _Users_ para especificar un grupo de roles del Centro de & seguridad. Así, podrá crear un grupo de roles personalizado y, a continuación, asignar a ese grupo de roles un filtro de permisos de búsqueda. Por ejemplo, supongamos que tiene un grupo de roles personalizado para los administradores de exhibición de documentos electrónicos de la sede en los Estados Unidos de una compañía multinacional. Puede usar el parámetro  _Users_ para especificar este grupo de roles (mediante la propiedad Name del grupo de roles) y, a continuación, usar el parámetro  _Filter_ para permitir que solo se busquen buzones en Estados Unidos. <br/><br/>Con este parámetro no es posible especificar grupos de distribución. |

## <a name="examples-of-changing-search-permissions-filters"></a>Ejemplos de cambio de filtros de permisos de búsqueda

En estos ejemplos se muestra cómo usar los cmdlets **Get-ComplianceSecurityFilter** y **Set-ComplianceSecurityFilter** para agregar o quitar un usuario a la lista de usuarios existente a la que está asignado el filtro. Al agregar o quitar usuarios de un filtro, especifique el usuario mediante su dirección SMTP. 
  
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

**Remove-ComplianceSecurityFilter** se usa para eliminar un filtro de búsqueda. Use el  _parámetro FilterName_ para especificar el filtro que desea eliminar. 
  
## <a name="more-information"></a>Más información

- **¿Cómo funciona el filtrado de permisos de búsqueda?** El filtro de permisos se agrega a la consulta de búsqueda cuando se ejecuta una búsqueda de contenido. El filtro de permisos se une a la consulta de búsqueda mediante el **operador booleano AND.** Por ejemplo, tiene un filtro de permisos que permite a Bob realizar todas las acciones de búsqueda en los buzones de los miembros del grupo de distribución Trabajadores. A continuación, Bob ejecuta una búsqueda de contenido en todos los buzones de la organización con la consulta de búsqueda  `sender:jerry@adatum.com` . Dado que el filtro de permisos y la consulta de búsqueda se combinan lógicamente por un operador **AND,** la búsqueda devuelve cualquier mensaje enviado por jerry@adatum.com a cualquier miembro del grupo de distribución Trabajadores. 
    
- **¿Qué sucede si tiene varios filtros de permisos de búsqueda?** En una consulta de búsqueda de contenido, los operadores **booleanos OR** combinan varios filtros de permisos. Por lo tanto, los resultados se devolverán si alguno de los filtros es true. En una búsqueda de contenido, el operador AND combina todos los filtros (combinados por operadores **OR)** con la consulta **de** búsqueda. Tomemos el ejemplo anterior, donde un filtro de búsqueda permite a Bob buscar solo los buzones de los miembros del grupo de distribución Trabajadores. A continuación, creamos otro filtro que impide que Bob busque en el buzón de Phil ("Mailbox_Alias -ne 'Phil'"). Además, supongamos que Phil es miembro del grupo Trabajadores. Cuando Bob ejecuta una búsqueda de contenido (del ejemplo anterior) en todos los buzones de la organización, los resultados de la búsqueda se devuelven para el buzón de Correo de Phil aunque haya aplicado un filtro para impedir que Bob busque el buzón de Phil. Esto se debe a que el primer filtro, que permite a Bob buscar en el grupo Trabajadores, es true. Y como Phil es miembro del grupo Trabajadores, Bob puede buscar en el buzón de Phil. 
    
- **¿Funciona el filtrado de permisos de búsqueda para buzones inactivos?** Sí, puede usar filtros de contenido de buzones y buzones de correo para limitar quién puede buscar buzones inactivos en su organización. Al igual que un buzón normal, un buzón inactivo debe configurarse con la propiedad recipient que se usa para crear un filtro de permisos. Si es necesario, puede usar el comando **Get-Mailbox -InactiveMailboxOnly** para mostrar las propiedades de los buzones inactivos. Para obtener más información, vea [Create and manage inactive mailboxes in Office 365](create-and-manage-inactive-mailboxes.md).
    
- **¿Funciona el filtrado de permisos de búsqueda para carpetas públicas?** No. Como se explicó anteriormente, el filtrado de permisos de búsqueda no se puede usar para limitar quién puede buscar carpetas públicas en Exchange. Por ejemplo, los elementos de las ubicaciones de carpetas públicas no se pueden excluir de los resultados de búsqueda mediante un filtro de permisos. 

- **¿Permitir que un usuario busque en todas las ubicaciones de contenido de un servicio específico también impide que busquen ubicaciones de contenido en un servicio diferente?** No. Como se explicó anteriormente, debe crear un filtro de permisos de búsqueda para impedir explícitamente que los usuarios busquen ubicaciones de contenido en un servicio específico (como impedir que un usuario busque en cualquier buzón de Exchange o en cualquier sitio SharePoint). En otras palabras, la creación de un filtro de permisos de búsqueda que permite a un usuario buscar en todos los SharePoint de la organización no impide que ese usuario busque buzones. Por ejemplo, para permitir que SharePoint administradores solo busquen sitios SharePoint, debe crear un filtro que les impida buscar buzones. Del mismo modo, para permitir que Exchange administradores solo busquen buzones de correo, debe crear un filtro que les impida buscar sitios.

- **¿Cuentan los filtros de permisos de búsqueda con respecto a los límites de caracteres de consulta de búsqueda?** Sí. Los filtros de permisos de búsqueda cuentan con el límite de caracteres para las consultas de búsqueda. Para obtener más información, vea [Limits in Advanced eDiscovery](limits-ediscovery20.md).

