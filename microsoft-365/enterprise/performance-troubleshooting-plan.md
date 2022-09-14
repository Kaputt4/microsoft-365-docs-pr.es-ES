---
title: Plan de solución de problemas de rendimiento para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 5/10/2019
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
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
description: Este artículo puede ayudarle a solucionar Office 365 problemas de rendimiento e incluso corregir algunos de los problemas más comunes.
ms.openlocfilehash: f60f9964753e7974121d1a7b3951352fedd2bf5f
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67672829"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Plan de solución de problemas de rendimiento para Office 365

¿Necesita conocer los pasos que debe seguir para identificar y corregir retrasos, bloqueos y rendimiento lento entre SharePoint Online, OneDrive para la Empresa, Exchange Online o Skype Empresarial Online y el equipo cliente? Antes de llamar al soporte técnico, este artículo puede ayudarle a solucionar problemas de rendimiento Office 365 e incluso corregir algunos de los problemas más comunes.

En realidad, este artículo es un plan de acción de ejemplo que puede usar para capturar datos valiosos sobre el problema de rendimiento a medida que sucede. En este artículo también se incluyen algunos de los principales problemas.

Si no está familiarizado con el rendimiento de la red y desea realizar un plan a largo plazo para supervisar el rendimiento entre las máquinas cliente y Office 365, eche un vistazo a [Office 365 optimización del rendimiento y solución de problemas: Administración y Profesionales de TI](performance-tuning-using-baselines-and-history.md).

## <a name="sample-performance-troubleshooting-action-plan"></a>Ejemplo de plan de acción de solución de problemas de rendimiento

Este plan de acción contiene dos partes; una fase de preparación y una fase de registro. Si tiene un problema de rendimiento en este momento y necesita realizar la recopilación de datos, puede empezar a usar este plan de inmediato.

### <a name="prepare-the-client-computer"></a>Preparación del equipo cliente

