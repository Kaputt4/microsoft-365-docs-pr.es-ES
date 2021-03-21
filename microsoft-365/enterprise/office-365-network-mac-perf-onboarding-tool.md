---
title: Herramienta de prueba de conectividad de red de Microsoft 365 (versión preliminar)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Herramienta de prueba de conectividad de red de Microsoft 365 (versión preliminar)
ms.openlocfilehash: 3597996a74cccc3a178f7a5a637c956e0393641b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926123"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Herramienta de prueba de conectividad de red de Microsoft 365 (versión preliminar)

La herramienta de prueba de conectividad de red de Microsoft 365 se encuentra en <https://connectivity.office.com> . Se trata de una herramienta adjunta a la información de evaluación de red e información de red disponible en el Centro de administración de Microsoft 365 en el área de **| Menú** Conectividad.

> [!IMPORTANT]
> Es importante iniciar sesión en el inquilino de Microsoft 365, ya que todos los informes de prueba se comparten con el administrador y se cargan en el inquilino mientras se inicia sesión.

![Herramienta de prueba de conectividad](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>La herramienta de prueba de conectividad de red admite inquilinos en WW Commercial y Alemania, pero no GCC Moderate, GCC High, DoD o China.

Los conocimientos de red del Centro de administración de Microsoft 365 se basan en medidas regulares del producto para el inquilino de Microsoft 365 que se agregan cada día. En comparación, los conocimientos de red de la prueba de conectividad de red de Microsoft 365 se ejecutan localmente y una vez en la herramienta. Las pruebas que se pueden realizar en el producto son limitadas y al ejecutar pruebas locales para el usuario se pueden recopilar más datos, lo que da como resultado información más detallada. Tenga en cuenta que las perspectivas de red del Centro de administración de Microsoft 365 mostrarán que hay un problema de red para el uso de Microsoft 365 en una ubicación de oficina específica. La prueba de conectividad de Microsoft 365 puede ayudar a identificar la causa raíz de ese problema que lleva a una acción recomendada de mejora del rendimiento de la red.

Se recomienda que se usen juntos donde se pueda evaluar el estado de calidad de las redes para cada ubicación de oficina en el Centro de administración de Microsoft 365 y se puedan encontrar más detalles después de la implementación de pruebas basadas en la prueba de conectividad de Microsoft 365.

>[!IMPORTANT]
>Los conocimientos de red, las recomendaciones de rendimiento y las evaluaciones del Centro de administración de Microsoft 365 se encuentran actualmente en estado de vista previa y solo están disponibles para los inquilinos de Microsoft 365 que se han inscrito en el programa de vista previa de características.

## <a name="what-happens-at-each-test-step"></a>Qué sucede en cada paso de prueba

### <a name="office-location-identification"></a>Identificación de ubicación de Office

Al hacer clic en el botón ejecutar prueba, se muestra la página de prueba en ejecución e identificamos la ubicación de la oficina. Puede escribir su ubicación por ciudad, estado y país o puede detectarla desde el explorador web. If you detect it then we request the latitude and longitude from the web browser and limit the accuracy to 300m by 300m before use. Lo hacemos porque no es necesario identificar la ubicación con más precisión que el edificio para el rendimiento de la red. 

### <a name="javascript-tests"></a>Pruebas de JavaScript

Después de la identificación de ubicación de la oficina, ejecutamos una prueba de latencia TCP en JavaScript y solicitamos datos del servicio sobre los servidores de puerta principal de servicio de Office 365 recomendados y en uso. Cuando se completan, se muestran en el mapa y en la pestaña detalles donde se pueden ver antes del paso siguiente.

### <a name="download-the-advanced-tests-client-application"></a>Descargar la aplicación cliente de pruebas avanzadas

A continuación, iniciamos la descarga de la aplicación cliente de pruebas avanzadas. Dependemos del usuario para iniciar la aplicación cliente y también debe tener instalado .NET Core.

Hay dos partes en la prueba de conectividad de red de Microsoft 365; el sitio web y una aplicación cliente de Windows descargable <https://connectivity.office.com> que ejecuta pruebas avanzadas de conectividad de red. La mayoría de las pruebas requieren que se ejecute la aplicación. Rellenará los resultados de nuevo en la página web mientras se ejecuta.

Se le pedirá que descargue la aplicación de prueba de cliente avanzada del sitio web una vez completadas las pruebas del explorador web. Abra y ejecute el archivo cuando se le pida.

![Aplicación cliente de pruebas avanzadas](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Iniciar la aplicación cliente de pruebas avanzadas

Una vez que la aplicación cliente inicia la página web se actualizará para mostrar esto y los datos de prueba empezarán a recibirse en la página web. Se actualiza cada vez que se reciben nuevos datos y puede revisar los datos a medida que llegan.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Pruebas avanzadas completadas y carga de informes de prueba

Una vez completadas las pruebas, la página web y el cliente de pruebas avanzadas lo indicarán y si el usuario ha iniciado sesión en el informe de prueba se cargará en el inquilino de clientes.

## <a name="sharing-your-test-report"></a>Compartir el informe de prueba

El informe de prueba requiere iniciar sesión en su cuenta de Office 365. El administrador selecciona cómo puede compartir el informe de prueba.

### <a name="sharing-your-report-with-your-administrator"></a>Compartir el informe con el administrador

Todos los informes de prueba mientras ha iniciado sesión se comparten con el administrador.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Uso compartido con el equipo de cuenta de Microsoft, soporte técnico u otro personal

Los informes de prueba que excluyen cualquier identificación personal se comparten con los empleados de Microsoft. Esto está habilitado de forma predeterminada y el administrador puede deshabilitarlo en el servicio **de mantenimiento | Página Conectividad de** red en el Centro de administración de Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Uso compartido con otros usuarios que inician sesión en el mismo inquilino de Office 365

Puede elegir los usuarios con los que compartir el informe y esto está habilitado de forma predeterminada. También puede deshabilitarlo el administrador.

![Compartir un vínculo a los resultados de la prueba con un usuario](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Compartir con cualquier persona que use un vínculo ReportID

Puede compartir el informe de prueba con cualquier persona proporcionando acceso a un vínculo ReportID. Esto genera una dirección URL que puede enviar a alguien para que pueda presentar el informe de prueba sin iniciar sesión. Esto está deshabilitado de forma predeterminada y el administrador debe habilitarlo.

![Compartir un vínculo a los resultados de la prueba](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Resultados de la prueba de conectividad de red

Los resultados se muestran en **las** pestañas Resumen **y** Detalles. La pestaña resumen muestra un mapa del perímetro de red detectado y una comparación de la evaluación de red con otros clientes de Office 365 cercanos. También permite compartir el informe de prueba. Este es el aspecto de la vista de resultados de resumen.

![Resultados de resumen de la herramienta de prueba de conectividad de red](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Este es un ejemplo de la salida de pestaña de detalles que muestra la herramienta. En la pestaña detalles se muestra una marca de verificación de círculo verde si el resultado se comparó de forma favorable con un umbral. Se muestra un signo de exclamación de triángulo rojo si el resultado superó un umbral que indica una información de red. En las secciones siguientes se describen cada una de las filas de resultados de pestañas de detalles y se explican los umbrales usados para la información de red.

![Resultados de pruebas de la herramienta de prueba de conectividad de red](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Información de ubicación

En esta sección se muestran los resultados de las pruebas relacionados con la ubicación.

#### <a name="your-location"></a>Su ubicación

La ubicación del usuario se detecta desde el explorador web de los usuarios o se puede escribir en la elección de los usuarios. Se usa para identificar distancias de red a partes específicas del perímetro de red empresarial. Solo la ciudad desde esta detección de ubicación y la distancia a otros puntos de red se guardan en el informe.

La ubicación de la oficina de usuario se muestra en la vista de mapa.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Ubicación de salida de red (la ubicación donde se conecta la red al ISP)

Identificamos la dirección IP de salida de red en el lado del servidor. Las bases de datos de ubicación se usan para buscar la ubicación aproximada de la salida de red. Estas bases de datos suelen tener una precisión de aproximadamente el 90 % de las direcciones IP. Si la ubicación buscada desde la dirección IP de salida de red no es precisa, esto daría lugar a un resultado falso de esta prueba. Para validar si se produce este error para una dirección IP específica, puede usar sitios web de ubicación de direcciones IP de red accesibles públicamente para comparar con su ubicación real.

#### <a name="your-distance-from-the-network-egress-location"></a>Distancia desde la ubicación de salida de red

Determinamos la distancia desde esa ubicación a la ubicación de la oficina. Esto se muestra como una información de red si la distancia es mayor que **500 millas** (800 kilómetros), ya que es probable que aumente la latencia TCP en más de 25 ms y puede afectar a la experiencia del usuario.

La ubicación de salida de red se muestra en la vista de mapa y se conecta a la ubicación de la oficina del usuario que indica el backhaul de red dentro de la WAN de empresa.

Para la conectividad de red de Microsoft 365 se recomienda implementar salidas de red locales y directas desde ubicaciones de oficina de usuario a Internet. Las mejoras en la salida local y directa son la mejor manera de abordar esta información de red.

#### <a name="proxy-server-information"></a>Información del servidor proxy

Identificamos los servidores proxy configurados en el equipo local. Identificamos si alguno de estos está configurado en la ruta de acceso de red para optimizar el tráfico de red de Microsoft 365. Identificamos la distancia desde la ubicación de la oficina de usuario hasta los servidores proxy. La distancia se prueba primero mediante el ping ICMP y, si esto falla, se prueba con ping TCP y, por último, si se produce un error, buscamos la dirección IP del servidor proxy en una base de datos de ubicación de direcciones IP. Mostramos una información de red si el servidor proxy está a más de **500 millas** (800 kilómetros) de distancia de la ubicación de la oficina del usuario.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Red privada virtual (VPN) que usa para conectarse a su organización

Esto detecta si usa una VPN para conectarse a Office 365. Un resultado de paso mostrará si no tiene VPN o si tiene una VPN con la configuración de túnel dividido recomendada para Office 365.

#### <a name="vpn-split-tunnel"></a>Túnel dividido de VPN

Cada ruta de categorías de optimización para Exchange Online, SharePoint Online y Microsoft Teams se prueba para ver si está tunelada en la VPN o no. Una carga de trabajo dividida evita la VPN por completo. Una carga de trabajo tunelada se envía a través de la VPN. Una carga de trabajo de túnel selectiva tiene algunas rutas enviadas a través de la VPN y otras divididas. Un resultado de paso mostrará si todas las cargas de trabajo se dividen o se tunelización selectiva.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Clientes de su área metropolitana con un mejor rendimiento

La latencia TCP de red de la ubicación de la oficina del usuario en la puerta principal del servicio Exchange Online se compara con otros clientes de Microsoft 365 en la misma área metropolitana. Se muestra una información de red si el 10 % o más de los clientes de la misma área metropolitana tienen un mejor rendimiento. Esto significa que sus usuarios tendrán un mejor rendimiento en la interfaz de usuario de Microsoft 365.

Esta información de red se genera sobre la base de que todos los usuarios de una ciudad tienen acceso a la misma infraestructura de telecomunicaciones y la misma proximidad a los circuitos de Internet y a la red de Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Hora de realizar una solicitud DNS en la red

Esto muestra el servidor DNS configurado en el equipo cliente que ejecutó las pruebas. Puede ser un servidor de resolución recursiva DNS, pero esto es poco común. Es más probable que sea un servidor de reenviador DNS que almacena en caché los resultados dns y reenvía las solicitudes DNS sin almacenar en caché a otro servidor DNS.

Esto se proporciona solo para la información y no contribuye a ninguna información de red.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Distancia desde y/o tiempo para conectarse a un solucionador recursivo DNS

El solucionador recursivo DNS en uso se identifica realizando una solicitud DNS específica y, a continuación, solicitando al servidor de nombres DNS la dirección IP de la que recibió la misma solicitud. Esta dirección IP es el solucionador recursivo DNS y se buscará en las bases de datos de ubicación de direcciones IP para encontrar la ubicación. A continuación, se calcula la distancia desde la ubicación de la oficina de usuario a la ubicación del servidor de resolución recursiva DNS. Esto se muestra como una información de red si la distancia es mayor que **500 millas** (800 kilómetros).

Es posible que la ubicación buscada desde la dirección IP de salida de red no sea precisa y esto daría lugar a un resultado falso de esta prueba. Para validar si se produce este error para una dirección IP específica, puede usar sitios web de ubicación de direcciones IP de red accesibles públicamente.

Esta información de red afectará específicamente a la selección de la puerta principal del servicio de Exchange Online. Para abordar esta información, la salida de red local y directa debe ser un requisito previo y, a continuación, el solucionador recursivo DNS debe encontrarse cerca de esa salida de red.

### <a name="exchange-online"></a>Exchange en línea

En esta sección se muestran los resultados de las pruebas relacionados con Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Ubicación de la puerta principal del servicio exchange

La puerta principal del servicio exchange en uso se identifica de la misma manera que Outlook lo hace y medimos la latencia TCP de red desde la ubicación del usuario hasta ella. Se muestra la latencia TCP y la puerta principal del servicio de Exchange en uso se compara con la lista de puertas frontales de mejor servicio para la ubicación actual. Esto se muestra como una información de red si una de las puertas frontales del mejor servicio de Exchange no está en uso.

No usar una de las puertas frontales del mejor servicio de Exchange podría deberse al backhaul de red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa. También podría deberse al uso de un servidor de resolución recursiva de DNS remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva DNS con la salida de red.

Calculamos una posible mejora en la latencia TCP (ms) en la puerta principal del servicio Exchange. Para ello, observa la latencia de red de la ubicación de la oficina de usuario probada y resta la latencia de red de la ubicación actual a la puerta principal del servicio Exchange. La diferencia representa la oportunidad potencial de mejora.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Puertas frontales del mejor servicio de Exchange para su ubicación

Esto enumera las mejores ubicaciones de la puerta principal del servicio Exchange por ciudad para su ubicación.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Puerta principal del servicio registrada en el DNS del cliente

Esto muestra el nombre DNS y la dirección IP del servidor de puerta principal del servicio exchange al que se le ha dirigido. Solo se proporciona para la información y no hay información de red asociada.

### <a name="sharepoint-online"></a>SharePoint en linea

En esta sección se muestran los resultados de las pruebas relacionadas con SharePoint Online y OneDrive.

#### <a name="the-service-front-door-location"></a>Ubicación de la puerta principal del servicio

La puerta principal del servicio de SharePoint en uso se identifica de la misma manera que lo hace el cliente de OneDrive y medimos la latencia TCP de red desde la ubicación de la oficina del usuario hasta ella.

#### <a name="download-speed"></a>Velocidad de descarga

Medimos la velocidad de descarga de un archivo de 15 Mb desde la puerta principal del servicio de SharePoint. El resultado se muestra en megabytes por segundo para indicar qué archivo de tamaño en megabytes se puede descargar desde SharePoint o OneDrive en **un segundo.** El número debe ser similar a una décima parte del ancho de banda mínimo del circuito en megabits por segundo. Por ejemplo, si tiene una conexión a Internet de 100mbps, puede esperar 10 megabytes por segundo (10 MBps).

#### <a name="buffer-bloat"></a>Bloat de búfer

Durante la descarga de 15 Mb, se mide la latencia TCP en la puerta principal del servicio de SharePoint. Esta es la latencia bajo carga y se compara con la latencia cuando no está bajo carga. El aumento de la latencia cuando se carga a menudo es atribuible a los búferes de dispositivos de red del consumidor que se cargan (o se saturan). Se muestra una información de red para cualquier bloat de 1.000 o más.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Puerta principal del servicio registrada en el DNS del cliente

Esto muestra el nombre DNS y la dirección IP del servidor de puerta principal del servicio de SharePoint al que se le ha dirigido. Solo se proporciona para la información y no hay información de red asociada.

### <a name="microsoft-teams"></a>Microsoft Teams

En esta sección se muestran los resultados de las pruebas relacionadas con Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Conectividad de medios (audio, vídeo y uso compartido de aplicaciones)

Esto prueba la conectividad UDP a la puerta principal del servicio de Microsoft Teams. Si esto está bloqueado, Microsoft Teams puede seguir funcionando con TCP, pero el audio y el vídeo se verán dañados. Obtenga más información sobre estas medidas de red UDP que también se aplican a Microsoft Teams en Calidad de medios y Rendimiento de conectividad de red [en Skype Empresarial Online](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Pérdida de paquetes

Muestra la pérdida de paquetes UDP medida en una llamada de audio de prueba de 10 segundos desde el cliente a la puerta principal del servicio de Microsoft Teams. Esto debe ser inferior al **1,00 %** para un pase.

#### <a name="latency"></a>Latencia

Muestra la latencia UDP medida, que debe ser inferior a **100 ms**.

#### <a name="jitter"></a>Vibración

Muestra el vibración UDP medido, que debe ser inferior a **30 ms.**

#### <a name="connectivity"></a>Conectividad

Se prueba la conectividad HTTP desde la ubicación de la oficina del usuario a todos los extremos de red de Microsoft 365 necesarios. Se publican en [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Se muestra una información de red para los puntos de conexión de red necesarios a los que no se puede conectar.

Un servidor proxy, un firewall u otro dispositivo de seguridad de red del perímetro de red empresarial pueden bloquear la conectividad. La conectividad al puerto TCP 80 se prueba con una solicitud HTTP y la conectividad al puerto TCP 443 se prueba con una solicitud HTTPS. Si no hay respuesta, el FQDN se marca como un error. Si hay un código de respuesta HTTP 407, el FQDN se marca como un error. Si hay un código de respuesta HTTP 403, comprobaremos el atributo Server de la respuesta y, si parece ser un servidor proxy, lo marcamos como un error. Puedes simular las pruebas que llevamos a cabo con la herramienta de línea de comandos de Windows curl.exe.

Se prueba el certificado SSL en cada extremo de red de Microsoft 365 necesario que se encuentra en la categoría optimizar o permitir tal como se define en [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Si alguna prueba no encuentra un certificado SSL de Microsoft, la red cifrada conectada debe haber sido interceptada por un dispositivo de red intermediario. Se muestra una información de red en los puntos de conexión de red cifrados interceptados.

Cuando se encuentra un certificado SSL que no proporciona Microsoft, se muestra el FQDN de la prueba y el propietario del certificado SSL en uso. Este propietario de certificado SSL puede ser un proveedor de servidores proxy o puede ser un certificado autofirmado de empresa.

#### <a name="network-path"></a>Ruta de acceso de red

En esta sección se muestran los resultados de una ruta de seguimiento ICMP a la puerta principal del servicio de Exchange Online, a la puerta principal del servicio de SharePoint Online y a la puerta principal del servicio de Microsoft Teams. Solo se proporciona para la información y no hay información de red asociada. Se proporcionan tres rutas de seguimiento. Un traceroute a _outlook.office365.com_, un traceroute a los clientes cliente de SharePoint front-end o _a microsoft.sharepoint.com_ si no se proporcionó uno y un traceroute a _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Informes de conectividad

Cuando haya iniciado sesión, puede revisar los informes anteriores que haya ejecutado. También puede compartirlos o eliminarlos de la lista.

![Informes](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Estado de mantenimiento de la red

Esto muestra cualquier problema de mantenimiento significativo con la red global de Microsoft que podría afectar a los clientes de Microsoft 365.

![Estado de mantenimiento de la red](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Preguntas más frecuentes

Estas son las respuestas a algunas de nuestras preguntas más frecuentes.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>¿Microsoft ha lanzado y admitido esta herramienta?

Actualmente es una versión preliminar y tenemos previsto proporcionar actualizaciones periódicamente hasta que alcancemos el estado de la versión de disponibilidad general con el soporte técnico de Microsoft. Proporcione comentarios para ayudarnos a mejorar. Estamos planeando publicar una guía de incorporación de red de Office 365 más detallada como parte de esta herramienta personalizada para la organización por sus resultados de prueba.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>¿Qué es necesario para ejecutar el cliente de prueba avanzada?

El cliente de prueba avanzada requiere .NET Core 3.1 Desktop Runtime. Si ejecuta el cliente de prueba avanzada sin que esté instalado, se le dirigirá a la página del instalador [de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1). Asegúrese de instalar Desktop Runtime y no el SDK, o el ASP.NET Core Runtime que están más arriba en la página. Los permisos de administrador en el equipo son necesarios para instalar .NET Core.

### <a name="what-is-microsoft-365-service-front-door"></a>¿Qué es la puerta principal del servicio de Microsoft 365?

La puerta principal del servicio de Microsoft 365 es un punto de entrada en la red global de Microsoft donde los clientes y servicios de Office terminan su conexión de red. Para una conexión de red óptima a Microsoft 365, se recomienda que la conexión de red finalice en la puerta principal de Microsoft 365 más cercana en su ciudad o metro.

Nota: La puerta principal del servicio de Microsoft 365 no tiene ninguna relación directa con el producto del servicio de puerta frontal de **Azure** disponible en azure marketplace.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>¿Cuál es la mejor puerta principal de servicio de Microsoft 365?

Una mejor puerta frontal de servicio de Microsoft 365 (anteriormente conocida como puerta principal de servicio óptimo) es la más cercana a la salida de la red, generalmente en su ciudad o área metropolitana. Use la herramienta de rendimiento de red de Microsoft 365 para determinar la ubicación de la puerta principal del servicio en uso de Microsoft 365 y las puertas frontales de mejor servicio. Si la herramienta determina que la puerta principal en uso es una de las mejores, debería esperar una gran conectividad a la red global de Microsoft.

### <a name="what-is-an-internet-egress-location"></a>¿Qué es una ubicación de salida de Internet?

La ubicación de salida de Internet es la ubicación donde el tráfico de red sale de la red empresarial y se conecta a Internet. Esto también se identifica como la ubicación donde tiene un dispositivo de traducción de direcciones de red (NAT) y, por lo general, donde se conecta con un proveedor de servicios de Internet (ISP). Si ves una larga distancia entre la ubicación y la ubicación de salida de Internet, esto puede identificar un backhaul wan significativo.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de administración de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-overview.md)

[Información de rendimiento de red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-insights.md)

[Evaluación de red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-score.md)

[Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)](office-365-network-mac-location-services.md)