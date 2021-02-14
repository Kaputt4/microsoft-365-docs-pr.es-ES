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
description: Use esta información para obtener información sobre cómo Office 365 usa redes de entrega de contenido (CDN) para mejorar el rendimiento.
ms.openlocfilehash: 1c2230b76f354bf6f3de524b2b8c75b7d8c380e7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693808"
---
# <a name="content-delivery-networks-cdns"></a>Redes de entrega de contenido (CDN)

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Las redes CDN ayudan a mantener Office 365 rápido y confiable para los usuarios finales. Los servicios en la nube, como Office 365, usan CDN para almacenar en caché activos estáticos más cerca de los exploradores que los solicitan para acelerar las descargas y reducir la latencia percibida del usuario final. La información de este tema le ayudará a obtener información sobre las redes de entrega de contenido (CDN) y cómo las usa Office 365.

## <a name="what-exactly-is-a-cdn"></a>¿Qué es exactamente una red CDN?

Una red CDN es una red distribuida geográficamente que consta de servidores proxy y de archivos en centros de datos conectados por redes troncales de alta velocidad. Las CDN se usan para reducir la latencia y los tiempos de carga de un conjunto especificado de archivos y objetos en un sitio web o servicio. Una red CDN puede tener muchos miles de puntos de conexión para un mantenimiento óptimo de las solicitudes entrantes desde cualquier ubicación.

Las redes CDN se usan normalmente para proporcionar descargas más rápidas de contenido genérico para un sitio web o servicio como archivos javascript, iconos e imágenes, y también pueden proporcionar acceso privado al contenido del usuario, como archivos en bibliotecas de documentos de SharePoint Online, archivos multimedia de streaming y código personalizado.

La mayoría de los servicios empresariales en la nube usan las redes CDN. Los servicios en la nube, como Office 365, tienen millones de clientes que descargan una mezcla de contenido propietario (como correos electrónicos) y contenido genérico (como iconos) a la vez. Es más eficaz colocar imágenes que todos los usuarios usan, como iconos, lo más cerca posible del equipo del usuario. No resulta práctico para todos los servicios en la nube crear centros de datos de red CDN que almacenen este contenido genérico en todas las áreas metropolitanas, o incluso en todos los principales centros de Internet de todo el mundo, por lo que algunas de estas redes CDN se comparten.

## <a name="how-do-cdns-make-services-work-faster"></a>¿Cómo las CDN hacen que los servicios funcionen más rápido?

La descarga de objetos comunes, como imágenes de sitio e iconos una y otra vez, puede tomar ancho de banda de red que se puede usar mejor para descargar contenido personal importante, como correo electrónico o documentos. Dado que Office 365 usa una arquitectura que incluye CDN, los iconos, scripts y otro contenido genérico se pueden descargar desde servidores más cercanos a los equipos cliente, lo que permite que las descargas sean más rápidas. Esto significa un acceso más rápido al contenido personal, que se almacena de forma segura en centros de datos de Office 365.

Las CDN ayudan a mejorar el rendimiento del servicio en la nube de varias maneras:

