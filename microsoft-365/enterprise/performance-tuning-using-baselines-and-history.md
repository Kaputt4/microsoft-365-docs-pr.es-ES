---
title: Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 07/08/2021
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
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: Obtenga información sobre cómo comprobar el historial de las conexiones del equipo cliente para ayudarle a detectar problemas emergentes de forma anticipada.
ms.openlocfilehash: 460bde30a0b292569b045c339066df2860c50989
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341585"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento

Hay algunas maneras sencillas de comprobar el rendimiento de la conexión entre Office 365 y su empresa que le permitirán establecer una línea base aproximada de la conectividad. Conocer el historial de rendimiento de las conexiones del equipo cliente puede ayudarle a detectar problemas emergentes de forma anticipada, identificar y predecir problemas.
  
Si no está acostumbrado a trabajar en problemas de rendimiento, este artículo está diseñado para ayudarle a considerar algunas preguntas comunes. ¿Cómo sabe que el problema que está viendo es un problema de rendimiento y no un Office 365 de servicio? ¿Cómo puede planear un buen rendimiento a largo plazo? ¿Cómo puede estar atento al rendimiento? Si el equipo o los clientes ven un rendimiento lento al usar Office 365 y te preguntas sobre alguna de estas preguntas, sigue leyendo.
  
> [!IMPORTANT]
> **¿Tiene un problema de rendimiento entre el cliente y Office 365 en este momento?** Siga los pasos descritos en el [plan de solución de problemas](performance-troubleshooting-plan.md)de rendimiento para Office 365 . 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Algo que debe saber sobre Office 365 rendimiento

Office 365 vive dentro de una red de Microsoft dedicada de alta capacidad supervisada por la automatización y personas reales. Parte del mantenimiento de la nube Office 365 es ajustar y optimizar el rendimiento siempre que sea posible. Dado que los clientes Office 365 la nube tienen que conectarse a través de Internet, hay un esfuerzo continuo para ajustar el rendimiento en Office 365 servicios.

Las mejoras de rendimiento nunca se detienen realmente en la nube, por lo que tampoco la experiencia con mantener la nube en buen estado y rápido. Si tiene un problema de rendimiento al conectarse de su ubicación a Office 365, lo mejor es no empezar con un caso de soporte técnico ni esperarlo. En su lugar, debe empezar a investigar el problema desde "desde dentro hacia fuera". Es decir, comience dentro de la red y salga a Office 365. Antes de abrir un caso con soporte técnico, puede recopilar datos y realizar acciones que explorarán y pueden resolver el problema.
  
> [!IMPORTANT]
> Tenga en cuenta la planeación de capacidad y los límites de Office 365. Esa información le pondrá por delante de la curva al intentar resolver un problema de rendimiento. Este es un vínculo a las descripciones [Microsoft 365 y Office 365 servicio](/office365/servicedescriptions/office-365-service-descriptions-technet-library). Este es un concentrador central y todos los servicios ofrecidos por Office 365 tienen un vínculo que va a sus propias descripciones de servicio desde aquí. Esto significa que, si necesita ver los límites estándar de SharePoint Online, por ejemplo, haría clic en SharePoint [Descripción](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description) del servicio en línea y encontraría su sección [SharePoint Online Limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).
  
Asegúrese de ir a la solución de problemas con la comprensión de que el rendimiento es una escala deslizante. No se trata de lograr un valor idealizado y mantenerlo permanentemente. Las tareas de ancho de banda alto ocasionales, como el abordaje de  un gran número de usuarios o la migración de datos grandes, serán estresantes, por lo que planear los impactos en el rendimiento entonces. Debes tener una idea aproximada de los objetivos de rendimiento, pero muchas variables se reproducen en el rendimiento, por lo que el rendimiento varía.
  
La solución de problemas de rendimiento no se trata de cumplir objetivos específicos y mantener esos números indefinidamente, se trata de mejorar las actividades existentes, dadas todas las variables. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>¿Cómo es un problema de rendimiento?

En primer lugar, debe asegurarse de que lo que está experimentando es realmente un problema de rendimiento y no un incidente de servicio. Un problema de rendimiento es diferente de un incidente de servicio en Office 365. Este es el modo de diferenciarlos.
  