- Busque un equipo cliente que pueda reproducir el problema de rendimiento. Este equipo se usará durante la solución de problemas.
- Anote los pasos que hacen que se produzca el problema de rendimiento para que esté listo cuando llegue el momento de realizar la prueba.
- Instale herramientas para recopilar y grabar información:
  - Instale [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865) (o use una herramienta de seguimiento de red equivalente).
  - Instale la edición básica gratuita de [HTTPWatch](https://www.httpwatch.com/download/) (o use una herramienta de seguimiento de red equivalente).
  - Usa una grabadora de pantalla o ejecuta la Grabadora de pasos (PSR.exe) que viene con Windows Vista y versiones posteriores, con el fin de mantener un registro de los pasos que realizas durante las pruebas.

### <a name="log-the-performance-issue"></a>Registro del problema de rendimiento

- Cierre todos los exploradores de Internet extraños.
- Inicie la Grabadora de pasos u otra grabadora de pantalla.
- Inicie la captura de Netmon (o herramienta de seguimiento de red).
- Borre la caché DNS en el equipo cliente de la línea de comandos escribiendo ipconfig /flushdns.
- Inicie una nueva sesión del explorador y active HTTPWatch.
- Opcional: si va a probar Exchange Online, ejecute la herramienta de Analizador de rendimiento cliente de Exchange desde la consola de administración de Office 365.
- Reproduzca los pasos exactos que provocan el problema de rendimiento.
- Detenga el seguimiento de Netmon u otra herramienta.
- En la línea de comandos, ejecute una ruta de seguimiento a la suscripción de Office 365 escribiendo el comando siguiente y, a continuación, presione ENTRAR:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Detenga la Grabadora de pasos y guarde el vídeo. Asegúrese de incluir la fecha y hora de la captura y si muestra un rendimiento bueno o incorrecto.
- Guarde los archivos de seguimiento. De nuevo, asegúrese de incluir la fecha y hora de la captura y si muestra un rendimiento bueno o incorrecto.

Si no está familiarizado con la ejecución de las herramientas mencionadas en este artículo, no se preocupe porque proporcionamos estos pasos a continuación. Si está acostumbrado a realizar este tipo de captura de red, puede ir directamente a [Cómo recopilar líneas base](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines), que describe el filtrado y la lectura de los registros.

### <a name="flush-the-dns-cache-first"></a>Vaciar primero la caché DNS

¿Por qué? Al vaciar la memoria caché dns, va a iniciar las pruebas con una pizarra limpia. Al borrar la memoria caché, va a restablecer el contenido de la resolución DNS a las entradas más actualizadas. Recuerde que un vaciado no quita las entradas de archivo HOST. Si usa las entradas de archivo HOST extensamente, debe copiar esas entradas en un archivo de otro directorio y, a continuación, vaciar el archivo HOST.

#### <a name="flush-your-dns-resolver-cache"></a>Vaciar la memoria caché del solucionador dns

1. Abra el símbolo del sistema ( **iniciar** \> **ejecutar** \> **cmd** o **clave de Windows** \> **cmd**).
2. Escriba el siguiente comando y presione ENTRAR:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

La herramienta de supervisión de red ([Netmon](https://www.microsoft.com/download/details.aspx?id=4865)) de Microsoft analiza los paquetes, es decir, el tráfico, que pasan entre equipos en redes. Al usar Netmon para realizar un seguimiento del tráfico con Office 365 puede capturar, ver y leer encabezados de paquetes, identificar dispositivos intermedios, comprobar la configuración importante en el hardware de red, buscar paquetes eliminados y seguir el flujo de tráfico entre equipos de la red corporativa y Office 365. Dado que el cuerpo real del tráfico está cifrado, es decir, viaja en el puerto 443 a través de SSL/TLS, no puede leer los archivos que se envían. En su lugar, obtiene un seguimiento sin filtrar de la ruta de acceso que toma el paquete, lo que puede ayudarle a rastrear el comportamiento del problema.

Asegúrese de no aplicar un filtro en este momento. En su lugar, ejecute los pasos y muestre el problema antes de detener el seguimiento y guardarlo.

Después de instalar Netmon 3.4, abra la herramienta y siga estos pasos:

### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Realizar un seguimiento de Netmon y reproducir el problema

1. Inicie Netmon 3.4.
Hay tres paneles en la página **Inicio**: **Capturas recientes**, **Seleccionar redes** y la **Introducción con Microsoft Network Monitor 3.4. Fíjese**. El panel Seleccionar redes también le proporcionará una lista de las redes predeterminadas desde las que puede capturar. Asegúrese de que las tarjetas de red estén seleccionadas aquí.

2. Haga clic en **Nueva captura** en la parte superior de la página **Inicio** . Esto agrega una nueva pestaña junto a la pestaña **Página de inicio** denominada **Capturar 1**.
![Interfaz de usuario de Netmon con los botones Nueva captura, Inicio y Detener resaltados.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Para realizar una captura sencilla, haga clic en **Iniciar** en la barra de herramientas.

4. Reproduzca los pasos que presentan un problema de rendimiento.

5. Haga clic en **Detener** \> **archivo** \> **guardar como**. No olvide dar la fecha y la hora con la zona horaria y mencionar si demuestra un rendimiento incorrecto o bueno.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) incluye un cargo y una edición gratuita. La edición básica gratuita cubre todo lo que necesita para esta prueba. HTTPWatch supervisa el tráfico de red y el tiempo de carga de la página directamente desde la ventana del explorador. HTTPWatch es un complemento de Internet Explorer que describe gráficamente el rendimiento. El análisis se puede guardar y ver en HTTPWatch Studio.

> [!NOTE]
> Si usa otro explorador, como Firefox, Google Chrome o si no puede instalar HTTPWatch en Internet Explorer, abra una nueva ventana del explorador y presione F12 en el teclado. Debería ver el elemento emergente Herramienta para desarrolladores en la parte inferior del explorador. Si usa Opera, presione CTRL+MAYÚS+I para Inspector web y, a continuación, haga clic en la pestaña **Red** y complete las pruebas que se describen a continuación. La información será ligeramente diferente, pero los tiempos de carga se seguirán mostrando en milisegundos. > HTTPWatch también es muy útil para problemas con los tiempos de carga de la página de SharePoint Online.

### <a name="run-httpwatch-and-reproduce-the-issue"></a>Ejecución de HTTPWatch y reproducción del problema

HTTPWatch es un complemento de explorador, por lo que exponer la herramienta en el explorador es ligeramente diferente para cada versión de Internet Explorer. Normalmente, puede encontrar HTTPWatch en la barra Comandos en el explorador Internet Explorer. Si no ve el complemento HTTPWatch en la ventana del explorador, compruebe la versión del explorador haciendo clic en **Ayuda** \> **acerca** de o en versiones posteriores de Internet Explorer, haga clic en el símbolo de engranaje y **Acerca de Internet Explorer**. Para iniciar la barra **Comandos** , haga clic con el botón derecho en la barra de menús de Internet Explorer y haga clic en **Barra de comandos**.

En el pasado, HTTPWatch se ha asociado a las barras Comandos y Explorador, por lo que una vez que se instala, si no ve inmediatamente el icono (incluso después del reinicio), compruebe **Herramientas** y las barras de herramientas para el icono. Recuerde que las barras de herramientas se pueden personalizar y se pueden agregar opciones a ellas.

![Barra de herramientas comandos de Internet Explorer con el icono HTTPWatch mostrado.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)

1. Inicie HTTPWatch en una ventana del explorador Internet Explorer. Aparecerá acoplado al explorador en la parte inferior de esa ventana. Haga clic en **Grabar**.

2. Reproduzca los pasos exactos implicados en el problema de rendimiento. Haga clic en el botón **Detener** en HTTPWatch.

3. **Guarde** HTTPWatch o **Send by Email**. No olvide asignar un nombre al archivo para que incluya información de fecha y hora y una indicación de si el reloj contiene una demostración de buen o mal rendimiento.

![HTTPWatch que muestra la ficha de red para una carga de página de la página de inicio de Office 365.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Esta captura de pantalla es de la versión Professional de HTTPWatch. Puede abrir los seguimientos realizados en la versión básica en un equipo con una versión Professional y leerlos allí. Es posible que haya información adicional disponible desde el seguimiento a través de ese método.

## <a name="problem-steps-recorder"></a>Grabadora de pasos del problema

La grabadora de pasos, o PSR.exe, permite registrar problemas a medida que se producen. Es una herramienta muy útil y fácil de ejecutar.

### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Ejecutar la grabadora de pasos de problemas (PSR.exe) para grabar el trabajo

1. Use **Iniciar** \> **tipo de ejecución** \> **PSR.exe** \> **Aceptar** o haga clic en el **PSR.exe** \> Tipo **de clave** \> de Windows y, a continuación, presione ENTRAR.

2. Cuando aparezca la pequeña ventana PSR.exe, haga clic en **Iniciar registro** y reproduzca los pasos que reproducen el problema de rendimiento. Para agregar comentarios según sea necesario, haga clic en **Agregar comentarios**.

3. Haga clic en **Detener registro** cuando haya completado los pasos. Si el problema de rendimiento es una representación de página, espere a que la página se represente antes de detener la grabación.

4. Haga clic en **Guardar**.

![Captura de pantalla de la grabadora de pasos o PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)

La fecha y hora se graban para usted. Esto vincula su PSR a su seguimiento de Netmon y HTTPWatch en el tiempo, y ayuda con la solución de problemas de precisión. La fecha y hora del registro PSR puede mostrar que se ha pasado un minuto entre el inicio de sesión y la exploración de la dirección URL y la representación parcial del sitio de administración, por ejemplo.

## <a name="read-your-traces"></a>Leer los seguimientos

No es posible enseñar todo sobre la solución de problemas de red y rendimiento que alguien necesitaría saber a través de un artículo. Obtener un buen rendimiento requiere experiencia y conocimiento de cómo funciona la red y, por lo general, funciona. Pero es posible redondear una lista de los principales problemas y mostrar cómo las herramientas pueden facilitar la eliminación de los problemas más comunes.

Si quiere adquirir aptitudes que leen seguimientos de red para los sitios de Office 365, no hay mejor profesor que crear seguimientos de cargas de página con regularidad y obtener experiencia al leerlos. Por ejemplo, cuando tenga una oportunidad, cargue un servicio Office 365 y haga un seguimiento del proceso. Filtre el seguimiento del tráfico DNS o busque en FrameData el nombre del servicio que ha explorado. Examine el seguimiento para obtener una idea de los pasos que se producen cuando se carga el servicio. Esto le ayudará a obtener información sobre el aspecto que debería tener la carga de página normal y, en el caso de la solución de problemas, especialmente en relación con el rendimiento, comparar los seguimientos buenos con los incorrectos puede enseñar mucho.

Netmon usa Microsoft Intellisense en el campo Mostrar filtro. IntelliSense, o finalización de código inteligente, es ese truco en el que escribe un punto y todas las opciones disponibles se muestran en un cuadro de selección desplegable. Por ejemplo, le preocupa el escalado de ventanas TCP; puede encontrar el camino a un filtro (por  `.protocol.tcp.window < 100`ejemplo, ) por este medio.

![Captura de pantalla de Netmon que muestra que el campo Filtro de visualización usa IntelliSense.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)

Los seguimientos de Netmon pueden tener mucho tráfico en ellos. Si no tiene experiencia al leerlas, es probable que se sienta abrumado al abrir el seguimiento la primera vez. Lo primero que hay que hacer es separar la señal del ruido de fondo en el seguimiento. Ha probado con Office 365 y ese es el tráfico que desea ver. Si está acostumbrado a navegar por los seguimientos, es posible que no necesite esta lista.

El tráfico entre el cliente y Office 365 viaja a través de TLS, lo que significa que el cuerpo del tráfico se cifrará y no se podrá leer en un seguimiento genérico de Netmon. El análisis de rendimiento no necesita conocer los detalles de la información del paquete. Sin embargo, está muy interesado en los encabezados de paquete y la información que contienen.

### <a name="tips-to-get-a-good-trace"></a>Sugerencias para obtener un buen seguimiento

- Conozca el valor de la dirección IPv4 o IPv6 del equipo cliente. Para obtener esto desde el símbolo del sistema, escriba **IPConfig** y presione ENTRAR. Conocer esta dirección le permitirá saber de un vistazo si el tráfico en el seguimiento implica directamente el equipo cliente. Si hay un proxy conocido, haga ping y obtenga también su dirección IP.

- Vacíe la caché del solucionador DNS y, si es posible, cierre todos los exploradores excepto el en el que ejecuta las pruebas. Si no puede hacerlo, por ejemplo, si la compatibilidad usa alguna herramienta basada en explorador para ver el escritorio del equipo cliente, prepárese para filtrar el seguimiento.

- En un seguimiento ocupado, busque el servicio de Office 365 que está usando. Si nunca ha visto o rara vez el tráfico, este es un paso útil para separar el problema de rendimiento de otro ruido de red. Hay varias maneras de hacerlo. Directamente antes de la prueba, puede usar _ping_ o _PsPing_ en la dirección URL del servicio específico (`ping outlook.office365.com` o `psping -4 microsoft-my.sharepoint.com:443`, por ejemplo). También puede encontrar fácilmente ese ping o PsPing en un seguimiento de Netmon (por su nombre de proceso). Eso te dará un lugar para empezar a buscar.

Si solo usa el seguimiento de Netmon en el momento del problema, también está bien. Para orientarse, use un filtro como `ContainsBin(FrameData, ASCII, "office")` o `ContainsBin(FrameData, ASCII, "outlook")`. Puede registrar el número de fotograma desde el archivo de seguimiento. También puede desplazarse por el panel _Resumen de fotogramas_ hasta la derecha y buscar la columna Id. de conversación. Hay un número indicado allí para el identificador de esta conversación específica que también puede grabar y examinar de forma aislada más adelante. No olvide quitar este filtro antes de aplicar cualquier otro filtrado.

> [!TIP]
> Netmon tiene una gran cantidad de filtros integrados útiles. Pruebe el botón **Cargar filtro** en la parte superior del panel _Mostrar_ filtro.

![Busque la dirección IP mediante PSPing en la línea de comandos del equipo cliente.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)

![Seguimiento de Netmon desde el cliente que muestra el mismo comando PSPing a través del tcp de filtro. Flags.Syn == 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)

Familiarícese con el tráfico y aprenda a localizar la información que necesita. Por ejemplo, aprenda a determinar qué paquete del seguimiento tiene la primera referencia al servicio de Office 365 que usa (por ejemplo, "Outlook").

Tomando Office 365 Outlook Online como ejemplo, el tráfico comienza algo parecido a esto:

- Consulta estándar dns y respuesta DNS para outlook.office365.com con identificadores de consulta coincidentes. Es importante tener en cuenta el desplazamiento de tiempo de este turno y dónde en el mundo el DNS global Office 365 envía la solicitud de resolución de nombres. Idealmente, lo más localmente posible, en lugar de a medio camino en todo el mundo.

- Una solicitud HTTP GET cuyo informe de estado se movió permanentemente (301)

- Tráfico de RWS, incluidas las solicitudes de RWS Connect y las respuestas de Connect. (Se trata de Winsock remoto que realiza una conexión para usted).

- Una conversación TCP SYN y TCP SYN/ACK. Muchas configuraciones de esta conversación afectan al rendimiento.

- A continuación, se muestra una serie de tráfico TLS:TLS, que es donde tienen lugar las conversaciones de protocolo de enlace TLS y certificado TLS. (Recuerde que los datos se cifran a través de SSL/TLS).

Todas las partes del tráfico son importantes y están conectadas, pero pequeñas partes del seguimiento contienen información importante en términos de solución de problemas de rendimiento, por lo que nos centraremos en esas áreas. Además, dado que hemos hecho suficientes Office 365 solución de problemas de rendimiento en Microsoft para compilar una lista de los diez primeros problemas comunes, nos centraremos en esos problemas y en cómo usar las herramientas que tenemos para rootearlos a continuación.

Si aún no los ha instalado, la matriz siguiente usa varias herramientas siempre que sea posible. Se proporcionan vínculos a los puntos de instalación. La lista incluye herramientas comunes de seguimiento de red como [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) y [Wireshark](https://www.wireshark.org/), pero usa cualquier herramienta de seguimiento con la que te sientas cómodo y en la que estés acostumbrado a filtrar el tráfico de red. Cuando realice pruebas, recuerde lo siguiente:

- *Cierre los exploradores y pruebe con un solo explorador en ejecución*  : esto reducirá el tráfico general que capture. Hace que se realice un seguimiento menos ocupado.
- *Vaciar la caché del solucionador DNS en el equipo cliente*  : esto le proporcionará una pizarra limpia cuando empiece a tomar la captura para obtener un seguimiento más limpio.

## <a name="common-issues"></a>Problemas comunes

Algunos problemas comunes a los que puede enfrentarse y cómo encontrarlos en el seguimiento de red.

### <a name="tcp-windows-scaling"></a>Escalado de Windows TCP

Se encuentra en SYN - SYN/ACK. Es posible que el hardware heredado o antiguo no aproveche el escalado de ventanas TCP.  Sin una configuración de escalado de windows TCP adecuada, el búfer predeterminado de 16 bits en encabezados TCP se rellena en milisegundos.  El tráfico no puede continuar enviando hasta que el cliente reciba una confirmación de que se han recibido los datos originales, lo que provoca retrasos.

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

Busque el tráfico SYN- SYN/ACK en el seguimiento de red.  En Netmon, use un filtro como  `tcp.flags.syn == 1`. Este filtro es el mismo en Wireshark.

![Filtre en Netmon o Wireshark para paquetes Syn para ambas herramientas: TCP. Flags.Syn == 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Observe que para cada SYN hay un número de puerto de origen (SrcPort) que coincide en el puerto de destino (DstPort) de la confirmación relacionada (SYN/ACK).

Para ver el valor de Escalado de Windows que usa la conexión de red, expanda primero SYN y, a continuación, syn/ACK relacionado.

![Gráfico que muestra cómo hacer coincidir SrcPort con DstPort en un seguimiento para obtener la diferencia de tiempo.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)

### <a name="tcp-idle-time-settings"></a>Configuración del tiempo de inactividad de TCP

Históricamente, la mayoría de las redes perimetrales están configuradas para conexiones transitorias, lo que significa que las conexiones inactivas suelen terminarse. Los servidores proxy y los firewalls pueden finalizar las sesiones TCP inactivas en más de 100 a 300 segundos. Esto es problemático para Outlook Online porque crea y usa conexiones a largo plazo, independientemente de si están inactivas o no.

Cuando las conexiones finalizan mediante dispositivos de proxy o firewall, el cliente no está informado y un intento de usar Outlook Online significará que un equipo cliente intentará, repetidamente, revivir la conexión antes de hacer una nueva. Es posible que vea bloqueos en el producto, mensajes o un rendimiento lento en la carga de página.

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

En Netmon, examine el campo Desplazamiento de tiempo para un recorrido de ida y vuelta. Un recorrido de ida y vuelta es el tiempo entre el cliente que envía una solicitud al servidor y recibe una respuesta. Compruebe entre el cliente y el punto de salida (por ejemplo, Cliente --\> Proxy) o el cliente que se va a Office 365 (cliente--\> Office 365). Puede ver esto en muchos tipos de paquetes.

Por ejemplo, el filtro de Netmon puede parecerse  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12`a , o, en Wireshark,  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12`.

> [!TIP]
> ¿No sabe si la dirección IP del seguimiento pertenece al servidor DNS? Intente buscarlo en la línea de comandos. Haga clic en **Iniciar** \> **ejecución** \> y escriba **cmd**, o bien presione **Tecla Windows** \> y escriba **cmd**. En el símbolo del sistema, escriba  `nslookup <the IP address from the network trace>`. Para probar, use nslookup en la dirección IP de su propio equipo. > Para ver una lista de los intervalos IP de Microsoft, consulte [Office 365 direcciones URL e intervalos de direcciones IP](./urls-and-ip-address-ranges.md).

Si hay un problema, espere que aparezcan desplazamientos de tiempo prolongados, en este caso (Outlook Online), especialmente en paquetes TLS:TLS que muestran el paso de datos de aplicación (por ejemplo, en Netmon puede encontrar paquetes de datos de aplicación a través  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"`de ). Debería ver una progresión suave en el tiempo a lo largo de la sesión. Si ve retrasos prolongados al actualizar Outlook Online, esto podría deberse a un alto grado de restablecimientos que se envían.

### <a name="latencyround-trip-time"></a>Latencia/tiempo de ida y vuelta

La latencia es una medida que puede cambiar mucho en función de muchas variables, como la actualización de dispositivos de envejecimiento, la adición de un gran número de usuarios a una red y el porcentaje de ancho de banda total consumido por otras tareas en una conexión de red.

Hay calculadoras de ancho de banda para Office 365 disponibles en esta página [Planeamiento de red y optimización del rendimiento para Office 365](network-planning-and-performance.md).

¿Necesita medir la velocidad de la conexión o el ancho de banda de la conexión ISP? Pruebe este sitio (o sitios como él): [Sitio oficial de Speedtest](https://www.speedtest.net/), o consulte su motor de búsqueda favorito para la **prueba de velocidad** de frase.

#### <a name="tools"></a>Herramientas

- Señal
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

Para realizar un seguimiento de la latencia en un seguimiento, se beneficiará de haber registrado la dirección IP del equipo cliente y la dirección IP del servidor DNS en Office 365. Esto es para facilitar el filtrado de seguimiento. Si se conecta a través de un proxy, necesitará la dirección IP del equipo cliente, la dirección IP de proxy/salida y la dirección IP Office 365 DNS, para facilitar el trabajo.

Una solicitud de ping enviada a outlook.office365.com le indicará el nombre del centro de datos que recibe la solicitud, incluso si  *es posible que*  ping no pueda conectarse para enviar los paquetes ICMP consecutivos de marca comercial. Si usa PsPing (una herramienta gratuita para descargar) y especifica el puerto (443) y quizás para usar IPv4 (-4), obtendrá un tiempo medio de ida y vuelta para los paquetes enviados. Esto funcionará para otras direcciones URL de los servicios de Office 365, como `psping -4 yourSite.sharepoint.com:443`. De hecho, puede especificar una serie de pings para obtener un ejemplo más grande para el promedio, probar algo parecido `psping -4 -n 20 yourSite-my.sharepoint.com:443`a .

> [!NOTE]
> PsPing no envía paquetes ICMP. Hace ping con paquetes TCP a través de un puerto específico, por lo que puede usar cualquiera que sepa que está abierto. En Office 365, que usa SSL/TLS, intente adjuntar el puerto :443 a psPing.

![Captura de pantalla que muestra un ping resolviendo outlook.office365.com y un PSPing con el 443 haciendo lo mismo, pero también informando de un RTT medio de 6,5 ms.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Si cargó la página de Office 365 de rendimiento lento mientras realiza un seguimiento de red, debe filtrar un seguimiento de Netmon o Wireshark por `DNS`. Esta es una de las direcciones IP que estamos buscando.

Estos son los pasos que debe seguir para filtrar su Netmon para obtener la dirección IP (y echar un vistazo a la latencia de DNS). En este ejemplo se usa outlook.office365.com, pero también se puede usar la dirección URL de un inquilino de SharePoint Online (hithere.sharepoint.com por ejemplo).

1. Haga ping a la dirección URL `ping outlook.office365.com` y, en los resultados, registre el nombre y la dirección IP del servidor DNS al que se envió la solicitud de ping.
2. Seguimiento de red que abre la página o realiza la acción que le proporciona el problema de rendimiento o, si ve una latencia alta en el ping, realice un seguimiento de la red.
3. Abra el seguimiento en Netmon y filtre por DNS (este filtro también funciona en Wireshark, pero distingue mayúsculas de minúsculas `-- dns`). Dado que conoce el nombre del servidor DNS del ping, también puede filtrar más rápidamente en Netmon de la siguiente manera: `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")`, que tiene este aspecto en Wireshark dns y frame contiene "namnorthwest".<br/>Abra el paquete de respuesta y, en la ventana **Detalles del marco** de Netmon, haga clic en **DNS** para expandirlo para obtener más información. En la información de DNS encontrará la dirección IP del servidor DNS a la que se ha dirigido la solicitud en Office 365. Necesitará esta dirección IP para el siguiente paso (la herramienta PsPing). Quite el filtro y haga clic con el botón derecho en la respuesta DNS en Netmon (**DNS** de búsqueda de **resumen** \> de **fotogramas**\>) para ver la consulta y la respuesta dns en paralelo.
4. En Netmon, tenga en cuenta también la columna Desplazamiento de tiempo entre la solicitud DNS y la respuesta. En el paso siguiente, la herramienta [PsPing](/sysinternals/downloads/psping) fácil de instalar y usar resulta muy útil, tanto porque ICMP se bloquea a menudo en firewalls como porque PsPing realiza un seguimiento elegante de la latencia en milisegundos. PsPing completa una conexión TCP a una dirección y un puerto (en nuestro caso, abra el puerto 443).
5. Instale PsPing.
6. Abra un símbolo del sistema (Start \> Run \> type cmd o Windows Key \> type cmd) y cambie el directorio al directorio donde instaló PsPing para ejecutar el comando PsPing. En mis ejemplos puede ver que hice una carpeta "Perf" en la raíz de C. Puede hacer lo mismo para un acceso rápido.
7. Escriba el comando para que realice su PsPing con la dirección IP del servidor DNS de Office 365 del seguimiento de Netmon anterior, incluido el número de puerto, como `psping -n 20 132.245.24.82:445`. Esto le proporcionará un muestreo de 20 pings y el promedio de latencia cuando PsPing se detenga.

Si va a Office 365 a través de un servidor proxy, los pasos son un poco diferentes. En primer lugar, usaría PsPing en el servidor proxy para obtener un valor de latencia promedio en milisegundos en proxy/salida y de vuelta y, a continuación, ejecutar PsPing en el proxy o en un equipo con una conexión directa a Internet para obtener el valor que falta (el que se va a Office 365 y atrás).

Si decide ejecutar PsPing desde el proxy, tendrá dos valores de milisegundos: equipo cliente al servidor proxy o punto de salida y servidor proxy para Office 365. ¡Y ya has terminado! Bueno, grabando valores, de todos modos.

Si ejecuta PsPing en otro equipo cliente que tiene una conexión directa a Internet, es decir, sin un proxy, tendrá dos valores de milisegundos: equipo cliente a servidor proxy o punto de salida y equipo cliente para Office 365. En este caso, reste el valor del equipo cliente al servidor proxy o al punto de salida del valor del equipo cliente a Office 365, y tendrá los números RTT del equipo cliente al servidor proxy o al punto de salida, y del servidor proxy o del punto de salida a Office 365.

Sin embargo, si puede encontrar un equipo cliente en la ubicación afectada que está conectado directamente o omite el proxy, puede optar por ver si el problema se reproduce allí para empezar y probar su uso a partir de entonces.

La latencia, como se ve en un seguimiento de Netmon, esos milisegundos adicionales pueden agregarse, si hay suficientes en una sesión determinada.

![Latencia general de Netmon, con la columna de diferencia de tiempo predeterminada de Netmon agregada al Resumen de marco.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Su dirección IP puede ser diferente de las direcciones IP que se muestran aquí, por ejemplo, el ping puede devolver algo más parecido a 157.56.0.0/16 o un intervalo similar. Para obtener una lista de los intervalos utilizados por Office 365, consulte [Office 365 direcciones URL e intervalos de direcciones IP](./urls-and-ip-address-ranges.md).

Recuerde expandir todos los nodos (hay un botón en la parte superior para esto) si desea buscar, por ejemplo, 132.245.

### <a name="proxy-authentication"></a>Autenticación de proxy

Esto solo se aplica a usted si va a pasar por un servidor proxy. Si no es así, puede omitir estos pasos. Cuando funciona correctamente, la autenticación de proxy debe tener lugar en milisegundos, de forma coherente. No debería ver un rendimiento incorrecto intermitente durante los períodos de uso máximos (por ejemplo).

Si la autenticación de proxy está activada, cada vez que realice una nueva conexión TCP a Office 365 para obtener información, debe pasar a través de un proceso de autenticación en segundo plano. Por ejemplo, al cambiar de Calendario a Correo en Outlook Online, se autenticará. Y en SharePoint Online, si una página muestra medios o datos de varios sitios o ubicaciones, se autenticará para cada conexión TCP diferente que sea necesaria para representar los datos.

En Outlook Online, puede experimentar tiempos de carga lentos cada vez que cambie entre calendario y buzón, o cargas de página lentas en SharePoint Online. Sin embargo, hay otros síntomas que no se enumeran aquí.

La autenticación de proxy es una configuración en el servidor proxy de salida. Si está causando un problema de rendimiento con Office 365, debe consultar a su equipo de red.

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Qué buscar

La autenticación de proxy tiene lugar cada vez que se debe poner en marcha una nueva sesión TCP, normalmente para solicitar archivos o información del servidor, o para proporcionar información. Por ejemplo, puede ver la autenticación de proxy en torno a las solicitudes HTTP GET o HTTP POST. Si desea ver los marcos en los que se autentican las solicitudes en el seguimiento, agregue la columna "Resumen de NTLMSSP" a Netmon y filtre por  `.property.NTLMSSPSummary`. Para ver cuánto tiempo tarda la autenticación, agregue la columna Delta de tiempo.

Para agregar una columna a Netmon:

1. Haga clic con el botón derecho en una columna como **Descripción**.
2. Haga clic en **Elegir columnas**.
3. Busque _NTLMSSP Summary_ and _Time Delta_ en la lista y haga clic en **Agregar**.
4. Mueva las nuevas columnas a su lugar antes o detrás de la columna _Descripción_ para que pueda leerlas en paralelo.
5. Haga clic en **Aceptar**.

Incluso si no agrega la columna, el filtro Netmon funcionará. Pero la solución de problemas será mucho más fácil si puede ver en qué fase de autenticación se encuentra.

Al buscar instancias de autenticación de proxy, asegúrese de estudiar todas las tramas en las que haya un desafío NTLM o que haya un mensaje de autenticación presente. Si es necesario, haga clic con el botón derecho en la parte específica del tráfico y en Buscar conversaciones \> TCP. Tenga en cuenta los valores de Time Delta en estas conversaciones.

![Seguimiento de Netmon que muestra la autenticación de proxy, filtrada por conversación.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Un retraso de cuatro segundos en la autenticación de proxy como se ve en Wireshark. La columna **Time delta from previous displayed frame (Diferencia de tiempo del marco mostrado anterior** ) se realizó haciendo clic con el botón derecho en el campo del mismo nombre en los detalles del marco y seleccionando Agregar como columna.  <br/> ![En Wireshark, la columna "Diferencia de tiempo del marco mostrado anterior" se puede realizar haciendo clic con el botón derecho en el campo del mismo nombre en los detalles del marco y seleccionando Agregar como columna.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>Rendimiento de DNS

La resolución de nombres funciona mejor y más rápidamente cuando tiene lugar lo más cerca posible del país del cliente.

Si la resolución de nombres DNS tiene lugar en el extranjero, puede agregar segundos a las cargas de página. Lo ideal es que la resolución de nombres se produzca en menos de 100 ms. Si no es así, debe realizar una investigación adicional.

> [!TIP]
> ¿No está seguro de cómo funciona la conectividad de cliente en Office 365? Eche un vistazo al documento Referencia de conectividad de [cliente aquí](/previous-versions//dn741250(v=technet.10)).

#### <a name="tools"></a>Herramientas

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Qué buscar

El análisis del rendimiento de DNS suele ser otro trabajo para un seguimiento de red. Sin embargo, PsPing también es útil para resolver o descartar una posible causa.

El tráfico DNS se basa en solicitudes TCP y UDP y las respuestas se marcan claramente con un identificador que ayudará a hacer coincidir una solicitud específica con su respuesta específica. Verá el tráfico DNS cuando, por ejemplo, SharePoint Online usa un nombre de red o una dirección URL en una página web. Como regla general, la mayor parte de este tráfico, excepto al transferir zonas, se ejecuta a través de UDP.

En Netmon y Wireshark, el filtro más básico que le permitirá ver el tráfico DNS es simplemente `dns`. Asegúrese de usar minúsculas al especificar el filtro. No olvide vaciar la memoria caché del solucionador DNS antes de empezar a reproducir el problema en el equipo cliente. Por ejemplo, si tiene una carga lenta de página de SharePoint Online para la página principal, debe cerrar todos los exploradores, abrir un nuevo explorador, iniciar el seguimiento, vaciar la caché de resolución DNS y examinar el sitio de SharePoint Online. Una vez que se resuelva toda la página, debe detener y guardar el seguimiento.

![Un filtro básico para DNS en Netmon es DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Desea ver el desplazamiento de tiempo aquí. Y puede resultar útil agregar la columna **Time Delta** a Netmon, que puede hacer completando estos pasos:

1. Haga clic con el botón derecho en una columna como **Descripción**.
2. Haga clic en **Elegir columnas**.
3. Busque _Time Delta_ en la lista y haga clic en **Agregar**.
4. Mueva la nueva columna antes o detrás de la columna _Descripción_ para que pueda leerla en paralelo.
5. Haga clic en **Aceptar**.

Si encuentra una consulta de interés, considere la posibilidad de aislarla haciendo clic con el botón derecho en esa consulta en el panel de detalles del marco, eligiendo **Buscar conversaciones** \> **DNS**. Observe que el panel Conversaciones de red salta directamente a la conversación específica en su registro de tráfico UDP.

![Un seguimiento netmon de la carga de Outlook Online filtrada por DNS, y usando Buscar conversaciones y, a continuación, DNS para restringir los resultados.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

En Wireshark puede crear una columna para la hora DNS. Realice el seguimiento (o abra un seguimiento) en Wireshark y filtre por `dns`o, de forma más útil,  `dns.time`. Haga clic en cualquier consulta DNS y, en el panel que muestra los detalles, expanda los  `Domain Name System (response)` detalles. Verá un campo para el tiempo (por ejemplo, `[Time: 0.001111100 seconds]`. Haga clic con el botón derecho en esta vez y seleccione **Aplicar como columna**. Esto le proporcionará una columna **Time** para ordenar más rápidamente el seguimiento. Haga clic en la nueva columna para ordenar por valores descendentes para ver qué llamada DNS tardó más tiempo en resolverse.

[Una exploración de SharePoint Online filtrada en Wireshark por dns.time (minúscula), con el tiempo de los detalles convertido en columna y ordenado de forma ascendente.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Si desea realizar una investigación más detallada del tiempo de resolución dns, pruebe una psPing con el puerto DNS usado por TCP (por ejemplo,  `psping <IP address of DNS server>:53`) . ¿Sigue viendo un problema de rendimiento? Si lo hace, es más probable que el problema sea un problema de red más amplio que un problema específico de la aplicación DNS a la que está llegando para resolverlo. También merece la pena mencionar, de nuevo, que un ping a outlook.office365.com le indicará dónde tiene lugar la resolución de nombres DNS para Outlook Online (por ejemplo, outlook-namnorthwest.office365.com).

Si el problema parece ser específico de DNS, puede ser necesario ponerse en contacto con el departamento de TI para examinar las configuraciones dns y los reenviadores DNS para investigar más este problema.

### <a name="proxy-scalability"></a>Escalabilidad del proxy

Servicios como Outlook Online en Office 365 conceder a los clientes varias conexiones a largo plazo. Por lo tanto, cada usuario puede usar más conexiones que requieran una vida más larga.

#### <a name="tools"></a>Herramientas

Matemáticas

#### <a name="what-to-look-for"></a>Qué buscar

No hay ninguna herramienta de seguimiento de red o solución de problemas específica para esto. En su lugar, se basa en los cálculos de ancho de banda dadas las limitaciones y otras variables.

### <a name="tcp-max-segment-size"></a>Tamaño máximo de segmento TCP

Se encuentra en SYN - SYN/ACK.  Realice esta comprobación en cualquier seguimiento de red de rendimiento que haya tomado para asegurarse de que los paquetes TCP están configurados para llevar la cantidad máxima posible de datos.

El objetivo es ver un MSS de 1460 bytes para la transmisión de datos. Si está detrás de un proxy o usa una NAT, no olvide ejecutar esta prueba desde el cliente hasta el proxy, la salida y nat, y desde proxy/ salida/NAT para Office 365 para obtener los mejores resultados! Estas son sesiones TCP diferentes.

#### <a name="tools"></a>Herramientas

Netmon

#### <a name="what-to-look-for"></a>Qué buscar

Tcp Max Segment Size (MSS) es otro parámetro del protocolo de enlace triple en el seguimiento de red, lo que significa que encontrará los datos que necesita en el paquete SYN - SYN/ACK. MSS es realmente bastante fácil de ver.

Abra cualquier seguimiento de red de rendimiento que tenga y busque la conexión que le interese o que muestre el problema de rendimiento.

> [!NOTE]
> Si busca un seguimiento y necesita encontrar el tráfico relevante para la conversación, filtre por la dirección IP del cliente, la dirección IP del servidor proxy o el punto de salida, o ambos. Yendo directamente, tendrá que hacer ping a la dirección URL que está probando para la dirección IP de Office 365 en el seguimiento y filtrar por ella.

¿Mirando el seguimiento de segunda mano? Pruebe a usar filtros para orientarse. En Netmon, ejecute una búsqueda basada en la dirección URL, como `Containsbin(framedata, ascii, "sphybridExample")`, tome nota del número de fotograma.

En Wireshark, use algo parecido a  `frame contains "sphybridExample"`. Si observa que ha encontrado tráfico de Winsock remoto (RWS) (puede aparecer como un [PSH, ACK] en Wireshark), recuerde que las conexiones RWS se pueden ver poco antes de los SYN - SYN/ACK pertinentes, como se ha explicado anteriormente.

En este punto, puede registrar el número de fotograma, quitar el filtro y hacer clic en **Todo el tráfico** en la ventana Conversaciones de red de Netmon para ver el SYN más cercano.

Lo importante es que, si no recibió ninguna información de la dirección IP en el momento del seguimiento, buscar la dirección URL en el seguimiento (parte de `sphybridExample-my.sharepoint.com`, por ejemplo), le proporcionará direcciones IP por las que filtrar.

Busque la conexión en el seguimiento que le interesa ver. Para ello, puede examinar el seguimiento, filtrar por direcciones IP o seleccionar identificadores de conversación específicos mediante la ventana Conversaciones de red de Netmon. Una vez que haya encontrado el paquete SYN, expanda TCP (en Netmon) o Protocolo de control de transmisión (en Wireshark) en el panel Detalles de marco. Expanda Opciones TCP y MaxSegmentSize. Busque el marco SYN-ACK relacionado y expanda Opciones TCP y MaxSegmentSize. El menor de los dos valores será el tamaño máximo del segmento. En esta imagen, utilizo la columna integrada en Netmon denominada Solución de problemas de TCP.

![Seguimiento de red filtrado en Netmon mediante las columnas integradas.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

La columna integrada se encuentra en la parte superior del panel **Detalles del marco** . (Para volver a la vista normal, haga clic de nuevo en **Columnas** y, a continuación, elija **Zona horaria**).

![Dónde encontrar la lista de columnas desplegable para la opción de Solucionar problemas de TCP (arriba del Resumen de marco).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Este es un seguimiento filtrado en Wireshark. Hay un filtro específico del valor de MSS (`tcp.options.mss`). Las tramas de un protocolo de enlace SYN, SYN/ACK, ACK se vinculan en la parte inferior de Wireshark equivalente a Detalles de marco (por lo tanto, marco 47 ACK, vínculos a 46 SYN/ACK, vínculos a 43 SYN) para facilitar este tipo de trabajo.

![Seguimiento filtrado en Wireshark por tcp.options.mss para Max Segment Size (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Si necesita comprobar **confirmación selectiva** (siguiente tema de esta matriz), no cierre el seguimiento.

### <a name="selective-acknowledgment"></a>Confirmación selectiva

Se encuentra en SYN - SYN/ACK. Se debe notificar como Permitido en SYN y SYN/ACK. La confirmación selectiva (SACK) permite una retransmisión de datos más fluida cuando falta un paquete o paquetes. Los dispositivos pueden deshabilitar esta característica, lo que puede provocar problemas de rendimiento.

Si está detrás de un proxy o usa una NAT, no olvide ejecutar esta prueba desde el cliente hasta el proxy, la salida y nat, y desde proxy/ salida/NAT para Office 365 para obtener los mejores resultados! Estas son sesiones TCP diferentes.

#### <a name="tools"></a>Herramientas

Netmon

#### <a name="what-to-look-for"></a>Qué buscar

La confirmación selectiva (SACK) es otro parámetro del protocolo de enlace SYN-SYN/ACK. Puede filtrar el seguimiento de SYN - SYN/ACK de muchas maneras.

Busque la conexión en el seguimiento que le interesa ver examinando el seguimiento, filtrando por direcciones IP o haciendo clic en un identificador de conversación mediante la ventana Conversaciones de red de Netmon. Una vez que haya encontrado el paquete SYN, expanda TCP en Netmon o Protocolo de control de transmisión en Wireshark en la sección Detalles de marco. Expanda Opciones TCP y, a continuación, SACK. Busque la trama SYN-ACK relacionada y expanda opciones TCP y su campo SACK. Asegúrese de que sack está permitido tanto en SYN como en SYN/ACK. Estos son los valores de SACK como se ve en Netmon y Wireshark.

![Confirmación selectiva (SACK) en Netmon como resultado de tcp.flags.syn == 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![BOLSA tal y como aparece en Wireshark con el filtro tcp.flags.syn == 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>Geolocalización de DNS

Donde en el mundo Office 365 intenta resolver la llamada DNS afecta a la velocidad de conexión.

En Outlook Online, una vez completada la primera búsqueda DNS, se usará la ubicación de ese DNS para conectarse al centro de datos más cercano. Se conectará a un servidor CAS de Outlook Online, que usará la red troncal para conectarse al centro de datos (dC) donde se almacenan los datos. Esto es más rápido.

Al acceder a SharePoint Online, se dirigirá a un usuario que viaja al extranjero a su centro de datos activo, que es el dC cuya ubicación se basa en la base de datos principal de su inquilino de SPO (por lo tanto, un dC en EE. UU. si el usuario está basado en EE. UU.).

Lync Online tiene nodos activos en más de un dC a la vez. Cuando se envían solicitudes para instancias de Lync Online, el DNS de Microsoft determinará de dónde procede la solicitud en el mundo y devolverá las direcciones IP del centro de datos regional más cercano donde lync online está activo.

> [!TIP]
> ¿Necesita saber más sobre cómo se conectan los clientes a Office 365? Eche un vistazo al artículo de referencia [de conectividad de cliente](/previous-versions//dn741250(v=technet.10)) (y sus gráficos útiles).

#### <a name="tools"></a>Herramientas

- Señal
- PsPing

#### <a name="what-to-look-for"></a>Qué buscar

En la mayoría de los casos, las solicitudes de resolución de nombres de los servidores DNS del cliente a los servidores DNS de Microsoft deben dar lugar a que Microsoft DNS devuelva la dirección IP de un centro de datos regional (dC). ¿Qué significa esto para ti? Si su sede central está en Bangalore, India, pero viaja en el Estados Unidos, cuando el explorador realiza una solicitud para Outlook Online, los servidores DNS de Microsoft deben entregarle direcciones IP a los centros de datos de la Estados Unidos, un centro de datos regional. Si se necesita correo de Outlook, esos datos viajarán a través de la red troncal rápida de Microsoft entre los centros de datos.

DNS funciona más rápido cuando la resolución de nombres se realiza lo más cerca posible de la ubicación del usuario. Si está en Europa, quiere ir a un DNS de Microsoft en Europa y( idealmente) tratar con un centro de datos en Europa. El rendimiento de un cliente en Europa que va a DNS y un centro de datos en Estados Unidos será más lento.

Ejecute la herramienta Ping en outlook.office365.com para determinar dónde se enruta la solicitud DNS en el mundo. Si está en Europa, debería ver una respuesta de algo como outlook-emeawest.office365.com. En las Américas, espere algo parecido a outlook-namnorthwest.office365.com.

Abra el símbolo del sistema en el equipo cliente (a través de Start \> Run \> cmd o el tipo de clave \> de Windows cmd). Escriba ping outlook.office365.com y presione ENTRAR. Recuerde que debe especificar -4 si desea especificar el ping a través de IPv4. Es posible que no obtenga una respuesta de los paquetes ICMP, pero debería ver el nombre del DNS al que se enrutó la solicitud. Si desea ver los números de latencia de esta conexión, pruebe PsPing a la dirección IP del servidor devuelta por ping.

![Ping de outlook.office365.com que muestra la resolución en outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PsPing a la dirección IP devuelta por el ping a outlook.office365.com que muestra una latencia media de 28 milisegundos.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>solución de problemas de aplicaciones de Office 365

#### <a name="tools"></a>Herramientas

- Netmon
- HTTPWatch
- Consola F12 en el explorador

En este artículo específico de la red no se tratan las herramientas que se usan en la solución de problemas específicas de la aplicación. Pero encontrará los recursos que  *puede*  usar [en esta página](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848).

## <a name="related-topics"></a>Temas relacionados

[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)