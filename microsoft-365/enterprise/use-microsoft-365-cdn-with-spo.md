---
title: Usar la red de entrega de contenido (CDN) de Office 365 con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Obtenga información sobre cómo usar la red de entrega de contenido (CDN) de Office 365 para acelerar la entrega de los activos de SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693647"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online

Puede usar la red de entrega de contenido (CDN) de Office 365 integrada para hospedar archivos estáticos y mejorar el rendimiento de las páginas de SharePoint Online. La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia. Además, la red CDN de Office 365 usa el [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para mejorar la compresión y la canalización HTTP. La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.

> [!NOTE]
> La red CDN de Office 365 solo está disponible para los inquilinos en la **nube de producción** (en todo el mundo). Actualmente, los inquilinos de las nubes del Gobierno de Estados Unidos, China y Alemania no admiten la red CDN de Office 365.

La CDN de Office 365 se compone de varias redes CDN que permite hospedar archivos estáticos en varias ubicaciones u _orígenes_ y a realizar la entrega desde redes de alta velocidad globales. Según el tipo de contenido que quiera hospedar en la CDN de Office 365, puede agregar orígenes **públicos**, **privados** o ambos. Consulta [Elegir si cada origen debe ser público o privado](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) para obtener más información sobre la diferencia entre orígenes públicos y privados.

![Diagrama conceptual de la red CDN de Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceptual de la red CDN de Office 365")

Si ya está familiarizado con el modo en que funcionan las CDN, solo tiene que completar unos pocos pasos para habilitar la red CDN de Office 365 para su espacio empresarial. En este tema se describe cómo hacerlo. Sigue leyendo para obtener información sobre cómo empezar a hospedar tus activos estáticos.

> [!TIP]
> Hay otras CDN hospedadas por Microsoft que se pueden usar con Office 365 para escenarios de uso especializado, pero no se abordan en este tema porque están fuera del ámbito de la red CDN de Office 365. Para obtener más información, vea [Otras CDN de Microsoft.](content-delivery-networks.md#other-microsoft-cdns)

 **Vuelva a la [planeación de red y al ajuste del rendimiento de Office 365.](https://aka.ms/tune)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Información general sobre cómo trabajar con la red CDN de Office 365 en SharePoint Online

Para configurar la red CDN de Office 365 para su organización, siga estos pasos básicos:

+ [Planear la implementación de la red CDN de Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Determine qué activos estáticos desea hospedar en la red CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determine dónde desea almacenar los activos.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Esta ubicación puede ser un sitio, biblioteca o carpeta de SharePoint y se denomina _origen._
  + [Elige si cada origen debe ser público o privado.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) Puede agregar varios orígenes de tipos públicos y privados.

+ Configurar y configurar la red CDN con PowerShell o la CLI de SharePoint Online

  + [Configurar y configurar la red CDN mediante el Shell de administración de SharePoint Online](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Configurar la red CDN con PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Configurar y configurar la red CDN con la CLI de Office 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Cuando complete este paso, tendrá:

  + Habilitó la red CDN para su organización.
  + Se agregaron los orígenes, identificando cada origen como público o privado.

Una vez que haya terminado con la configuración, puede administrar la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) con el tiempo:
  
+ Agregar, actualizar y quitar activos
+ Agregar y quitar orígenes
+ Configuración de directivas de red CDN
+ Si es necesario, deshabilitar la red CDN

Por último, consulte [Uso de los activos de la red CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) para obtener información sobre cómo obtener acceso a los activos de la red CDN desde orígenes públicos y privados.

Vea la solución de problemas de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) para obtener instrucciones sobre cómo resolver problemas comunes.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planear la implementación de la red CDN de Office 365

Antes de implementar la red CDN de Office 365 para su inquilino de Office 365, debe tener en cuenta los siguientes factores como parte del proceso de planeación.

  + [Determinar qué activos estáticos desea hospedar en la red CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determinar dónde quieres almacenar los activos](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Elegir si cada origen debe ser público o privado](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Determinar qué activos estáticos desea hospedar en la red CDN

En general, las CDN son más eficaces para hospedar activos _estáticos_ o activos que no cambian con mucha frecuencia. Una buena regla general es identificar los archivos que cumplen algunas o todas estas condiciones:

+ Archivos estáticos incrustados en una página (como scripts e imágenes) que pueden tener un impacto incremental significativo en los tiempos de carga de la página
+ Archivos de gran tamaño, como archivos ejecutables y archivos de instalación
+ Bibliotecas de recursos que admiten código del lado cliente

Por ejemplo, los archivos pequeños que se solicitan repetidamente, como imágenes de sitio y scripts, pueden mejorar significativamente el rendimiento de la representación del sitio y reducir de forma incremental la carga en los sitios de SharePoint Online al agregarlos a un origen de red CDN. Los archivos más grandes, como los ejecutables de instalación, se pueden descargar desde la red CDN, lo que proporciona un impacto positivo en el rendimiento y una reducción posterior de la carga en el sitio de SharePoint Online, incluso si no se tiene acceso a ellos con tanta frecuencia.

La mejora del rendimiento por archivo depende de muchos factores, como la proximidad del cliente al punto de conexión de red CDN más cercano, las condiciones transitorias en la red local, etc. Muchos archivos estáticos son bastante pequeños y se pueden descargar de Office 365 en menos de un segundo. Sin embargo, una página web puede contener muchos archivos incrustados con un tiempo de descarga acumulado de varios segundos. El servicio de estos archivos desde la red CDN puede reducir significativamente el tiempo de carga general de la página. Vea [¿Qué mejoras de rendimiento proporciona una red CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) para ver un ejemplo.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Determinar dónde quieres almacenar los activos

La red CDN recupera los activos de una ubicación denominada _origen._ Un origen puede ser un sitio de SharePoint, una biblioteca de documentos o una carpeta a la que se puede tener acceso mediante una dirección URL. Tiene una gran flexibilidad al especificar los orígenes de su organización. Por ejemplo, puede especificar varios orígenes o un único origen donde quiera colocar todos los activos de la red CDN. Puede elegir tener orígenes públicos o privados para su organización. La mayoría de las organizaciones elegirán implementar una combinación de las dos.

Puede crear un nuevo contenedor para sus orígenes, como carpetas o bibliotecas de documentos, y agregar archivos que desee que estén disponibles desde la red CDN. Este es un buen enfoque si tiene un conjunto específico de activos que desea que estén disponibles desde la red CDN y desea restringir el conjunto de activos de la red CDN solo a esos archivos en el contenedor.

También puede configurar una colección de sitios, un sitio, una biblioteca o una carpeta existentes como origen, lo que hará que todos los activos elegibles del contenedor estén disponibles desde la red CDN. Antes de agregar un contenedor existente como origen, es importante asegurarse de que conoce su contenido y permisos para que no exponga accidentalmente activos a usuarios anónimos o no autorizados.

Puede definir directivas _de red CDN_ para excluir contenido de sus orígenes de la red CDN. Las directivas de red CDN excluyen activos  en orígenes públicos o privados por atributos como el tipo de archivo y la clasificación de _sitios,_ y se aplican a todos los orígenes de CdnType (privado o público) que especifique en la directiva. Por ejemplo, si agrega un origen privado que consta de un sitio que contiene varios  subsitios, puede definir una directiva para excluir sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se aprotegerá desde la red CDN. La directiva se aplicará al contenido de _todos los_ orígenes privados que haya agregado a la red CDN.
  
Tenga en cuenta que, a mayor número de orígenes, mayor será el impacto en el tiempo que tarda el servicio de red CDN en procesar las solicitudes. Se recomienda limitar el número de orígenes tanto como sea posible.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Elegir si cada origen debe ser público o privado

Cuando identifica un origen, especifica si debe hacerse público _o_ _privado._ El acceso a los activos de la red CDN en orígenes públicos es anónimo y el contenido de la red CDN en orígenes privados se protege mediante tokens generados dinámicamente para una mayor seguridad. Independientemente de la opción que elija, Microsoft realiza todo el trabajo pesado por usted cuando se trata de la administración de la propia red CDN. Además, puede cambiar de opinión más adelante, después de configurar la red CDN e identificar sus orígenes.

Las opciones públicas y privadas proporcionan mejoras de rendimiento similares, pero cada una tiene atributos y ventajas únicos.

**Los** orígenes públicos dentro de la red CDN de Office 365 son accesibles de forma anónima y cualquier persona que tenga la dirección URL del activo puede tener acceso a los activos hospedados. Como el acceso al contenido en orígenes públicos es anónimo, solo debe usarlos para almacenar en caché contenido genérico y no confidencial, como archivos javascript, scripts, iconos e imágenes.

**Los** orígenes privados dentro de la red CDN de Office 365 proporcionan acceso privado al contenido del usuario, como bibliotecas de documentos de SharePoint Online, sitios e imágenes propietarias. El acceso al contenido en orígenes privados se protege mediante tokens generados dinámicamente para que solo puedan acceder a él los usuarios con permisos en la biblioteca de documentos original o la ubicación de almacenamiento. Los orígenes privados en la red CDN de Office 365 solo se pueden usar para el contenido de SharePoint Online y solo puede acceder a los activos en orígenes privados a través de la redirección desde su espacio empresarial de SharePoint Online.

Puede obtener más información sobre cómo funciona el acceso de la red CDN a los activos de un origen privado en Uso de [activos en orígenes privados.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Atributos y ventajas de hospedar activos en orígenes públicos
  
+ Cualquier persona puede acceder a los activos expuestos en un origen público de forma anónima.
    > [!IMPORTANT]
    > Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.
+ Si elimina un activo de un origen público, el activo podría continuar disponible durante un máximo de 30 días desde la memoria caché. Sin embargo, se invalidarán los vínculos a los activos en la red CDN en 15 minutos.
+ Si hospeda hojas de estilo (archivos CSS) en un origen público, puede usar las rutas relativas y URI dentro del código. Esto significa que puede hacer referencia a la ubicación de las imágenes de fondo y otros objetos con respecto a la ubicación del activo que está llamando.
+ Aunque puede integrar una dirección URL de un origen público, no se recomienda. El motivo de esto es que, si no está disponible el acceso a la red CDN, la dirección URL no resolverá automáticamente su organización en SharePoint Online y podría producir vínculos rotos y otros errores.
+ Los tipos de archivo predeterminados que se incluyen para orígenes públicos son .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2. Puede especificar tipos de archivo adicionales.
+ Puede configurar una directiva para excluir los activos identificados por las clasificaciones de sitio que especifique. Por ejemplo, puede elegir excluir todos los activos que están marcados como restringidos o confidenciales aunque sean un tipo de archivo permitido y se encuentren en un origen público.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Atributos y ventajas de hospedar activos en orígenes privados

+ Los orígenes privados solo se pueden usar para activos de SharePoint Online.
+ Los usuarios solo pueden acceder a los activos desde un origen privado si tienen permisos para acceder al contenedor. Se impide el acceso anónimo a estos activos.
+ Los activos en orígenes privados se deben hacer referencia desde el inquilino de SharePoint Online. El acceso directo a los activos de red CDN privada no funciona.
+ Si quita un activo del origen privado, el activo puede seguir estando disponible hasta una hora de la memoria caché; sin embargo, invalidaremos los vínculos al activo en la red CDN en un plazo de 15 minutos a partir de la eliminación del activo.
+ Los tipos de archivo predeterminados que se incluyen en el origen privado son .gif, .ico, .jpeg, .jpg, .js y .png. Puede especificar tipos de archivo adicionales.
+ Al igual que con los orígenes públicos, puede configurar una directiva para excluir los activos identificados por las clasificaciones de sitio que especifique, incluso si usa caracteres comodín para incluir todos los activos dentro de una carpeta o biblioteca de documentos.

Para obtener más información sobre por qué usar la red CDN de Office 365, los conceptos generales de la red CDN y otras redes CDN de Microsoft que puede usar con su inquilino de Office 365, vea Redes de entrega de [contenido.](content-delivery-networks.md)

### <a name="default-cdn-origins"></a>Orígenes predeterminados de la red CDN

A menos que especifique lo contrario, Office 365 configura algunos orígenes predeterminados automáticamente al habilitar la red CDN de Office 365. Si inicialmente opta por no aprovisionarlos, puede agregar estos orígenes después de completar la configuración. A menos que comprenda las consecuencias de omitir la configuración de los orígenes predeterminados y tenga una razón específica para hacerlo, debe permitir que se cree cuando habilite la red CDN.
  
Orígenes predeterminados de la red CDN privada:
  
+ \*/userphoto.aspx
+ \*/siteassets

Orígenes predeterminados de la red CDN pública:
  
+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ es un origen público predeterminado que se agregó al servicio de red CDN de Office 365 en diciembre de 2017. Este origen debe estar presente para que las soluciones de SharePoint Framework en la red CDN funcionen. Si habilitó la red CDN de Office 365 antes de diciembre de 2017 o si omitió la configuración de los orígenes predeterminados al habilitar la red CDN, puede agregar manualmente este origen. Para obtener más información, vea Mi elemento web del lado cliente o La solución [de SharePoint Framework no funciona.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Configurar y configurar la red CDN de Office 365 mediante el Shell de administración de SharePoint Online

Los procedimientos de esta sección requieren que use el Shell de administración de SharePoint Online para conectarse a SharePoint Online. Para obtener instrucciones, consulte [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Complete estos pasos para configurar y configurar la red CDN para hospedar los activos en SharePoint Online mediante el Shell de administración de SharePoint Online.

<details>
  <summary>Haga clic para expandir</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Permitir que su organización use la red CDN de Office 365

Antes de realizar cambios en la configuración de la red CDN del espacio empresarial, debe recuperar el estado actual de la configuración de la red CDN privada en su inquilino de Office 365. Conéctese al espacio empresarial mediante el Shell de administración de SharePoint Online:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Ahora use el cmdlet **Get-SPOTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

El estado de la red CDN para el CdnType especificado se mostrará en pantalla.

Use el cmdlet **Set-SPOTenantCdnEnabled** para permitir que su organización use la red CDN de Office 365. Puede permitir que su organización use orígenes públicos, privados o ambos a la vez. También puede configurar la red CDN para omitir la configuración de los orígenes predeterminados al habilitarla. Siempre puede agregar estos orígenes más adelante, como se describe en este tema.
  
En Windows PowerShell para SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Por ejemplo, para permitir que su organización use orígenes públicos y privados, escriba el siguiente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Para permitir que su organización use orígenes públicos y privados, pero omita la configuración de los orígenes predeterminados, escriba el siguiente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Vea los orígenes predeterminados de la red [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de los orígenes predeterminados.

Para permitir que su organización use orígenes públicos, escriba el siguiente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Para permitir que su organización use orígenes privados, escriba el siguiente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Para obtener más información acerca de este cmdlet, [vea Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Cambiar la lista de tipos de archivo para incluir en la red CDN de Office 365 (opcional)

> [!TIP]
> Al definir tipos de archivo mediante el cmdlet **Set-SPOTenantCdnPolicy,** se sobrescribe la lista definida actualmente. Si desea agregar tipos de archivo adicionales a la lista, use el cmdlet primero para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.
  
Use el cmdlet **Set-SPOTenantCdnPolicy** para definir tipos de archivo estáticos que se pueden hospedar en orígenes públicos y privados en la red CDN. De forma predeterminada, se permiten tipos de activos comunes, por ejemplo .css, .gif, .jpg y .js.

En Windows PowerShell para SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, debe escribir el comando:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Para obtener más información acerca de estos cmdlets, vea [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) y [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365 (opcional)

> [!TIP]
> Cuando se excluyen las clasificaciones de sitio mediante el cmdlet **Set-SPOTenantCdnPolicy,** se sobrescribe la lista definida actualmente. Si desea excluir clasificaciones de sitio adicionales, use el cmdlet primero para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.

Use el cmdlet **Set-SPOTenantCdnPolicy** para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN. De forma predeterminada, no se excluyen clasificaciones de sitio.

En Windows PowerShell para SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Para ver qué clasificaciones de sitio están restringidas actualmente, use el cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Las propiedades que se devolverán _son IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.

La _propiedad IncludeFileExtensions_ contiene la lista de extensiones de archivo que se van a servir desde la red CDN.

> [!NOTE]
> Las extensiones de archivo predeterminadas son diferentes entre pública y privada.

La _propiedad ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN. Por ejemplo, puede excluir  sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se abate desde la red CDN.

La _propiedad ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración de atributos _de NoScript_ en el nivel de sitio. De forma predeterminada, _el atributo NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para _sitios clásicos._ Esto depende de la configuración del espacio empresarial.

Para obtener más información acerca de estos cmdlets, vea [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) y [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Agregar un origen para los activos

Use el **cmdlet Add-SPOTenantCdnOrigin** para definir un origen. Puede definir varios orígenes. El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.
  
> [!IMPORTANT]
> Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

El valor de _la ruta de_ acceso es la ruta de acceso relativa a la biblioteca o carpeta que contiene los activos. Puede usar caracteres comodín además de rutas relativas. Los orígenes admiten caracteres comodín anteponer a la dirección URL. Esto le permite crear orígenes que abarcan varios sitios. Por ejemplo, para incluir todos los activos en la carpeta masterpages de todos los sitios como un origen público dentro de la red CDN, escriba el siguiente comando:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ El modificador de caracteres comodín * solo se puede usar al principio de la ruta de acceso y coincidirá con todos los segmentos de dirección URL en **/** la dirección URL especificada.
+ La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio. Por ejemplo, la ruta _de acceso */site1_ coincidirá con todas las bibliotecas de documentos del sitio.

Puede agregar un origen con una ruta de acceso relativa específica. No se puede agregar un origen mediante la ruta de acceso completa.

En este ejemplo se agrega un origen privado de la biblioteca siteassets en un sitio específico:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

En este ejemplo se agrega un origen privado de la _carpeta folder1_ en la biblioteca de activos del sitio de la colección de sitios:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio con la codificación DE URL %20. En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de activos del sitio de la colección de sitios:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

> [!NOTE]
> En los orígenes privados, los activos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.
  
Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Ejemplo: configurar un origen público para las páginas maestras y para la biblioteca de estilos de SharePoint Online

Normalmente, estos orígenes se establecen automáticamente cuando habilita la red CDN de Office 365. Sin embargo, si desea habilitarlos manualmente, siga estos pasos.
  
+ Use el **cmdlet Add-SPOTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Use el **cmdlet Add-SPOTenantCdnOrigin** para definir las páginas maestras como un origen público.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Ejemplo: configurar un origen privado para los activos del sitio, las páginas del sitio y las imágenes de publicación para SharePoint Online

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de activos del sitio como un origen privado.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de páginas del sitio como un origen privado.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Ejemplo: Configurar un origen privado para una colección de sitios para SharePoint Online

Use el **cmdlet Add-SPOTenantCdnOrigin** para definir una colección de sitios como un origen privado. Por ejemplo:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).
  
Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Es posible que vea un _mensaje pendiente de_ configuración que se espera a medida que el inquilino de SharePoint Online se conecta al servicio de red CDN. Esto puede tardar hasta 15 minutos.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Administrar la red CDN de Office 365

Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualiza el contenido o cuando sus necesidades cambian, como se describe en esta sección.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Agregar, actualizar o quitar activos de la red CDN de Office 365

Una vez que haya completado los pasos de configuración, puede agregar nuevos activos y actualizar o quitar los activos existentes cuando lo desee. Solo tiene que realizar los cambios en los activos de la carpeta o biblioteca de SharePoint que identificó como origen. Si agrega un nuevo activo, estará disponible a través de la red CDN inmediatamente. Sin embargo, si actualiza el activo, la nueva copia llevará hasta 15 minutos en propagarse y estar disponible en la red CDN.
  
Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-SPOTenantCdnOrigins.** Para obtener información sobre cómo usar este cmdlet, vea [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Quitar un origen de la red CDN de Office 365

Puede quitar el acceso a una carpeta o biblioteca de SharePoint que identificó como origen. Para ello, use el cmdlet **Remove-SPOTenantCdnOrigin.**

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Para obtener información sobre cómo usar este cmdlet, vea [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificar un origen en la red CDN de Office 365

No puede modificar un origen que haya creado. En su lugar, quite el origen y, a continuación, agregue uno nuevo. Para obtener más información, vea Para quitar un origen de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) y Para agregar un [origen para sus activos.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deshabilitar la red CDN de Office 365

Use el cmdlet **Set-SPOTenantCdnEnabled** para deshabilitar la red CDN de su organización. Si tiene los orígenes público y privado habilitados para la red CDN, debe ejecutar el cmdlet dos veces, como se muestra en los ejemplos siguientes.
  
Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Para obtener más información acerca de este cmdlet, [vea Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Configurar y configurar la red CDN de Office 365 con PnP PowerShell

Los procedimientos de esta sección requieren que use PnP PowerShell para conectarse a SharePoint Online. Para obtener instrucciones, consulte [Introducción a PowerShell PnP.](https://github.com/SharePoint/PnP-PowerShell#getting-started)

Siga estos pasos para configurar y configurar la red CDN para hospedar los activos en SharePoint Online con PnP PowerShell.

<details>
  <summary>Haga clic para expandir</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Permitir que su organización use la red CDN de Office 365

Antes de realizar cambios en la configuración de la red CDN del espacio empresarial, debe recuperar el estado actual de la configuración de la red CDN privada en su inquilino de Office 365. Conéctese a su espacio empresarial con PnP PowerShell:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Ahora use el cmdlet **Get-PnPTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

El estado de la red CDN para el CdnType especificado se mostrará en pantalla.

Use el cmdlet **Set-PnPTenantCdnEnabled** para permitir que su organización use la red CDN de Office 365. Puede permitir que su organización use orígenes públicos, privados o ambos al mismo tiempo. También puede configurar la red CDN para omitir la configuración de los orígenes predeterminados al habilitarla. Siempre puede agregar estos orígenes más adelante, como se describe en este tema.
  
En PnP PowerShell:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Por ejemplo, para permitir que su organización use orígenes públicos y privados, escriba el siguiente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Para permitir que su organización use orígenes públicos y privados, pero omita la configuración de los orígenes predeterminados, escriba el siguiente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Vea los orígenes predeterminados de la red [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de los orígenes predeterminados.

Para permitir que su organización use orígenes públicos, escriba el siguiente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Para permitir que su organización use orígenes privados, escriba el siguiente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Para obtener más información acerca de este cmdlet, [vea Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Cambiar la lista de tipos de archivo para incluir en la red CDN de Office 365 (opcional)

> [!TIP]
> Al definir tipos de archivo mediante el cmdlet **Set-PnPTenantCdnPolicy,** se sobrescribe la lista definida actualmente. Si desea agregar tipos de archivo adicionales a la lista, use el cmdlet primero para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.
  
Use el cmdlet **Set-PnPTenantCdnPolicy** para definir tipos de archivo estáticos que se pueden hospedar en orígenes públicos y privados en la red CDN. De forma predeterminada, se permiten tipos de activos comunes, por ejemplo .css, .gif, .jpg y .js.

En PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, debe escribir el comando:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Para obtener más información acerca de estos cmdlets, vea [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) y [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365 (opcional)

> [!TIP]
> Cuando se excluyen las clasificaciones de sitio mediante el cmdlet **Set-PnPTenantCdnPolicy,** se sobrescribe la lista definida actualmente. Si desea excluir clasificaciones de sitio adicionales, use el cmdlet primero para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.

Use el cmdlet **Set-PnPTenantCdnPolicy** para excluir las clasificaciones de sitio que no desea que estén disponibles a través de la red CDN. De forma predeterminada, no se excluyen clasificaciones de sitio.

En PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Para ver qué clasificaciones de sitio están restringidas actualmente, use el cmdlet **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Las propiedades que se devolverán _son IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.

La _propiedad IncludeFileExtensions_ contiene la lista de extensiones de archivo que se van a servir desde la red CDN.

> [!NOTE]
> Las extensiones de archivo predeterminadas son diferentes entre pública y privada.

La _propiedad ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN. Por ejemplo, puede excluir  sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se abate desde la red CDN.

La _propiedad ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración de atributos _de NoScript_ en el nivel de sitio. De forma predeterminada, _el atributo NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para _sitios clásicos._ Esto depende de la configuración del espacio empresarial.

Para obtener más información acerca de estos cmdlets, vea [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) y [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Agregar un origen para los activos

Use el **cmdlet Add-PnPTenantCdnOrigin** para definir un origen. Puede definir varios orígenes. El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.
  
> [!IMPORTANT]
> Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

El valor de _la ruta de_ acceso es la ruta de acceso relativa a la biblioteca o carpeta que contiene los activos. Puede usar caracteres comodín además de rutas relativas. Los orígenes admiten caracteres comodín anteponer a la dirección URL. Esto le permite crear orígenes que abarcan varios sitios. Por ejemplo, para incluir todos los activos en la carpeta masterpages de todos los sitios como un origen público dentro de la red CDN, escriba el siguiente comando:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ El modificador de caracteres comodín * solo se puede usar al principio de la ruta de acceso y coincidirá con todos los segmentos de dirección URL en **/** la dirección URL especificada.
+ La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio. Por ejemplo, la ruta _de acceso */site1_ coincidirá con todas las bibliotecas de documentos del sitio.

Puede agregar un origen con una ruta de acceso relativa específica. No se puede agregar un origen mediante la ruta de acceso completa.

En este ejemplo se agrega un origen privado de la biblioteca de activos del sitio en un sitio específico:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

En este ejemplo se agrega un origen privado de la _carpeta folder1_ en la biblioteca de activos del sitio de la colección de sitios:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio con la codificación DE URL %20. En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de activos del sitio de la colección de sitios:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> En los orígenes privados, los activos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.
  
Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Ejemplo: configurar un origen público para las páginas maestras y para la biblioteca de estilos de SharePoint Online

Normalmente, estos orígenes se establecen automáticamente cuando habilita la red CDN de Office 365. Sin embargo, si desea habilitarlos manualmente, siga estos pasos.
  
+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Use el **cmdlet Add-PnPTenantCdnOrigin** para definir las páginas maestras como un origen público.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Ejemplo: configurar un origen privado para los activos del sitio, las páginas del sitio y las imágenes de publicación para SharePoint Online

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de activos del sitio como un origen privado.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de páginas del sitio como un origen privado.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Ejemplo: Configurar un origen privado para una colección de sitios para SharePoint Online

Use el cmdlet **Add-PnPTenantCdnOrigin** para definir una colección de sitios como un origen privado. Por ejemplo:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Es posible que vea un _mensaje pendiente de_ configuración que se espera a medida que el inquilino de SharePoint Online se conecta al servicio de red CDN. Esto puede tardar hasta 15 minutos.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Administrar la red CDN de Office 365

Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualiza el contenido o cuando sus necesidades cambian, como se describe en esta sección.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Agregar, actualizar o quitar activos de la red CDN de Office 365

Una vez que haya completado los pasos de configuración, puede agregar nuevos activos y actualizar o quitar los activos existentes cuando lo desee. Solo tiene que realizar los cambios en los activos de la carpeta o biblioteca de SharePoint que identificó como origen. Si agrega un nuevo activo, estará disponible a través de la red CDN inmediatamente. Sin embargo, si actualiza el activo, la nueva copia llevará hasta 15 minutos en propagarse y estar disponible en la red CDN.
  
Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-PnPTenantCdnOrigin.** Para obtener información sobre cómo usar este cmdlet, vea [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Quitar un origen de la red CDN de Office 365

Puede quitar el acceso a una carpeta o biblioteca de SharePoint que identificó como origen. Para ello, use el cmdlet **Remove-PnPTenantCdnOrigin.**

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Para obtener información sobre cómo usar este cmdlet, vea [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificar un origen en la red CDN de Office 365

No puede modificar un origen que haya creado. En su lugar, quite el origen y, a continuación, agregue uno nuevo. Para obtener más información, vea Para quitar un origen de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) y Para agregar un [origen para sus activos.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deshabilitar la red CDN de Office 365

Use el cmdlet **Set-PnPTenantCdnEnabled** para deshabilitar la red CDN de su organización. Si tiene los orígenes público y privado habilitados para la red CDN, debe ejecutar el cmdlet dos veces, como se muestra en los ejemplos siguientes.
  
Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Para obtener más información acerca de este cmdlet, [vea Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Instalar y configurar la red CDN de Office 365 con la CLI de Office 365

Los procedimientos de esta sección requieren que haya instalado la [CLI de Office 365.](https://aka.ms/o365cli) A continuación, conéctese al inquilino de Office 365 con el comando [de inicio de](https://pnp.github.io/office365-cli/cmd/login/) sesión.

Complete estos pasos para configurar y configurar la red CDN para hospedar sus activos en SharePoint Online mediante la CLI de Office 365.

<details>
  <summary>Haga clic para expandir</summary>

### <a name="enable-the-office-365-cdn"></a>Habilitar la red CDN de Office 365

Puede administrar el estado de la red CDN de Office 365 en su cuenta empresarial con el comando [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).

Para habilitar la red CDN pública de Office 365 en su cuenta empresarial ejecute:

```sh
spo cdn set --type Public --enabled true
```

Para habilitar la red CDN de SharePoint de Office 365, ejecute:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Vea el estado actual de la red CDN de Office 365.

Para comprobar si el tipo concreto de red CDN de Office 365 está habilitado o deshabilitado, use el comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Para comprobar si la red CDN pública de Office 365 está habilitada, ejecute:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Ver los orígenes de la red CDN de Office 365

Para ver los orígenes configurados actualmente de la red CDN pública de Office 365, ejecute:

```sh
spo cdn origin list --type Public
```

Vea los orígenes predeterminados de la red [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365.

### <a name="add-an-office-365-cdn-origin"></a>Agregar un origen de red CDN de Office 365

> [!IMPORTANT]
> Nunca debe colocar recursos que se consideren confidenciales para su organización en una biblioteca de documentos de SharePoint configurada como un origen público.

Use el comando [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) definir un origen de la red CDN. Puede definir varios orígenes. El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Dónde `path` está la ruta de acceso relativa a la carpeta que contiene los activos. Puede usar caracteres comodín además de rutas relativas.

Para incluir todos los activos en la **Galería de páginas maestras** de todos los sitios como origen público, ejecute:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Para configurar un origen privado para una colección de sitios específica, ejecute:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Después de agregar un origen de la red CDN, puede tardar hasta 15 minutos para poder recuperar archivos mediante el servicio de la red CDN. Puede comprobar si ya se ha habilitado el origen particular con el comando [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).

### <a name="remove-an-office-365-cdn-origin"></a>Quitar un origen de red CDN de Office 365

Use el comando [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) para eliminar un origen de la red CDN para el tipo de red CDN especificado.

Para quitar un origen público de la configuración de la red CDN, ejecute:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> La eliminación de un origen de red CDN no afecta a los archivos almacenados en ninguna biblioteca de documentos que coincida con ese origen. Si se ha hecho referencia a estos activos mediante su dirección URL de SharePoint, SharePoint volverá automáticamente a la dirección URL original que apunta a la biblioteca de documentos. Sin embargo, si se ha hecho referencia a los activos mediante una dirección URL de red CDN pública, al quitar el origen se romperá el vínculo y tendrá que cambiarlos manualmente.

### <a name="modify-an-office-365-cdn-origin"></a>Modificar un origen de la red CDN de Office 365

No es posible modificar un origen de la red CDN existente. En su lugar, debe eliminar el origen de la red CDN definido anteriormente con el comando `spo cdn origin remove` y agregar uno nuevo con el comando `spo cdn origin add`.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Cambiar los tipos de archivos que se incluirán en la red CDN de Office 365

De forma predeterminada, los siguientes tipos de archivo se incluyen en la red CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2_. Si tiene que incluir otros tipos de archivo en la red CDN, puede cambiar la configuración de la red CDN con el comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).

> [!NOTE]
> Al cambiar la lista de tipos de archivo, se sobrescribe la lista definida actualmente. Si desea incluir otros tipos de archivo, use el comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) para averiguar qué tipos de archivos están configurados en este momento.

Para agregar el tipo de archivo _JSON_ a la lista predeterminada de tipos de archivo incluidos en la red CDN pública, ejecute:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365

Use el comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN. De forma predeterminada, no se excluyen clasificaciones de sitio.

> [!NOTE]
> Al cambiar la lista de clasificaciones de sitio excluidas, se sobrescribe la lista definida actualmente. Si quiere excluir clasificaciones adicionales, use el comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) para averiguar qué clasificaciones están configuradas en este momento.

Para excluir sitios clasificados como _HBI_ de la red CDN pública, ejecute

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Deshabilitar la red CDN de Office 365

Para deshabilitar la red CDN de Office 365, use el comando `spo cdn set`, por ejemplo:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Uso de los activos de la red CDN

Ahora que ha habilitado la red CDN y ha configurado orígenes y directivas, puede empezar a usar los activos de la red CDN.

Esta sección le ayudará a comprender cómo usar direcciones URL de red CDN en sus páginas y contenido de SharePoint para que SharePoint redirija las solicitudes de activos en orígenes públicos y privados a la red CDN.

+ [Actualización de vínculos a activos de red CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Uso de activos en orígenes públicos](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Uso de activos en orígenes privados](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Para obtener información sobre cómo usar la red CDN para hospedar elementos web del lado cliente, vea el tema Hospedar el elemento web del lado cliente desde la red CDN de [Office 365 (parte 4](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)de Hello World).

> [!NOTE]
> Si agrega la carpeta _ClientSideAssets_ a la lista de orígenes de la red **CDN** privada, los elementos web personalizados hospedados en la red CDN no se representarán. Los archivos usados por los elementos web de SPFX solo pueden usar la red CDN pública y la carpeta ClientSideAssets es un origen predeterminado para la red CDN pública. 

### <a name="updating-links-to-cdn-assets"></a>Actualización de vínculos a activos de red CDN

Para usar activos que haya agregado a un origen, simplemente actualice los vínculos al archivo original con la ruta de acceso al archivo en el origen.

+ Edite la página o el contenido que contiene vínculos a activos que ha agregado a un origen. También puede usar uno de varios métodos para buscar y reemplazar vínculos de forma global en un sitio o colección de sitios si desea actualizar el vínculo a un activo determinado en cualquier lugar donde aparezca.
+ Para cada vínculo a un activo en un origen, reemplace la ruta de acceso por la ruta de acceso al archivo en el origen de la red CDN. Puede usar rutas de acceso relativas.
+ Guarde la página o el contenido.

Por ejemplo, considere la imagen _/site/SiteAssets/images/image.png_, que ha copiado en la carpeta de la biblioteca de documentos _/site/CDN_origins/public/_. Para usar el activo de red CDN, reemplace la ruta de acceso original a la ubicación del archivo de imagen por la ruta de acceso al origen para que la nueva dirección URL _/site/CDN_origins/public/image.png_.

Si desea usar la dirección URL completa del activo en lugar de una ruta de acceso relativa, cree el vínculo de la siguiente manera:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> En general, no debe codificar las direcciones URL directamente a los activos de la red CDN. Sin embargo, puede crear manualmente direcciones URL para activos en orígenes públicos si es necesario. Para obtener más información, vea [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).

Para obtener información sobre cómo comprobar que los activos se sirven desde la red CDN, consulte ¿Cómo confirmo que la red [CDN](use-microsoft-365-cdn-with-spo.md#CDNConfirm) proporciona activos? en la sección Solución de problemas de la red CDN de [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>Uso de activos en orígenes públicos

La  característica de publicación en SharePoint Online reescribe automáticamente las direcciones URL de los activos almacenados en orígenes públicos en sus equivalentes de red CDN para que los activos se atenúen desde el servicio de red CDN en lugar de SharePoint.

Si su origen se encuentra en un sitio con la característica de publicación habilitada y los activos que desea descargar a la red CDN se encuentran en una de las siguientes categorías, SharePoint reescribirá automáticamente las direcciones URL de los activos en el origen, siempre que el activo no haya sido excluido por una directiva de red CDN.

A continuación, se muestra información general sobre los vínculos que la característica de publicación de SharePoint reescribe automáticamente:

+ URL de IMG/LINK/CSS en respuestas de HTML de página de publicación clásica
  + Esto incluye imágenes que han agregado autores en el contenido HTML de una página
+ URL de las imágenes del elemento web de presentación de la biblioteca de imágenes
+ Campos de imagen de los resultados de la API de REST SPList (RenderListDataAsStream)
  + Usar la nueva propiedad _ImageFieldsToTryRewriteToCdnUrls_ para proporcionar una lista separada por comas de campos
  + Admite campos de hipervínculo y campos PublishingImage
+ Representaciones de imágenes de SharePoint

En el siguiente diagrama se muestra el flujo de trabajo cuando SharePoint recibe una solicitud para una página que contiene activos de un origen público.

![Diagrama de flujo de trabajo: recuperar activos de red CDN de Office 365 desde un origen público](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flujo de trabajo: recuperar activos de red CDN de Office 365 desde un origen público")

> [!TIP]
> Si desea deshabilitar la reescritura automática para direcciones URL específicas de una página, ¿puede des consultar la página y agregar el parámetro de cadena de **consulta? NoAutoReWrites=true** al final de cada vínculo que desea deshabilitar.

#### <a name="hardcoding-cdn-urls-for-public-assets"></a>Hardcoding CDN URLs for public assets

Si  la característica de publicación no está habilitada para un origen público o el activo no es uno de los tipos de vínculo admitidos por la característica de reescritura automática del servicio de red CDN, puede construir manualmente direcciones URL en la ubicación de la red CDN de los activos y usar estas direcciones URL en el contenido.

> [!NOTE]
> No puede codificar las direcciones URL de la red CDN en activos de origen privado porque el token de acceso necesario que forma la última sección de la dirección URL se genera en el momento en que se solicita el recurso.

Para los activos de la red CDN pública, el formato de dirección URL tendrá el siguiente aspecto:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Reemplace **TenantHostName por** su nombre de inquilino. Ejemplo:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a>Uso de activos en orígenes privados

No se requiere ninguna configuración adicional para usar activos en orígenes privados. SharePoint Online reescribe automáticamente las direcciones URL de los activos en orígenes privados para que las solicitudes de esos activos siempre se atenúe desde la red CDN. No puede crear manualmente direcciones URL en activos de red CDN en orígenes privados porque estas direcciones URL contienen tokens que SharePoint Online debe generar automáticamente en el momento en que se solicita el activo.

El acceso a los activos en orígenes privados está protegido por tokens generados dinámicamente en función de los permisos de usuario para el origen, con las advertencias descritas en las secciones siguientes. Los usuarios deben tener al menos **acceso de** lectura a los orígenes para que la red CDN represente contenido.

En el siguiente diagrama se muestra el flujo de trabajo cuando SharePoint recibe una solicitud de una página que contiene activos de un origen privado.

![Diagrama de flujo de trabajo: recuperación de activos de red CDN de Office 365 desde un origen privado](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flujo de trabajo: recuperar activos de red CDN de Office 365 desde un origen privado")

#### <a name="token-based-authorization-in-private-origins"></a>Autorización basada en tokens en orígenes privados

El acceso a los activos en orígenes privados en la red CDN de Office 365 se concede mediante tokens generados por SharePoint Online. A los usuarios que ya tienen permiso para acceder a la carpeta o biblioteca designada por el origen se les conceden automáticamente tokens que permiten al usuario tener acceso al archivo en función de su nivel de permisos. Estos tokens de acceso son válidos durante 30 a 90 minutos después de que se generen para ayudar a evitar ataques de reproducción de tokens.

Una vez generado el token de acceso, SharePoint Online devuelve  un URI personalizado al cliente que contiene dos parámetros de autorización (token de autorización perimetral) y _oat_ (token de autorización de origen). La estructura de cada token es< fecha de expiración en formato de hora de la época >__< la firma _segura >_. Por ejemplo:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Cualquier persona que posea el token puede acceder al recurso en la red CDN. Sin embargo, las direcciones URL que contienen estos tokens de acceso solo se comparten a través de HTTPS, por lo que a menos que un usuario final comparta explícitamente la dirección URL antes de que expire el token, el activo no será accesible para los usuarios no autorizados.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Los permisos de nivel de elemento no se admiten para activos en orígenes privados

Es importante tener en cuenta que SharePoint Online no admite permisos de nivel de elemento para activos en orígenes privados. Por ejemplo, para un archivo ubicado en , los usuarios tienen acceso efectivo al archivo `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` en las siguientes condiciones:

|Usuario  |Permissions  |Acceso efectivo  |
|---------|---------|---------|
|Usuario 1     |Tiene acceso a la carpeta1         |Puede obtener image1.jpg desde la red CDN         |
|Usuario 2     |No tiene acceso a folder1         |No se puede image1.jpg desde la red CDN         |
|Usuario 3     |No tiene acceso a folder1, pero se le concede permiso explícito para acceder a image1.jpg en SharePoint Online         |Puede obtener acceso al recurso image1.jpg directamente desde SharePoint Online, pero no desde la red CDN         |
|Usuario 4     |Tiene acceso a la carpeta 1, pero se le ha denegado explícitamente el acceso a image1.jpg en SharePoint Online         |No se puede obtener acceso al activo desde SharePoint Online, pero puede acceder al activo desde la red CDN a pesar de que se le deniega el acceso al archivo en SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Solución de problemas de la red CDN de Office 365

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>¿Cómo confirmo que la red CDN sirve los activos?

Una vez que haya agregado vínculos a activos de red CDN a una página, puede confirmar que el activo se sirve desde la red CDN. Para ello, examine la página, haga clic con el botón secundario en la imagen una vez que se haya representado y revise la dirección URL de la imagen.

También puede usar las herramientas de desarrollo del explorador para ver la dirección URL de cada activo en una página o usar una herramienta de seguimiento de red de terceros.

> [!NOTE]
> Si usa una herramienta de red como Fiddler para probar los activos fuera de representar el activo desde una página de SharePoint, debe agregar manualmente el encabezado de referencia "Referer: " a la solicitud GET, donde la dirección URL es la dirección URL raíz de su inquilino de `https://yourdomain.sharepoint.com` SharePoint Online.

No puede probar las direcciones URL de la red CDN directamente en un explorador web porque debe tener un referenciador procedente de SharePoint Online. Sin embargo, si agrega la dirección URL del activo de red CDN a una página de SharePoint y, a continuación, abre la página en un explorador, verá el activo de red CDN representado en la página.

Para obtener más información sobre el uso de las herramientas de desarrollo en el explorador Microsoft Edge, vea [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).

Para ver un breve vídeo hospedado en el canal de YouTube de modelos y prácticas para desarrolladores de [SharePoint](https://aka.ms/sppnp-videos) que muestra cómo comprobar que la red CDN funciona, consulte Comprobar el uso de la red [CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)y garantizar una conectividad de red óptima.

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>¿Por qué los activos de un nuevo origen no están disponibles?
Los activos de nuevos orígenes no estarán disponibles inmediatamente para su uso, ya que el registro tarda en propagarse a través de la red CDN y para que los activos se carguen desde el origen al almacenamiento de la red CDN. El tiempo necesario para que los activos estén disponibles en la red CDN depende de cuántos activos y tamaños de archivos.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Mi elemento web del lado cliente o la solución de SharePoint Framework no funcionan

Cuando habilita la red CDN de Office 365 para orígenes públicos, el servicio de red CDN crea automáticamente estos orígenes predeterminados:

+ */MASTERPAGE
+ */BIBLIOTECA DE ESTILOS
+ */CLIENTSIDEASSETS

Si falta el origen */clientsideassets, se producirá un error en las soluciones de SharePoint Framework y no se generarán mensajes de advertencia o error. Es posible que falte este origen porque la red CDN se habilitó con el parámetro _-NoDefaultOrigins_ establecido en **$true** o porque el origen se eliminó manualmente.

Puedes comprobar qué orígenes están presentes con el siguiente comando de PowerShell:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

O puede consultar con la CLI de Office 365:

``` powershell
spo cdn origin list
```

Para agregar el origen en PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Para agregar el origen en la CLI de Office 365:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>¿Qué módulos de PowerShell y shells de CLI necesito para trabajar con la red CDN de Office 365?

Puede elegir trabajar con la red CDN de Office 365 mediante el módulo de PowerShell del Shell de administración de **SharePoint Online** o la **CLI de Office 365.**

+ [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Instalar Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Vea también

[Redes de entrega de contenido](https://aka.ms/o365cdns)

[Planeamiento de red y ajuste del rendimiento para Office 365](https://aka.ms/tune)

[Serie de rendimiento de SharePoint: serie de vídeos de red CDN de Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
