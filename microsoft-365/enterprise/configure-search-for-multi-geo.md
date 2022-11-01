---
title: Configurar la búsqueda para Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar la búsqueda en un entorno multigeográfico. Solo algunos clientes, como OneDrive, pueden devolver resultados en un entorno multigeográfico.
ms.openlocfilehash: 2cd31d6b5b5b4f6b957741b8b9209c7693ca169f
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804650"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a>Configurar la búsqueda para Microsoft 365 Multi-Geo

## <a name="configure-multi-geo-search"></a>Configuración de la búsqueda multigeográfica

El _inquilino multigeográfico_ tendrá funcionalidades de búsqueda agregadas que permiten que una consulta de búsqueda devuelva resultados desde cualquier lugar dentro del _inquilino_.

De forma predeterminada, las búsquedas de estos puntos de entrada devolverán resultados agregados, aunque cada índice de búsqueda se encuentre dentro de su ubicación _geográfica_ pertinente:

- OneDrive para la Empresa
- Delve
- Página principal de SharePoint
- Centro de búsqueda

Además, las funcionalidades de búsqueda multigeográfica se pueden configurar para las aplicaciones de búsqueda personalizadas que usan la API de búsqueda de SharePoint.

Revise [Configurar la búsqueda en OneDrive para la Empresa multigeográfico](configure-search-for-multi-geo.md) para obtener instrucciones, incluidas las limitaciones y diferencias.

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>Validar la configuración de Microsoft 365 Multi-Geo

A continuación se muestran algunos casos de uso básicos que tal vez quiera incluir en el plan de validación antes implementar Microsoft 365 Multi-Geo de manera general en la compañía. Después de completar estas pruebas y los casos de uso adicionales que sean relevantes para su compañía, puede continuar y agregar los usuarios al grupo piloto inicial.

OneDrive para la Empresa:

Seleccione OneDrive en el iniciador de aplicaciones de Microsoft 365 y confirme que se le dirige automáticamente a la ubicación _geográfica_ adecuada para el usuario, en función de la PDL del usuario. OneDrive para la Empresa debería ahora comenzar el aprovisionamiento en esa ubicación. Una vez aprovisionado, pruebe a cargar y descargar algunos documentos.

Aplicación móvil de OneDrive:

Inicie sesión en la aplicación móvil de OneDrive con las credenciales de la cuenta de prueba. Confirme que puede ver sus archivos de OneDrive para la Empresa y puede interactuar con ellos desde su dispositivo móvil.

Sincronización de OneDrive cliente:

Confirme que el cliente de Sincronización de OneDrive detecta automáticamente la ubicación OneDrive para la Empresa _Geography_ al iniciar sesión. Si necesita descargar el cliente de sincronización, puede hacer clic en **Sincronizar** en la biblioteca de OneDrive.

Aplicaciones de Office:

Confirme que puede acceder a OneDrive para la Empresa iniciando sesión desde una aplicación de Office, como Word. Abra la aplicación de Office y seleccione **OneDrive: \<TenantName\>**. Office detectará la ubicación de OneDrive y le mostrará los archivos que puede abrir.

Compartir:

Pruebe a compartir archivos de OneDrive. Confirme que el selector de personas le muestra todos los usuarios de SharePoint Online independientemente de su ubicación _geográfica_ .

En un entorno multigeográfico, cada ubicación _geography_ tiene su propio índice de búsqueda y centro de búsqueda. Cuando un usuario realiza una búsqueda, se efectúa una distribución ramificada de la consulta a todos los índices y los resultados devueltos se combinan.

Por ejemplo, un usuario de una ubicación _geography_ puede buscar contenido almacenado en otra ubicación _de Geography_ o contenido en un sitio de SharePoint restringido a otra ubicación geográfica. Si el usuario tiene acceso a este contenido, la búsqueda mostrará el resultado.

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a>¿Qué clientes de búsqueda funcionan en un entorno multigeográfico?

Estos clientes pueden devolver resultados de todas las ubicaciones geography:

- OneDrive
- Delve
- Página principal de SharePoint
- Centro de búsqueda
- Aplicaciones de búsqueda personalizada que usan la API de SharePoint Search

### <a name="onedrive"></a>OneDrive

Tan pronto como se haya configurado el entorno multigeográfico, los usuarios que busquen en OneDrive obtendrán resultados de todas las ubicaciones _geográficas_ .

