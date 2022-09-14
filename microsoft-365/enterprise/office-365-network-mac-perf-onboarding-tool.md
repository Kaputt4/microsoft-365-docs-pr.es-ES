---
title: Prueba de conectividad de red de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 1/18/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Prueba de conectividad de red de Microsoft 365
ms.openlocfilehash: e4045a8fde1d33bdc0072fbce9368d0ef8774ae7
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670573"
---
# <a name="microsoft-365-network-connectivity-test-tool"></a>Prueba de conectividad de red de Microsoft 365

La herramienta de prueba de conectividad de red de Microsoft 365 se encuentra en <https://connectivity.office.com>. Es una herramienta adjunta para la evaluación de la red y la información de red disponible en la Centro de administración de Microsoft 365 en health **| Menú Conectividad**.

> [!IMPORTANT]
> Es importante iniciar sesión en el inquilino de Microsoft 365, ya que todos los informes de prueba se comparten con el administrador y se cargan en el inquilino mientras inicia sesión.

> [!div class="mx-imgBorder"]
> ![Herramienta de prueba de conectividad.](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>La herramienta de prueba de conectividad de red admite inquilinos en WW Commercial pero no GCC Moderate, GCC High, DoD o China.

La información de red del Centro de Administración de Microsoft 365 se basa en mediciones regulares del producto para el inquilino de Microsoft 365, agregadas cada día. En comparación, la información de red de la prueba de conectividad de red de Microsoft 365 se ejecuta localmente en la herramienta.

Las pruebas en el producto son limitadas y la ejecución de pruebas locales para el usuario recopila más datos, lo que da como resultado información más detallada. La información de red del Centro de Administración de Microsoft 365 mostrará que hay un problema de red en una ubicación de oficina específica. La prueba de conectividad de Microsoft 365 puede ayudar a identificar la causa principal de ese problema y proporcionar una acción de mejora del rendimiento dirigida.

Se recomienda que estas conclusiones se usen juntos, donde se puede evaluar el estado de calidad de las redes para cada ubicación de la oficina en el Centro de Administración de Microsoft 365 y se pueden encontrar más detalles después de la implementación de pruebas basadas en la prueba de conectividad de Microsoft 365.

## <a name="what-happens-at-each-test-step"></a>Lo que sucede en cada paso de prueba

### <a name="office-location-identification"></a>Identificación de ubicación de Office

Al hacer clic en el botón *Ejecutar prueba* , se muestra la página de prueba en ejecución e identificamos la ubicación de office. Puede escribir su ubicación por ciudad, estado y país o elegir que se detecte automáticamente. Si detecta la ubicación de la oficina, la herramienta solicita la latitud y longitud del explorador web y limita la precisión a 300 metros por 300 metros antes de su uso. No es necesario identificar la ubicación de forma más precisa que el edificio para medir el rendimiento de la red.

### <a name="javascript-tests"></a>Pruebas de JavaScript

Después de la identificación de la ubicación de office, ejecutamos una prueba de latencia TCP en JavaScript y solicitamos datos al servicio sobre los servidores front-door del servicio de Microsoft 365 en uso y recomendados. Cuando se completan estas pruebas, se muestran en el mapa y en la pestaña de detalles, donde se pueden ver antes del paso siguiente.

### <a name="download-the-advanced-tests-client-application"></a>Descarga de la aplicación cliente de pruebas avanzadas

A continuación, se inicia la descarga de la aplicación cliente de pruebas avanzadas. Confiamos en que el usuario inicie la aplicación cliente y también debe tener instalado el entorno de ejecución de .NET 6.0.

Hay dos partes de la prueba de conectividad de red de Microsoft 365: el sitio <https://connectivity.office.com> web y una aplicación cliente de Windows descargable que ejecuta pruebas avanzadas de conectividad de red. La mayoría de las pruebas requieren la ejecución de la aplicación. Rellenará los resultados de nuevo en la página web a medida que se ejecute.

Se le pedirá que descargue la aplicación de prueba de cliente avanzada del sitio web una vez completadas las pruebas del explorador web. Abra y ejecute el archivo cuando se le solicite.

> [!div class="mx-imgBorder"]
> ![Pruebas avanzadas de la aplicación cliente.](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Inicio de la aplicación cliente de pruebas avanzadas

Una vez que se inicia la aplicación cliente, la página web se actualizará para mostrar este resultado. Los datos de prueba comenzarán a recibirse en la página web. La página se actualiza cada vez que se reciben nuevos datos y puede revisar los datos a medida que llegan.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Pruebas avanzadas completadas y carga de informes de prueba

Cuando se completen las pruebas, la página web y el cliente de pruebas avanzadas lo mostrarán. Si el usuario ha iniciado sesión, el informe de prueba se cargará en el inquilino del cliente.

## <a name="sharing-your-test-report"></a>Uso compartido del informe de prueba

El informe de prueba requiere autenticación en la cuenta de Microsoft 365. El administrador selecciona cómo puede compartir el informe de prueba. La configuración predeterminada permite compartir los informes con otro usuario de la organización y el vínculo ReportID no está disponible. Los informes expirarán de forma predeterminada después de 90 días.

### <a name="sharing-your-report-with-your-administrator"></a>Uso compartido del informe con el administrador

Si ha iniciado sesión cuando se produce un informe de prueba, el informe se comparte con el administrador.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Uso compartido con el equipo de su cuenta de Microsoft, soporte técnico u otro personal

Los informes de prueba (excepto cualquier identificación personal) se comparten con los empleados de Microsoft. Este uso compartido está habilitado de forma predeterminada y el administrador puede deshabilitarlo en el | de mantenimiento **Página Conectividad de red** en el Centro de Administración de Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-microsoft-365-tenant"></a>Uso compartido con otros usuarios que inician sesión en el mismo inquilino de Microsoft 365

Puede elegir los usuarios con los que compartir el informe. La opción de elegir está habilitada de forma predeterminada, pero el administrador puede deshabilitarla.

> [!div class="mx-imgBorder"]
> ![Compartir un vínculo a los resultados de la prueba con un usuario.](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Uso compartido con cualquier persona que use un vínculo ReportID

Puede compartir el informe de prueba con cualquier persona proporcionando acceso a un vínculo ReportID. Este vínculo genera una dirección URL que puede enviar a alguien para que pueda mostrar el informe de prueba sin iniciar sesión. Este uso compartido está deshabilitado de forma predeterminada y el administrador debe habilitarlo.

> [!div class="mx-imgBorder"]
> ![Compartir un vínculo a los resultados de la prueba.](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Resultados de las pruebas de conectividad de red

Los resultados se muestran en las pestañas **Resumen** y **Detalles**. La pestaña de resumen muestra un mapa del perímetro de red detectado y una comparación de la evaluación de red con otros clientes de Microsoft 365 cercanos. También permite compartir el informe de prueba. Este es el aspecto de la vista de resultados de resumen:

> [!div class="mx-imgBorder"]
> ![Resultados de resumen de la herramienta de prueba de conectividad de red.](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Este es un ejemplo de la salida de la pestaña de detalles. En la pestaña de detalles se muestra una marca de verificación de círculo verde si el resultado se comparó favorablemente. Se muestra un signo de exclamación de triángulo rojo si el resultado superó un umbral que indica una información de red. En las secciones siguientes se describe cada una de las filas de resultados de la pestaña de detalles y se explican los umbrales usados para la información de red.

> [!div class="mx-imgBorder"]
> ![Resultados de prueba de la herramienta de prueba de conectividad de red.](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Información de ubicación

En esta sección se muestran los resultados de las pruebas relacionados con la ubicación.

#### <a name="your-location"></a>Su ubicación

La ubicación del usuario se detecta desde el explorador web de usuarios. También se puede escribir a elección del usuario. Se usa para identificar las distancias de red a partes específicas del perímetro de red empresarial. Solo la ciudad de esta detección de ubicación y la distancia a otros puntos de red se guardan en el informe.

La ubicación de la oficina del usuario se muestra en la vista de mapa.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Ubicación de salida de red (la ubicación donde la red se conecta al ISP)

Identificamos la dirección IP de salida de red en el lado servidor. Las bases de datos de ubicación se usan para buscar la ubicación aproximada de la salida de la red. Estas bases de datos suelen tener una precisión de aproximadamente el 90 % de las direcciones IP. Si la ubicación buscada desde la dirección IP de salida de red no es precisa, esto daría lugar a un resultado falso. Para validar si se está produciendo este error para una dirección IP específica, puede usar sitios web de ubicación de direcciones IP de red accesibles públicamente para compararlos con la ubicación real.

#### <a name="your-distance-from-the-network-egress-location"></a>La distancia desde la ubicación de salida de red

Determinamos la distancia entre esa ubicación y la ubicación de la oficina. Esto se muestra como una información de red si la distancia es mayor que **500 millas** (800 kilómetros), ya que es probable que aumente la latencia tcp en más de 25 ms y puede afectar a la experiencia del usuario.

El mapa muestra la ubicación de salida de la red en relación con la ubicación de la oficina del usuario que indica el backhaul de red dentro de la WAN empresarial.

Implemente la salida de red local y directa desde las ubicaciones de la oficina del usuario a Internet para obtener una conectividad de red óptima de Microsoft 365. Las mejoras en la salida local y directa son la mejor manera de abordar esta información de red.

#### <a name="proxy-server-information"></a>Información del servidor proxy

Identificamos si los servidores proxy están configurados en el equipo local para pasar el tráfico de red de Microsoft 365 en la categoría **Optimizar** . Identificamos la distancia desde la ubicación de la oficina del usuario a los servidores proxy.

La distancia se prueba primero mediante ping ICMP. Si se produce un error, se prueba con ping TCP y, por último, se busca la dirección IP del servidor proxy en una base de datos de ubicación de direcciones IP. Se muestra una información de red si el servidor proxy está a más de **500 millas** (800 kilómetros) de distancia de la ubicación de la oficina del usuario.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Red privada virtual (VPN) que usa para conectarse a su organización

Esta prueba detecta si usa una VPN para conectarse a Microsoft 365. Un resultado que pasa mostrará si no tiene ninguna VPN o si tiene una VPN con la configuración de túnel dividido recomendada para Microsoft 365.

#### <a name="vpn-split-tunnel"></a>Túnel dividido de VPN

Cada ruta de categoría **optimizar** para Exchange Online, SharePoint Online y Microsoft Teams se prueba para ver si está tunelización en la VPN. Una carga de trabajo dividida evita completamente la VPN. Se envía una carga de trabajo tunelización a través de la VPN. Una carga de trabajo tunelización selectiva tiene algunas rutas enviadas a través de la VPN y algunas divididas. Un resultado que pasa mostrará si todas las cargas de trabajo se dividen o se tunelizarán selectivamente.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Clientes de su área metropolitana con mejor rendimiento

La latencia de red entre la ubicación de la oficina del usuario y el servicio de Exchange Online se compara con otros clientes de Microsoft 365 de la misma área metropolitana. Se muestra una información de red si el 10 % o más de los clientes de la misma área metropolitana tienen un mejor rendimiento. Esto significa que sus usuarios tendrán un mejor rendimiento en la interfaz de usuario de Microsoft 365.

Esta información de red se genera sobre la base de que todos los usuarios de una ciudad tienen acceso a la misma infraestructura de telecomunicaciones y a la misma proximidad a los circuitos de Internet y a la red de Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Hora de realizar una solicitud DNS en la red

Esto muestra el servidor DNS configurado en el equipo cliente que ejecutó las pruebas. Puede ser un servidor de resolución recursiva de DNS, pero esto es poco frecuente. Es más probable que sea un servidor de reenviador DNS, que almacena en caché los resultados dns y reenvía las solicitudes DNS no almacenadas en caché a otro servidor DNS.

Esto solo se proporciona para información y no contribuye a ninguna información de red.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Distancia desde y/o tiempo para conectarse a un solucionador recursivo de DNS

La resolución recursiva de DNS en uso se identifica realizando una solicitud DNS específica y, a continuación, solicitando al servidor de nombres DNS la dirección IP de la que recibió la misma solicitud. Esta dirección IP es la resolución recursiva de DNS y se buscará en las bases de datos de ubicación de direcciones IP para encontrar la ubicación. A continuación, se calcula la distancia desde la ubicación de la oficina del usuario hasta la ubicación del servidor de resolución recursiva de DNS. Esto se muestra como una información de red si la distancia es mayor que **500 millas** (800 kilómetros).

Es posible que la ubicación buscada desde la dirección IP de salida de red no sea precisa y esto daría lugar a un resultado falso de esta prueba. Para validar si este error se está produciendo para una dirección IP específica, puede usar sitios web de ubicación de direcciones IP de red accesibles públicamente.

Esta información de red afectará específicamente a la selección de la puerta principal del servicio Exchange Online. Para abordar esta información, la salida de red local y directa debe ser un requisito previo y, a continuación, la resolución recursiva de DNS debe encontrarse cerca de esa salida de red.

### <a name="exchange-online"></a>Exchange Online

En esta sección se muestran los resultados de las pruebas relacionados con Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Ubicación de la puerta principal del servicio Exchange

La puerta principal del servicio exchange en uso se identifica de la misma manera que Outlook y medimos la latencia TCP de red desde la ubicación del usuario hasta ella. Se muestra la latencia TCP y la puerta principal del servicio de Exchange en uso se compara con la lista de las mejores puertas delanteras de servicio para la ubicación actual. Esto se muestra como una información de red si uno de los mejores servicios de Exchange no está en uso.

No usar una de las mejores puertas de servicio de Exchange podría deberse a un backhaul de red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa. También podría deberse al uso de un servidor de resolución recursivo dns remoto, en cuyo caso se recomienda alinear el servidor de resolución recursivo DNS con la salida de red.

Calculamos una posible mejora en la latencia TCP (ms) en la puerta principal del servicio Exchange. Para ello, examine la latencia de red de la ubicación de la oficina del usuario probada y reste la latencia de red de la ubicación actual a la puerta principal del servicio exchange de armarios. La diferencia representa la posible oportunidad de mejora.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Puertas delanteras del mejor servicio de Exchange para su ubicación

Se enumeran las mejores ubicaciones de puerta de servicio de Exchange por ciudad para su ubicación.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Puerta de servicio registrada en el DNS del cliente

Esto muestra el nombre DNS y la dirección IP del servidor front-door del servicio Exchange al que se le ha dirigido. Solo se proporciona para información y no hay información de red asociada.

### <a name="sharepoint-online"></a>SharePoint Online

En esta sección se muestran los resultados de las pruebas relacionadas con SharePoint Online y OneDrive.

#### <a name="the-service-front-door-location"></a>Ubicación de la puerta principal del servicio

La puerta principal del servicio de SharePoint en uso se identifica de la misma manera que lo hace el cliente de OneDrive y se mide la latencia TCP de red desde la ubicación de la oficina del usuario a ella.

#### <a name="download-speed"></a>Velocidad de descarga

Medimos la velocidad de descarga de un archivo de 15 Mb desde la puerta principal del servicio de SharePoint. El resultado se muestra en megabytes por segundo para indicar qué archivo de tamaño en megabytes se puede descargar de SharePoint o OneDrive en **un segundo**. El número debe ser similar a una décima parte del ancho de banda mínimo del circuito en megabits por segundo. Por ejemplo, si tiene una conexión a Internet de 100 mbps, puede esperar 10 megabytes por segundo (10 MBps).

#### <a name="buffer-bloat"></a>Saturación del búfer

Durante la descarga de 15 Mb, se mide la latencia tcp en la puerta principal del servicio de SharePoint. Esta es la latencia bajo carga y se compara con la latencia cuando no está bajo carga. El aumento de la latencia cuando está bajo carga suele atribuirse a los búferes de dispositivo de red de consumidor que se cargan (o se inflan). Se muestra una información de red para cualquier distensión de 100 ms o más.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Puerta de servicio registrada en el DNS del cliente

Esto muestra el nombre DNS y la dirección IP del servidor front-door del servicio de SharePoint al que se le dirigió. Solo se proporciona para información y no hay información de red asociada.

### <a name="microsoft-teams"></a>Microsoft Teams

En esta sección se muestran los resultados de pruebas relacionados con Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Conectividad multimedia (audio, vídeo y uso compartido de aplicaciones)

Esto comprueba la conectividad UDP con la puerta principal del servicio de Microsoft Teams. Si se bloquea, es posible que Microsoft Teams siga funcionando con TCP, pero el audio y el vídeo se verán afectados. Obtenga más información sobre estas medidas de red UDP, que también se aplican a Microsoft Teams en [Calidad de los medios y Rendimiento de conectividad de red en Skype Empresarial Online](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

#### <a name="packet-loss"></a>Pérdida de paquetes

Muestra la pérdida de paquetes UDP medida en una llamada de audio de prueba de 10 segundos desde el cliente a la puerta principal del servicio de Microsoft Teams. Debe ser inferior al **1,00 %** para un pase.

#### <a name="latency"></a>Latencia

Muestra la latencia udp medida, que debe ser inferior a **100 ms**.

#### <a name="jitter"></a>Jitter

Muestra la vibración udp medida, que debe ser inferior a **30 ms**.

#### <a name="connectivity"></a>Conectividad

Se prueba la conectividad HTTP desde la ubicación de la oficina del usuario a todos los puntos de conexión de red de Microsoft 365 necesarios. Se publican en [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md). Se muestra una información de red para los puntos de conexión de red necesarios, a los que no se puede conectar.

Un servidor proxy, un firewall u otro dispositivo de seguridad de red en el perímetro de red empresarial pueden bloquear la conectividad. La conectividad con el puerto TCP 80 se prueba con una solicitud HTTP y la conectividad con el puerto TCP 443 se prueba con una solicitud HTTPS. Si no hay ninguna respuesta, el FQDN se marca como un error. Si hay un código de respuesta HTTP 407, el FQDN se marca como un error. Si hay un código de respuesta HTTP 403, comprobamos el atributo Server de la respuesta y, si parece ser un servidor proxy, lo marcamos como un error. Puede simular las pruebas que realizamos con la herramienta de línea de comandos de Windows curl.exe.

Probamos el certificado SSL en cada punto de conexión de red de Microsoft 365 necesario que se encuentra en la categoría optimizar o permitir tal como se define en [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md). Si alguna prueba no encuentra un certificado SSL de Microsoft, un dispositivo de red intermedio debe haber interceptado la red cifrada conectada. Se muestra una información de red en cualquier punto de conexión de red cifrado interceptado.

Cuando se encuentra un certificado SSL que no proporciona Microsoft, se muestra el FQDN de la prueba y el propietario del certificado SSL en uso. Este propietario del certificado SSL puede ser un proveedor de servidor proxy o puede ser un certificado autofirmado de empresa.

#### <a name="network-path"></a>Ruta de acceso a la red

En esta sección se muestran los resultados de un traceroute ICMP a la puerta principal del servicio Exchange Online, la puerta principal del servicio de SharePoint Online y la puerta principal del servicio de Microsoft Teams. Solo se proporciona para información y no hay información de red asociada. Se proporcionan tres rutas de seguimiento. Un traceroute para _outlook.office365.com_, un traceroute al front-end de SharePoint de los clientes o para _microsoft.sharepoint.com_ si no se proporcionó uno, y un traceroute para _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Informes de conectividad

Cuando haya iniciado sesión, puede revisar los informes anteriores que ha ejecutado. También puede compartirlos o eliminarlos de la lista.

> [!div class="mx-imgBorder"]
> ![Informes.](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Estado del estado de la red

Esto muestra cualquier problema de estado significativo con la red global de Microsoft, lo que podría afectar a los clientes de Microsoft 365.

> [!div class="mx-imgBorder"]
> ![Estado de mantenimiento de la red.](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="testing-from-the-command-line"></a>Pruebas desde la línea de comandos

Proporcionamos un ejecutable de línea de comandos que las herramientas de implementación y ejecución remotas pueden usar y ejecutar las mismas pruebas que están disponibles en el sitio web de la herramienta de prueba de conectividad de red de Microsoft 365.

La herramienta de prueba de línea de comandos se puede descargar aquí: [Herramienta de línea de comandos](https://connectivity.office.com/api/AnonymousConnectivityTest/DownloadStandAloneRichClient)

Puede ejecutarlo haciendo doble clic en el archivo ejecutable en Windows Explorador de archivos, o bien puede iniciarlo desde un símbolo del sistema o puede programarlo con el programador de tareas.

La primera vez que inicie el ejecutable, se le pedirá que acepte el contrato de licencia de usuario final (CLUF) antes de realizar las pruebas. Si ya ha leído y aceptado el CLUF, puede crear un archivo vacío denominado Microsoft-365-Network-Connectivity-Test-EULA-accepted.txt en el directorio de trabajo actual para el proceso ejecutable cuando se inicie. Para aceptar el CLUF, puede escribir "y" y presionar Entrar en la ventana de la línea de comandos cuando se le solicite.

El ejecutable acepta los siguientes parámetros de línea de comandos:
- -h para mostrar un vínculo a esta documentación de ayuda
- -testlist &lt;test&gt; Especifica las pruebas que se van a ejecutar. De forma predeterminada, solo se ejecutan pruebas básicas. Los nombres de prueba válidos incluyen: all, dnsConnectivityPerf, dnsResolverIdentification, bufferBloat, traceroute, proxy, vpn, skype, connectivity, networkInterface
- -filepath &lt;filedir Ruta de acceso del directorio&gt; de los archivos de resultados de prueba. El valor permitido es la ruta de acceso absoluta o relativa de un directorio accesible
- -city &lt;city&gt; Para los campos de ciudad, estado y país, se usará el valor especificado si se proporciona. Si no se proporciona, se consultará Windows Location Services (WLS). Si se produce un error en WLS, la ubicación se detectará desde la salida de la red de las máquinas. 
- -state &lt;state&gt;
- -país &lt;&gt; 
- -proxy &lt;account&gt; &lt;password&gt; El nombre y la contraseña de la cuenta de proxy se pueden proporcionar si necesita un proxy para acceder a Internet.

### <a name="results"></a>Resultados
La salida de los resultados se escribe en un archivo JSON de una carpeta denominada TestResults que se crea en el directorio de trabajo actual del proceso a menos que ya exista. El formato de nombre de archivo de la salida es connectivity_test_result_YYYY-MM-DD-HH-MM-SS.json. Los resultados se encuentran en nodos JSON que coinciden con la salida que se muestra en la página web del sitio web de la herramienta de prueba de conectividad de red de Microsoft 365. Se crea un nuevo archivo de resultados cada vez que lo ejecuta y el ejecutable independiente no carga los resultados en el inquilino de Microsoft para verlos en las páginas de conectividad de red del Centro de Administración. Los códigos de front door, las longitudes y las latitudes no se incluyen en el archivo de resultados.

### <a name="launching-from-windows-file-explorer"></a>Inicio desde Windows Explorador de archivos
Simplemente puede hacer doble clic en el archivo ejecutable para iniciar las pruebas y aparecerá una ventana del símbolo del sistema.

### <a name="launching-from-the-command-prompt"></a>Inicio desde el símbolo del sistema
En una ventana del símbolo del sistema CMD.EXE puede escribir la ruta de acceso y el nombre del archivo ejecutable para ejecutarlo. El nombre de archivo es Microsoft.Connectivity.Test.exe

### <a name="launching-from-windows-task-scheduler"></a>Inicio desde el Programador de tareas de Windows
En el Programador de tareas de Windows, puede agregar una tarea para iniciar el ejecutable de prueba independiente. Debe especificar el directorio de trabajo actual de la tarea donde ha creado el archivo aceptado del CLUF, ya que el ejecutable se bloqueará hasta que se acepte el CLUF. No puede aceptar interactivamente el CLUF si el proceso se inicia en segundo plano sin consola.

### <a name="more-details-on-the-standalone-executable"></a>Más detalles sobre el ejecutable independiente
La herramienta de línea de comandos usa Servicios de ubicación de Windows para buscar la información del país de estado de la ciudad de los usuarios para determinar algunas distancias. Si Windows Location Services está deshabilitado en el panel de control, las evaluaciones basadas en la ubicación del usuario estarán en blanco. En Configuración de Windows, "Los servicios de ubicación" deben estar activados y "Permitir que las aplicaciones de escritorio accedan a su ubicación" también deben estar activadas.

La herramienta de línea de comandos intentará instalar .NET Framework si aún no está instalado. También descargará el ejecutable de prueba principal de la herramienta de prueba de conectividad de red de Microsoft 365 y lo iniciará.

## <a name="faq"></a>Preguntas más frecuentes

Estas son las respuestas a algunas de nuestras preguntas más frecuentes.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>¿Qué es necesario para ejecutar el cliente de prueba avanzada?

El cliente de prueba avanzada requiere el entorno de ejecución de .NET 6.0. Si ejecuta el cliente de prueba avanzada sin que esté instalado, se le dirigirá a [la página del instalador de .NET 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0/runtime?utm_source=getdotnetcore). Asegúrese de instalar desde la columna Ejecutar aplicaciones de escritorio para Windows. Se requieren permisos de administrador en la máquina para instalar el entorno de ejecución de .NET 6.0.

El cliente de prueba avanzada usa SignalR para comunicarse con la página web. Para ello, debe asegurarse de que la conectividad del puerto TCP 443 con **connectivity.service.signalr.net** está abierta. Esta dirección URL no se publica en <https://aka.ms/o365ip> porque no es necesaria la conectividad para un usuario de aplicación cliente de Microsoft 365.

### <a name="what-is-microsoft-365-service-front-door"></a>¿Qué es la puerta principal del servicio de Microsoft 365?

La puerta principal del servicio de Microsoft 365 es un punto de entrada en la red global de Microsoft donde los clientes y servicios de Office finalizan su conexión de red. Para una conexión de red óptima a Microsoft 365, se recomienda que la conexión de red finalice en la puerta principal de Microsoft 365 más cercana de su ciudad o metro.

> [!NOTE]
> El servicio front door de Microsoft 365 no tiene ninguna relación directa con el producto **Azure Front Door Service** disponible en Azure Marketplace.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>¿Cuál es la mejor puerta de servicio de Microsoft 365?

Una mejor puerta de servicio de Microsoft 365 (anteriormente conocida como puerta de servicio óptima) es la más cercana a la salida de la red, por lo general en su ciudad o área metropolitana. Use la herramienta de rendimiento de red de Microsoft 365 para determinar la ubicación de la puerta principal del servicio de Microsoft 365 en uso y las mejores puertas de servicio. Si la herramienta determina que la puerta principal en uso es una de las mejores, debe esperar una excelente conectividad con la red global de Microsoft.

### <a name="what-is-an-internet-egress-location"></a>¿Qué es una ubicación de salida de Internet?

La ubicación de salida de Internet es la ubicación donde el tráfico de red sale de la red empresarial y se conecta a Internet. Esto también se identifica como la ubicación donde tiene un dispositivo de traducción de direcciones de red (NAT) y, normalmente, donde se conecta con un proveedor de servicios de Internet (ISP). Si ve una larga distancia entre su ubicación y su ubicación de salida de Internet, esto puede identificar un backhaul WAN significativo.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de Administración de Microsoft 365](office-365-network-mac-perf-overview.md)

[Información sobre el rendimiento de red de Microsoft 365](office-365-network-mac-perf-insights.md)

[Evaluación de red de Microsoft 365](office-365-network-mac-perf-score.md)

[Servicios de ubicación de conectividad de red de Microsoft 365](office-365-network-mac-location-services.md)
