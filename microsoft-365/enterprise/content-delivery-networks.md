---
title: Redes de entrega de contenido
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: Use esta información para obtener información sobre cómo Office 365 redes de entrega de contenido (CDN) para mejorar el rendimiento.
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911101"
---
# <a name="content-delivery-networks-cdns"></a>Redes de entrega de contenido (CDN)

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Las CDN ayudan a Office 365 rápidas y confiables para los usuarios finales. Los servicios en la nube como Office 365 las CDN para almacenar en caché activos estáticos más cercanos a los exploradores que les solicitan que aceleres las descargas y reduzcan la latencia percibida por el usuario final. La información de este tema le ayudará a obtener información sobre las redes de entrega de contenido (CDN) y cómo las usa Office 365.

## <a name="what-exactly-is-a-cdn"></a>¿Qué es exactamente CDN?

Un CDN es una red distribuida geográficamente formada por servidores proxy y de archivos en centros de datos conectados por redes troncales de alta velocidad. Las CDN se usan para reducir los tiempos de latencia y carga de un conjunto especificado de archivos y objetos en un sitio web o servicio. Un CDN puede tener muchos miles de puntos de conexión para el mantenimiento óptimo de las solicitudes entrantes desde cualquier ubicación.

Las CDN se usan normalmente para proporcionar descargas más rápidas de contenido genérico para un sitio web o servicio, como archivos javascript, iconos e imágenes, y también pueden proporcionar acceso privado al contenido del usuario, como archivos de bibliotecas de documentos en línea de SharePoint, archivos multimedia de streaming y código personalizado.

La mayoría de los servicios en la nube de empresa usan las CDN. Los servicios en la nube como Office 365 millones de clientes descargan una mezcla de contenido propietario (como correos electrónicos) y contenido genérico (como iconos) a la vez. Es más eficaz colocar imágenes que todos los usuarios usan, como iconos, lo más cerca posible del equipo del usuario. No es práctico para todos los servicios en la nube crear centros de datos CDN que almacenen este contenido genérico en todas las áreas metropolitanas, o incluso en todos los principales centros de Internet de todo el mundo, por lo que algunas de estas CDN se comparten.

## <a name="how-do-cdns-make-services-work-faster"></a>¿Cómo las CDN hacen que los servicios funcionen más rápido?

Descargar objetos comunes como imágenes de sitio e iconos una y otra vez puede tomar un ancho de banda de red que se puede usar mejor para descargar contenido personal importante, como correo electrónico o documentos. Dado que Office 365 una arquitectura que incluye CDN, los iconos, scripts y otro contenido genérico se pueden descargar desde servidores más cercanos a los equipos cliente, lo que hace que las descargas sean más rápidas. Esto significa un acceso más rápido al contenido personal, que se almacena de forma segura en Office 365 centros de datos.

Las CDN ayudan a mejorar el rendimiento del servicio en la nube de varias maneras:

- Las CDN alejan parte de la carga de descarga de archivos y red del servicio en la nube, liberando recursos de servicio en la nube para servir contenido de usuario y otros servicios al reducir la necesidad de atender solicitudes de activos estáticos.
- Las CDN están diseñadas para proporcionar acceso a archivos de baja latencia mediante la implementación de redes de alto rendimiento y servidores de archivos, y al aprovechar protocolos de red actualizados como [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) con compresión y multiplexación de solicitudes altamente eficientes.
- CDN usan muchos puntos de conexión distribuidos globalmente para que el contenido esté disponible lo más cerca posible para los usuarios.

## <a name="the-office-365-cdn"></a>El Office 365 CDN