Los incidentes de servicio se suceden cuando el Office 365 propio servicio tiene problemas. Es posible que vea iconos rojos o amarillos en **Estado** actual en el Centro de administración de Microsoft 365. Es posible que observe que el rendimiento en los equipos cliente que se conectan Office 365 es lento. Por ejemplo, si estado actual informa  de un icono rojo y ve Investigar junto a Exchange, es posible que también reciba llamadas de personas de su organización que se quejan de que los buzones de cliente que usan Exchange Online son lentos. En ese caso, es razonable suponer que el rendimiento Exchange Online fue una víctima de problemas de servicio.
  
![El Office 365 de mantenimiento con todas las cargas de trabajo que se muestran en verde, excepto Exchange, que muestra Service Restored.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
En este momento, usted, el administrador de  Office 365, debe comprobar estado actual y, a continuación, ver detalles e **historial,** a menudo, para mantenerse al día del mantenimiento en el sistema. El **panel de mantenimiento** actual se ha realizado para actualizarlo acerca de los cambios y problemas en el servicio. Las notas y explicaciones escritas en el historial de mantenimiento, administración a administrador, están ahí para ayudarle a medir y para mantenerte informado sobre el trabajo en curso.
  
![Una imagen del panel de Office 365 de mantenimiento que explica que el Exchange Online se ha restaurado y por qué.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Un problema de rendimiento no es un incidente de servicio, aunque los incidentes pueden causar un rendimiento lento. Un problema de rendimiento tiene este aspecto:
  
- Se produce un problema de rendimiento independientemente de lo que informe el centro de **administración** Estado actual del servicio.
    
-  Un comportamiento que solía fluir tarda mucho tiempo en completarse o nunca se completa.
    
- También puede replicar el problema o saber que ocurrirá si hace la serie correcta de pasos.
    
-  Si el problema es intermitente, todavía puede haber un patrón. Por ejemplo, sabe que a las 10:00 am tendrá llamadas de usuarios que no siempre pueden acceder a Office 365. Las llamadas finalizarán alrededor del mediodía.
    
Esta lista probablemente suene familiar; quizás demasiado familiar. Una vez que sepas que se trata de un problema de rendimiento, la pregunta es: "¿Qué haces a continuación?". El resto de este artículo le ayuda a determinar exactamente eso.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Cómo definir y probar el problema de rendimiento

Los problemas de rendimiento suelen surgir con el tiempo, por lo que puede resultar difícil definir el problema real. Cree una buena instrucción de problema con una buena idea del contexto del problema y, a continuación, debe repetir los pasos de prueba. Estos son algunos ejemplos de instrucciones de problemas que no proporcionan suficiente información:
  
- Cambiar de la Bandeja de entrada a mi calendario solía ser algo que no noté y ahora es un descanso. ¿Puede hacer que actúe como antes?
    
- Cargar mis archivos en SharePoint Online lleva para siempre. ¿Por qué es lento en la tarde, pero en cualquier otro momento, es rápido? ¿No puede ser rápido?
    
Las instrucciones de problema anteriores plantean varios desafíos de gran tamaño. En concreto, demasiadas ambigüedades para tratar. Por ejemplo:
  
- No está claro cómo se usaba el cambio entre bandeja de entrada y calendario para actuar en el portátil.
    
- Cuando el usuario dice: "¿No puede ser rápido?", ¿qué es "rápido"?
    
- ¿Cuánto tiempo es "para siempre"? ¿Son varios segundos? ¿O muchos minutos? ¿O podría el usuario tomar el almuerzo y la acción terminaría 10 minutos después de haber vuelto?
    
El administrador y el solucionador de  problemas no pueden ser conscientes de los detalles del problema de instrucciones generales como estas. Por ejemplo, no saben cuándo comenzó a ocurrir el problema. Es posible que el solucionador de problemas no sepa que el usuario funciona desde casa y solo ve un cambio lento mientras está en su red doméstica. O que el usuario ejecuta otras aplicaciones intensivas de RAM en el cliente local. Es posible que los administradores no sepan que el usuario ejecuta un sistema operativo anterior o que no ha ejecutado actualizaciones recientes.
  
Cuando los usuarios informan de un problema de rendimiento, hay mucha información que recopilar. Obtener y grabar información se denomina ámbito del problema. Esta es una lista de ámbito básica que puede usar para recopilar información sobre problemas de rendimiento. Esta lista no es exhaustiva, pero es un lugar para empezar:
  
- ¿En qué fecha se ha sucedido el problema y en qué hora del día o de la noche?
    
- ¿Qué tipo de equipo cliente estaba usando y cómo se conecta a la red empresarial (VPN, Wired, Wireless)?
    
- ¿Estaba trabajando de forma remota o estaba en la oficina?
    
- ¿Ha hecho las mismas acciones en otro equipo y ha visto el mismo comportamiento?
    
- Siga los pasos que le están dando problemas para que pueda escribir las acciones que lleve a cabo.
    
- ¿Qué tan lento es el rendimiento en segundos o minutos?
    
- ¿Dónde se encuentra en el mundo?
    
Algunas de estas preguntas son más obvias que otras. La mayoría de los usuarios comprenderán que un solucionador de problemas necesita los pasos exactos para reproducir el problema. Después de todo, ¿cómo se puede registrar lo que está mal y cómo probar si se soluciona el problema? Menos obvias son las cosas como "¿Qué fecha y hora ha visto el problema?", y "¿Dónde se encuentra?", información que se puede usar en tándem. Según el momento en que el usuario estaba trabajando, unas pocas horas de diferencia de tiempo puede significar que el mantenimiento ya está en curso en partes de la red de su empresa. Si, por ejemplo, la empresa tiene una implementación híbrida, como una búsqueda híbrida de SharePoint, que puede consultar índices de búsqueda en SharePoint Online y en una instancia local de SharePoint Server 2013, es posible que se esté actualizando en la granja de servidores local. Si su empresa está en la nube, el mantenimiento del sistema puede incluir agregar o quitar hardware de red, implementar actualizaciones en toda la empresa o realizar cambios en DNS u otra infraestructura principal.
  
Cuando está solucionando un problema de rendimiento, es un poco como una escena del crimen, debe ser preciso y observador para extraer conclusiones de la evidencia. Para ello, debe obtener una buena declaración de problema mediante la recopilación de pruebas. Debe incluir el contexto del equipo, el contexto del usuario, cuándo comenzó el problema y los pasos exactos que exponen el problema de rendimiento. Esta instrucción de problema debe ser, y permanecer, la página superior de las notas. Al volver a recorrer la instrucción de problema después de trabajar en la resolución, está llevando a cabo los pasos para probar y demostrar si las acciones que lleva a cabo han resuelto el problema. Esto es fundamental para saber cuándo se realiza el trabajo.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>¿Sabe cómo se ve el rendimiento cuando era bueno?

Si no tiene suerte, nadie lo sabe. Nadie tenía números. Eso significa que nadie puede responder a la pregunta sencilla "¿Cuántos segundos se tardaron en abrir una Bandeja de entrada en Office 365?", o "¿Cuánto tiempo se tardaron los ejecutivos en tener una reunión de Lync Online?", que es un escenario común para muchas empresas.
  
Lo que falta aquí es una línea base de rendimiento.
  
Las líneas base le dan un contexto para el rendimiento. Debe tomar una línea base de vez en cuando a con frecuencia, según las necesidades de su empresa. Si es una empresa más grande, el equipo de operaciones puede tomar ya las líneas base para su entorno local. Por ejemplo, si se revisiones todos los servidores de Exchange el primer lunes del mes y todos los servidores de SharePoint el tercer lunes, el equipo de operaciones probablemente tenga una lista de tareas y escenarios que ejecuta después de la revisión, para demostrar que las funciones críticas están operativas. Por ejemplo, abrir la Bandeja de entrada, hacer clic en Enviar o recibir y asegurarse de que las carpetas se actualicen o, en SharePoint, examinar la página principal del sitio, ir a la página de búsqueda de empresa y realizar una búsqueda que devuelva resultados.
  
Si las aplicaciones están en Office 365, algunas de las líneas base más fundamentales se pueden tomar para medir el tiempo (en milisegundos) desde un equipo cliente dentro de la red, hasta un punto de salida o el punto en el que sale de la red y sale a Office 365. Estas son algunas líneas base útiles que puede investigar y registrar:
  
- Identifique los dispositivos entre el equipo cliente y el punto de salida, por ejemplo, el servidor proxy.
    
  - Debes conocer los dispositivos para que tenga contexto (direcciones IP, tipo de dispositivo, etc.) para los problemas de rendimiento que se presenten.
    
  - Los servidores proxy son puntos de salida comunes, por lo que puede comprobar el explorador web para ver qué servidor proxy está configurado para usar, si lo hay.
    
  - Existen herramientas de terceros que pueden detectar y asignar la red, pero la forma más segura de conocer los dispositivos es preguntar a un miembro del equipo de red.
    
- Identifique su proveedor de servicios de Internet (ISP), anote su información de contacto y pregunte cuántos circuitos tiene el ancho de banda.
    
- Dentro de la empresa, identifique los recursos para los dispositivos entre el cliente y el punto de salida, o identifique un contacto de emergencia con el que hablar sobre problemas de red.
    
Estas son algunas líneas base que las pruebas sencillas con herramientas pueden calcular por usted:
  
- Tiempo desde el equipo cliente hasta el punto de salida en milisegundos
    
- El tiempo desde la salida apunta a Office 365 en milisegundos
    
- Ubicación en el mundo del servidor que resuelve las direcciones URL de Office 365 al examinar
    
- La velocidad de la resolución DNS del ISP en milisegundos, incoherencias en la llegada de paquetes (vibración de red), tiempos de carga y descarga en milisegundos
    
Si no está familiarizado con cómo llevar a cabo estos pasos, vamos a entrar en más detalles en este artículo. 
  
## <a name="what-is-a-baseline"></a>¿Qué es una línea base?

Conocerá el impacto cuando salga mal, pero si no conoce los datos de rendimiento históricos, no es posible tener un contexto de lo malo que puede haber sido y cuándo. Por lo tanto, sin una línea base, te falta la clave para resolver el puzzle: la imagen en el cuadro del puzzle. En la solución de problemas de rendimiento, necesita un punto de  *comparación*  . Las líneas base de rendimiento simples no son difíciles de tomar. El equipo de operaciones puede tener la tarea de llevar a cabo estas tareas en una programación. Por ejemplo, supongamos que la conexión tiene este aspecto: 
  
![Un gráfico de red básico que muestra cliente, proxy y Office 365 nube.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Eso significa que ha comprobado con su equipo de red y ha descubierto que deja su empresa para Internet a través de un servidor proxy y que el proxy controla todas las solicitudes que el equipo cliente envía a la nube. En este caso, debe dibujar una versión simplificada de la conexión que enumera todos los dispositivos que intervienen. Ahora, inserte las herramientas que puede usar para probar el rendimiento entre el cliente, el punto de salida (donde deja la red para Internet) y la Office 365 nube.
  
![Red básica con cliente, proxy y nube, y sugerencias de herramientas PSPing, TraceTCP y seguimientos de red.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Las opciones se enumeran como **Simple** y **Advanced** debido a la cantidad de experiencia que necesita para encontrar los datos de rendimiento. Un seguimiento de red llevará mucho tiempo, en comparación con la ejecución de herramientas de línea de comandos como PsPing y TraceTCP. Estas dos herramientas de línea de comandos se han elegido porque no usan paquetes ICMP, que se bloquearán mediante Office 365, y porque dan el tiempo en milisegundos que se tarda en salir del equipo cliente o del servidor proxy (si tiene acceso) y llegar a Office 365. Cada salto individual de un equipo a otro terminará con un valor de tiempo, y eso es ideal para las líneas base. Igual de importante, estas herramientas de línea de comandos le permiten agregar un número de puerto al comando, esto es útil porque Office 365 se comunica a través del puerto 443, que es el puerto que usa la capa de sockets seguros y la seguridad de la capa de transporte (SSL y TLS). Sin embargo, otras herramientas de terceros pueden ser mejores soluciones para su situación. Microsoft no admite todas estas herramientas, por lo que si, por algún motivo, no puede hacer que PsPing y TraceTCP funcionen, pase a un seguimiento de red con una herramienta como Netmon. 
  
Puede tomar una línea base antes del horario laboral, de nuevo durante el uso intenso y, a continuación, de nuevo después del horario laboral. Esto significa que puede tener una estructura de carpetas que tenga un aspecto similar al siguiente al final:
  
![Gráfico que propone una manera de organizar los datos de rendimiento en carpetas.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
También debe elegir una convención de nomenclatura de los archivos. Estos son algunos ejemplos:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Hay muchas maneras diferentes de hacerlo, pero el uso del formato **\<dateTime\>\<what's happening in the test\>** es un buen lugar para empezar. Ser diligente con esto ayudará mucho cuando intente solucionar problemas más adelante. Más adelante, podrá decir "El 8 de febrero hice dos seguimientos, uno mostró un buen rendimiento y otro se mostró mal, por lo que podemos compararlos". Esto es extremadamente útil para solucionar problemas. 
  
Debe tener una forma organizada de mantener las líneas base históricas. En este ejemplo, los métodos simples produjeron tres salidas de línea de comandos y los resultados se recopilaron como capturas de pantalla, pero es posible que tenga archivos de captura de red en su lugar. Use el método que mejor se adapte a usted. Almacene las líneas base históricas y haga referencia a ellas en los puntos en los que observe cambios en el comportamiento de los servicios en línea. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>¿Por qué recopilar datos de rendimiento durante un piloto?

No hay mejor momento para empezar a hacer líneas base que durante un piloto del Office 365 servicio. Su oficina puede tener miles de usuarios, cientos de miles o puede tener cinco, pero incluso con un número reducido de usuarios, puede realizar pruebas para medir las variaciones en el rendimiento. En el caso de una empresa grande, una muestra representativa de varios cientos de usuarios que pilota Office 365 se puede proyectar hacia fuera a varios miles para que sepa dónde pueden surgir problemas antes de que se den.
  
En el caso de una pequeña empresa, donde el internado significa que todos los usuarios van al servicio al mismo tiempo y no hay ningún piloto, mantenga las medidas de rendimiento para que tenga datos que mostrar a cualquier persona que pueda tener que solucionar problemas de una operación de mal rendimiento. Por ejemplo, si observa que de repente puede recorrer el edificio en el tiempo que tarda en cargar un gráfico de tamaño mediano donde solía ocurrir muy rápidamente.
  
## <a name="how-to-collect-baselines"></a>Cómo recopilar líneas base

Para todos los planes de solución de problemas, debe identificar estas cosas como mínimo:
  
- El equipo cliente que está usando (el tipo de equipo o dispositivo, una dirección IP y las acciones que provocaron el problema)
    
- Donde se encuentra el equipo cliente en el mundo (por ejemplo, si este usuario en una VPN a la red, trabajando de forma remota o en la intranet de la empresa)
    
- El punto de salida que el equipo cliente usa desde la red (el punto en el que el tráfico deja su negocio para un ISP o Internet)
    
 Puede averiguar el diseño de la red desde el administrador de red. Si estás en una red pequeña, echa un vistazo a los dispositivos que te conectan a Internet y llama a tu ISP si tienes preguntas sobre el diseño. Cree un gráfico del diseño final de la referencia. 
  
Esta sección se divide en métodos y herramientas de línea de comandos sencillas y opciones de herramientas más avanzadas. En primer lugar, cubriremos métodos sencillos. Pero si tiene un problema de rendimiento en este momento, debe ir a métodos avanzados y probar el plan de acción de solución de problemas de rendimiento de ejemplo.
  
### <a name="simple-methods"></a>Métodos sencillos

El objetivo de estos métodos sencillos es aprender a tomar, comprender y almacenar correctamente líneas base de rendimiento simples con el tiempo para que esté informado sobre Office 365 rendimiento. Este es el diagrama muy sencillo para ser sencillo, como has visto antes:
  
![Red básica con cliente, proxy y nube, y sugerencias de herramientas PSPing, TraceTCP y seguimientos de red.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP se incluye en esta captura de pantalla porque es una herramienta útil para mostrar, en milisegundos, cuánto tarda una solicitud en procesarse y cuántos saltos de red, o conexiones de un equipo al siguiente, tarda la solicitud en llegar a un destino. TraceTCP también puede dar los nombres de los servidores usados durante los saltos, lo que puede ser útil para un Microsoft Office 365 de problemas en soporte técnico. > comandos TraceTCP pueden ser muy sencillos, como: >> Recuerde incluir el número de puerto  `tracetcp.exe outlook.office365.com:443` en el comando. > [TraceTCP es](https://simulatedsimian.github.io/tracetcp_download.html) una descarga gratuita, pero se basa en Wincap. Wincap es una herramienta que Netmon también usa e instala. También usamos Netmon en la sección de métodos avanzados. 
  
 Si tiene varias oficinas, también tendrá que mantener un conjunto de datos de un cliente en cada una de esas ubicaciones. Esta prueba mide la latencia, que, en este caso, es un valor numérico que describe la cantidad de tiempo entre un cliente que envía una solicitud a Office 365 y Office 365 responder a la solicitud. Las pruebas se originan dentro de su dominio en un equipo cliente y busca medir un recorrido de ida y vuelta desde dentro de la red, a través de un punto de salida, a través de Internet para Office 365 y atrás. 
  
Hay varias formas de tratar el punto de salida, en este caso, el servidor proxy. Puede realizar un seguimiento de 1 a 2 y luego de 2 a 3 y, a continuación, agregar los números en milisegundos para obtener un total final al borde de la red. O bien, puede configurar la conexión para omitir el proxy de Office 365 direcciones. En una red más grande con un firewall, un proxy inverso o una combinación de los dos, es posible que deba realizar excepciones en el servidor proxy que permitirán que el tráfico pase para una gran cantidad de direcciones URL. Para obtener la lista de puntos de conexión usados por Office 365, [vea Office 365 URL e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Si tiene un proxy de autenticación, comience probando excepciones para lo siguiente:
  
- Puertos 80 y 443
    
- TCP y HTTP
    
- Conexiones salientes a cualquiera de estas direcciones URL:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
Todos los usuarios deben tener permiso para llegar a estas direcciones sin ninguna interferencia de proxy o autenticación. En una red más pequeña, debe agregarlos a la lista de desvío de proxy en el explorador web. 
  
Para agregarlos a la lista de desvío de proxy en Internet Explorer, vaya a **Herramientas** \> **Opciones de Internet** \> **Configuración** \> **de LAN avanzada** \> . La pestaña avanzada también es donde encontrará el servidor proxy y el puerto del servidor proxy. Es posible que tenga que hacer clic en la casilla **Usar un servidor proxy para la LAN**, para obtener acceso al **botón** Avanzado. Querrá asegurarse de que está activada la opción Omitir **servidor proxy** para direcciones locales. Una vez que **haga clic en** Avanzadas, verá un cuadro de texto donde puede escribir excepciones. Separe las direcciones URL comodín enumeradas anteriormente con punto y coma, por ejemplo:
  
\*.microsoftonline.com; \*.sharepoint.com
  
Una vez que omite el proxy, debe poder usar ping o PsPing directamente en una dirección URL Office 365 usuario. El siguiente paso será probar ping **outlook.office365.com**. O bien, si usa PsPing u otra herramienta que le permitirá proporcionar un número de puerto al comando, PsPing contra **portal.microsoftonline.com:443** para ver el tiempo promedio de ida y vuelta en milisegundos. 
  
El tiempo de ida y vuelta, o RTT, es un valor numérico que mide cuánto tiempo se tarda en enviar una solicitud HTTP a un servidor como outlook.office365.com y obtener una respuesta que reconozca que el servidor sabe que lo hizo. A veces verás esto abreviado como RTT. Debe ser una cantidad de tiempo relativamente corta.
  
Debe usar [PSPing](/sysinternals/downloads/psping) u otra herramienta que no use paquetes ICMP bloqueados por Office 365 para realizar esta prueba. 
  
 **Cómo usar PsPing para obtener un tiempo de ida y vuelta general en milisegundos directamente desde una dirección URL Office 365 url**
  
1. Ejecute un símbolo del sistema con privilegios elevados completando estos pasos:
    
1. Haga clic en **Iniciar**.
    
2. En el **cuadro Iniciar búsqueda,** escriba cmd y, a continuación, presione CTRL+MAYÚS+ENTRAR.
    
3. Si aparece el cuadro de diálogo **Control de cuentas de usuario**, confirme que la acción que muestra es la que desea y, a continuación, haga clic en **Continuar**.
    
2. Navegue a la carpeta donde está instalada la herramienta (en este caso PsPing) y pruebe estas Office 365 url:
    
  - psping admin.microsoft.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![El comando PSPing va a microsoft-my.sharepoint.com puerto 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Asegúrese de incluir el número de puerto de 443. Recuerde que Office 365 funciona en un canal cifrado. Si psPing sin el número de puerto, se producirá un error en la solicitud. Una vez que hayas hecho ping en la lista corta, busca el tiempo promedio en milisegundos (ms). Eso es lo que desea grabar.
  
![Gráfico que muestra una ilustración de PSPing de cliente a proxy con un tiempo de ida y vuelta de 2,8 milisegundos.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Si no está familiarizado con la omisión de proxy y prefiere realizar las cosas paso a paso, primero debe averiguar el nombre del servidor proxy. En Internet Explorer, vaya a **Herramientas** \> **Opciones de Internet** \>  \> **Conexiones Configuración DE LAN** \> **Avanzada**. La **pestaña** Avanzadas es donde verá la lista del servidor proxy. Haga ping a ese servidor proxy en un símbolo del sistema completando esta tarea: 
  
 **Para hacer ping al servidor proxy y obtener un valor de ida y vuelta en milisegundos para la fase 1 a 2**
  
1. Ejecute un símbolo del sistema con privilegios elevados completando estos pasos:
    
1. Haga clic en **Iniciar**.
    
2. En el **cuadro Iniciar búsqueda,** escriba cmd y, a continuación, presione CTRL+MAYÚS+ENTRAR.
    
3. Si aparece el cuadro de diálogo **Control de cuentas de usuario**, confirme que la acción que muestra es la que desea y, a continuación, haga clic en **Continuar**.
    
2. Escriba ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> y, a continuación, presione ENTRAR. Si tienes psping o alguna otra herramienta instalada, puedes elegir usar esa herramienta en su lugar. 
    
    El comando puede ser parecido a cualquiera de estos ejemplos: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. Cuando el seguimiento deja de enviar paquetes de prueba, se obtiene un pequeño resumen que enumera un promedio, en milisegundos, y ese es el valor que está buscando. Haga una captura de pantalla del símbolo del sistema y guárdelo con la convención de nomenclatura. En este punto, también puede ayudar a rellenar el diagrama con el valor.
    
Tal vez haya realizado un seguimiento en la madrugada y su cliente pueda llegar rápidamente al proxy (o cualquier servidor de salida que salga a Internet). En este caso, los números pueden tener este aspecto:
  
![Gráfico que muestra el tiempo de ida y vuelta de un cliente a un proxy de 2,8 milisegundos.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Si el equipo cliente es uno de los pocos seleccionados con acceso al servidor proxy (o salida), puede ejecutar la siguiente etapa de la prueba conectándose de forma remota a ese equipo, ejecutando el símbolo del sistema en PsPing a una dirección URL de Office 365 desde allí. Si no tiene acceso a ese equipo, puede ponerse en contacto con los recursos de red para obtener ayuda con el siguiente tramo y obtener números exactos de esa manera. Si no es posible, realice un PsPing con la dirección URL de Office 365 en cuestión y compárela con el tiempo de PsPing o Ping con el servidor proxy. 
  
Por ejemplo, si tiene 51,84 milisegundos desde el cliente a la dirección URL de Office 365 y tiene 2,8 milisegundos desde el cliente hasta el proxy (o punto de salida), tiene 49,04 milisegundos desde la salida a Office 365. Del mismo modo, si tiene un PsPing de 12,25 milisegundos desde el cliente al proxy durante el alto del día y 62,01 milisegundos desde el cliente hasta la dirección URL de Office 365, el valor promedio de la salida del proxy a la dirección URL de Office 365 es de 49,76 milisegundos.
  
![Gráfico adicional que muestra el ping en milisegundos de cliente a proxy junto al cliente Office 365 para que se puedan restar los valores.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
En términos de solución de problemas, es posible que encuentre algo interesante solo para mantener estas líneas base. Por ejemplo, si encuentra que generalmente tiene entre 40 y 59 milisegundos de latencia desde el proxy o la salida, apunte a la dirección URL Office 365, y tener una latencia de punto de salida o proxy de un cliente de entre 3 y 7 milisegundos (según la cantidad de tráfico de red que esté viendo durante esa hora del día), seguramente sabrá que algo es problemático si los tres últimos clientes a las líneas base de proxy o salida muestran una latencia de 45 milisegundos.
  
### <a name="advanced-methods"></a>Métodos avanzados

Si realmente desea saber lo que está sucediendo con las solicitudes de Internet para Office 365, debe familiarizarse con los seguimientos de red. No importa qué herramientas prefiera para estos seguimientos, HTTPWatch, Netmon, Message Analyzer, Wireshark, Fiddler, Developer Dashboard tool o cualquier otra hará lo mismo siempre que esa herramienta pueda capturar y filtrar el tráfico de red. Verá en esta sección que es beneficioso ejecutar más de una de estas herramientas para obtener una imagen más completa del problema. Cuando está probando, algunas de estas herramientas también actúan como servidores proxy por su propio derecho. Las herramientas usadas en el artículo complementario, Plan de solución de problemas de rendimiento [para Office 365](performance-troubleshooting-plan.md), incluyen [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)o [WireShark](https://www.wireshark.org/).
  
Realizar una línea base de rendimiento es la parte sencilla de este método y muchos de los pasos son los mismos que cuando se soluciona un problema de rendimiento. Los métodos más avanzados para crear líneas base para el rendimiento requieren que se tomen y almacenen seguimientos de red. La mayoría de los ejemplos de este artículo usan SharePoint Online, pero debe desarrollar una lista de acciones comunes en los servicios de Office 365 a los que se suscriba para probar y registrar. Este es un ejemplo de línea base:
  
- Lista de línea base para SPO : ** Paso 1: ** Examinar la página principal del sitio web de SPO y realizar un seguimiento de red. Guarde el seguimiento. 
    
- Lista de línea base para SPO: Paso **2:** Buscar un término (como el nombre de la empresa) a través de Enterprise búsqueda y realizar un seguimiento de red. Guarde el seguimiento. 
    
- Lista de línea base para SPO: paso **3:** Upload un archivo grande a una biblioteca de documentos de SharePoint online y realice un seguimiento de red. Guarde el seguimiento. 
    
- Lista de línea base para **SPO: Paso 4:** Examinar la página principal del OneDrive web y realizar un seguimiento de red. Guarde el seguimiento. 
    
Esta lista debe incluir las acciones comunes más importantes que los usuarios llevan a cabo en SharePoint Online. Observe que el último paso, para realizar un seguimiento de OneDrive para la Empresa, crea una comparación entre la carga de la página principal de SharePoint Online (que OneDrive para la Empresa menudo las empresas personalizan) y la página principal, que rara vez se personaliza. Se trata de una prueba muy básica cuando se trata de un sitio de carga SharePoint online. Puede crear un registro de esta diferencia en las pruebas.
  
Si está en medio de un problema de rendimiento, muchos de los pasos son los mismos que al realizar una línea base. Los seguimientos de red se vuelven críticos, por lo que controlaremos  *cómo*  realizar los seguimientos importantes a continuación. 
  
Para solucionar un problema de  *rendimiento,*  en este momento, debe realizar un seguimiento en el momento en que experimenta el problema de rendimiento. Debe tener las herramientas adecuadas disponibles para recopilar registros y necesita un plan de acción, es decir, una lista de las acciones de solución de problemas que debe realizar para recopilar la mejor información que pueda. Lo primero que debe hacer es registrar la fecha y hora de la prueba para que los archivos se puedan guardar en una carpeta que refleje el tiempo. A continuación, limite los pasos del problema. Estos son los pasos exactos que usará para las pruebas. No olvide los conceptos básicos: si el problema es solo con Outlook, asegúrese de registrar que el comportamiento del problema se produce en un solo Office 365 servicio. Restringir el ámbito de este problema le ayudará a centrarse en algo que pueda resolver. 
  
## <a name="see-also"></a>Recursos adicionales

[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)