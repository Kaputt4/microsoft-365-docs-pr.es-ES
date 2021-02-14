---
title: Plan de solución de problemas de rendimiento para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: Este artículo puede ayudarle a solucionar problemas de rendimiento de Office 365 e incluso solucionar algunos de los problemas más comunes.
ms.openlocfilehash: 4f66ed43df2da47c9ea1931b8508dfecf4546b1c
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948393"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Plan de solución de problemas de rendimiento para Office 365

¿Necesita conocer los pasos a seguir para identificar y corregir los demoras, las faltas y el rendimiento lento entre SharePoint Online, OneDrive para la Empresa, Exchange Online o Skype Empresarial Online, y el equipo cliente? Antes de llamar al soporte técnico, este artículo puede ayudarle a solucionar problemas de rendimiento de Office 365 e incluso a solucionar algunos de los problemas más comunes.

En realidad, este artículo es un plan de acción de ejemplo que puede usar para capturar datos valiosos sobre el problema de rendimiento mientras está sucediendo. En este artículo también se incluyen algunos de los principales problemas.

Si no tiene experiencia en el rendimiento de la red y desea realizar un plan a largo plazo para supervisar el rendimiento entre los equipos cliente y Office 365, consulte el ajuste del rendimiento y la solución de problemas de [Office 365:](performance-tuning-using-baselines-and-history.md)administrador y profesional de TI.

## <a name="sample-performance-troubleshooting-action-plan"></a>Plan de acción de solución de problemas de rendimiento de ejemplo

Este plan de acción contiene dos partes; una fase de preparación y una fase de registro. Si tiene un problema de rendimiento en este momento y necesita realizar la recopilación de datos, puede empezar a usar este plan inmediatamente.

### <a name="prepare-the-client-computer"></a>Preparar el equipo cliente