El Office 365 Content Delivery Network integrado (CDN) permite a los administradores de Office 365 proporcionar un mejor rendimiento para las páginas de SharePoint Online de su organización mediante el almacenamiento en caché de activos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar las descargas y reducir la latencia. El Office 365 CDN usa el [protocolo HTTP/2 para](https://en.wikipedia.org/wiki/HTTP/2) mejorar las velocidades de compresión y descarga.

> [!NOTE]
> La Office 365 CDN solo está disponible para los inquilinos en la **nube de** producción (en todo el mundo). Actualmente, los inquilinos de las nubes de Estados Unidos, China y Alemania no admiten el Office 365 CDN.

La CDN de Office 365 se compone de varias redes CDN que permite hospedar archivos estáticos en varias ubicaciones u _orígenes_ y a realizar la entrega desde redes de alta velocidad globales. Según el tipo de contenido que quiera hospedar en la CDN de Office 365, puede agregar orígenes **públicos**, **privados** o ambos.

![Office 365 CDN diagrama conceptual](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN diagrama conceptual")

El contenido en orígenes **públicos** dentro de la CDN de Office 365 es accesible de forma anónima y cualquier persona que tenga la URL a los activos hospedado puede acceder. Como el acceso al contenido en orígenes públicos es anónimo, solo debe usarlos para almacenar en caché contenido genérico y no confidencial, como archivos javascript, scripts, iconos e imágenes. La CDN de Office 365 se usa de forma predeterminada para descargar activos de recurso genéricos como las aplicaciones cliente de Office 365 desde un origen público.

**Los** orígenes privados dentro del Office 365 CDN proporcionan acceso privado al contenido del usuario, como bibliotecas de documentos en línea, sitios e imágenes propietarias de SharePoint en línea. El acceso al contenido de orígenes privados está protegido con tokens generados de forma dinámica, por lo que pueden acceder los usuarios con permisos para la ubicación de almacenamiento o de biblioteca de documentos original. Los orígenes privados en la CDN de Office 365 solo pueden usarse para el contenido de SharePoint Online y solo se puede acceder a los activos mediante el redireccionamiento de su espacio empresarial de SharePoint Online.

La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.

Para obtener más información acerca de cómo usar el Office 365 CDN, vea [Use the Office 365 content delivery network with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Para ver una serie de vídeos cortos que proporcionan información conceptual y HOWTO sobre el uso de la Office 365 CDN, visite el canal de YouTube SharePoint [Developer Patterns and Practices](https://aka.ms/sppnp-videos).

## <a name="other-microsoft-cdns"></a>Otras CDN de Microsoft

Aunque no forma parte del Office 365 CDN, puede usar estas CDN en su inquilino de Office 365 para obtener acceso a bibliotecas de desarrollo de SharePoint, código personalizado y otros fines que se encuentran fuera del ámbito del Office 365 CDN.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>A partir del tercer trimestre de 2020, SharePoint Online empezará a almacenar vídeos en caché en el Azure CDN para admitir una reproducción y confiabilidad de vídeo mejoradas. Los vídeos populares se transmitirán desde CDN punto de conexión más cercano al usuario. Estos datos permanecerán dentro del límite Microsoft 365 cumplimiento. Este es un servicio gratuito para todos los inquilinos y no requiere ninguna acción del cliente para configurar.

Puede usar el **Azure CDN** para implementar su propia instancia de CDN para hospedar elementos web personalizados, bibliotecas y otros activos de recursos, lo que le permite aplicar claves de acceso al almacenamiento de CDN y ejercer un mayor control sobre la configuración de CDN. El uso del Azure CDN no es gratuito y requiere una suscripción de Azure.

Para obtener más información sobre cómo configurar una instancia Azure CDN, vea [Inicio rápido: Integrar](/azure/cdn/cdn-create-a-storage-account-with-cdn)una cuenta de Azure Storage con Azure CDN .

Para obtener un ejemplo de cómo Azure CDN puede usarse para hospedar elementos web SharePoint, vea [Deploy your SharePoint client-side web part to Azure CDN](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Para obtener información sobre el Azure CDN de PowerShell, [vea Manage Azure CDN with PowerShell](/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Ajax **CDN** de Microsoft es un CDN de solo lectura que ofrece muchas bibliotecas de desarrollo populares, incluidas jQuery (y todas sus otras bibliotecas), ASP.NET Ajax, Bootstrap, Knockout.js y otras.
  
Para incluir estos scripts en el proyecto, simplemente reemplace las referencias a estas bibliotecas disponibles públicamente por referencias a la dirección CDN en lugar de incluirla en el propio proyecto. Por ejemplo, use el siguiente código para vincular a jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Para obtener más información acerca de cómo usar microsoft Ajax CDN, vea [Microsoft Ajax CDN](/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>¿Cómo Office 365 el contenido de un CDN?

Independientemente de qué CDN configurar para el inquilino Office 365, el proceso básico de recuperación de datos es el mismo.

1. El cliente (un explorador o una Office cliente) solicita datos de Office 365.

2. Office 365 devuelve los datos directamente al cliente o, si los datos forman parte de un conjunto de contenido hospedado por el CDN, redirige el cliente a la dirección URL CDN.

    a. Si los datos ya están almacenados en caché en un origen _público,_ el cliente descarga los datos directamente desde la ubicación CDN más cercana al cliente.

    b. Si los datos ya  están almacenados en caché en un origen privado, el servicio CDN comprueba los Office 365 de la cuenta de usuario en el origen. Si tiene permisos, SharePoint Online genera dinámicamente una dirección URL personalizada compuesta de la ruta de acceso al activo en el CDN y dos tokens de acceso, y devuelve la dirección URL personalizada al cliente. A continuación, el cliente descarga los datos directamente desde la ubicación CDN más cercana al cliente mediante la dirección URL personalizada.

3. Si los datos no se almacenan en caché en el CDN, el nodo CDN solicita los datos de Office 365 y, a continuación, los almacena en caché durante un período de tiempo después de que el cliente descargue los datos.

El CDN encuentra el centro de datos más cercano al explorador del usuario y, mediante el redireccionamiento, descarga los datos solicitados desde allí. CDN la redirección es rápida y puede ahorrar a los usuarios mucho tiempo de descarga.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>¿Cómo debo configurar mi red para que las CDN funcionen mejor con Office 365?

Minimizar la latencia entre los clientes de la red y los CDN de conexión es la consideración clave para garantizar un rendimiento óptimo. Puede usar los [procedimientos recomendados](managing-office-365-endpoints.md) descritos en Managing Office 365 endpoints para asegurarse de que la configuración de red permite que los exploradores cliente accedan a CDN directamente en lugar de enrutar el tráfico CDN a través de servidores proxy centrales para evitar introducir latencia innecesaria.

También puede leer los Office 365 de conectividad de red para comprender los [conceptos subyacentes](./microsoft-365-network-connectivity-principles.md) a la optimización del Office 365 de red.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>¿Hay una lista de todas las CDN que Office 365 usa?

Las CDN en uso por Office 365 siempre están sujetas a cambios y, en muchos casos, hay varios asociados de CDN configurados en caso de que uno no esté disponible. Las CDN principales usadas por Office 365 son:

|CDN  |Empresa  |Uso  |Vínculo  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Activos genéricos en orígenes públicos, SharePoint de usuario en orígenes privados         |[Uso de la red de entrega de contenido de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Código personalizado, SharePoint Framework soluciones         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (solo lectura)     |Microsoft         |Bibliotecas comunes para Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js etc.         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>¿Qué mejoras de rendimiento CDN proporciona?

Hay muchos factores implicados en la medición de diferencias específicas en el rendimiento entre los datos descargados directamente de Office 365 y los datos descargados de un CDN específico, como la ubicación relativa al inquilino y al punto de conexión CDN más cercano, el número de activos de una página que sirve el CDN y los cambios transitorios en la latencia de red y el ancho de banda. Sin embargo, una prueba A/B sencilla puede ayudar a mostrar la diferencia en el tiempo de descarga de un archivo específico.

Las siguientes capturas de pantalla ilustran la diferencia en la velocidad de descarga entre la ubicación del archivo nativo en Office 365 y el mismo archivo hospedado en microsoft [Ajax Content Delivery Network](/aspnet/ajax/cdn/overview). Estas capturas de pantalla se encuentran en la **pestaña Red** de las herramientas para desarrolladores de Internet Explorer 11. Estas capturas de pantalla muestran la latencia en la popular biblioteca jQuery. Para mostrar esta pantalla, en Internet Explorer, presione  **F12** y seleccione la pestaña Red, que está Wi-Fi icono.
  
![Captura de pantalla de red F12](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
En esta captura de pantalla se muestra la biblioteca cargada en la galería de páginas maestras del SharePoint sitio en línea. El tiempo que tardó en cargar la biblioteca es de 1,51 segundos.
  
![Captura de pantalla de tiempo de carga de 1,51 s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
La segunda captura de pantalla muestra el mismo archivo entregado por el CDN de Microsoft. Esta vez, la latencia ronda los 496 milisegundos. Se trata de una gran mejora y muestra que se afeita un segundo completo el tiempo total para descargar el objeto.
  
![Captura de pantalla de los tiempos de carga de 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>¿Mis datos son seguros?

Nos preocupamos mucho para proteger los datos que administra su empresa. Los datos almacenados en el Office 365 CDN se cifran tanto en tránsito como en reposo, y el acceso a los datos en el Office 365 SharePoint CDN se protege mediante Office 365 permisos de usuario y autorización de tokens. Las solicitudes de datos en el Office 365 SharePoint CDN deben ser referidas (redirigidas) desde el Office 365 inquilino o no se generará un token de autorización.

Para garantizar que los datos permanecen seguros, se recomienda que nunca almacene contenido de usuario u otros datos confidenciales en un sitio CDN. Dado que el acceso a los datos de un CDN público es anónimo, las CDN públicas solo deben usarse para hospedar contenido genérico, como archivos de script web, iconos, imágenes y otros activos no confidenciales.

> [!NOTE]
> Los proveedores de CDN terceros pueden tener estándares de privacidad y cumplimiento que difieren de los compromisos descritos por el Centro de Office 365 confianza. Es posible que los datos almacenados en caché a través del servicio CDN no se ajusten a los Términos de procesamiento de datos (DPT) de Microsoft y que se encuentran fuera de los límites de cumplimiento de Office 365 centro de confianza.

Para obtener información detallada sobre privacidad y protección de datos para Office 365 CDN proveedores, visite lo siguiente:  

- Obtenga más información sobre Office 365 privacidad y protección de datos en el [Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter)
- Obtenga más información sobre la privacidad y protección de datos de Akamai en el Centro de confianza [de privacidad de Akamai](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Obtenga más información sobre la privacidad y protección de datos de Azure en [el Centro de confianza de Azure](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>¿Cómo puedo proteger mi red con todos estos servicios de terceros?

El aprovechamiento de un amplio conjunto de servicios asociados permite a Office 365 escalar y cumplir los requisitos de disponibilidad, así como mejorar la experiencia del usuario al usar Office 365. Las ventajas de los servicios de terceros Office 365 incluyen listas de revocación de certificados; como crl.microsoft.com o sa.symcb.com, y LAS CDN; como r3.res.outlook.com. Cada CDN FQDN generado por Office 365 es un FQDN personalizado para Office 365. Si se le envía a un FQDN a petición de Office 365 puede estar seguro de que el proveedor de CDN controla el FQDN y el contenido subyacente en esa ubicación.
  
Para los clientes que desean segregar solicitudes destinadas a un centro de datos de Microsoft o Office 365 de solicitudes destinadas a terceros, hemos escrito instrucciones sobre administración de puntos de conexión Office 365 [.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>¿Hay una lista de todos los FQDN que aprovechan las CDN?

La lista de FQDN y cómo aprovechan las CDN cambian con el tiempo. Consulte nuestra página de direcciones URL Office 365 e intervalos de direcciones [IP publicadas](./urls-and-ip-address-ranges.md) para estar actualizados en los FQDN más recientes que aprovechan las CDN.

También puede usar el servicio web Office 365 dirección IP y [dirección URL](microsoft-365-ip-web-service.md) para solicitar las direcciones URL de Office 365 y los intervalos de direcciones IP con formato CSV o JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>¿Puedo usar mi propio contenido CDN y caché en mi red local?

Estamos buscando continuamente nuevas formas de satisfacer las necesidades de nuestros clientes y actualmente estamos explorando el uso de soluciones de proxy de almacenamiento en caché y otras soluciones de almacenamiento CDN locales.

Aunque no forma parte del Office 365 CDN, también puede usar **el Azure CDN** para hospedar elementos web personalizados, bibliotecas y otros activos de recursos, lo que le permite aplicar claves de acceso al almacenamiento de CDN y ejercer un mayor control sobre la configuración de CDN. El uso del Azure CDN no es gratuito y requiere una suscripción de Azure. Para obtener más información sobre cómo configurar una instancia Azure CDN, vea [Inicio rápido: Integrar](/azure/cdn/cdn-create-a-storage-account-with-cdn)una cuenta de Azure Storage con Azure CDN .

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Estoy usando Azure ExpressRoute para Office 365, ¿eso cambia las cosas?

[Azure ExpressRoute para Office 365](azure-expressroute.md) proporciona una conexión dedicada a Office 365 infraestructura segregada de Internet pública. Esto significa que los clientes tendrán que conectarse a través de conexiones que no son de ExpressRoute para conectarse a las CDN y otra infraestructura de Microsoft que no se incluye explícitamente en la lista de servicios compatibles con ExpressRoute. Para obtener más información acerca de cómo enrutar tráfico específico, como las solicitudes destinadas a LAS CDN, consulte Office 365 [administración de tráfico de red](routing-with-expressroute.md).

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>¿Puedo usar CDN con SharePoint servidor local?

El uso de LAS CDN solo tiene sentido en un SharePoint online y debe evitarse con SharePoint Server. Esto se debe a que todas las ventajas de la ubicación geográfica no son verdaderas si el servidor se encuentra local o geográficamente cerca de todos modos. Además, si hay una conexión de red a los servidores donde está hospedado, el sitio puede usarse sin conexión a Internet y, por lo tanto, no puede recuperar los archivos CDN servidor. De lo contrario, debe usar un CDN si hay uno disponible y estable para la biblioteca y los archivos que necesita para el sitio.
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Vea también

[Principios de conectividad de red de Office 365](./microsoft-365-network-connectivity-principles.md)

[Evaluar la red de Office 365](assessing-network-connectivity.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](./urls-and-ip-address-ranges.md)

[Uso de la red de entrega de contenido de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter)

[Ajustar el rendimiento de Office 365](tune-microsoft-365-performance.md)