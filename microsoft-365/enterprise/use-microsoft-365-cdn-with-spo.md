---
title: Uso de Office 365 Content Delivery Network (CDN) con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/13/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Obtenga información sobre cómo usar la red de entrega de contenido (CDN) Office 365 para acelerar la entrega de los recursos de SharePoint Online.
ms.openlocfilehash: 19a6ef51c73340c9f048ffa60208a5216a1959db
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66492521"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online

Puede usar la red de entrega de contenido (CDN) de Office 365 integrada para hospedar archivos estáticos y mejorar el rendimiento de las páginas de SharePoint Online. La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia. Además, el Office 365 CDN usa el [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para mejorar la compresión y la canalización HTTP. La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.

> [!NOTE]
> La red CDN de Office 365 solo está disponible para los inquilinos en la nube **de producción** (en todo el mundo). Los inquilinos de las nubes del Gobierno de EE. UU. y China no admiten actualmente la red CDN de Office 365.

La CDN de Office 365 se compone de varias redes CDN que permite hospedar archivos estáticos en varias ubicaciones u _orígenes_ y a realizar la entrega desde redes de alta velocidad globales. Según el tipo de contenido que quiera hospedar en la CDN de Office 365, puede agregar orígenes **públicos**, **privados** o ambos. Consulte [Elegir si cada origen debe ser público o privado](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) para obtener más información sobre la diferencia entre orígenes públicos y privados.

![Office 365 diagrama conceptual de CDN.](../media/O365-CDN/o365-cdn-flow-transparent.png "diagrama conceptual de Office 365 CDN")

Si ya está familiarizado con la forma en que funcionan las redes CDN, solo tiene que completar algunos pasos para habilitar la red CDN de Office 365 para el inquilino. En este tema se describe cómo. Siga leyendo para obtener información sobre cómo empezar a hospedar los recursos estáticos.

> [!TIP]
> Hay otras redes CDN hospedadas en Microsoft que se pueden usar con Office 365 para escenarios de uso especializados, pero no se tratan en este tema porque están fuera del ámbito de la red CDN de Office 365. Para obtener más información, consulte [Otras redes CDN de Microsoft](content-delivery-networks.md#other-microsoft-cdns).

 **Vuelva a [Planeamiento de red y ajuste de rendimiento para Office 365](./network-planning-and-performance.md).**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Información general sobre cómo trabajar con la red CDN de Office 365 en SharePoint Online

Para configurar la red CDN de Office 365 para su organización, siga estos pasos básicos:

+ [Planeamiento de la implementación de la red CDN de Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Determine qué recursos estáticos desea hospedar en la red CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).
  + [Determine dónde desea almacenar los recursos](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets). Esta ubicación puede ser un sitio, una biblioteca o una carpeta de SharePoint y se denomina _origen_.
  + [Elija si cada origen debe ser público o privado](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate). Puede agregar varios orígenes de tipos públicos y privados.

+ Configuración y configuración de la red CDN mediante PowerShell o la CLI de Microsoft 365

  + [Configuración y configuración de la red CDN mediante el Shell de administración de SharePoint Online](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Configuración y configuración de la red CDN mediante PowerShell PnP](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Configuración y configuración de la red CDN mediante la CLI de Microsoft 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Cuando complete este paso, tendrá:

  + Se ha habilitado la red CDN para su organización.
  + Se agregaron los orígenes, identificando cada origen como público o privado.

Una vez que haya terminado con la configuración, puede [administrar la red CDN de Office 365 con el](use-microsoft-365-cdn-with-spo.md#CDNManage) tiempo:

+ Adición, actualización y eliminación de recursos
+ Adición y eliminación de orígenes
+ Configuración de directivas de CDN
+ Si es necesario, deshabilitar la red CDN

Por último, consulte [Uso de los recursos de la red CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) para obtener información sobre el acceso a los recursos de la red CDN desde orígenes públicos y privados.

Consulte [Solución de problemas de la red CDN de Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) para obtener instrucciones sobre cómo resolver problemas comunes.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planeamiento de la implementación de la red CDN de Office 365

Antes de implementar la red CDN de Office 365 para el inquilino de Office 365, debe tener en cuenta los siguientes factores como parte del proceso de planeamiento.

  + [Determinar qué recursos estáticos desea hospedar en la red CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determinar dónde desea almacenar los recursos](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Elija si cada origen debe ser público o privado.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Determinar qué recursos estáticos desea hospedar en la red CDN

En general, las redes CDN son más eficaces para hospedar _recursos estáticos_ o recursos que no cambian con mucha frecuencia. Una buena regla general es identificar los archivos que cumplen algunas o todas estas condiciones:

+ Archivos estáticos incrustados en una página (como scripts e imágenes) que pueden tener un impacto incremental significativo en los tiempos de carga de la página
+ Archivos grandes, como archivos ejecutables y archivos de instalación
+ Bibliotecas de recursos que admiten código del lado cliente

Por ejemplo, los archivos pequeños que se solicitan repetidamente, como imágenes de sitio y scripts, pueden mejorar significativamente el rendimiento de la representación del sitio y reducir incrementalmente la carga en los sitios de SharePoint Online al agregarlos a un origen de red CDN. Los archivos más grandes, como los ejecutables de instalación, se pueden descargar desde la red CDN, lo que proporciona un impacto positivo en el rendimiento y una reducción posterior de la carga en el sitio de SharePoint Online, incluso si no se accede a ellos con tanta frecuencia.

La mejora del rendimiento por archivo depende de muchos factores, como la proximidad del cliente al punto de conexión de CDN más cercano, las condiciones transitorias en la red local, etc. Muchos archivos estáticos son bastante pequeños y se pueden descargar desde Office 365 en menos de un segundo. Sin embargo, una página web puede contener muchos archivos incrustados con un tiempo de descarga acumulado de varios segundos. El servicio de estos archivos desde la red CDN puede reducir significativamente el tiempo de carga general de la página. Consulte [¿Qué mejoras de rendimiento proporciona una red CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) para obtener un ejemplo.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Determinar dónde desea almacenar los recursos

El CDN captura los recursos de una ubicación denominada _origen_. Un origen puede ser un sitio de SharePoint, una biblioteca de documentos o una carpeta a la que puede acceder una dirección URL. Tiene una gran flexibilidad al especificar orígenes para su organización. Por ejemplo, puede especificar varios orígenes o un único origen donde quiera colocar todos los recursos de la red CDN. Puede elegir tener orígenes públicos o privados para su organización. La mayoría de las organizaciones elegirán implementar una combinación de las dos.

Puede crear un nuevo contenedor para sus orígenes, como carpetas o bibliotecas de documentos, y agregar archivos que quiera que estén disponibles desde la red CDN. Este es un buen enfoque si tiene un conjunto específico de recursos que desea que estén disponibles en la red CDN y quiera restringir el conjunto de recursos de la red CDN a solo esos archivos del contenedor.

También puede configurar una colección de sitios, un sitio, una biblioteca o una carpeta existentes como origen, lo que hará que todos los recursos aptos del contenedor estén disponibles en la red CDN. Antes de agregar un contenedor existente como origen, es importante asegurarse de que conoce su contenido y permisos para no exponer involuntariamente los recursos a usuarios anónimos o no autorizados.

Puede definir _directivas de RED CDN_ para excluir contenido en los orígenes de la red CDN. Las directivas de RED CDN excluyen recursos en orígenes públicos o privados por atributos como _el tipo de archivo_ y la _clasificación de sitio_, y se aplican a todos los orígenes de CdnType (privado o público) que especifique en la directiva. Por ejemplo, si agrega un origen privado que consta de un sitio que contiene varios subsitios, puede definir una directiva para excluir sitios marcados como **Confidenciales** para que el contenido de los sitios con esa clasificación aplicada no se sirva de la red CDN. La directiva se aplicará al contenido de _todos los_ orígenes privados que haya agregado a la red CDN.

Tenga en cuenta que cuanto mayor sea el número de orígenes, mayor será el impacto en el tiempo que tarda el servicio cdn en procesar las solicitudes. Se recomienda limitar el número de orígenes tanto como sea posible.

<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Elija si cada origen debe ser público o privado.

Cuando se identifica un origen, se especifica si se debe hacer _público_ o _privado_. El acceso a los recursos de la red CDN en orígenes públicos es anónimo y el contenido de la red CDN en orígenes privados se protege mediante tokens generados dinámicamente para una mayor seguridad. Independientemente de la opción que elija, Microsoft realiza todo el trabajo pesado por usted en lo que respecta a la administración de la propia red CDN. Además, puede cambiar de opinión más adelante, después de configurar la red CDN e identificar sus orígenes.

Tanto las opciones públicas como las privadas proporcionan mejoras de rendimiento similares, pero cada una tiene atributos y ventajas únicos.

**Los orígenes públicos** dentro de la red CDN de Office 365 son accesibles de forma anónima y cualquier persona que tenga la dirección URL al recurso puede acceder a los recursos hospedados. Como el acceso al contenido en orígenes públicos es anónimo, solo debe usarlos para almacenar en caché contenido genérico y no confidencial, como archivos JavaScript, scripts, iconos e imágenes.

**Los orígenes privados** dentro de la red CDN de Office 365 proporcionan acceso privado al contenido del usuario, como bibliotecas de documentos de SharePoint Online, sitios e imágenes propietarias. El acceso al contenido en orígenes privados se protege mediante tokens generados dinámicamente, por lo que solo pueden acceder a él los usuarios con permisos para la biblioteca de documentos original o la ubicación de almacenamiento. Los orígenes privados de la red CDN de Office 365 solo se pueden usar para el contenido de SharePoint Online y solo puede acceder a los recursos en orígenes privados a través del redireccionamiento desde el inquilino de SharePoint Online.

Puede obtener más información sobre cómo funciona el acceso de red CDN a los recursos de un origen privado en [Uso de recursos en orígenes privados](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Atributos y ventajas del hospedaje de recursos en orígenes públicos

+ Cualquier persona puede acceder a los activos expuestos en un origen público de forma anónima.
    > [!IMPORTANT]
    > Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.

+ Si elimina un activo de un origen público, el activo podría continuar disponible durante un máximo de 30 días desde la memoria caché. Sin embargo, se invalidarán los vínculos a los activos en la red CDN en 15 minutos.

+ Si hospeda hojas de estilo (archivos CSS) en un origen público, puede usar las rutas relativas y URI dentro del código. Esto significa que puede hacer referencia a la ubicación de las imágenes de fondo y otros objetos con respecto a la ubicación del activo que está llamando.

+ Aunque puede construir la dirección URL de un origen público, debe proceder con precaución y asegurarse de usar la propiedad de contexto de página y seguir las instrucciones para hacerlo. El motivo de esto es que, si no está disponible el acceso a la red CDN, la dirección URL no resolverá automáticamente su organización en SharePoint Online y podría producir vínculos rotos y otros errores. La dirección URL también está sujeta a cambios, por lo que no solo debe codificarse de forma rígida en su valor actual.

+ Los tipos de archivo predeterminados que se incluyen para orígenes públicos son .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2. Puede especificar tipos de archivo adicionales.

+ Puede configurar una directiva para excluir los recursos identificados por las clasificaciones de sitio que especifique. Por ejemplo, puede elegir excluir todos los activos que están marcados como restringidos o confidenciales aunque sean un tipo de archivo permitido y se encuentren en un origen público.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Atributos y ventajas del hospedaje de recursos en orígenes privados

+ Los orígenes privados solo se pueden usar para los recursos de SharePoint Online.

+ Los usuarios solo pueden acceder a los recursos desde un origen privado si tienen permisos para acceder al contenedor. Se impide el acceso anónimo a estos activos.

+ Los recursos de orígenes privados se deben hacer referencia desde el inquilino de SharePoint Online. El acceso directo a recursos de red CDN privados no funciona.

+ Si quita un recurso del origen privado, el recurso puede seguir estando disponible hasta una hora de la memoria caché; sin embargo, invalidaremos los vínculos al recurso en la red CDN en un plazo de 15 minutos después de la eliminación del recurso.

+ Los tipos de archivo predeterminados que se incluyen en el origen privado son .gif, .ico, .jpeg, .jpg, .js y .png. Puede especificar tipos de archivo adicionales.

+ Al igual que con los orígenes públicos, puede configurar una directiva para excluir los recursos identificados por las clasificaciones de sitio que especifique incluso si usa caracteres comodín para incluir todos los recursos dentro de una carpeta o biblioteca de documentos.

Para obtener más información sobre por qué usar la red CDN de Office 365, los conceptos generales de la red CDN y otras redes CDN de Microsoft que puede usar con su inquilino de Office 365, consulte [Content Delivery Networks](content-delivery-networks.md).

### <a name="default-cdn-origins"></a>Orígenes de red CDN predeterminados

A menos que especifique lo contrario, Office 365 configura algunos orígenes predeterminados al habilitar la red CDN de Office 365. Si inicialmente decide no aprovisionarlos, puede agregar estos orígenes después de completar la configuración. A menos que comprenda las consecuencias de omitir la configuración de orígenes predeterminados y tenga un motivo específico para hacerlo, debe permitir que se creen al habilitar la red CDN.

Orígenes de CDN privados predeterminados:

+ \*/userphoto.aspx
+ \*/siteassets

Orígenes de red CDN pública predeterminados:

+ \*/masterpage
+ \*Biblioteca /style
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ es un origen público predeterminado que se agregó al servicio Office 365 CDN en diciembre de 2017. Este origen debe estar presente para que funcionen SharePoint Framework soluciones de la red CDN. Si ha habilitado la red CDN de Office 365 antes de diciembre de 2017 o si omitió la configuración de orígenes predeterminados al habilitar la red CDN, puede agregar manualmente este origen. Para obtener más información, vea [Mi elemento web del lado cliente o SharePoint Framework solución no funciona](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Configuración y configuración de la red CDN de Office 365 mediante el Shell de administración de SharePoint Online

Los procedimientos de esta sección requieren que use el Shell de administración de SharePoint Online para conectarse a SharePoint Online. Para obtener instrucciones, consulte [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

Complete estos pasos para configurar y configurar la red CDN para hospedar los recursos en SharePoint Online mediante el Shell de administración de SharePoint Online.

<details>
  <summary>Haga clic para expandir</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Permitir que la organización use la red CDN de Office 365

Antes de realizar cambios en la configuración de la red CDN del inquilino, debe recuperar el estado actual de la configuración de la red CDN privada en el inquilino de Office 365. Conéctese al inquilino mediante el Shell de administración de SharePoint Online:

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Ahora use el cmdlet **Get-SPOTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

El estado de la red CDN del cdnType especificado se mostrará en la pantalla.

Use el cmdlet **Set-SPOTenantCdnEnabled** para permitir que la organización use la red CDN de Office 365. Puede permitir que su organización use orígenes públicos, orígenes privados o ambos a la vez. También puede configurar la red CDN para omitir la configuración de orígenes predeterminados al habilitarla. Siempre puede agregar estos orígenes más adelante, como se describe en este tema.

En Windows PowerShell para SharePoint Online:

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Por ejemplo, para permitir que su organización use orígenes públicos y privados, escriba el siguiente comando:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Para permitir que la organización use orígenes públicos y privados, pero omita la configuración de los orígenes predeterminados, escriba el siguiente comando:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Consulte [Orígenes de red CDN predeterminados](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes aprovisionados de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de orígenes predeterminados.

Para permitir que la organización use orígenes públicos, escriba el siguiente comando:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Para permitir que la organización use orígenes privados, escriba el siguiente comando:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Para obtener más información sobre este cmdlet, vea [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Cambiar la lista de tipos de archivo que se van a incluir en la red CDN de Office 365 (opcional)

> [!TIP]
> Al definir tipos de archivo mediante el cmdlet **Set-SPOTenantCdnPolicy** , se sobrescribe la lista definida actualmente. Si desea agregar tipos de archivo adicionales a la lista, use primero el cmdlet para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.

Use el cmdlet **Set-SPOTenantCdnPolicy** para definir tipos de archivo estáticos que se pueden hospedar mediante orígenes públicos y privados en la red CDN. De forma predeterminada, se permiten tipos de recursos comunes, como .css, .gif, .jpg y .js.

En Windows PowerShell para SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, escriba el comando :

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-SPOTenantCdnPolicies** :

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Para obtener más información sobre estos cmdlets, vea [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) y [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365 (opcional)

> [!TIP]
> Cuando se excluyen las clasificaciones de sitios mediante el cmdlet **Set-SPOTenantCdnPolicy** , se sobrescribe la lista definida actualmente. Si desea excluir clasificaciones de sitio adicionales, use primero el cmdlet para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.

Use el cmdlet **Set-SPOTenantCdnPolicy** para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN. De forma predeterminada, no se excluyen clasificaciones de sitio.

En Windows PowerShell para SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Para ver qué clasificaciones de sitio están restringidas actualmente, use el cmdlet **Get-SPOTenantCdnPolicies** :

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Las propiedades que se devolverán son _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.

La propiedad _IncludeFileExtensions_ contiene la lista de extensiones de archivo que se proporcionarán desde la red CDN.

> [!NOTE]
> Las extensiones de archivo predeterminadas son diferentes entre públicas y privadas.

La propiedad _ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN. Por ejemplo, puede excluir sitios marcados como **Confidenciales** para que el contenido de los sitios con esa clasificación aplicada no se sirva de la red CDN.

La propiedad _ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración del atributo _NoScript_ de nivel de sitio. De forma predeterminada, el atributo _NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para sitios _clásicos_ . Esto depende de la configuración del inquilino.

Para obtener más información sobre estos cmdlets, vea [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) y [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Adición de un origen para los recursos

Use el cmdlet **Add-SPOTenantCdnOrigin** para definir un origen. Puede definir varios orígenes. El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.

> [!IMPORTANT]
> Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

El valor de _path_ es la ruta de acceso relativa a la biblioteca o carpeta que contiene los recursos. Puede usar caracteres comodín además de rutas relativas. Los orígenes admiten caracteres comodín antepuestos a la dirección URL. Esto le permite crear orígenes que abarcan varios sitios. Por ejemplo, para incluir todos los recursos en la carpeta masterpages de todos los sitios como origen público dentro de la red CDN, escriba el siguiente comando:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ El modificador comodín ***/** solo se puede usar al principio de la ruta de acceso y coincidirá con todos los segmentos de dirección URL en la dirección URL especificada.
+ La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio. Por ejemplo, la ruta _de acceso */site1_ coincidirá con todas las bibliotecas de documentos del sitio.

Puede agregar un origen con una ruta de acceso relativa específica. No se puede agregar un origen mediante la ruta de acceso completa.

En este ejemplo se agrega un origen privado de la biblioteca siteassets en un sitio específico:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

En este ejemplo se agrega un origen privado de la carpeta _folder1_ en la biblioteca de recursos de sitio de la colección de sitios:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio por la codificación de dirección URL %20. En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de recursos de sitio de la colección de sitios:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Para obtener más información sobre este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

> [!NOTE]
> En los orígenes privados, los recursos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Ejemplo: Configuración de un origen público para las páginas maestras y para la biblioteca de estilos para SharePoint Online

Normalmente, estos orígenes se configuran de forma predeterminada al habilitar la red CDN de Office 365. Sin embargo, si desea habilitarlos manualmente, siga estos pasos.

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir las páginas maestras como un origen público.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Para obtener más información sobre este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Ejemplo: Configuración de un origen privado para los recursos del sitio, páginas de sitio e imágenes de publicación para SharePoint Online

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de recursos del sitio como un origen privado.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de páginas de sitio como un origen privado.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Para obtener más información sobre este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Ejemplo: Configuración de un origen privado para una colección de sitios para SharePoint Online

Use el cmdlet **Add-SPOTenantCdnOrigin** para definir una colección de sitios como un origen privado. Por ejemplo:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Para obtener más información sobre este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Es posible que vea un mensaje _pendiente de configuración_ que se espera a medida que el inquilino de SharePoint Online se conecta al servicio CDN. Esto puede tardar hasta 15 minutos.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Administración de la red CDN de Office 365

Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualice el contenido o cuando sus necesidades cambien, como se describe en esta sección.

<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Agregar, actualizar o quitar recursos de la red CDN de Office 365

Una vez que haya completado los pasos de configuración, puede agregar nuevos recursos y actualizar o quitar los recursos existentes siempre que lo desee. Solo tiene que realizar los cambios en los recursos de la carpeta o biblioteca de SharePoint que identificó como origen. Si agrega un nuevo recurso, estará disponible a través de la red CDN inmediatamente. Sin embargo, si actualiza el recurso, la nueva copia tardará hasta 15 minutos en propagarse y estar disponible en la red CDN.

Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-SPOTenantCdnOrigins** . Para obtener información sobre cómo usar este cmdlet, consulte [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Eliminación de un origen de la red CDN de Office 365

Puede quitar el acceso a una carpeta o biblioteca de SharePoint que haya identificado como origen. Para ello, use el cmdlet **Remove-SPOTenantCdnOrigin** .

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Para obtener información sobre cómo usar este cmdlet, consulte [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificación de un origen en la red CDN de Office 365

No se puede modificar un origen que haya creado. En su lugar, quite el origen y agregue uno nuevo. Para obtener más información, consulte [Para quitar un origen de la red CDN de Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) y [Para agregar un origen para los recursos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deshabilitar la red CDN de Office 365

Use el cmdlet **Set-SPOTenantCdnEnabled** para deshabilitar la red CDN de su organización. Si tiene habilitados los orígenes público y privado para la red CDN, debe ejecutar el cmdlet dos veces como se muestra en los ejemplos siguientes.

Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Para obtener más información sobre este cmdlet, vea [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Configuración y configuración de la red CDN de Office 365 mediante PowerShell PnP

Los procedimientos de esta sección requieren que use PowerShell PnP para conectarse a SharePoint Online. Para obtener instrucciones, consulte [Introducción a PowerShell PnP](https://github.com/SharePoint/PnP-PowerShell#getting-started).

Complete estos pasos para configurar y configurar la red CDN para hospedar los recursos en SharePoint Online mediante PowerShell PnP.

<details>
  <summary>Haga clic para expandir</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Permitir que la organización use la red CDN de Office 365

Antes de realizar cambios en la configuración de la red CDN del inquilino, debe recuperar el estado actual de la configuración de la red CDN privada en el inquilino de Office 365. Conéctese al inquilino mediante PowerShell PnP:

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Ahora use el cmdlet **Get-PnPTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

El estado de la red CDN del cdnType especificado se mostrará en la pantalla.

Use el cmdlet **Set-PnPTenantCdnEnabled** para permitir que su organización use la red CDN de Office 365. Puede permitir que su organización use orígenes públicos, orígenes privados o ambos al mismo tiempo. También puede configurar la red CDN para omitir la configuración de orígenes predeterminados al habilitarla. Siempre puede agregar estos orígenes más adelante, como se describe en este tema.

En PowerShell PnP:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Por ejemplo, para permitir que su organización use orígenes públicos y privados, escriba el siguiente comando:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Para permitir que la organización use orígenes públicos y privados, pero omita la configuración de los orígenes predeterminados, escriba el siguiente comando:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Consulte [Orígenes de red CDN predeterminados](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes aprovisionados de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de orígenes predeterminados.

Para permitir que la organización use orígenes públicos, escriba el siguiente comando:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Para permitir que la organización use orígenes privados, escriba el siguiente comando:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Para obtener más información sobre este cmdlet, vea [Set-PnPTenantCdnEnabled](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnEnabled.html).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Cambiar la lista de tipos de archivo que se van a incluir en la red CDN de Office 365 (opcional)

> [!TIP]
> Al definir tipos de archivo mediante el cmdlet **Set-PnPTenantCdnPolicy** , se sobrescribe la lista definida actualmente. Si desea agregar tipos de archivo adicionales a la lista, use primero el cmdlet para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.

Use el cmdlet **Set-PnPTenantCdnPolicy** para definir tipos de archivo estáticos que se pueden hospedar mediante orígenes públicos y privados en la red CDN. De forma predeterminada, se permiten tipos de recursos comunes, como .css, .gif, .jpg y .js.

En PowerShell PnP:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, escriba el comando :

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-PnPTenantCdnPolicies** :

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Para obtener más información sobre estos cmdlets, vea [Set-PnPTenantCdnPolicy](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnPolicy.html) y [Get-PnPTenantCdnPolicies](https://pnp.github.io/powershell/cmdlets/Get-PnPTenantCdnPolicies.html).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365 (opcional)

> [!TIP]
> Cuando se excluyen las clasificaciones de sitios mediante el cmdlet **Set-PnPTenantCdnPolicy** , se sobrescribe la lista definida actualmente. Si desea excluir clasificaciones de sitio adicionales, use primero el cmdlet para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.

Use el cmdlet **Set-PnPTenantCdnPolicy** para excluir las clasificaciones de sitio que no desea que estén disponibles a través de la red CDN. De forma predeterminada, no se excluyen clasificaciones de sitio.

En PowerShell PnP:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Para ver qué clasificaciones de sitio están restringidas actualmente, use el cmdlet **Get-PnPTenantCdnPolicies** :

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Las propiedades que se devolverán son _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.

La propiedad _IncludeFileExtensions_ contiene la lista de extensiones de archivo que se proporcionarán desde la red CDN.

> [!NOTE]
> Las extensiones de archivo predeterminadas son diferentes entre públicas y privadas.

La propiedad _ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN. Por ejemplo, puede excluir sitios marcados como **Confidenciales** para que el contenido de los sitios con esa clasificación aplicada no se sirva de la red CDN.

La propiedad _ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración del atributo _NoScript_ de nivel de sitio. De forma predeterminada, el atributo _NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para sitios _clásicos_ . Esto depende de la configuración del inquilino.

Para obtener más información sobre estos cmdlets, vea [Set-PnPTenantCdnPolicy](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnPolicy.html) y [Get-PnPTenantCdnPolicies](https://pnp.github.io/powershell/cmdlets/Get-PnPTenantCdnPolicies.html).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Adición de un origen para los recursos

Use el cmdlet **Add-PnPTenantCdnOrigin** para definir un origen. Puede definir varios orígenes. El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.

> [!IMPORTANT]
> Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

El valor de _path_ es la ruta de acceso relativa a la biblioteca o carpeta que contiene los recursos. Puede usar caracteres comodín además de rutas relativas. Los orígenes admiten caracteres comodín antepuestos a la dirección URL. Esto le permite crear orígenes que abarcan varios sitios. Por ejemplo, para incluir todos los recursos en la carpeta masterpages de todos los sitios como origen público dentro de la red CDN, escriba el siguiente comando:

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ El modificador comodín ***/** solo se puede usar al principio de la ruta de acceso y coincidirá con todos los segmentos de dirección URL en la dirección URL especificada.
+ La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio. Por ejemplo, la ruta _de acceso */site1_ coincidirá con todas las bibliotecas de documentos del sitio.

Puede agregar un origen con una ruta de acceso relativa específica. No se puede agregar un origen mediante la ruta de acceso completa.

En este ejemplo se agrega un origen privado de la biblioteca de recursos del sitio en un sitio específico:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

En este ejemplo se agrega un origen privado de la carpeta _folder1_ en la biblioteca de recursos de sitio de la colección de sitios:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio por la codificación de dirección URL %20. En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de recursos de sitio de la colección de sitios:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Para obtener más información sobre este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html).

> [!NOTE]
> En los orígenes privados, los recursos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Ejemplo: Configuración de un origen público para las páginas maestras y para la biblioteca de estilos para SharePoint Online

Normalmente, estos orígenes se configuran de forma predeterminada al habilitar la red CDN de Office 365. Sin embargo, si desea habilitarlos manualmente, siga estos pasos.

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir las páginas maestras como un origen público.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Para obtener más información sobre este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Ejemplo: Configuración de un origen privado para los recursos del sitio, páginas de sitio e imágenes de publicación para SharePoint Online

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de recursos del sitio como un origen privado.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de páginas de sitio como un origen privado.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Para obtener más información sobre este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Esto puede tardar hasta 15 minutos.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Ejemplo: Configuración de un origen privado para una colección de sitios para SharePoint Online

Use el cmdlet **Add-PnPTenantCdnOrigin** para definir una colección de sitios como origen privado. Por ejemplo:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Para obtener más información sobre este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html).

Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos. Es posible que vea un mensaje _pendiente de configuración_ que se espera a medida que el inquilino de SharePoint Online se conecta al servicio CDN. Esto puede tardar hasta 15 minutos.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Administración de la red CDN de Office 365

Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualice el contenido o cuando sus necesidades cambien, como se describe en esta sección.

<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Agregar, actualizar o quitar recursos de la red CDN de Office 365

Una vez que haya completado los pasos de configuración, puede agregar nuevos recursos y actualizar o quitar los recursos existentes siempre que lo desee. Solo tiene que realizar los cambios en los recursos de la carpeta o biblioteca de SharePoint que identificó como origen. Si agrega un nuevo recurso, estará disponible a través de la red CDN inmediatamente. Sin embargo, si actualiza el recurso, la nueva copia tardará hasta 15 minutos en propagarse y estar disponible en la red CDN.

Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-PnPTenantCdnOrigin** . Para obtener información sobre cómo usar este cmdlet, consulte [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Eliminación de un origen de la red CDN de Office 365

Puede quitar el acceso a una carpeta o biblioteca de SharePoint que haya identificado como origen. Para ello, use el cmdlet **Remove-PnPTenantCdnOrigin** .

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Para obtener información sobre cómo usar este cmdlet, consulte [Remove-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Remove-PnPTenantCdnOrigin.html).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificación de un origen en la red CDN de Office 365

No se puede modificar un origen que haya creado. En su lugar, quite el origen y agregue uno nuevo. Para obtener más información, consulte [Para quitar un origen de la red CDN de Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) y [Para agregar un origen para los recursos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deshabilitar la red CDN de Office 365

Use el cmdlet **Set-PnPTenantCdnEnabled** para deshabilitar la red CDN de su organización. Si tiene habilitados los orígenes público y privado para la red CDN, debe ejecutar el cmdlet dos veces como se muestra en los ejemplos siguientes.

Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Para obtener más información sobre este cmdlet, vea [Set-PnPTenantCdnEnabled](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnEnabled.html).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-cli-for-microsoft-365"></a>Configuración y configuración de la red CDN de Office 365 mediante la CLI de Microsoft 365

Los procedimientos de esta sección requieren que haya instalado la [CLI para Microsoft 365](https://aka.ms/cli-m365). A continuación, conéctese al inquilino de Office 365 mediante el comando [de inicio de sesión](https://pnp.github.io/cli-microsoft365/cmd/login/).

Complete estos pasos para configurar y configurar la red CDN para hospedar los recursos en SharePoint Online mediante la CLI de Microsoft 365.

<details>
  <summary>Haga clic para expandir</summary>

### <a name="enable-the-office-365-cdn"></a>Habilitación de la red CDN de Office 365

Puede administrar el estado de la red CDN de Office 365 en su cuenta empresarial con el comando [spo cdn set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-set/).

Para habilitar la red CDN pública de Office 365 en su cuenta empresarial ejecute:

```cli
spo cdn set --type Public --enabled true
```

Para habilitar la red CDN de SharePoint Office 365, ejecute:

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Vea el estado actual de la red CDN de Office 365.

Para comprobar si el tipo determinado de Office 365 CDN está habilitado o deshabilitado, use el comando [spo cdn get](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-get/).

Para comprobar si la red CDN pública de Office 365 está habilitada, ejecute:

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Visualización de los orígenes de la red CDN de Office 365

Para ver los orígenes configurados actualmente de la red CDN pública de Office 365, ejecute:

```cli
spo cdn origin list --type Public
```

Consulte [Orígenes de red CDN predeterminados](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365.

### <a name="add-an-office-365-cdn-origin"></a>Adición de un origen de red CDN de Office 365

> [!IMPORTANT]
> Nunca debe colocar recursos que se consideren confidenciales para su organización en una biblioteca de documentos de SharePoint configurada como un origen público.

Use el comando [spo cdn origin add](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-add/) definir un origen de la red CDN. Puede definir varios orígenes. El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

Donde `path` es la ruta de acceso relativa a la carpeta que contiene los recursos. Puede usar caracteres comodín además de rutas relativas.

Para incluir todos los recursos en la **Galería de páginas maestras** de todos los sitios como origen público, ejecute:

```cli
spo cdn origin add --type Public --origin */masterpage
```

Para configurar un origen privado para una colección de sitios específica, ejecute:

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Después de agregar un origen de la red CDN, puede tardar hasta 15 minutos para poder recuperar archivos mediante el servicio de la red CDN. Puede comprobar si ya se ha habilitado el origen particular con el comando [spo cdn origin list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-list/).

### <a name="remove-an-office-365-cdn-origin"></a>Eliminación de un origen de red CDN de Office 365

Use el comando [spo cdn origin remove](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-remove/) para eliminar un origen de la red CDN para el tipo de red CDN especificado.

Para quitar un origen público de la configuración de la red CDN, ejecute:

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> La eliminación de un origen de CDN no afecta a los archivos almacenados en ninguna biblioteca de documentos que coincida con ese origen. Si se ha hecho referencia a estos recursos mediante su dirección URL de SharePoint, SharePoint volverá automáticamente a la dirección URL original que apunta a la biblioteca de documentos. Sin embargo, si se ha hecho referencia a los recursos mediante una dirección URL de red CDN pública, la eliminación del origen interrumpirá el vínculo y tendrá que cambiarlos manualmente.

### <a name="modify-an-office-365-cdn-origin"></a>Modificación de un origen de red CDN de Office 365

No es posible modificar un origen de la red CDN existente. En su lugar, debe eliminar el origen de la red CDN definido anteriormente con el comando `spo cdn origin remove` y agregar uno nuevo con el comando `spo cdn origin add`.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Cambiar los tipos de archivos que se van a incluir en la red CDN de Office 365

De forma predeterminada, los siguientes tipos de archivo se incluyen en la red CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2_. Si tiene que incluir otros tipos de archivo en la red CDN, puede cambiar la configuración de la red CDN con el comando [spo cdn policy set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-set/).

> [!NOTE]
> Al cambiar la lista de tipos de archivo, se sobrescribe la lista definida actualmente. Si desea incluir otros tipos de archivo, use el comando [spo cdn policy list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-list/) para averiguar qué tipos de archivos están configurados en este momento.

Para agregar el tipo de archivo _JSON_ a la lista predeterminada de tipos de archivo incluidos en la red CDN pública, ejecute:

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365

Use el comando [spo cdn policy set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-set/) para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN. De forma predeterminada, no se excluyen clasificaciones de sitio.

> [!NOTE]
> Al cambiar la lista de clasificaciones de sitio excluidas, se sobrescribe la lista definida actualmente. Si quiere excluir clasificaciones adicionales, use el comando [spo cdn policy list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-list/) para averiguar qué clasificaciones están configuradas en este momento.

Para excluir sitios clasificados como _HBI_ de la red CDN pública, ejecute

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Deshabilitar la red CDN de Office 365

Para deshabilitar la red CDN de Office 365, use el comando `spo cdn set`, por ejemplo:

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Uso de los recursos de la red CDN

Ahora que ha habilitado la red CDN y ha configurado orígenes y directivas, puede empezar a usar los recursos de la red CDN.

Esta sección le ayudará a comprender cómo usar direcciones URL de CDN en las páginas y el contenido de SharePoint para que SharePoint redirija las solicitudes de recursos en orígenes públicos y privados a la red CDN.

+ [Actualización de vínculos a recursos de RED CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Uso de recursos en orígenes públicos](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Uso de recursos en orígenes privados](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Para obtener información sobre cómo usar la red CDN para hospedar elementos web del lado cliente, vea el tema [Host your client-side web part from Office 365 CDN (Hola mundo part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).

> [!NOTE]
> Si agrega la carpeta _ClientSideAssets_ a la lista de orígenes de red CDN **privada** , los elementos web personalizados hospedados en CDN no se representarán. Los archivos que usan los elementos web SPFX solo pueden usar la red CDN pública y la carpeta ClientSideAssets es un origen predeterminado para la red CDN pública.

### <a name="updating-links-to-cdn-assets"></a>Actualización de vínculos a recursos de RED CDN

Para usar los recursos que ha agregado a un origen, basta con actualizar los vínculos al archivo original con la ruta de acceso al archivo en el origen.

+ Edite la página o el contenido que contiene vínculos a los recursos que ha agregado a un origen. También puede usar uno de varios métodos para buscar globalmente y reemplazar vínculos en un sitio o colección de sitios de entrada si desea actualizar el vínculo a un recurso determinado en cualquier lugar donde aparezca.
+ Para cada vínculo a un recurso de un origen, reemplace la ruta de acceso por la ruta de acceso al archivo en el origen de la red CDN. Puede usar rutas de acceso relativas.
+ Guarde la página o el contenido.

Por ejemplo, considere la imagen _/site/SiteAssets/images/image.png_, que ha copiado en la carpeta de la biblioteca de documentos _/site/CDN_origins/public/_. Para usar el recurso de CDN, reemplace la ruta de acceso original a la ubicación del archivo de imagen por la ruta de acceso al origen para que la nueva dirección URL _/site/CDN_origins/public/image.png_.

Si desea usar la dirección URL completa del recurso en lugar de una ruta de acceso relativa, construya el vínculo de la siguiente manera:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> En general, no debe codificar direcciones URL directamente en los recursos de la red CDN. Sin embargo, puede crear manualmente direcciones URL para los recursos en orígenes públicos si es necesario. Para obtener más información, consulte [Codificación rígida de direcciones URL de CDN para recursos públicos](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets).

Para obtener información sobre cómo comprobar que los recursos se atienden desde la red CDN, consulte [Cómo confirmar que la red CDN proporciona los recursos?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) en [Solución de problemas de la red CDN de Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).

### <a name="using-assets-in-public-origins"></a>Uso de recursos en orígenes públicos

La **característica de publicación** en SharePoint Online vuelve a escribir automáticamente las direcciones URL de los recursos almacenados en orígenes públicos en sus equivalentes de red CDN para que los recursos se sirvan desde el servicio CDN en lugar de SharePoint.

Si el origen está en un sitio con la característica publicación habilitada y los recursos que desea descargar en la red CDN se encuentran en una de las siguientes categorías, SharePoint volverá a escribir automáticamente las direcciones URL de los recursos del origen, siempre que una directiva de CDN no excluya el recurso.

A continuación, se muestra información general sobre los vínculos que la característica de publicación de SharePoint reescribe automáticamente:

+ URL de IMG/LINK/CSS en respuestas de HTML de página de publicación clásica
  + Esto incluye imágenes que han agregado autores en el contenido HTML de una página
+ URL de las imágenes del elemento web de presentación de la biblioteca de imágenes
+ Campos de imagen de los resultados de la API de REST SPList (RenderListDataAsStream)
  + Use la nueva propiedad _ImageFieldsToTryRewriteToCdnUrls_ para proporcionar una lista separada por comas de campos
  + Admite campos de hipervínculo y campos PublishingImage
+ Representaciones de imágenes de SharePoint

En el diagrama siguiente se muestra el flujo de trabajo cuando SharePoint recibe una solicitud para una página que contiene recursos de un origen público.

![Diagrama de flujo de trabajo: recuperación de Office 365 recursos de red CDN de un origen público.](../media/O365-CDN/o365-cdn-public-steps-transparent.png "Flujo de trabajo: recuperación de Office 365 recursos de red CDN desde un origen público")

> [!TIP]
> Si desea deshabilitar la reescritura automática para direcciones URL específicas en una página, puede desteger la página y agregar el parámetro de cadena de consulta **? NoAutoReWrites=true** al final de cada vínculo que quiera deshabilitar.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Construcción de direcciones URL de CDN para recursos públicos

Si la característica _de publicación_ no está habilitada para un origen público o el recurso no es uno de los tipos de vínculo admitidos por la característica de reescritura automática del servicio CDN, puede crear manualmente direcciones URL en la ubicación de la red CDN de los recursos y usar estas direcciones URL en el contenido.

> [!NOTE]
> No puede codificar de forma rígida ni construir direcciones URL de CDN en recursos de un origen privado porque el token de acceso necesario que forma la última sección de la dirección URL se genera en el momento en que se solicita el recurso. Puede construir la dirección URL para la red CDN pública y la dirección URL no debe codificarse de forma rígida, ya que está sujeta a cambios.

En el caso de los recursos de red CDN públicos, el formato de dirección URL será similar al siguiente:

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Reemplace **TenantHostName** por el nombre del inquilino. Ejemplo:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> La propiedad de contexto de página debe usarse para construir el prefijo en lugar de codificar de forma rígida "https://publiccdn.sharepointonline.com". La dirección URL está sujeta a cambios y no debe codificarse de forma rígida. Si usa plantillas para mostrar con SharePoint Online clásico, puede usar la propiedad "window._spPageContextInfo.publicCdnBaseUrl" en la plantilla para mostrar para el prefijo de la dirección URL. Si es elementos web SPFx para SharePoint moderno y clásico, puede usar la propiedad "this.context.pageContext.legacyPageContext.publicCdnBaseUrl". Esto proporcionará el prefijo para que, si se cambia, la implementación se actualice con él. Como ejemplo para SPFx, la dirección URL se puede construir mediante la propiedad "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL para el elemento". Consulte [Uso de CDN en el código del lado cliente](https://youtu.be/IH1RbQlbhIA) que forma parte de la serie de rendimiento de la [temporada 1](https://aka.ms/sppnp-perfvideos).


### <a name="using-assets-in-private-origins"></a>Uso de recursos en orígenes privados

No se requiere ninguna configuración adicional para usar recursos en orígenes privados. SharePoint Online vuelve a escribir automáticamente las direcciones URL de los recursos en orígenes privados, por lo que las solicitudes de esos recursos siempre se atenderán desde la red CDN. No se pueden crear manualmente direcciones URL en recursos de CDN en orígenes privados porque estas direcciones URL contienen tokens que SharePoint Online debe generar automáticamente en el momento en que se solicita el recurso.

El acceso a los recursos en orígenes privados está protegido por tokens generados dinámicamente en función de los permisos de usuario para el origen, con las advertencias descritas en las secciones siguientes. Los usuarios deben tener al menos acceso de **lectura** a los orígenes para que la red CDN represente el contenido.

En el diagrama siguiente se muestra el flujo de trabajo cuando SharePoint recibe una solicitud para una página que contiene recursos de un origen privado.

![Diagrama de flujo de trabajo: recuperación de Office 365 recursos de red CDN desde un origen privado.](../media/O365-CDN/o365-cdn-private-steps-transparent.png "Flujo de trabajo: recuperación de Office 365 recursos de red CDN desde un origen privado")

#### <a name="token-based-authorization-in-private-origins"></a>Autorización basada en tokens en orígenes privados

El acceso a los recursos en orígenes privados en la red CDN de Office 365 se concede mediante tokens generados por SharePoint Online. A los usuarios que ya tienen permiso para acceder a la carpeta o biblioteca designada por el origen se les conceden automáticamente tokens que permiten al usuario acceder al archivo en función de su nivel de permiso. Estos tokens de acceso son válidos entre 30 y 90 minutos después de que se generen para ayudar a evitar ataques de reproducción de tokens.

Una vez generado el token de acceso, SharePoint Online devuelve un URI personalizado al cliente que contiene dos parámetros de autorización _comer_ (token de autorización perimetral) y _avena_ (token de autorización de origen). La estructura de cada token es _< tiempo de expiración en formato de hora de época'>__<'secure signature'>_. Por ejemplo:

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Cualquier persona que posea el token puede acceder al recurso en la red CDN. Sin embargo, las direcciones URL que contienen estos tokens de acceso solo se comparten a través de HTTPS, por lo que, a menos que un usuario final comparta explícitamente la dirección URL antes de que expire el token, el recurso no será accesible para los usuarios no autorizados.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>No se admiten permisos de nivel de elemento para recursos en orígenes privados

Es importante tener en cuenta que SharePoint Online no admite permisos de nivel de elemento para los recursos en orígenes privados. Por ejemplo, para un archivo ubicado en `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, los usuarios tienen acceso efectivo al archivo dadas las condiciones siguientes:

|Usuario  |Permisos  |Acceso efectivo  |
|---------|---------|---------|
|Usuario 1     |Tiene acceso a folder1         |Puede acceder a image1.jpg desde la red CDN.         |
|Usuario 2     |No tiene acceso a folder1         |No se puede acceder a image1.jpg desde la red CDN         |
|Usuario 3     |No tiene acceso a folder1, pero se le concede permiso explícito para acceder a image1.jpg en SharePoint Online.         |Puede acceder al recurso image1.jpg directamente desde SharePoint Online, pero no desde la red CDN.         |
|Usuario 4     |Tiene acceso a folder1, pero se ha denegado explícitamente el acceso a image1.jpg en SharePoint Online.         |No se puede acceder al recurso desde SharePoint Online, pero puede acceder al recurso desde la red CDN a pesar de que se le ha denegado el acceso al archivo en SharePoint Online.         |

<a name="CDNTroubleshooting"></a>

## <a name="troubleshooting-the-office-365-cdn"></a>Solución de problemas de la red CDN de Office 365

<a name="CDNConfirm"></a>

### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Cómo confirmar que la red CDN está ateniendo recursos?

Una vez que haya agregado vínculos a recursos de CDN a una página, puede confirmar que el recurso se está sirviendo desde la red CDN; para ello, vaya a la página, haga clic con el botón derecho en la imagen una vez que se haya representado y revise la dirección URL de la imagen.

También puede usar las herramientas de desarrollo del explorador para ver la dirección URL de cada recurso de una página o usar una herramienta de seguimiento de red de terceros.

> [!NOTE]
> Si usa una herramienta de red como Fiddler para probar los recursos fuera de la representación del recurso desde una página de SharePoint, debe agregar manualmente el encabezado de referencia "Referencia: `https://yourdomain.sharepoint.com`" a la solicitud GET donde la dirección URL es la dirección URL raíz del inquilino de SharePoint Online.

No puede probar las direcciones URL de CDN directamente en un explorador web porque debe tener un referenciador procedente de SharePoint Online. Sin embargo, si agrega la dirección URL del recurso de CDN a una página de SharePoint y, a continuación, abre la página en un explorador, verá el recurso de CDN representado en la página.

Para obtener más información sobre el uso de las herramientas de desarrollo en el explorador Microsoft Edge, consulte [Herramientas de desarrollo de Microsoft Edge](/microsoft-edge/devtools-guide).

Para ver un breve vídeo hospedado en el [canal de YouTube Patrones y prácticas para desarrolladores de SharePoint](https://aka.ms/sppnp-videos) que muestra cómo comprobar que la red CDN funciona, consulte [Comprobación del uso de la red CDN y garantía de una conectividad de red óptima](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>¿Por qué los recursos de un nuevo origen no están disponibles?
Los recursos de orígenes nuevos no estarán disponibles inmediatamente para su uso, ya que el registro tarda tiempo en propagarse a través de la red CDN y para que los recursos se carguen desde el origen al almacenamiento de la red CDN. El tiempo necesario para que los recursos estén disponibles en la red CDN depende del número de recursos y de los tamaños de los archivos.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Mi elemento web del lado cliente o SharePoint Framework solución no funciona

Al habilitar la red CDN de Office 365 para orígenes públicos, el servicio CDN crea automáticamente estos orígenes predeterminados:

+ */MASTERPAGE
+ */BIBLIOTECA DE ESTILOS
+ */CLIENTSIDEASSETS

Si falta el origen */clientsideassets, se producirá un error en las soluciones SharePoint Framework y no se generarán mensajes de advertencia o error. Puede que falte este origen porque la red CDN se ha habilitado con el parámetro _-NoDefaultOrigins_ establecido en **$true** o porque el origen se ha eliminado manualmente.

Puede comprobar qué orígenes están presentes con el siguiente comando de PowerShell:

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

O bien, puede comprobar con la CLI de Office 365:

```cli
spo cdn origin list
```

Para agregar el origen en PowerShell:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Para agregar el origen en la CLI de Office 365:

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>¿Qué módulos de PowerShell y shells de la CLI necesito para trabajar con la red CDN de Office 365?

Puede optar por trabajar con la red CDN de Office 365 mediante el módulo de PowerShell del **Shell de administración de SharePoint Online** o la **CLI de Office 365**.

+ [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [Instalar Office 365 CLI](https://pnp.github.io/cli-microsoft365/user-guide/installing-cli/)

## <a name="see-also"></a>Consulte también

[Redes de entrega de contenido](./content-delivery-networks.md)

[Planeamiento de red y ajuste del rendimiento para Office 365](./network-planning-and-performance.md)

[Serie de rendimiento de SharePoint: serie de vídeo Office 365 CDN](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