- Busque un equipo cliente que pueda reproducir el problema de rendimiento. Este equipo se usará durante el transcurso de la solución de problemas.
- Anote los pasos que provocan el problema de rendimiento para que esté listo cuando llegue el momento de la prueba.
- Instalar herramientas para recopilar y grabar información:
  - Instale [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865) (o use una herramienta de seguimiento de red equivalente).
  - Instala la edición básica gratuita de [HTTPWatch](https://www.httpwatch.com/download/) (o usa una herramienta de seguimiento de red equivalente).
  - Use una grabadora de pantalla o ejecute la Grabadora de pasos (PSR.exe) que se incluye con Windows Vista y versiones posteriores, para mantener un registro de los pasos que realiza durante las pruebas.

### <a name="log-the-performance-issue"></a>Registrar el problema de rendimiento

- Cierre todos los exploradores de Internet que no son habituales.
- Inicie la Grabadora de pasos u otra grabadora de pantalla.
- Inicia la captura de Netmon (o herramienta de seguimiento de red).
- Borre la memoria caché DNS en el equipo cliente desde la línea de comandos escribiendo ipconfig /flushdns.
- Inicie una nueva sesión del explorador y active HTTPWatch.
- Opcional: si está probando Exchange Online, ejecute la herramienta Analizador de rendimiento de cliente de Exchange desde la consola de administración de Office 365.
- Reproduzca los pasos exactos que provocan el problema de rendimiento.
- Detenga el seguimiento de Netmon u otra herramienta.
- En la línea de comandos, ejecute una ruta de seguimiento a su suscripción de Office 365 escribiendo el siguiente comando y, a continuación, presionando ENTRAR:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Detenga la grabadora de pasos y guarde el vídeo. Asegúrese de incluir la fecha y la hora de la captura y si muestra un rendimiento bueno o mal rendimiento.
- Guarde los archivos de seguimiento. Una vez más, asegúrate de incluir la fecha y hora de la captura y si muestra un rendimiento bueno o un mal rendimiento.

Si no está familiarizado con la ejecución de las herramientas mencionadas en este artículo, no se preocupe porque le proporcionamos estos pasos a continuación. Si está acostumbrado a realizar este tipo de captura de red, puede ir directamente a Cómo recopilar líneas [base,](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines)que describe el filtrado y la lectura de los registros.

### <a name="flush-the-dns-cache-first"></a>Vaciar primero la caché DNS

¿Por qué? Al vaciar la memoria caché DNS, está iniciando las pruebas con una pizarra limpia. Al borrar la memoria caché, restablece el contenido de resolución DNS a las entradas más actualizadas. Recuerde que un vaciado no quita las entradas del archivo HOSTs. Si usa entradas de archivo HOST de forma extensiva, debe copiar esas entradas en un archivo de otro directorio y, a continuación, vaciar el archivo HOST.

#### <a name="flush-your-dns-resolver-cache"></a>Vaciar la memoria caché de resolución DNS

1. Abra el símbolo del sistema **(cmd iniciar** ejecución o cmd \>  \>  de clave **de Windows).** \> 
2. Escriba el siguiente comando y presione ENTRAR:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

La herramienta de supervisión de red de Microsoft[(Netmon)](https://www.microsoft.com/download/details.aspx?id=4865)analiza los paquetes, es decir, el tráfico, que pasa entre equipos en redes. Al usar Netmon para rastrear el tráfico con Office 365, puede capturar, ver y leer encabezados de paquetes, identificar dispositivos que intervienen, comprobar la configuración importante en el hardware de red, buscar paquetes perdidos y seguir el flujo de tráfico entre los equipos de la red corporativa y Office 365. Dado que el cuerpo real del tráfico está cifrado, es decir, (viaja en el puerto 443 a través de SSL/TLS, no se pueden leer los archivos que se envían. En su lugar, obtiene un seguimiento sin filtrar de la ruta que toma el paquete, lo que puede ayudarle a realizar un seguimiento del comportamiento del problema.

Asegúrese de no aplicar un filtro en este momento. En su lugar, ejecute los pasos y demuestre el problema antes de detener el seguimiento y guardar.

Después de instalar Netmon 3.4, abra la herramienta y siga estos pasos:

### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Realizar un seguimiento de Netmon y reproducir el problema

1. Inicie Netmon 3.4.
Hay tres paneles en  la página de inicio: **Capturas** **recientes,** Seleccionar redes y Introducción a **Microsoft Network Monitor 3.4. Tenga en cuenta** que . El panel Seleccionar redes también le dará una lista de las redes predeterminadas desde las que puede capturar. Asegúrese de que las tarjetas de red están seleccionadas aquí.

2. Haga **clic en Nueva** captura en la parte superior de la **página** De inicio. Esto agrega una nueva pestaña junto a la **pestaña Página** de inicio denominada **Captura 1**.
![Interfaz de usuario de Netmon con los botones Nueva captura, Inicio y Detener resaltados.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Para realizar una captura simple, haga clic **en Inicio en** la barra de herramientas.

4. Reproduzca los pasos que presentan un problema de rendimiento.

5. Haga **clic en Detener** \> **guardar** archivo \> **como**. Recuerde proporcionar la fecha y la hora con la zona horaria y mencionar si muestra un rendimiento bueno o mal rendimiento.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) viene cargado y una edición gratuita. La edición básica gratuita cubre todo lo que necesita para esta prueba. HTTPWatch supervisa el tráfico de red y el tiempo de carga de la página directamente desde la ventana del explorador. HTTPWatch es un complemento de Internet Explorer que describe gráficamente el rendimiento. El análisis se puede guardar y ver en HTTPWatch Studio.

> [!NOTE]
> Si usa otro explorador, como Firefox, Google Chrome o si no puede instalar HTTPWatch en Internet Explorer, abra una nueva ventana del explorador y presione F12 en el teclado. Debería ver la herramienta de desarrollo emergente en la parte inferior del explorador. Si usa Opera, presione CTRL+MAYÚS+I para Inspector  web y, a continuación, haga clic en la pestaña Red y complete las pruebas que se describen a continuación. La información será ligeramente diferente, pero los tiempos de carga se seguirán visualizando en milisegundos. > HTTPWatch también es muy útil para problemas con los tiempos de carga de la página de SharePoint Online.

### <a name="run-httpwatch-and-reproduce-the-issue"></a>Ejecutar HTTPWatch y reproducir el problema

HTTPWatch es un complemento de explorador, por lo que exponer la herramienta en el explorador es ligeramente diferente para cada versión de Internet Explorer. Normalmente, puedes encontrar HTTPWatch en la barra de comandos en el explorador Internet Explorer. Si no ve el complemento HTTPWatch en la ventana del explorador, compruebe  la versión del explorador haciendo clic en Ayuda o, en versiones posteriores de Internet Explorer, haga clic en el símbolo de engranaje e Información \> sobre **Internet Explorer.** Para iniciar la **barra comandos,** haga clic con el botón secundario en la barra de menús en Internet Explorer y haga clic en **la barra de comandos.**

En el pasado, HTTPWatch se ha asociado con las barras Comandos y Explorador, por lo que una vez instalado, si no ves inmediatamente el icono (incluso después del reinicio), comprueba Herramientas y las barras de herramientas para el icono. Recuerde que las barras de herramientas se pueden personalizar y se pueden agregar opciones a ellas.

![Barra de herramientas comandos de Internet Explorer con el icono HTTPWatch mostrado.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)

1. Inicia HTTPWatch en una ventana del explorador Internet Explorer. Aparecerá acoplado al explorador en la parte inferior de esa ventana. Haga clic **en Registro**.

2. Reproduzca los pasos exactos implicados en el problema de rendimiento. Haga clic **en el botón** Detener en HTTPWatch.

3. **Guarde** httpwatch o **enviar por correo electrónico**. Recuerde nombrar el archivo para que incluya información de fecha y hora, así como una indicación de si su watch contiene una demostración de un rendimiento bueno o un mal rendimiento.

![HTTPWatch que muestra la ficha de red para una carga de página de la página de inicio de Office 365.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Esta captura de pantalla es de la versión profesional de HTTPWatch. Puede abrir los seguimientos tomados en la versión básica en un equipo con una versión Profesional y leerlo allí. Es posible que haya información adicional disponible desde el seguimiento a través de ese método.

## <a name="problem-steps-recorder"></a>Grabadora de pasos del problema

Steps Recorder o PSR.exe, le permite registrar los problemas a medida que se producen. Es una herramienta muy útil y muy sencilla de ejecutar.

### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Ejecutar la Grabadora de pasos de problemas (PSR.exe) para grabar el trabajo

1. Use el **tipo iniciar** ejecuciónPSR.exeAceptar o haga clic en el tipo de tecla \>  \> de  \>  **Windows** \> **PSR.exe** \> presione ENTRAR.

2. Cuando aparezca la PSR.exe pequeña,  haga clic en Iniciar registro y reproduzca los pasos que reproducen el problema de rendimiento. Puede agregar comentarios según sea necesario haciendo clic **en Agregar comentarios.**

3. Haga **clic en Detener** registro cuando haya completado los pasos. Si el problema de rendimiento es una representación de página, espere a que la página se represente antes de detener la grabación.

4. Haga clic en **Guardar**.

![Captura de pantalla de la grabadora de pasos o PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)

La fecha y la hora se registran por usted. Esto vincula el PSR a su seguimiento de Netmon y HTTPWatch en el tiempo, y ayuda a solucionar problemas de precisión. La fecha y hora en el registro de PSR puede mostrar que transcurre un minuto entre el inicio de sesión y la exploración de la dirección URL y la representación parcial del sitio de administración, por ejemplo.

## <a name="read-your-traces"></a>Leer los seguimientos

No es posible enseñar todo acerca de la solución de problemas de red y rendimiento que alguien necesita saber a través de un artículo. Obtener un buen rendimiento requiere experiencia y conocimientos sobre cómo funciona la red y suele realizarse. Pero es posible redondear una lista de problemas principales y mostrar cómo las herramientas pueden facilitar la eliminación de los problemas más comunes.

Si desea obtener conocimientos de lectura de seguimientos de red para sus sitios de Office 365, no hay mejor profesor que crear seguimientos de cargas de página periódicamente y obtener experiencia en leerlos. Por ejemplo, cuando tenga la oportunidad, cargue un servicio de Office 365 y trace el proceso. Filtre el seguimiento del tráfico DNS o busque en FrameData el nombre del servicio que ha explorado. Analice el seguimiento para obtener una idea de los pasos que se producen cuando se carga el servicio. Esto le ayudará a saber qué aspecto debe tener la carga normal de la página y, en el caso de la solución de problemas, especialmente en relación con el rendimiento, comparar los seguimientos buenos con los errores puede enseñarte mucho.

Netmon usa Microsoft IntelliSense en el campo Filtro de visualización. IntelliSense, o finalización de código inteligente, es ese trucos en el que escribes en un período y todas las opciones disponibles se muestran en un cuadro de selección desplegable. Si, por ejemplo, te preocupa el escalado de ventanas TCP, puedes encontrar tu manera de acceder a un filtro (por  `.protocol.tcp.window < 100` ejemplo) por este medio.

![Captura de pantalla de Netmon que muestra que el campo Filtro de visualización usa IntelliSense.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)

Los seguimientos de Netmon pueden tener mucho tráfico en ellos. Si no tiene experiencia en leerlos, es probable que se sienta desbordado al abrir el seguimiento la primera vez. Lo primero que hay que hacer es separar la señal del ruido de fondo en el seguimiento. Ha probado con Office 365 y ese es el tráfico que quiere ver. Si estás acostumbrado a navegar por seguimientos, es posible que no necesites esta lista.

El tráfico entre el cliente y Office 365 viaja a través de TLS, lo que significa que el cuerpo del tráfico se cifrará y no podrá leerse en un seguimiento genérico de Netmon. El análisis de rendimiento no necesita conocer los detalles de la información del paquete. Sin embargo, está muy interesado en los encabezados de paquetes y la información que contienen.

### <a name="tips-to-get-a-good-trace"></a>Sugerencias para obtener un buen seguimiento

- Conozca el valor de la dirección IPv4 o IPv6 del equipo cliente. Para obtener esto en el símbolo del sistema, escriba **IPConfig** y, a continuación, presione ENTRAR. Conocer esta dirección le permitirá saber de un vistazo si el tráfico del seguimiento implica directamente al equipo cliente. Si hay un proxy conocido, haga ping y obtenga también su dirección IP.

- Vacíe la memoria caché de resolución DNS y, si es posible, cierre todos los exploradores excepto el que está ejecutando las pruebas. Si no puede hacerlo, por ejemplo, si el soporte técnico usa alguna herramienta basada en explorador para ver el escritorio del equipo cliente, esté preparado para filtrar el seguimiento.

- En un seguimiento de disponibilidad, busque el servicio de Office 365 que está usando. Si nunca ha visto o rara vez el tráfico antes, este es un paso útil para separar el problema de rendimiento de otro ruido de red. Hay varias formas de hacerlo. Directamente antes de la prueba, puede usar _ping_ o _PsPing_ en la dirección URL del servicio específico ( `ping outlook.office365.com` `psping -4 microsoft-my.sharepoint.com:443` o, por ejemplo). También puede encontrar fácilmente ese ping o PsPing en un seguimiento de Netmon (por su nombre de proceso). Eso le dará un lugar donde empezar a buscar.

Si solo usas el seguimiento de Netmon en el momento del problema, eso también está bien. Para orientarse, use un filtro como `ContainsBin(FrameData, ASCII, "office")` `ContainsBin(FrameData, ASCII, "outlook")` o . Puede grabar el número de fotograma desde el archivo de seguimiento. Es posible que también desee desplazar el _panel_ Resumen de marco hacia la derecha y buscar la columna Id. de conversación. There is a number indicated there for the ID of this specific conversation that you can also record and look at in isolation later. Recuerde quitar este filtro antes de aplicar cualquier otro filtrado.

> [!TIP]
> Netmon tiene una gran cantidad de filtros integrados útiles. Pruebe el **botón Cargar** filtro en la parte superior del _panel de_ filtro de visualización.

![Busque su IP mediante PSPing en la línea de comandos del equipo cliente.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)

![Netmon trace from the client showing the same PSPing command through the filter TCP. Flags.Syn == 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)

Familiarícese con el tráfico y obtenga información sobre cómo encontrar la información que necesita. Por ejemplo, aprenda a determinar qué paquete del seguimiento tiene la primera referencia al servicio de Office 365 que está usando (como "Outlook").

Tomando Como ejemplo Office 365 Outlook Online, el tráfico comienza de la siguiente forma:

- Consulta estándar DNS y respuesta DNS para outlook.office365.com con queryIDs que coincidan. Es importante tener en cuenta el desplazamiento de tiempo para este cambio, así como dónde en el mundo el DNS global de Office 365 envía la solicitud de resolución de nombres. Idealmente, lo más localmente posible, en lugar de medio mundo.

- Una solicitud HTTP GET cuyo informe de estado se movió permanentemente (301)

- Tráfico RWS, incluidas las solicitudes RWS Connect y las respuestas Connect. (Se trata de Winsock remoto realizando una conexión por ti).

- Una conversación TCP SYN y TCP SYN/ACK. Muchas de las opciones de configuración de esta conversación afectan al rendimiento.

- A continuación, una serie de tráfico TLS:TLS que es donde tienen lugar las conversaciones de protocolo de enlace TLS y certificado TLS. (Recuerde que los datos se cifran a través de SSL/TLS).

Todas las partes del tráfico son importantes y conectadas, pero pequeñas partes del seguimiento contienen información especialmente importante en términos de solución de problemas de rendimiento, por lo que nos centraremos en esas áreas. Además, como hemos realizado suficiente solución de problemas de rendimiento de Office 365 en Microsoft para compilar una lista de los diez primeros problemas comunes, nos centraremos en esos problemas y en cómo usar las herramientas que tenemos para solucionarlos a continuación.

Si no los has instalado todos listos, la siguiente matriz usa varias herramientas. Siempre que sea posible. Se proporcionan vínculos a los puntos de instalación. La lista incluye herramientas comunes de seguimiento de red como [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) y [Wireshark,](https://www.wireshark.org/)pero usa cualquier herramienta de seguimiento con la que estés cómodo y en la que estés acostumbrado a filtrar el tráfico de red. Cuando esté probando, recuerde:

- *Cierre los exploradores y pruebe solo con*  un explorador en ejecución, lo que reducirá el tráfico general que capture. Hace que el seguimiento sea menos ocupado.
- *Vaciar la memoria caché de resolución DNS*  en el equipo cliente: esto le dará una pizarra limpia cuando empiece a realizar la captura, para un seguimiento más limpio.

## <a name="common-issues"></a>Problemas comunes

Algunos problemas comunes a los que puedes enfrentarte y cómo encontrarlos en el seguimiento de red.

### <a name="tcp-windows-scaling"></a>Escala de Windows TCP

Se encuentra en SYN - SYN/ACK. Es posible que el hardware heredado o antiguo no aproveche el escalado de ventanas TCP.  Sin una configuración correcta de escalado de ventanas TCP, el búfer predeterminado de 16 bits en encabezados TCP se llena en milisegundos.  El tráfico no puede seguir enviándose hasta que el cliente reciba un acuse de recibo de que se han recibido los datos originales, lo que provoca retrasos.

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

Busque el tráfico SYN - SYN/ACK en el seguimiento de red.  En Netmon, use un filtro como  `tcp.flags.syn == 1` . Este filtro es el mismo en Wireshark.

![Filtra en Netmon o Wireshark por paquetes Syn para ambas herramientas: TCP. Flags.Syn == 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Observe que para cada SYN hay un número de puerto de origen (SrcPort) que coincide con el puerto de destino (DstPort) del acuse de recibo relacionado (SYN/ACK).

Para ver el valor de Escala de Windows que usa la conexión de red, expanda primero SYN y, a continuación, el SYN/ACK relacionado.

![Gráfico que muestra cómo hacer coincidir SrcPort con DstPort en un seguimiento, para obtener la diferencia de tiempo.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)

### <a name="tcp-idle-time-settings"></a>Configuración de tiempo de inactividad TCP

Históricamente, la mayoría de las redes perimetrales están configuradas para conexiones transitorias, lo que significa que las conexiones inactivas generalmente finalizan. Los servidores proxy y firewalls pueden finalizar las sesiones TCP inactivas en un tiempo superior a 100 a 300 segundos. Esto es problemático para Outlook Online porque crea y usa conexiones a largo plazo, independientemente de si están inactivas o no.

Cuando los dispositivos proxy o firewall finalizan las conexiones, no se informa al cliente y un intento de usar Outlook Online significará que un equipo cliente intentará, repetidamente, reactivar la conexión antes de realizar una nueva. Es posible que veas problemas en el producto, avisos o rendimiento lento en la carga de la página.

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

En Netmon, vea el campo Desplazamiento de tiempo para un viaje de ida y vuelta. Un viaje de ida y vuelta es el tiempo entre el cliente que envía una solicitud al servidor y recibe una respuesta. Comprobar entre el cliente y el punto de salida (por ejemplo, Cliente -- \> Proxy) o el cliente a Office 365 (cliente -- \> Office 365). Puede verlo en muchos tipos de paquetes.

Por ejemplo, el filtro de Netmon puede tener el aspecto  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` de , o, en Wireshark,  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .

> [!TIP]
> ¿No sabe si la dirección IP del seguimiento pertenece al servidor DNS? Intente buscarla en la línea de comandos. Haga **clic en** Iniciar \> **ejecución** y escriba \> **cmd,** o presione **la tecla Windows** y escriba \> **cmd**. En el símbolo del sistema, escriba  `nslookup <the IP address from the network trace>` . Para realizar pruebas, use nslookup en la dirección IP de su propio equipo. > Para ver una lista de los intervalos IP de Microsoft, vea direcciones URL e intervalos de direcciones [IP de Office 365.](https://technet.microsoft.com/library/hh373144.aspx)

Si hay un problema, espere que aparezcan desplazamientos de tiempo largos, en este caso (Outlook Online), especialmente en paquetes TLS:TLS que muestran el paso de los datos de la aplicación (por ejemplo, en Netmon puede encontrar paquetes de datos de aplicación a través  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` de ). Debería ver un progreso suave en el tiempo que atraviesa la sesión. Si ve retrasos largos al actualizar Outlook Online, esto podría deberse a un alto grado de restablecimientos que se envían.

### <a name="latencyround-trip-time"></a>Tiempo de latencia/recorrido de ida y vuelta

La latencia es una medida que puede cambiar mucho en función de muchas variables, como la actualización de dispositivos de vencimiento, la adición de un gran número de usuarios a una red y el porcentaje de ancho de banda total consumido por otras tareas en una conexión de red.

Hay calculadoras de ancho de banda para Office 365 disponibles en esta página de planeación de red y ajuste del rendimiento [para Office 365.](network-planning-and-performance.md)

¿Necesita medir la velocidad de la conexión o el ancho de banda de la conexión isp? Pruebe este sitio (o sitios como este): Sitio oficial de [Speedtest](https://www.speedtest.net/)o consulte su motor de búsqueda favorito para la prueba de velocidad **de frases.**

#### <a name="tools"></a>Herramientas

- Ping
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

Para realizar un seguimiento de la latencia en un seguimiento, se beneficiará de haber registrado la dirección IP del equipo cliente y la dirección IP del servidor DNS en Office 365. Esto se hace con el fin de facilitar el filtrado de seguimiento. Si se conecta a través de un proxy, necesitará la dirección IP del equipo cliente, la dirección IP de proxy/salida y la dirección IP DNS de Office 365 para facilitar el trabajo.

Una solicitud de ping enviada a outlook.office365.com le mostrará el nombre del centro de datos que recibe la solicitud, incluso si  *es*  posible que ping no pueda conectarse para enviar los paquetes ICMP consecutivos de marca comercial. Si usa PsPing (una herramienta gratuita para descargar) y especifica el puerto (443) y quizás para usar IPv4 (-4), recibirá un tiempo medio de ida y vuelta para los paquetes enviados. Esto funcionará para otras direcciones URL de los servicios de Office 365, como `psping -4 yourSite.sharepoint.com:443` . De hecho, puede especificar una serie de pings para obtener una muestra más grande para su promedio, pruebe algo como `psping -4 -n 20 yourSite-my.sharepoint.com:443` .

> [!NOTE]
> PsPing no envía paquetes ICMP. Hace ping con paquetes TCP a través de un puerto específico, por lo que puede usar cualquiera que sepa que está abierto. En Office 365, que usa SSL/TLS, pruebe a adjuntar el puerto :443 a su PsPing.

![Captura de pantalla que muestra un ping que resuelve outlook.office365.com y un PSPing con el 443 haciendo lo mismo, pero también informando de un rtt promedio de 6,5 ms.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Si cargó la página de Office 365 con un rendimiento lento mientras realizaba un seguimiento de red, debe filtrar un seguimiento de Netmon o Wireshark por `DNS` . Esta es una de las IP que buscamos.

Estos son los pasos a seguir para filtrar netmon para obtener la dirección IP (y echar un vistazo a la latencia de DNS). Este ejemplo usa outlook.office365.com, pero también puede usar la dirección URL de un inquilino de SharePoint Online (hithere.sharepoint.com por ejemplo).

1. Haga ping a la dirección URL y, en los resultados, registre el nombre y la dirección IP del servidor DNS al que se `ping outlook.office365.com` envió la solicitud de ping.
2. Seguimiento de red abriendo la página, realizando la acción que le da el problema de rendimiento o, si ve una latencia alta en el ping, en sí mismo, el seguimiento de red.
3. Abra el seguimiento en Netmon y filtre por DNS (este filtro también funciona en Wireshark, pero distingue mayúsculas de `-- dns` minúsculas). Dado que conoce el nombre del servidor DNS de su ping, también puede filtrar más rápidamente en Netmon de la siguiente manera: , que tiene este aspecto en el dns de Wireshark y el marco contiene `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` "namnorthwest".<br/>Abra el paquete de respuesta y, en la ventana Detalles de marco de **Netmon,** haga clic en **DNS** para expandirse para obtener más información. En la información de DNS encontrará la dirección IP del servidor DNS al que se hizo la solicitud en Office 365. Necesitará esta dirección IP para el siguiente paso (la herramienta PsPing). Quite el filtro, haga clic con el botón secundario en la respuesta DNS en Netmon \>  \> **(DNS** de búsqueda de conversaciones de resumen de marco) para ver la consulta DNS y la respuesta en paralelo.
4. En Netmon, también tenga en cuenta la columna Desfaso de tiempo entre la solicitud y la respuesta de DNS. En el siguiente paso, la herramienta [PsPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) fácil de instalar y usar resulta muy útil, tanto porque ICMP suele bloquearse en firewalls como porque PsPing realiza un seguimiento elegante de la latencia en milisegundos. PsPing completa una conexión TCP a una dirección y un puerto (en nuestro caso, abre el puerto 443).
5. Instale PsPing.
6. Abra un símbolo del sistema (cmd de tipo Iniciar ejecución o tipo de clave de Windows cmd) y cambie el directorio al directorio donde instaló PsPing para ejecutar el \> \> comando \> PsPing. En mis ejemplos, puede ver que he hecho una carpeta "Perf" en la raíz de C. Puede hacer lo mismo para obtener acceso rápido.
7. Escriba el comando para que el psping se haga en la dirección IP del servidor DNS de Office 365 desde el seguimiento de Netmon anterior, incluido el número de puerto, como `psping -n 20 132.245.24.82:445` . Esto le dará un muestreo de 20 pings y el promedio de la latencia cuando se detenga PsPing.

Si va a Office 365 a través de un servidor proxy, los pasos son un poco diferentes. Primero, psping a su servidor proxy para obtener un valor de latencia promedio en milisegundos para proxy/salida y atrás y, a continuación, ejecutar PsPing en el proxy, o en un equipo con una conexión directa a Internet para obtener el valor que falta (el de Office 365 y de vuelta).

Si decide ejecutar PsPing desde el proxy, tendrá dos valores en milisegundos: equipo cliente a servidor proxy o punto de salida y servidor proxy a Office 365. Y ya has terminado. Bueno, grabando valores, de todos modos.

Si ejecuta PsPing en otro equipo cliente que tenga una conexión directa a Internet, es decir, sin un proxy, tendrá valores de dos milisegundos: equipo cliente a servidor proxy o punto de salida y equipo cliente a Office 365. En este caso, resta el valor del equipo cliente al servidor proxy o al punto de salida del valor del equipo cliente a Office 365, y tendrá los números RTT del equipo cliente al servidor proxy o al punto de salida, y del servidor proxy o el punto de salida a Office 365.

Sin embargo, si puede encontrar un equipo cliente en la ubicación afectada que está conectado directamente o omite el proxy, puede elegir ver si el problema se reproduce ahí para empezar y probar su uso a partir de entonces.

La latencia, como se ve en un seguimiento de Netmon, esos milisegundos adicionales pueden sumar, si hay suficientes en una sesión determinada.

![Latencia general de Netmon, con la columna de diferencia de tiempo predeterminada de Netmon agregada al Resumen de marco.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Su dirección IP puede ser diferente de las DIRECCIONES IP que se muestran aquí, por ejemplo, el ping puede devolver algo más parecido a 157.56.0.0/16 o un intervalo similar. Para obtener una lista de los intervalos usados por Office 365, consulte las direcciones URL de [Office 365](https://technet.microsoft.com/library/hh373144.aspx)y los intervalos de direcciones IP.

Recuerde expandir todos los nodos (hay un botón en la parte superior para esto) si desea buscar, por ejemplo, 132.245.

### <a name="proxy-authentication"></a>Autenticación de proxy

Esto solo se aplica a ti si estás pasando por un servidor proxy. Si no es así, puede omitir estos pasos. Cuando funciona correctamente, la autenticación proxy debe realizarse en milisegundos, de forma coherente. No debería ver un mal rendimiento intermitente durante los períodos de uso máximo (por ejemplo).

Si la autenticación de proxy está activa, cada vez que realice una nueva conexión TCP a Office 365 para obtener información, debe pasar por un proceso de autenticación en segundo plano. Por lo tanto, por ejemplo, al cambiar de calendario a correo en Outlook Online, se autenticará. Y en SharePoint Online, si una página muestra medios o datos de varios sitios o ubicaciones, se autenticará para cada conexión TCP diferente necesaria para representar los datos.

En Outlook Online, puede experimentar tiempos de carga lentos siempre que cambie entre el calendario y el buzón de correo, o cargas de página lentas en SharePoint Online. Sin embargo, hay otros síntomas no enumerados aquí.

La autenticación de proxy es una configuración del servidor proxy de salida. Si está causando un problema de rendimiento con Office 365, debe consultar a su equipo de red.

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

La autenticación de proxy tiene lugar siempre que se debe spun up una nueva sesión TCP, normalmente para solicitar archivos o información del servidor, o para proporcionar información. Por ejemplo, puede que vea la autenticación proxy en torno a las solicitudes HTTP GET o HTTP POST. Si desea ver los marcos donde va a autenticar las solicitudes en el seguimiento, agregue la columna "Resumen NTLMSSP" a Netmon y filtre por  `.property.NTLMSSPSummary` . Para ver cuánto tiempo tarda la autenticación, agregue la columna Delta de tiempo.

Para agregar una columna a Netmon:

1. Haga clic con el botón secundario en una columna como **Descripción.**
2. Haga clic **en Elegir columnas.**
3. Busque _resumen NTLMSSP y_ delta _de_ tiempo en la lista y haga clic en **Agregar**.
4. Mueva las nuevas columnas antes  o detrás de la columna Descripción para poder leerlas en paralelo.
5. Haga clic en **Aceptar**.

Incluso si no agrega la columna, el filtro Netmon funcionará. Pero la solución de problemas será mucho más sencilla si puede ver en qué fase de autenticación se encuentra.

Cuando busque instancias de autenticación de proxy, asegúrese de estudiar todos los fotogramas en los que haya un desafío NTLM o un mensaje de autenticación presente. Si es necesario, haga clic con el botón secundario en la parte específica del tráfico y Busque \> conversaciones TCP. Tenga en cuenta los valores de Delta de tiempo en estas conversaciones.

![Seguimiento de Netmon que muestra la autenticación proxy, filtrada por conversación.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Un retraso de cuatro segundos en la autenticación proxy como se ve en Wireshark. La **diferencia de tiempo de la** columna de marco mostrada anteriormente se realizó haciendo clic con el botón secundario en el campo con el mismo nombre en los detalles del marco y seleccionando Agregar como columna.  <br/> ![En Wireshark, la columna "Diferencia de tiempo del marco mostrado anterior" se puede realizar haciendo clic con el botón secundario en el campo del mismo nombre en los detalles del marco y seleccionando Agregar como columna.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>Rendimiento de DNS

La resolución de nombres funciona mejor y más rápidamente cuando tiene lugar lo más cerca posible del país del cliente.

Si se está llevando a cabo la resolución de nombres DNS, puede agregar segundos a las cargas de página. Lo ideal es que la resolución de nombres se produce en menos de 100 ms. Si no es así, debe realizar más investigaciones.

> [!TIP]
> ¿No está seguro de cómo funciona la conectividad de clientes en Office 365? Echa un vistazo aquí al documento de referencia de conectividad de [cliente.](https://technet.microsoft.com/library/dn741250.aspx)

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Qué buscar

El análisis del rendimiento de DNS suele ser otro trabajo para un seguimiento de red. Sin embargo, PsPing también es útil para provocar o descartar una posible causa.

El tráfico DNS se basa en solicitudes TCP y UDP y las respuestas se marcan claramente con un identificador que ayudará a hacer coincidir una solicitud específica con su respuesta específica. Verá el tráfico DNS cuando, por ejemplo, SharePoint Online usa un nombre de red o una dirección URL en una página web. Como regla general, la mayor parte de este tráfico, excepto al transferir zonas, se ejecuta a través de UDP.

En Netmon y Wireshark, el filtro más básico que le permitirá ver el tráfico DNS es simplemente `dns` . Asegúrese de usar minúsculas al especificar el filtro. Recuerde vaciar la memoria caché de resolución DNS antes de empezar a reproducir el problema en el equipo cliente. Por ejemplo, si tiene una carga lenta de la página de SharePoint Online para la página principal, debe cerrar todos los exploradores, abrir un nuevo explorador, iniciar el seguimiento, vaciar la memoria caché de resolución dns y navegar al sitio de SharePoint Online. Una vez que se resuelve toda la página, debe detener y guardar el seguimiento.

![Un filtro básico para DNS en Netmon es DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Aquí desea ver el desplazamiento de tiempo. Y puede resultar útil agregar la columna **Delta** de tiempo a Netmon, lo que puede hacer si realiza estos pasos:

1. Haga clic con el botón secundario en una columna como **Descripción.**
2. Haga clic **en Elegir columnas.**
3. Busque _Delta de tiempo_ en la lista y haga clic en **Agregar**.
4. Mueva la nueva columna antes  o detrás de la columna Descripción para poder leerlas en paralelo.
5. Haga clic en **Aceptar**.

Si encuentra una consulta de interés, considere la posibilidad de aislarla haciendo clic con el botón secundario en esa consulta en el panel de detalles del marco, eligiendo **Buscar** \> **conversaciones DNS**. Observe que el panel Conversaciones de red salta directamente a la conversación específica en su registro de tráfico UDP.

![Un seguimiento netmon de la carga de Outlook Online filtrada por DNS y, a continuación, usando Buscar conversaciones, DNS para restringir los resultados.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

En Wireshark puede crear una columna para la hora DNS. Tome el seguimiento (o abra un seguimiento) en Wireshark y filtre por `dns` , o, de forma más útil,  `dns.time` . Haga clic en cualquier consulta DNS y, en el panel que muestra los detalles, expanda los  `Domain Name System (response)` detalles. Verá un campo para el tiempo (por ejemplo, `[Time: 0.001111100 seconds]` . Haga clic con el botón secundario en esta hora y **seleccione Aplicar como columna**. Esto le dará una **columna Hora** para ordenar más rápidamente el seguimiento. Haga clic en la nueva columna para ordenar por valores descendentes para ver qué llamada DNS tardó más en resolverse.

[Una exploración de SharePoint Online filtrada en Wireshark por dns.time (minúscula), con el tiempo de los detalles convertido en columna y ordenado de forma ascendente.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Si desea realizar más investigaciones del tiempo de resolución DNS, pruebe un PsPing con el puerto DNS usado por TCP (por ejemplo,  `psping <IP address of DNS server>:53` ). ¿Sigues teniendo problemas de rendimiento? Si lo hace, es más probable que el problema sea un problema de red más amplio que un problema específico de la aplicación DNS con la que está trabajando para solucionarlo. También vale la pena mencionar, de nuevo, que un ping a outlook.office365.com le dirá dónde se está llevando a cabo la resolución de nombres DNS para Outlook Online (por ejemplo, outlook-namnorthwest.office365.com).

Si el problema parece ser específico de DNS, puede que sea necesario ponerse en contacto con su departamento de TI para ver las configuraciones dns y los reenviadores de DNS para investigar aún más este problema.

### <a name="proxy-scalability"></a>Escalabilidad de proxy

Servicios como Outlook Online en Office 365 conceden a los clientes varias conexiones a largo plazo. Por lo tanto, cada usuario puede usar más conexiones que requieran una vida más larga.

#### <a name="tools"></a>Herramientas

Matemáticas

#### <a name="what-to-look-for"></a>Qué buscar

No hay ninguna herramienta de seguimiento de red o solución de problemas específica para esto. En su lugar, se basa en cálculos de ancho de banda dados limitaciones y otras variables.

### <a name="tcp-max-segment-size"></a>Tamaño máximo de segmento TCP

Se encuentra en SYN - SYN/ACK.  Realice esta comprobación en cualquier seguimiento de red de rendimiento que haya realizado para asegurarse de que los paquetes TCP están configurados para transportar la máxima cantidad de datos posible.

El objetivo es ver un MSS de 1460 bytes para la transmisión de datos. Si está detrás de un proxy o está usando una NAT, recuerde ejecutar esta prueba de cliente a proxy/salida/NAT, y de proxy/salida/NAT a Office 365 para obtener mejores resultados. Se trata de diferentes sesiones TCP.

#### <a name="tools"></a>Herramientas

Netmon

#### <a name="what-to-look-for"></a>Qué buscar

Tcp Max Segment Size (MSS) es otro parámetro del protocolo de enlace triple en el seguimiento de red, lo que significa que encontrará los datos que necesita en el paquete SYN - SYN/ACK. MSS es realmente bastante sencillo de ver.

Abra cualquier seguimiento de red de rendimiento que tenga y encuentre la conexión que le interesa, o que demuestra el problema de rendimiento.

> [!NOTE]
> Si está buscando un seguimiento y necesita encontrar el tráfico relevante para su conversación, filtre por la DIRECCIÓN IP del cliente, la DIRECCIÓN IP del servidor proxy o el punto de salida, o ambos. Si va directamente, tendrá que hacer ping a la dirección URL que está probando para la dirección IP de Office 365 en el seguimiento y filtrar por ella.

¿Observa el seguimiento de segunda mano? Intente usar filtros para orientarse. En Netmon, ejecute una búsqueda basada en la dirección URL, como `Containsbin(framedata, ascii, "sphybridExample")` , tome nota del número de fotograma.

En Wireshark, use algo como  `frame contains "sphybridExample"` . Si observa que ha encontrado tráfico de Winsock remoto (RWS) (puede aparecer como un [PSH, ACK] en Wireshark), recuerde que las conexiones RWS se pueden ver poco antes de syn - SYN/ACKs relevantes, como se explicó anteriormente.

En este punto, puede grabar el número de  fotograma, colocar el filtro, hacer clic en Todo el tráfico en la ventana Conversaciones de red de Netmon para ver el SYN más cercano.

Es importante destacar que si no recibió ninguna información de la dirección IP en el momento del seguimiento, buscar la dirección URL en el seguimiento (parte de , por ejemplo), le dará direcciones IP por las que `sphybridExample-my.sharepoint.com` filtrar.

Busque la conexión en el seguimiento que le interesa ver. Para ello, puede examinar el seguimiento, filtrar por direcciones IP o seleccionar determinados IDs de conversación mediante la ventana Conversaciones de red de Netmon. Una vez que haya encontrado el paquete SYN, expanda TCP (en Netmon) o protocolo de control de transmisión (en Wireshark) en el panel Detalles del marco. Expanda Opciones TCP y MaxSegmentSize. Busque el marco SYN-ACK relacionado y expanda las opciones TCP y MaxSegmentSize. El menor de los dos valores será el tamaño máximo del segmento. En esta imagen, uso la columna integrada en Netmon denominada Solución de problemas TCP.

![Seguimiento de red filtrado en Netmon mediante las columnas integradas.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

La columna integrada se encuentra en la parte superior del panel Detalles **del** marco. (Para volver a la vista normal, haga clic de nuevo en **Columnas** y, a continuación, elija **Zona horaria).**

![Dónde encontrar la lista de columnas desplegable para la opción de Solucionar problemas de TCP (arriba del Resumen de marco).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Este es un seguimiento filtrado en Wireshark. Hay un filtro específico para el valor de MSS ( `tcp.options.mss` ). Los fotogramas de un protocolo de enlace SYN, SYN/ACK y ACK están vinculados en la parte inferior del wireshark equivalente a detalles de fotograma (por lo tanto, marco 47 ACK, vínculos a 46 SYN/ACK, vínculos a 43 SYN) para facilitar este tipo de trabajo.

![Seguimiento filtrado en Wireshark por tcp.options.mss para tamaño máximo de segmento (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Si necesita comprobar la confirmación **selectiva** (tema siguiente de esta matriz), no cierre el seguimiento.

### <a name="selective-acknowledgment"></a>Confirmación selectiva

Se encuentra en SYN - SYN/ACK. Debe estar notificado como permitido en SYN y SYN/ACK. El acuse de recibo selectivo (OFS) permite una retransmisión de datos más fluida cuando falta un paquete o paquetes. Los dispositivos pueden deshabilitar esta característica, lo que puede provocar problemas de rendimiento.

Si está detrás de un proxy o está usando una NAT, recuerde ejecutar esta prueba de cliente a proxy/salida/NAT, y de proxy/salida/NAT a Office 365 para obtener mejores resultados. Se trata de diferentes sesiones TCP.

#### <a name="tools"></a>Herramientas

Netmon

#### <a name="what-to-look-for"></a>Qué buscar

El acuse de recibo selectivo (DESL) es otro parámetro del protocolo de enlace SYN-SYN/ACK. Puede filtrar el seguimiento por SYN - SYN/ACK de muchas maneras.

Busque la conexión en el seguimiento que le interesa ver mediante el examen del seguimiento, el filtrado por direcciones IP o haciendo clic en un identificador de conversación mediante la ventana Conversaciones de red en Netmon. Una vez que haya encontrado el paquete SYN, expanda TCP en Netmon o protocolo de control de transmisión en Wireshark en la sección Detalles del marco. Expanda Opciones TCP y, a continuación, DESA. Busque el marco SYN-ACK relacionado y expanda las opciones TCP y su campo DESENLAZ. Asegúrese de que se permite realizar certains DESESP tanto en SYN como en SYN/ACK. Estos son los valores DESPROTEM como se ve en Netmon y Wireshark.

![Confirmación selectiva (DESPROTEGA) en Netmon como resultado de tcp.flags.syn == 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![BOLSA tal y como aparece en Wireshark con el filtro tcp.flags.syn == 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>Geolocalización DNS

Donde en el mundo Office 365 intenta resolver la llamada DNS afecta a la velocidad de conexión.

En Outlook Online, una vez completada la primera búsqueda dns, se usará la ubicación de ese DNS para conectarse al centro de datos más cercano. Se conectará a un servidor CAS de Outlook Online, que usará la red troncal para conectarse al centro de datos (dC) donde se almacenan los datos. Esto es más rápido.

Al obtener acceso a SharePoint Online, se dirigirá a un usuario que viaja a su centro de datos activo, es decir, al DC cuya ubicación se basa en la base de inicio de su espacio empresarial de SPO (por lo tanto, un dC en Estados Unidos si el usuario está basado en EE. UU.).

Lync Online tiene nodos activos en más de un dC a la vez. Cuando se envían solicitudes para instancias de Lync Online, el DNS de Microsoft determinará de dónde viene la solicitud en el mundo y devolverá direcciones IP del DC regional más cercano donde Lync Online está activo.

> [!TIP]
> ¿Necesita saber más sobre cómo se conectan los clientes a Office 365? Echa un vistazo al artículo de referencia [de conectividad](https://technet.microsoft.com/library/dn741250.aspx) de cliente (y sus gráficos útiles).

#### <a name="tools"></a>Herramientas

- Ping
- PsPing

#### <a name="what-to-look-for"></a>Qué buscar

Las solicitudes de resolución de nombres desde los servidores DNS del cliente a los servidores DNS de Microsoft deberían, en la mayoría de los casos, hacer que DNS de Microsoft devuelva la dirección IP de un centro de datos regional (dC). ¿Qué significa esto para usted? Si su sede se encuentra en Bengalre, India, pero está de viaje en Los Estados Unidos, cuando el explorador realiza una solicitud para Outlook Online, los servidores DNS de Microsoft deben entregar direcciones IP a centros de datos de Estados Unidos, un centro de datos regional. Si se necesita correo de Outlook, los datos se desplazarán a través de la red troncal rápida de Microsoft entre los centros de datos.

DNS funciona más rápido cuando la resolución de nombres se realiza lo más cerca posible de la ubicación del usuario. Si está en Europa, quiere ir a un DNS de Microsoft en Europa y (idealmente) tratar con un centro de datos en Europa. El rendimiento de un cliente en Europa que va a DNS y un centro de datos en Estados Unidos será más lento.

Ejecute la herramienta Ping en outlook.office365.com para determinar dónde se enruta su solicitud DNS en el mundo. Si está en Europa, debería ver una respuesta de algo como outlook-emeawest.office365.com. En América, espere algo como outlook-namnorthwest.office365.com.

Abra el símbolo del sistema en el equipo cliente (a través de Cmd ejecutar inicio o cmd \> de tipo de clave de \> \> Windows). Escriba ping outlook.office365.com y presione ENTRAR. Recuerde que debe especificar -4 si desea especificar que se haga ping a través de IPv4. Es posible que no obtenga una respuesta de los paquetes ICMP, pero debería ver el nombre del DNS al que se enrutó la solicitud. Si desea ver los números de latencia de esta conexión, pruebe psping a la dirección IP del servidor que devuelve el ping.

![Ping de outlook.office365.com que muestra la resolución en outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PsPing to the IP address returned by the ping to outlook.office365.com showing average 28 millisecond latency.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Solución de problemas de aplicaciones de Office 365

#### <a name="tools"></a>Herramientas

- Netmon
- HTTPWatch
- Consola F12 en el explorador

No tratamos las herramientas usadas en la solución de problemas específicas de la aplicación en este artículo específico de la red. Pero encontrará recursos que puede *usar* [en esta página.](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848)

## <a name="related-topics"></a>Temas relacionados

[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