- Las REDES CDN alejan parte de la carga de descarga de archivos y red del servicio en la nube, liberando recursos de servicio en la nube para atender contenido de usuario y otros servicios al reducir la necesidad de atender solicitudes de activos estáticos.
- Las REDES CDN están diseñadas para proporcionar acceso a archivos de baja latencia mediante la implementación de redes de alto rendimiento y servidores de archivos, y al aprovechar protocolos de red actualizados, como [HTTP/2,](https://en.wikipedia.org/wiki/HTTP/2) con una compresión y multiplexación de solicitudes altamente eficientes.
- Las redes CDN usan muchos puntos de conexión distribuidos globalmente para que el contenido esté disponible lo más cerca posible para los usuarios.

## <a name="the-office-365-cdn"></a>La red CDN de Office 365

La red de entrega de contenido (CDN) integrada de Office 365 permite a los administradores de Office 365 proporcionar un mejor rendimiento para las páginas de SharePoint Online de su organización mediante el almacenamiento en caché de activos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar las descargas y reducir la latencia. La red CDN de Office 365 usa el [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para mejorar la compresión y las velocidades de descarga.

> [!NOTE]
> La red CDN de Office 365 solo está disponible para los inquilinos en la **nube de producción** (en todo el mundo). Actualmente, los inquilinos de las nubes del Gobierno de Estados Unidos, China y Alemania no admiten la red CDN de Office 365.

La CDN de Office 365 se compone de varias redes CDN que permite hospedar archivos estáticos en varias ubicaciones u _orígenes_ y a realizar la entrega desde redes de alta velocidad globales. Según el tipo de contenido que quiera hospedar en la CDN de Office 365, puede agregar orígenes **públicos**, **privados** o ambos.

![Diagrama conceptual de la red CDN de Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceptual de la red CDN de Office 365")

El contenido en orígenes **públicos** dentro de la CDN de Office 365 es accesible de forma anónima y cualquier persona que tenga la URL a los activos hospedado puede acceder. Como el acceso al contenido en orígenes públicos es anónimo, solo debe usarlos para almacenar en caché contenido genérico y no confidencial, como archivos javascript, scripts, iconos e imágenes. La CDN de Office 365 se usa de forma predeterminada para descargar activos de recurso genéricos como las aplicaciones cliente de Office 365 desde un origen público.

**Los** orígenes privados dentro de la red CDN de Office 365 proporcionan acceso privado al contenido del usuario, como bibliotecas de documentos de SharePoint Online, sitios e imágenes propietarias. El acceso al contenido de orígenes privados está protegido con tokens generados de forma dinámica, por lo que pueden acceder los usuarios con permisos para la ubicación de almacenamiento o de biblioteca de documentos original. Los orígenes privados en la CDN de Office 365 solo pueden usarse para el contenido de SharePoint Online y solo se puede acceder a los activos mediante el redireccionamiento de su espacio empresarial de SharePoint Online.

La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.

Para obtener más información acerca de cómo usar la red CDN de Office 365, vea Usar la red de entrega de contenido de [Office 365 con SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

Para ver una serie de vídeos breves que proporcionan información conceptual y HOWTO sobre el uso de la red CDN de Office 365, visite el canal de YouTube de modelos y prácticas para desarrolladores de [SharePoint.](https://aka.ms/sppnp-videos)

## <a name="other-microsoft-cdns"></a>Otras CDN de Microsoft

Aunque no forma parte de la red CDN de Office 365, puede usar estas CDN en su espacio empresarial de Office 365 para obtener acceso a bibliotecas de desarrollo de SharePoint, código personalizado y otros fines que se encuentran fuera del ámbito de la red CDN de Office 365.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>A partir del tercer trimestre de 2020, SharePoint Online empezará a almacenar vídeos en caché en la red CDN de Azure para admitir una reproducción y confiabilidad de vídeo mejoradas. Los vídeos populares se transmitirán desde el punto de conexión de red CDN más cercano al usuario. Estos datos permanecerán dentro del límite de cumplimiento de Microsoft 365. Este es un servicio gratuito para todos los inquilinos y no requiere ninguna acción del cliente para configurar.

Puede usar la **red CDN** de Azure para implementar su propia instancia de red CDN para hospedar elementos web personalizados, bibliotecas y otros activos de recursos, lo que le permite aplicar claves de acceso al almacenamiento de la red CDN y ejercer un mayor control sobre la configuración de la red CDN. El uso de la red CDN de Azure no es gratuito y requiere una suscripción de Azure.

Para obtener más información sobre cómo configurar una instancia de red CDN de Azure, vea Inicio rápido: Integrar una cuenta de [Azure Storage con la red CDN de Azure.](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn)

Para obtener un ejemplo de cómo se puede usar la red CDN de Azure para hospedar elementos web de SharePoint, vea Implementar el elemento web del lado cliente de [SharePoint en la red CDN de Azure.](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)

Para obtener información sobre el módulo de PowerShell de red CDN de Azure, vea [Administrar la red CDN de Azure con PowerShell.](https://docs.microsoft.com/azure/cdn/cdn-manage-powershell)

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsoft's **Ajax CDN** is a read-only CDN that offers many popular development libraries including jQuery (and all of its other libraries), ASP.NET Ajax, Bootstrap, Knockout.js, and others.
  
Para incluir estos scripts en el proyecto, simplemente reemplace las referencias a estas bibliotecas disponibles públicamente por referencias a la dirección cdn en lugar de incluirla en el propio proyecto. Por ejemplo, use el siguiente código para vincular a jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Para obtener más información acerca de cómo usar la red CDN de Microsoft Ajax, vea [Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>¿Cómo usa Office 365 contenido de una red CDN?

Independientemente de la red CDN que configure para su inquilino de Office 365, el proceso básico de recuperación de datos es el mismo.

1. El cliente (un explorador o una aplicación cliente de Office) solicita datos de Office 365.

2. Office 365 devuelve los datos directamente al cliente o, si los datos forman parte de un conjunto de contenido hospedado por la red CDN, redirige al cliente a la dirección URL de la red CDN.

    a. Si los datos ya están almacenados en caché en un _origen_ público, el cliente descarga los datos directamente desde la ubicación de red CDN más cercana al cliente.

    b. Si los datos ya  están almacenados en caché en un origen privado, el servicio de red CDN comprueba los permisos de su cuenta de usuario de Office 365 en el origen. Si tiene permisos, SharePoint Online genera dinámicamente una dirección URL personalizada compuesta de la ruta de acceso al activo en la red CDN y dos tokens de acceso, y devuelve la dirección URL personalizada al cliente. A continuación, el cliente descarga los datos directamente desde la ubicación de red CDN más cercana al cliente mediante la dirección URL personalizada.

3. Si los datos no se almacenan en caché en la red CDN, el nodo de la red CDN solicita los datos de Office 365 y, a continuación, los almacena en caché durante un período de tiempo después de que el cliente descargue los datos.

La red CDN encuentra el centro de datos más cercano al explorador del usuario y, mediante el redireccionamiento, descarga los datos solicitados desde allí. La redirección de la red CDN es rápida y puede ahorrar mucho tiempo de descarga a los usuarios.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>¿Cómo debería configurar mi red para que las redes CDN funcionen mejor con Office 365?

Minimizar la latencia entre los clientes de la red y los puntos de conexión de red CDN es la consideración clave para garantizar un rendimiento óptimo. Puede usar los procedimientos recomendados descritos en la administración de puntos de conexión de [Office 365](managing-office-365-endpoints.md) para asegurarse de que la configuración de red permite que los exploradores cliente accedan a la red CDN directamente en lugar de enrutar el tráfico de la red CDN a través de servidores proxy centrales para evitar introducir latencias innecesarias.

También puede leer los Principios de conectividad de red de [Office 365](https://aka.ms/o365networkingprinciples) para comprender los conceptos subyacentes a la optimización del rendimiento de la red de Office 365.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>¿Hay una lista de todas las CDN que usa Office 365?

Las CDN que usa Office 365 siempre están sujetas a cambios y, en muchos casos, hay varios asociados de red CDN configurados en caso de que uno no esté disponible. Las cdn principales usadas por Office 365 son:

|CDN  |Company  |Uso  |Vínculo  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Activos genéricos en orígenes públicos, contenido de usuario de SharePoint en orígenes privados         |[Uso de la red de entrega de contenido de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Código personalizado, soluciones de SharePoint Framework         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Cdn de Microsoft Ajax (solo lectura)     |Microsoft         |Bibliotecas comunes para Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js etc.         |[Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>¿Qué mejoras de rendimiento proporciona una red CDN?

Hay muchos factores implicados en la medición de diferencias específicas de rendimiento entre los datos descargados directamente de Office 365 y los datos descargados de una red CDN específica, como la ubicación relativa a su espacio empresarial y al punto de conexión de red CDN más cercano, el número de activos de una página a los que sirve la red CDN y los cambios transitorios en la latencia de red y el ancho de banda. Sin embargo, una prueba A/B sencilla puede ayudar a mostrar la diferencia en el tiempo de descarga de un archivo específico.

Las siguientes capturas de pantalla ilustran la diferencia en la velocidad de descarga entre la ubicación del archivo nativo en Office 365 y el mismo archivo hospedado en la red de entrega de contenido de [Microsoft Ajax.](https://docs.microsoft.com/aspnet/ajax/cdn/overview) Estas capturas de pantalla se encuentran en la **pestaña Red** de las herramientas de desarrollo de Internet Explorer 11. Estas capturas de pantalla muestran la latencia en la popular biblioteca jQuery. Para abrir esta pantalla, en Internet Explorer, presione  **F12** y seleccione la pestaña Red que aparece con un icono Wi-Fi pantalla.
  
![Captura de pantalla de red F12](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
En esta captura de pantalla se muestra la biblioteca cargada en la galería de páginas maestras del propio sitio de SharePoint Online. El tiempo que tardó en cargar la biblioteca es de 1,51 segundos.
  
![Captura de pantalla de tiempo de carga de 1,51 s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
La segunda captura de pantalla muestra el mismo archivo entregado por la red CDN de Microsoft. Esta vez, la latencia es de unos 496 milisegundos. Esto es una gran mejora y muestra que se ha recortado un segundo entero del tiempo total para descargar el objeto.
  
![Captura de pantalla de los tiempos de carga de 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>¿Mis datos son seguros?

Nos ocupamos mucho de proteger los datos que administra su empresa. Los datos almacenados en la red CDN de Office 365 se cifran tanto en tránsito como en reposo, y el acceso a los datos de la red CDN de SharePoint de Office 365 está protegido con permisos de usuario y autorización de token de Office 365. Las solicitudes de datos en la red CDN de SharePoint de Office 365 deben ser referenciadas (redirigidas) desde su inquilino de Office 365 o no se generará un token de autorización.

Para asegurarse de que los datos permanecen seguros, le recomendamos que nunca almacene contenido de usuario u otros datos confidenciales en una red CDN pública. Dado que el acceso a los datos de una red CDN pública es anónimo, las CDN públicas solo deben usarse para hospedar contenido genérico, como archivos de script web, iconos, imágenes y otros activos no confidenciales.

> [!NOTE]
> Los proveedores de red CDN de terceros pueden tener estándares de privacidad y cumplimiento que difieren de los compromisos descritos por el Centro de confianza de Office 365. Los datos almacenados en caché a través del servicio de red CDN pueden no cumplir con los Términos de procesamiento de datos (DPT) de Microsoft y pueden estar fuera de los límites de cumplimiento del Centro de confianza de Office 365.

Para obtener información detallada acerca de la privacidad y la protección de datos para los proveedores de red CDN de Office 365, visite lo siguiente:  

- Obtenga más información sobre la privacidad y la protección de datos de Office 365 en el [Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter)
- Obtenga más información sobre la privacidad y la protección de datos de Akamai en el Centro de confianza [de privacidad de Akamai](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Obtenga más información sobre la privacidad de Azure y la protección de datos en el [Centro de confianza de Azure](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>¿Cómo puedo proteger mi red con todos estos servicios de terceros?

Aprovechar un amplio conjunto de servicios de asociados permite a Office 365 escalar y cumplir los requisitos de disponibilidad, así como mejorar la experiencia del usuario al usar Office 365. Los servicios de terceros que Usa Office 365 incluyen listas de revocación de certificados; como crl.microsoft.com o sa.symcb.com y CDN; por ejemplo, r3.res.outlook.com. Cada FQDN de red CDN generado por Office 365 es un FQDN personalizado para Office 365. Si se le envía a un FQDN a petición de Office 365, puede estar seguro de que el proveedor de red CDN controla el FQDN y el contenido subyacente en esa ubicación.
  
Para los clientes que quieran segregar las solicitudes destinadas a un centro de datos de Microsoft u Office 365 de las solicitudes destinadas a terceros, hemos escrito instrucciones sobre la administración de puntos de conexión de [Office 365.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>¿Hay una lista de todos los FQDN que aprovechan las CDN?

La lista de FQDN y cómo aprovechan las CDN cambian con el tiempo. Consulte nuestra página de intervalos de direcciones IP y DIRECCIONES URL de [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744) publicada para estar al día sobre los FQDN más recientes que aprovechan las redes CDN.

También puede usar el servicio web de url y dirección IP de [Office 365](microsoft-365-ip-web-service.md) para solicitar las direcciones URL e intervalos de direcciones IP de Office 365 actuales con formato CSV o JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>¿Puedo usar mi propia red CDN y almacenar en caché contenido en mi red local?

We're continually looking for new ways to support our customers needs and are currently exploring the use of caching proxy solutions and other on-premises CDN solutions.

Aunque no forma parte de la red CDN de Office 365, también puede usar la red **CDN** de Azure para hospedar elementos web personalizados, bibliotecas y otros activos de recursos, lo que le permite aplicar claves de acceso al almacenamiento de la red CDN y ejercer un mayor control sobre la configuración de la red CDN. El uso de la red CDN de Azure no es gratuito y requiere una suscripción de Azure. Para obtener más información sobre cómo configurar una instancia de red CDN de Azure, vea Inicio rápido: Integrar una cuenta de [Azure Storage con la red CDN de Azure.](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn)

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Estoy usando Azure ExpressRoute para Office 365, ¿eso cambia?

[Azure ExpressRoute para Office 365](azure-expressroute.md) proporciona una conexión dedicada a la infraestructura de Office 365 segregada de Internet público. Esto significa que los clientes seguirán teniendo que conectarse a través de conexiones que no son de ExpressRoute para conectarse a cdns y otra infraestructura de Microsoft que no se incluya explícitamente en la lista de servicios compatibles con ExpressRoute. Para obtener más información acerca de cómo enrutar tráfico específico, como las solicitudes destinadas a las redes CDN, consulte Administración del tráfico de red [de Office 365.](routing-with-expressroute.md)

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>¿Puedo usar CDN con SharePoint Server local?

El uso de CDN solo tiene sentido en un contexto de SharePoint Online y debe evitarse con SharePoint Server. Esto se debe a que todas las ventajas de la ubicación geográfica no son verdaderas si el servidor se encuentra local o geográficamente cerca de todos modos. Además, si hay una conexión de red a los servidores donde se hospeda, el sitio puede usarse sin conexión a Internet y, por lo tanto, no puede recuperar los archivos de la red CDN. De lo contrario, debe usar una red CDN si hay una disponible y estable para la biblioteca y los archivos que necesita para el sitio.
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/o365cdns](https://aka.ms/o365cdns)
  
## <a name="see-also"></a>Vea también

[Principios de conectividad de red de Office 365](https://aka.ms/o365networkingprinciples)

[Evaluar la red de Office 365](assessing-network-connectivity.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744)

[Uso de la red de entrega de contenido de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter)

[Ajustar el rendimiento de Office 365](tune-microsoft-365-performance.md)
