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
ms.openlocfilehash: b29eb29cd390c3febd0992e942cf8ab39f652fb2
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49569992"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Herramienta de prueba de conectividad de red de Microsoft 365 (versión preliminar)

La herramienta de prueba de conectividad de red de Microsoft 365 se encuentra en <https://connectivity.office.com> . Es una herramienta adjunta a la evaluación de red y a la información de la red disponible en el Centro de administración de Microsoft 365 en el centro de **| Menú** Conectividad.

> [!IMPORTANT]
> Es importante iniciar sesión en el inquilino de Microsoft 365, ya que todos los informes de prueba se comparten con el administrador y se cargan en el espacio empresarial mientras se inicia sesión.

![Herramienta de prueba de conectividad](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>La herramienta de prueba de conectividad de red admite inquilinos en WW Commercial y Alemania, pero no GCC Moderate, GCC High, DoD o China.

La información de red del Centro de administración de Microsoft 365 se basa en medidas regulares del producto para su inquilino de Microsoft 365 que se agregan cada día. En comparación, la información de red de la prueba de conectividad de red de Microsoft 365 se ejecuta localmente y una vez en la herramienta. Las pruebas que se pueden realizar en el producto son limitadas y, al ejecutar pruebas locales para el usuario, se pueden recopilar más datos, lo que da como resultado información más profunda. Tenga en cuenta que la información de red en el Centro de administración de Microsoft 365 mostrará que hay un problema de red para el uso de Microsoft 365 en una ubicación de oficina específica. La prueba de conectividad de Microsoft 365 puede ayudar a identificar la causa principal de ese problema, lo que conduce a una acción recomendada para mejorar el rendimiento de la red.

Recomendamos que se usen conjuntamente donde se pueda evaluar el estado de calidad de las redes para cada ubicación de la oficina en el Centro de administración de Microsoft 365 y se puedan encontrar más detalles después de la implementación de pruebas basadas en la prueba de conectividad de Microsoft 365.

>[!IMPORTANT]
>La información de red, las recomendaciones de rendimiento y las evaluaciones en el Centro de administración de Microsoft 365 se encuentra actualmente en estado de vista previa y solo está disponible para los inquilinos de Microsoft 365 que se han inscrito en el programa de vista previa de características.

## <a name="what-happens-at-each-test-step"></a>Qué sucede en cada paso de prueba

### <a name="office-location-identification"></a>Identificación de ubicación de la oficina

Al hacer clic en el botón ejecutar prueba, se muestra la página de prueba en ejecución e identificamos la ubicación de la oficina. Puede escribir su ubicación por ciudad, estado y país, o bien puede detectarla desde el explorador web. Si lo detectas, solicitamos la latitud y longitud del explorador web y limitamos la precisión a 300m por 300m antes de su uso. Lo hacemos porque no es necesario identificar la ubicación de forma más precisa que el edificio para el rendimiento de la red. 

### <a name="javascript-tests"></a>Pruebas de JavaScript

Después de la identificación de la ubicación de la oficina, ejecutamos una prueba de latencia TCP en JavaScript y solicitamos datos del servicio sobre los servidores front-end de servicio de Office 365 en uso y recomendados. Cuando se completan, se muestran en el mapa y en la pestaña de detalles, donde se pueden ver antes del paso siguiente.

### <a name="download-the-advanced-tests-client-application"></a>Descargar la aplicación cliente de pruebas avanzadas

A continuación, se inicia la descarga de la aplicación cliente de pruebas avanzadas. Dependemos de que el usuario inicie la aplicación cliente y también debe tener instalado .NET Core.

Hay dos partes en la prueba de conectividad de red de Microsoft 365; el sitio web <https://connectivity.office.com> y una aplicación cliente de Windows descargable que ejecuta pruebas avanzadas de conectividad de red. La mayoría de las pruebas requieren que se ejecute la aplicación. Volverá a rellenar los resultados en la página web mientras se ejecuta.

Se le pedirá que descargue la aplicación de prueba de cliente avanzada del sitio web una vez completadas las pruebas del explorador web. Abra y ejecute el archivo cuando se le pida.

![Aplicación cliente de pruebas avanzadas](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Iniciar la aplicación cliente de pruebas avanzadas

Una vez que la aplicación cliente inicia la página web se actualizará para mostrar esto y los datos de prueba comenzarán a recibirse en la página web. Se actualiza cada vez que se reciben nuevos datos y puedes revisar los datos a medida que llegan.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Pruebas avanzadas completadas y carga de informes de prueba

Una vez completadas las pruebas, la página web y el cliente de pruebas avanzadas lo indicarán y si el usuario ha iniciado sesión en el informe de pruebas se cargará en el inquilino de clientes.

## <a name="sharing-your-test-report"></a>Compartir el informe de pruebas

El informe de prueba requiere iniciar sesión en su cuenta de Office 365. El administrador selecciona cómo puede compartir el informe de prueba.

### <a name="sharing-your-report-with-your-administrator"></a>Compartir el informe con el administrador

Todos los informes de prueba mientras ha iniciado sesión se comparten con el administrador.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Uso compartido con su equipo de cuenta de Microsoft, soporte técnico u otro personal

Los informes de prueba, excepto cualquier identificación personal, se comparten con los empleados de Microsoft. Esta opción está habilitada de forma predeterminada y el administrador puede deshabilitarla en el servicio de **| Página Conectividad de** red en el Centro de administración de Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Uso compartido con otros usuarios que inician sesión en el mismo inquilino de Office 365

Puede elegir los usuarios con los que compartir el informe y esta opción está habilitada de forma predeterminada. También puede deshabilitarlo el administrador.

![Compartir un vínculo a los resultados de la prueba con un usuario](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Uso compartido con cualquier persona que use un vínculo ReportID

Puede compartir el informe de prueba con cualquier persona proporcionando acceso a un vínculo ReportID. Esto genera una dirección URL que puede enviar a alguien para que pueda abrir el informe de prueba sin iniciar sesión. Esta opción está deshabilitada de forma predeterminada y el administrador debe habilitarla.

![Compartir un vínculo a los resultados de las pruebas](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Resultados de la prueba de conectividad de red

Los resultados se muestran en **las pestañas** Resumen **y** Detalles. La pestaña de resumen muestra un mapa del perímetro de red detectado y una comparación de la evaluación de red con otros clientes de Office 365 cercanos. También permite compartir el informe de prueba. Este es el aspecto de la vista de resultados de resumen.

![Resultados de resumen de la herramienta de prueba de conectividad de red](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Este es un ejemplo de los resultados de la pestaña de detalles que muestra la herramienta. En la pestaña detalles se muestra una marca de verificación de círculo verde si el resultado se ha comparado de forma favorecida con un umbral. Se muestra un signo de exclamación de triángulo rojo si el resultado superó un umbral que indica una información de red. En las secciones siguientes se describe cada una de las filas de resultados de la pestaña de detalles y se explican los umbrales usados para la información de red.

![Resultados de pruebas de la herramienta de prueba de conectividad de red](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Información de ubicación

En esta sección se muestran los resultados de las pruebas relacionados con la ubicación.

#### <a name="your-location"></a>Su ubicación

La ubicación del usuario se detecta desde el explorador web de los usuarios o se puede escribir en la elección de los usuarios. Se usa para identificar distancias de red a partes específicas del perímetro de la red empresarial. Solo la ciudad desde esta detección de ubicación y la distancia a otros puntos de red se guardan en el informe.

La ubicación de la oficina del usuario se muestra en la vista de mapa.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Ubicación de salida de red (la ubicación donde la red se conecta al ISP)

Identificamos la dirección IP de salida de red en el lado del servidor. Las bases de datos de ubicación se usan para buscar la ubicación aproximada de la salida de red. Estas bases de datos suelen tener una precisión de aproximadamente el 90 % de las direcciones IP. Si la ubicación buscada desde la dirección IP de salida de red no es precisa, esto daría lugar a un resultado falso de esta prueba. Para validar si se está produciendo este error para una dirección IP específica, puede usar sitios web de ubicación de direcciones IP de red de acceso público para compararlos con su ubicación real.

#### <a name="your-distance-from-the-network-egress-location"></a>Distancia desde la ubicación de salida de red

Determinamos la distancia desde esa ubicación hasta la ubicación de la oficina. Esto se muestra como información de red si la distancia es superior a **500** millas (800 kilómetros), ya que es probable que aumente la latencia TCP en más de 25 ms y puede afectar a la experiencia del usuario.

La ubicación de salida de red se muestra en la vista de mapa y se conecta a la ubicación de la oficina del usuario que indica la red backhaul dentro de la WAN empresarial.

Para la conectividad de red de Microsoft 365 se recomienda implementar la salida de red local y directa desde las ubicaciones de las oficinas de los usuarios a Internet. Las mejoras en la salida directa y local son la mejor forma de abordar esta información de red.

#### <a name="proxy-server-information"></a>Información del servidor proxy

Identificamos los servidores proxy configurados en el equipo local. Identificamos si alguno de ellos está configurado en la ruta de acceso de red para optimizar el tráfico de red de Microsoft 365 de la categoría. Identificamos la distancia desde la ubicación de la oficina del usuario hasta los servidores proxy. La distancia la prueba primero el ping ICMP y, si esto falla, se prueba con el ping TCP y, por último, si se produce un error, buscamos la dirección IP del servidor proxy en una base de datos de ubicación de direcciones IP. Mostramos información de red si el servidor proxy está a más de **500** millas (800 kilómetros) de la ubicación de la oficina del usuario.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Red privada virtual (VPN) que usa para conectarse a su organización

Esto detecta si usa una VPN para conectarse a Office 365. Un resultado de paso mostrará si no tiene VPN o si tiene una VPN con la configuración de túnel dividido recomendada para Office 365.

#### <a name="vpn-split-tunnel"></a>Túnel dividido de VPN

Cada ruta de categoría de optimización para Exchange Online, SharePoint Online y Microsoft Teams se prueba para ver si está tunelada en la VPN o no. Una carga de trabajo dividida evita completamente la VPN. Una carga de trabajo de túnel se envía a través de la VPN. Una carga de trabajo de túnel selectivo tiene algunas rutas enviadas a través de la VPN y otras divididas. Un resultado de paso mostrará si todas las cargas de trabajo se dividen o se tunelización selectiva.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Clientes de tu área metropolitana con mejor rendimiento

La latencia TCP de red de la ubicación de la oficina del usuario en la puerta principal del servicio de Exchange Online se compara con otros clientes de Microsoft 365 en la misma zona de metro. Se muestra una información de red si el 10 % o más de los clientes de la misma área de metro tienen un mejor rendimiento. Esto significa que sus usuarios tendrán un mejor rendimiento en la interfaz de usuario de Microsoft 365.

Esta información de red se genera en función de que todos los usuarios de una ciudad tienen acceso a la misma infraestructura de telecomunicaciones y la misma proximidad a los circuitos de Internet y a la red de Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Tiempo para realizar una solicitud DNS en la red

Esto muestra el servidor DNS configurado en el equipo cliente que ejecutó las pruebas. Puede ser un servidor de resolución recursiva DNS, pero esto no es común. Es más probable que sea un servidor de reenviador DNS que almacena en caché los resultados dns y reenvía las solicitudes DNS sin almacenar en caché a otro servidor DNS.

Esto se proporciona solo para la información y no contribuye a ninguna información de red.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Distancia y/o tiempo para conectarse a una resolución recursiva de DNS

El solucionador recursivo DNS en uso se identifica realizando una solicitud DNS específica y, a continuación, solicitando al servidor de nombres DNS la dirección IP de la que recibió la misma solicitud. Esta dirección IP es el solucionador recursivo DNS y se buscará en las bases de datos de ubicación de direcciones IP para encontrar la ubicación. A continuación, se calcula la distancia entre la ubicación de la oficina del usuario y la ubicación del servidor de resolución recursiva dns. Esto se muestra como información de red si la distancia es superior a **500 millas** (800 kilómetros).

Es posible que la ubicación buscada desde la dirección IP de salida de red no sea precisa y esto daría lugar a un resultado falso de esta prueba. Para validar si se está produciendo este error para una dirección IP específica, puede usar sitios web de ubicación de direcciones IP de red de acceso público.

Esta información de red afectará específicamente a la selección de la puerta principal del servicio de Exchange Online. Para abordar esta información, la salida de red local y directa debe ser un requisito previo y, a continuación, resolver recursivo DNS debe estar ubicado cerca de esa salida de red.

### <a name="exchange-online"></a>Exchange Online

En esta sección se muestran los resultados de las pruebas relacionadas con Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Ubicación de la puerta principal del servicio de Exchange

La puerta principal del servicio exchange en uso se identifica de la misma manera que Outlook lo hace y se mide la latencia TCP de red desde la ubicación del usuario hasta ella. Se muestra la latencia TCP y la puerta frontal del servicio de Exchange en uso se compara con la lista de mejores puertas frontales de servicio para la ubicación actual. Esto se muestra como información de red si una de las mejores puertas de servicio de Exchange no está en uso.

El hecho de no usar una de las mejores puertas frontales del servicio de Exchange podría deberse a la reenlace de la red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa. También podría deberse al uso de un servidor de resolución recursiva de DNS remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva dns con la salida de red.

Calculamos una posible mejora en la latencia TCP (ms) en la puerta principal del servicio de Exchange. Para ello, se analiza la latencia de la red de ubicación de la oficina de usuario probada y se resta la latencia de red de la ubicación actual a la puerta principal del servicio Exchange. La diferencia representa la posibilidad de mejorar.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Mejor servicio de Exchange front-door(s) para su ubicación

Se enumeran las mejores ubicaciones de la puerta principal del servicio de Exchange por ciudad para su ubicación.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Puerta frontal del servicio registrada en el DNS del cliente

Muestra el nombre DNS y la dirección IP del servidor front-end del servicio de Exchange al que se le ha dirigido. Solo se proporciona para obtener información y no hay ninguna información de red asociada.

### <a name="sharepoint-online"></a>SharePoint Online

En esta sección se muestran los resultados de las pruebas relacionados con SharePoint Online y OneDrive.

#### <a name="the-service-front-door-location"></a>La ubicación de la puerta principal del servicio

La puerta principal del servicio de SharePoint en uso se identifica de la misma manera que lo hace el cliente de OneDrive y se mide la latencia TCP de red desde la ubicación de la oficina del usuario hasta ella.

#### <a name="download-speed"></a>Velocidad de descarga

Se mide la velocidad de descarga de un archivo de 15 Mb desde la puerta principal del servicio de SharePoint. El resultado se muestra en megabytes por segundo para indicar el tamaño del archivo en megabytes que se puede descargar de SharePoint o OneDrive **en un segundo.** El número debe ser similar a una décima parte del ancho de banda mínimo del circuito en megabits por segundo. Por ejemplo, si tiene una conexión a Internet de 100 mbps, puede esperar 10 megabytes por segundo (10 MBps).

#### <a name="buffer-bloat"></a>Saturación del búfer

Durante la descarga de 15 Mb, se mide la latencia TCP en la puerta principal del servicio de SharePoint. Esta es la latencia bajo carga y se compara con la latencia cuando no está bajo carga. El aumento de la latencia cuando se carga a menudo se atribuyó a los búferes de dispositivos de red del consumidor que se cargan (o se saturan). Se muestra una información de red para cualquier gran cantidad de 1.000 o más.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Puerta frontal del servicio registrada en el DNS del cliente

Muestra el nombre DNS y la dirección IP del servidor front-end del servicio de SharePoint al que se le ha dirigido. Solo se proporciona para obtener información y no hay ninguna información de red asociada.

### <a name="microsoft-teams"></a>Microsoft Teams

En esta sección se muestran los resultados de las pruebas relacionadas con Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Conectividad de medios (audio, vídeo y uso compartido de aplicaciones)

Esto comprueba la conectividad UDP con la puerta frontal del servicio de Microsoft Teams. Si se bloquea, es posible que Microsoft Teams aún funcione con TCP, pero el audio y el vídeo serán deficientes. Obtenga más información sobre estas medidas de red UDP que también se aplican a Microsoft Teams en calidad de medios y rendimiento de conectividad de [red en Skype Empresarial Online](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Pérdida de paquetes

Muestra la pérdida de paquetes UDP medida en una llamada de audio de prueba de 10 segundos desde el cliente a la puerta principal del servicio de Microsoft Teams. Debe ser inferior al **1,00%** para un pase.

#### <a name="latency"></a>Latencia

Muestra la latencia UDP medida, que debe ser inferior a **100 ms.**

#### <a name="jitter"></a>Vibración

Muestra la vibración UDP medida, que debe ser inferior a **30 ms.**

#### <a name="connectivity"></a>Conectividad

Se prueba la conectividad HTTP desde la ubicación de la oficina del usuario a todos los puntos de conexión de red de Microsoft 365 necesarios. Estos se publican en [https://aka.ms/o365ip](https://aka.ms/o365ip) . Se muestra una información de red para los puntos de conexión de red necesarios a los que no se puede conectar.

La conectividad puede estar bloqueada por un servidor proxy, un firewall u otro dispositivo de seguridad de red en el perímetro de red de la empresa. La conectividad con el puerto TCP 80 se prueba con una solicitud HTTP y la conectividad al puerto TCP 443 se prueba con una solicitud HTTPS. Si no hay respuesta, el FQDN se marca como error. Si hay un código de respuesta HTTP 407, el FQDN se marca como error. Si hay un código de respuesta HTTP 403, comprobaremos el atributo Server de la respuesta y, si parece ser un servidor proxy, lo marcamos como un error. Puedes simular las pruebas que se realizan con la herramienta de línea de comandos de Windows curl.exe.

Se prueba el certificado SSL en cada extremo de red de Microsoft 365 necesario que se encuentra en la categoría optimizar o permitir tal como se define en [https://aka.ms/o365ip](https://aka.ms/o365ip) . Si alguna prueba no encuentra un certificado SSL de Microsoft, la red cifrada conectada debe haber sido interceptada por un dispositivo de red intermediario. Se muestra una información de red en cualquier punto de conexión de red cifrado interceptado.

Cuando se encuentra un certificado SSL que no proporciona Microsoft, se muestra el FQDN de la prueba y el propietario del certificado SSL en uso. Este propietario del certificado SSL puede ser un proveedor de servidores proxy o puede ser un certificado autofirmado de empresa.

#### <a name="network-path"></a>Ruta de acceso de red

En esta sección se muestran los resultados de un traceroute ICMP a la puerta principal del servicio de Exchange Online, la puerta frontal del servicio de SharePoint Online y la puerta frontal del servicio de Microsoft Teams. Solo se proporciona para obtener información y no hay ninguna información de red asociada. Se proporcionan tres rutas de seguimiento. Un traceroute a _outlook.office365.com_, un traceroute a los clientes front-end de SharePoint o _a microsoft.sharepoint.com_ si no se proporcionó uno, y un traceroute a _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Informes de conectividad

Cuando haya iniciado sesión, puede revisar los informes anteriores que haya ejecutado. También puede compartirlos o eliminarlos de la lista.

![Informes](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Estado de mantenimiento de la red

Esto muestra los problemas de salud importantes con la red global de Microsoft que podrían afectar a los clientes de Microsoft 365.

![Estado de mantenimiento de la red](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Preguntas más frecuentes

Estas son las respuestas a algunas de nuestras preguntas más frecuentes.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>¿Esta herramienta está publicada y es compatible con Microsoft?

Actualmente es una versión preliminar y tenemos previsto proporcionar actualizaciones periódicamente hasta que lleguemos al estado de versión de disponibilidad general con el soporte técnico de Microsoft. Envíe sus comentarios para ayudarnos a mejorar. Estamos planeando publicar una guía de incorporación de red de Office 365 más detallada como parte de esta herramienta personalizada para la organización por sus resultados de prueba.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>¿Qué es necesario para ejecutar el cliente de prueba avanzado?

El cliente de prueba avanzada requiere .NET Core 3.1 Desktop Runtime. Si ejecutas el cliente de prueba avanzada sin eso instalado, se te dirigirá a la página del [instalador de .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1) Asegúrate de instalar El tiempo de ejecución de escritorio y no el SDK o ASP.NET Core Runtime que están en la parte superior de la página. Se requieren permisos de administrador en el equipo para instalar .NET Core.

### <a name="what-is-microsoft-365-service-front-door"></a>¿Qué es la puerta principal del servicio de Microsoft 365?

La puerta principal del servicio de Microsoft 365 es un punto de entrada en la red global de Microsoft donde los clientes y servicios de Office finalizan su conexión de red. Para una conexión de red óptima a Microsoft 365, se recomienda que la conexión de red finalice en la puerta principal de Microsoft 365 más cercana en su ciudad o metro.

Nota: la puerta frontal del servicio de Microsoft 365 no tiene una relación directa con el producto **de servicio front-door** de Azure disponible en azure marketplace.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>¿Cuál es la mejor puerta de servicio de Microsoft 365?

Una mejor puerta frontal del servicio de Microsoft 365 (anteriormente conocida como una puerta de servicio óptima) es la que está más cerca de la salida de red, generalmente en su ciudad o área de metro. Use la herramienta de rendimiento de red de Microsoft 365 para determinar la ubicación de la puerta frontal del servicio de Microsoft 365 en uso y las mejores puertas de servicio. Si la herramienta determina que la puerta principal en uso es una de las mejores, debería esperar una gran conectividad a la red global de Microsoft.

### <a name="what-is-an-internet-egress-location"></a>¿Qué es una ubicación de salida de Internet?

La ubicación de salida de Internet es la ubicación donde el tráfico de red sale de la red empresarial y se conecta a Internet. También se identifica como la ubicación donde tiene un dispositivo de traducción de direcciones de red (NAT) y, por lo general, donde se conecta con un proveedor de servicios de Internet (ISP). Si ve una larga distancia entre su ubicación y la ubicación de salida de Internet, esto puede identificar una red WAN de reserva significativa.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de administración de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-overview.md)

[Información de rendimiento de red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-insights.md)

[Evaluación de red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-score.md)

[Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)](office-365-network-mac-location-services.md)