### <a name="delve"></a>Delve

Tan pronto como se haya configurado el entorno multigeográfico, los usuarios que busquen en Delve obtendrán resultados de todas las ubicaciones _geográficas_ .

La fuente de Delve y la tarjeta de perfil solo muestran vistas previas de los archivos almacenados en la ubicación central. En el caso de los archivos almacenados en ubicaciones _de Geografía satélite_ , se muestra el icono del tipo de archivo en su lugar.

### <a name="the-sharepoint-home-page"></a>Página principal de SharePoint

En cuanto se haya configurado el entorno multigeográfico, los usuarios verán noticias, sitios recientes y seguidos de varias ubicaciones _geográficas_ en su página principal de SharePoint. Si usan el cuadro de búsqueda en la página principal de SharePoint, obtendrán resultados combinados de varias ubicaciones _geography_ .

### <a name="the-search-center"></a>Centro de búsqueda

Una vez configurado el entorno multigeográfico, cada Centro de búsqueda sigue mostrando solo los resultados de su propia ubicación _geográfica_ . Los administradores deben [cambiar la configuración de cada Centro de búsqueda](#_Set_up_a_1) para obtener resultados de todas las ubicaciones _de Geografía_ . Después, los usuarios que buscan en el Centro de búsqueda obtienen resultados de todas las ubicaciones _de Geography_ .

### <a name="custom-search-applications"></a>Aplicaciones de búsqueda personalizada

Como de costumbre, las aplicaciones de búsqueda personalizadas interactúan con los índices de búsqueda mediante las API REST de búsqueda de SharePoint existentes. Para obtener resultados de todas o algunas ubicaciones _de Geography_ , la aplicación debe [llamar a la API e incluir los nuevos parámetros de consulta multigeográfica](#_Get_custom_search) en la solicitud. Esto desencadena un ventilador fuera de la consulta a todas las ubicaciones _geography_ .

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a>¿Qué hay de diferente en la búsqueda en un entorno multigeográfico?

Algunas características de búsqueda con las que tal vez esté familiarizado, funcionan de forma distinta en un entorno multigeográfico.

<table>
<thead>
<tr class="header">
<th align="left">Característica</th>
<th align="left">Cómo funciona</th>
<th align="left">Solución alternativa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Resultados promocionados</td>
<td align="left">Puede crear reglas de consulta con resultados promocionados en distintos niveles: para todo el _inquilino_, para una colección de sitios o para un sitio. En un entorno multigeográfico, defina los resultados promocionados en el nivel _de inquilino_ para promover los resultados a los centros de búsqueda de todas las ubicaciones _geográficas_ . Si solo desea promocionar los resultados en el Centro de búsqueda que se encuentra en la ubicación _Geography_ de la colección de sitios o el sitio, defina los resultados promocionados en el nivel de sitio o colección de sitios. Estos resultados no se promueven en otras ubicaciones _de Geography_ .</td>
<td align="left">Si no necesita resultados promocionados diferentes por ubicación _geográfica_ , por ejemplo, reglas diferentes para viajar, se recomienda definir los resultados promocionados en el nivel _de inquilino_ .</td>
</tr>
<tr class="even">
<td align="left">Refinadores de búsquedas</td>
<td align="left">Search devuelve refinadores de todas las ubicaciones _geography_ de un _inquilino_ y, a continuación, los agrega. La agregación es un esfuerzo óptimo, lo que significa que es posible que los recuentos de refinador no sean 100% precisos. Para la mayoría de los escenarios controlados por búsqueda, esta precisión es suficiente.
</td>
<td align="left">Para las aplicaciones controladas por búsqueda que dependen de la integridad del refinador, consulte cada ubicación _de Geography_ de forma independiente.</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left">La búsqueda multigeográfica no admite el cubo dinámico para refinadores numéricos.</td>
<td align="left">Use el <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">parámetro "Discretize"</a> para refinadores numéricos.</td>
</tr>
<tr class="even">
<td align="left">Identificadores de documento</td>
<td align="left">Si va a desarrollar una aplicación controlada por búsquedas que depende de los identificadores de documento, tenga en cuenta que los identificadores de documento en un entorno multigeográfico no son únicos en ubicaciones _geográficas_ , son únicos por ubicación _geográfica_ .</td>
<td align="left">Hemos agregado una columna que identifica la ubicación _geography_ . Utilice esta columna para lograr unicidad. Esta columna se denomina "GeoLocationSource".</td>
</tr>
<tr class="odd">
<td align="left">Número de resultados</td>
<td align="left">La página de resultados de búsqueda muestra los resultados combinados de las ubicaciones _geography_ , pero no es posible paginar más allá de 500 resultados.</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Búsqueda híbrida</td>
<td align="left">En un entorno de SharePoint híbrido con <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">búsqueda de nube híbrida</a>, el contenido local se agrega al índice de Microsoft 365 de la ubicación central.</td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a>¿Qué no es compatible con la búsqueda en un entorno multigeográfico?

Algunas características de búsqueda con las que tal vez esté familiarizado, no se admiten en un entorno multigeográfico.

<table>
<thead>
<tr class="header">
<th align="left">Característica de búsqueda</th>
<th align="left">Nota:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Autenticación solo de aplicación</td>
<td align="left">La autenticación solo de aplicación (acceso con privilegios desde servicios) no se admite en la búsqueda multigeográfica.</td>
</tr>
<tr class="even">
<td align="left">Invitados</td>
<td align="left">Los invitados solo obtienen resultados de la ubicación _de Geography_ desde la que buscan.</td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a>¿Cómo funciona la búsqueda en un entorno multigeográfico?

Todos los clientes de búsqueda usan la API REST de SharePoint Search existente para interactuar con los índices de búsqueda.

![Diagrama que muestra cómo interactúan las API REST de Búsqueda de SharePoint con los índices de búsqueda.](../media/configure-search-for-multi-geo-image1-1.png)

1. Un cliente de búsqueda llama al punto de conexión de REST de búsqueda con la propiedad EnableMultiGeoSearch= true.
2. La consulta se envía a todas las ubicaciones _geography_ del _inquilino_.
3. Los resultados de búsqueda de cada ubicación _geography_ se combinan y clasifican.
4. El cliente obtiene resultados unificados.

<span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Observe que no combinamos los resultados de búsqueda hasta que hemos recibido los resultados de todas las ubicaciones geográficas. Esto significa que las búsquedas multigeográficas tienen latencia adicional con respecto a las búsquedas en un entorno de una sola ubicación geográfica.

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a>Obtener un Centro de búsqueda que muestre los resultados de todas las ubicaciones geográficas

Cada Centro de búsqueda tiene varios sectores verticales y hay que configurar individualmente cada sector vertical.

1. Asegúrese de realizar estos pasos con una cuenta que tenga permiso para editar la página de resultados de búsqueda y el elemento web de resultados de búsqueda.

2. Navegue a la página de resultados de búsqueda (vea la [lista](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) de páginas de resultados de búsqueda).

3. Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**. The search results page opens in Edit mode.

   ![Edite la selección de página en Configuración.](../media/configure-search-for-multi-geo-image2.png)

4. En el elemento web Resultados de búsqueda, mueva el puntero a la esquina superior derecha del elemento web, haga clic en la flecha y, a continuación, haga clic en **Editar elemento web** en el menú. El panel de herramientas del elemento web de resultados de búsqueda se abrirá debajo de la cinta en la parte superior derecha de la página.

   ![Editar selección de elementos web.](../media/configure-search-for-multi-geo-image3.png)

5. En la sección **Configuración** del panel de herramientas del elemento web de resultados de búsqueda, en **Configuración de control de resultados**, seleccione **Show Multi-Geo results** (Mostrar resultados multigeográficos) para que el elemento web de resultados de la búsqueda muestre los resultados de todas las ubicaciones geográficas.

6. Haga clic en **Aceptar** para guardar los cambios y cierre el panel de herramientas del elemento web.

7. Para comprobar los cambios realizados en el elemento web de resultados de búsqueda, haga clic en **Proteger** en la pestaña de página del menú principal.

8. Publique los cambios mediante el vínculo incluido en la nota de la parte superior de la página.

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a>Obtener aplicaciones de búsqueda personalizada que muestren los resultados de todas o algunas de las ubicaciones geográficas

Las aplicaciones de búsqueda personalizadas obtienen resultados de todas o algunas ubicaciones _de Geography_ especificando parámetros de consulta con la solicitud a la API REST de búsqueda de SharePoint. En función de los parámetros de consulta, la consulta se amplía a todas las ubicaciones _geography_ o a algunas ubicaciones geográficas. Por ejemplo, si solo necesita consultar un subconjunto de ubicaciones _geography_ para encontrar información relevante, puede controlar el ventilador solo para estas. Si la solicitud se realiza correctamente, la API REST de Búsqueda de SharePoint devuelve datos de respuesta.

### <a name="requirement"></a>Requisito

For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso **APAC**.sharepoint.com/ and contoso **EU**.sharepoint.com/). [Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).

### <a name="query-parameters"></a>Parámetros de consulta

EnableMultiGeoSearch: se trata de un valor booleano que especifica si la consulta se debe ampliar a los índices de otras ubicaciones geográficas del _inquilino multigeográfico_. Establézcalo en **true** para efectuar una distribución ramificada de la consulta o en **false** para no hacerlo. Si no incluye este parámetro, el valor por defecto es **falso**, excepto cuando se realiza una llamada a REST API contra un sitio que utiliza la plantilla de Enterprise Search Center, en este caso el valor por defecto es **verdadero**.  Si usa el parámetro en un entorno que no es multigeográfico, se ignorará el parámetro.

ClientType: es una cadena. Escriba un nombre de cliente único para cada aplicación de búsqueda. Si no incluye este parámetro, no se efectúa una distribución ramificada de la consulta a otra ubicación geográfica.

MultiGeoSearchConfiguration: se trata de una lista opcional de las ubicaciones geográficas del _inquilino_ multigeográfico a las que se va a hospedar la consulta cuando **EnableMultiGeoSearch** es **true**. Si no incluye este parámetro o lo deja en blanco, se efectúa una distribución ramificada de la consulta a todas las ubicaciones geográficas. Para cada ubicación geográfica, escriba los elementos siguientes, con formato JSON:

<table>
<thead>
<tr class="header">
<th align="left">Elemento</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">DataLocation</td>
<td align="left">Ubicación _geográfica_ , por ejemplo, NAM.</td>
</tr>
<tr class="even">
<td align="left">EndPoint</td>
<td align="left">Punto de conexión al que conectarse; por ejemplo, https://contoso.sharepoint.com</td>
</tr>
<tr class="odd">
<td align="left">SourceId</td>
<td align="left">GUID del origen de resultados, por ejemplo, B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</td>
</tr>
</tbody>
</table>

If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails. [You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).

### <a name="response-data"></a>Datos de respuesta

MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request. The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:

<table>
<thead>
<tr class="header">
<th align="left">Valor</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Full</td>
<td align="left">Resultados completos de <strong>todas</strong> las ubicaciones _geography_ .</td>
</tr>
<tr class="even">
<td align="left">Parcial</td>
<td align="left">Resultados parciales de una o varias ubicaciones _geography_ . Los resultados están incompletos debido a un error transitorio.</td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a>Consultar con el servicio REST

With a GET request, you specify the query parameters in the URL. With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.

#### <a name="request-headers"></a>Encabezados de solicitud

<table>
<thead>
<tr class="header">
<th align="left">Nombre</th>
<th align="left">Valor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Content-Type</td>
<td align="left">application/json;odata=verbose</td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a>Ejemplo de distribución ramificada de una solicitud GET a **todas** las ubicaciones geográficas

```http
https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'
```

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a>Ejemplo de solicitud GET para efectuar una distribución ramificada en **algunas** ubicaciones geográficas

```http
https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'
```

> [!NOTE]
> Las comas y los dos puntos de la lista de ubicaciones geográficas de la propiedad MultiGeoSearchConfiguration van precedidas por el carácter **barra diagonal inversa**. Esto se debe a que las solicitudes GET usan dos puntos para separar las propiedades y comas para separar los argumentos de las propiedades. Sin la barra diagonal inversa como carácter de escape, la propiedad MultiGeoSearchConfiguration se interpreta de forma errónea.

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a>Ejemplo de distribución ramificada de una solicitud POST a **todas** las ubicaciones geográficas

```http
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a>Ejemplo de distribución ramificada de una solicitud POST a **algunas** ubicaciones geográficas

```http
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a>Consultar con CSOM

Esta es una consulta de CSOM de ejemplo que se amplía a **todas las** ubicaciones _de Geography_ :

```CSOM
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery.Properties["EnableMultiGeoSearch"] = true;
```
