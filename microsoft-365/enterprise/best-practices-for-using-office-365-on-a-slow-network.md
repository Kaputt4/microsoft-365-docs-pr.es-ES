---
title: Procedimientos recomendados para usar Office 365 en una red lenta
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Este artículo le guía por los procedimientos recomendados que puede adoptar para usar Office 365 en una red lenta.
ms.openlocfilehash: 5ed3a9dfc665d5067fb3f310fc74aa4b100190f2
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091641"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Procedimientos recomendados para usar Office 365 en una red lenta

¿No sería agradable que tu conexión a Internet fuera siempre rápida y nunca se haya caído? Tal vez ese día llegue. Pero mientras tanto, hay cosas prácticas que puede hacer para trabajar en torno a una red desafiado y seguir haciendo su trabajo diario. Aunque Office 365 es un servicio basado en la nube, también proporciona muchas maneras de trabajar con el contenido sin conexión y mantener sincronizados los cambios sin problemas. Además, a veces es más eficaz trabajar con contenido sin conexión solo porque las aplicaciones se ejecutan más rápido y la interfaz de usuario tiene mayor capacidad de respuesta. El punto es el siguiente: Office 365 te da lo mejor de ambos mundos. Aquí te mostremos cómo aprovechar esto.

> [!TIP]
> ¿Desea ver lo lenta (o rápida) que es la conexión de red? Pruebe la [prueba de velocidad de OOKLA](https://www.speedtest.net/) o la [aplicación de prueba de velocidad de red](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70).

## <a name="why-is-my-network-so-slow"></a>¿Por qué mi red es tan lenta?

Aunque no tiene control sobre el propio rendimiento de la red, ayuda a comprender lo que sucede en segundo plano. Internet es enormemente complejo, pero hay algunos conceptos que pueden ayudarle a entender la situación mucho mejor. Seguir los procedimientos recomendados de este artículo puede ayudar a solucionar problemas de rendimiento y reducir la frustración.

### <a name="major-factors-that-affect-network-performance"></a>Factores principales que afectan al rendimiento de la red

![Factores de rendimiento de red.](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)

 **Ancho de banda y latencia**: las dos medidas más importantes del rendimiento de la red son el ancho de banda y la latencia:

- El ancho de banda es la velocidad de rendimiento medida en bits por segundo. Más grande es mejor. El ancho de banda es como una tubería de agua. Cuanto mayor sea la tubería, más agua se puede "poner a través" de ella.

- La latencia es el tiempo que tarda el contenido en obtenerse de un servidor o servicio en el dispositivo y se mide en milisegundos. Más rápido es mejor. La latencia puede deberse a varios factores, como el bajo ancho de banda, una conexión dispersa o el tiempo de transmisión.

 **Problemas comunes**: además del ancho de banda y la latencia, otros problemas afectan al rendimiento de la red y suelen ser impredecibles. El rendimiento de la red puede fluctuar en función de la hora del día o de la ubicación física. La red se puede obstruyr cuando se producen determinados eventos que disparan el uso de Internet, como un desastre natural o un evento público importante. El tamaño y la complejidad de la página que se carga y el número y el tamaño de los archivos que se transfieren influyen directamente en el rendimiento. Una conexión WiFi puede degradarse temporalmente: por ejemplo, sondea una gran reunión de conferencias de miles solicitando a todos que tweete al mismo tiempo.

 **Consideraciones para una red por satélite**: una red por satélite es útil cuando una red terrestre no es factible, como el país de regreso, un crucero o un área científica remota. Estas redes dependen de satélites colocados en una órbita geosincrónica a 22.000 millas por encima del ecuador. Sin embargo, una transmisión realmente viaja aproximadamente 90 000 millas, por lo que una red satélite tiene una latencia más lenta (500 ms o más) que una red terrestre (20 a 50 ms). En las mejores condiciones, es posible que no observe esta latencia, pero para descargar archivos de gran tamaño, transmitir vídeos y jugar a juegos, probablemente lo hará. Otro problema es el "desvanecimiento de la lluvia" en el que el clima pesado, como tormentas de truenos y ventiscas, puede interrumpir temporalmente la transmisión por satélite.

## <a name="are-you-sure-its-the-network"></a>¿Está seguro de que es la red?

Siempre que experimente problemas de rendimiento, asegúrese primero de que el dispositivo no sea la causa principal del problema. Hay dos cosas que puede hacer que puedan hacer una gran mejora:

- Asegúrese de que el dispositivo se está ejecutando bien y de que no hay malware en el equipo.

- Si es posible, compre más memoria. Agregar memoria es la manera más sencilla y a menudo más eficaz de mejorar el rendimiento en el dispositivo. Es especialmente útil cuando se trabaja con archivos y vídeos de gran tamaño.

Para obtener más información, consulte [Windows Rendimiento y mantenimiento](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) y [Sugerencias para mejorar el rendimiento del equipo en Windows 10](https://support.microsoft.com/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Procedimientos recomendados para usar el explorador

El explorador es la puerta de enlace para Office 365, por lo que puede tener un impacto en el rendimiento, especialmente con el tiempo que se tarda en cargar una página y la frecuencia con la que se realiza un recorrido de ida y vuelta al servicio Office 365.

### <a name="browsers-in-general"></a>Exploradores en general

Estas son algunas sugerencias para exploradores en general:

- Deshabilite los complementos del explorador que puedan afectar al rendimiento o que realmente no necesite.

- Aumente el tamaño de caché de los archivos temporales de Internet.

- Una vez que haya iniciado sesión en su cuenta profesional o educativa, mantenga abierta la ventana del explorador durante todo el día. Puede abrir otras pestañas y ventanas sin volver a iniciar sesión. Si necesita iniciar sesión en otra cuenta, use Exploración privada.

- Una vez que se descargue y abra cada página, manténgalos abiertos mediante pestañas. Es fácil navegar entre pestañas y usar la página más adelante en el día. Actualice una página solo si necesita los datos más recientes en esa página.

- Si una página tarda demasiado tiempo en abrirse, detenga la descarga de la página (presione ESC) y, a continuación, actualice la página (presione F5).

- Cuando sea posible, reduzca los viajes de ida y vuelta a Office 365. Por ejemplo, en lugar de paginar a través de listas o bibliotecas, use la búsqueda para buscar archivos en una biblioteca grande y filtrar en una lista para obtener directamente los resultados que desee. O bien, cree vistas que minimicen el tiempo de carga de la página. Para obtener más información, consulte [Administración de listas y bibliotecas grandes en Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Si el rendimiento del vídeo es deficiente, es posible que pueda descargar el vídeo y verlo en el dispositivo. Puede que haya disponible un vínculo de descarga o que pueda hacer clic con el botón derecho en el vínculo de vídeo y seleccionar **Guardar destino como**.

### <a name="browser-specific"></a>Específico del explorador

Estas son algunas sugerencias para el explorador específico:

- **Internet Explorer**: actualice a Internet Explorer versión 11 o posterior para mejorar considerablemente el rendimiento con respecto a versiones anteriores. Para obtener más información, consulte [La guía de solución de problemas de Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).
- **FireFox**: para obtener más información, consulta [Firefox es lento o deja de funcionar](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging).
- **Safari**: para obtener más información, consulte [Apple - Safari](https://www.apple.com/safari/).
- **Chrome**: para obtener más información, consulte [la Ayuda de Chrome](https://support.google.com/chrome/?hl=en).

## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Procedimientos recomendados para usar Outlook y Outlook Web App

Leer, escribir y organizar el correo electrónico es una gran parte del día de todos. Tanto Outlook como Outlook Web App (OWA) ofrecen compatibilidad sin conexión. El uso de una aplicación de correo electrónico en el teléfono inteligente es otra alternativa útil. Use las siguientes opciones que mejor se adapten a sus necesidades:

- Actualice a la versión más reciente de Outlook para mejorar considerablemente el rendimiento con respecto a las versiones anteriores.

- Outlook Web App permite crear mensajes sin conexión, contactos y eventos de calendario que se cargan cuando OWA puede conectarse a Office 365. Para obtener más información sobre cómo configurar y usar OWA en modo sin conexión, consulte [Uso de Outlook Web App sin conexión](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- Outlook permite trabajar en modo almacenado en caché, en el que se conecta automáticamente siempre que sea posible. Puede hacer que Outlook descargue todo el buzón o solo una parte de él. Para obtener más información, vea [Activar el modo de Exchange almacenado en caché](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) y [Trabajar sin conexión en Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook también ofrece un modo sin conexión. Para usar esto, primero debe configurar el modo almacenado en caché para que la información de la cuenta se copie en el equipo. En el modo sin conexión, Outlook intentará conectarse mediante la configuración de envío y recepción, o cuando la establezca manualmente para que funcione en línea. Para obtener más información, vea [Trabajar sin conexión para evitar cargos de conexión de datos](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), [Cambiar la configuración de envío y recepción cuando trabaje sin conexión](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a) y [Cambiar de trabajar sin conexión a en línea](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Si tiene un teléfono inteligente, puede usarlo para evaluar el correo electrónico y el calendario a través de la red de su operador de teléfono.

> [!NOTE]
> Estas son algunas instrucciones sobre cuándo usar Outlook o OWA. Si el espacio en disco no es un problema en el dispositivo, Outlook tiene un conjunto completo de características y podría funcionar mejor para usted. Si el espacio en disco es un problema en el dispositivo, considere la posibilidad de usar OWA que tiene un subconjunto de características, pero que también funciona mejor en una situación en línea. Por supuesto, puede usar ya sea porque funcionan bien juntos.

## <a name="best-practices-for-using-onedrive-for-business"></a>Procedimientos recomendados para usar OneDrive para la Empresa

OneDrive para la Empresa está diseñado desde cero para trabajar con sus archivos en línea y sin conexión. Una vez configurado, la sincronización de los cambios se produce de forma automática y confiable en cualquier lugar y cada vez que los realice. Si la red es lenta, puede trabajar con la versión sin conexión de los archivos.

La aplicación de sincronización de OneDrive para la Empresa incluye una suscripción de SharePoint Online y Office 365 empresa, o puede [descargar](https://support.microsoft.com/kb/2903984) la aplicación de sincronización de OneDrive para la Empresa de forma gratuita. Esta aplicación también es más rápida que el uso de los comandos **Abrir en el Explorador** o **Upload**. Para obtener más información, consulte [Configuración del equipo para sincronizar los archivos de OneDrive para la Empresa en Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).

Estas son algunas instrucciones adicionales para usar la aplicación de sincronización de OneDrive para la Empresa:

- Si va a sincronizar una biblioteca grande por primera vez, inicie la sincronización durante las horas de descanso, por ejemplo, durante la noche.
- Puede usar la característica [Detener la sincronización de una biblioteca con la característica OneDrive para la Empresa aplicación](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) para detener temporalmente la sincronización de actualizaciones. Sin embargo, use esta característica durante breves períodos, como unas pocas horas a la vez, para evitar poner en cola un gran número de actualizaciones y minimizar el riesgo de conflictos de combinación si varias personas trabajan en el mismo documento.

## <a name="best-practices-for-using-onenote"></a>Procedimientos recomendados para usar OneNote

Cada sitio de equipo de SharePoint tiene un cuaderno de OneNote integrado y puede crear fácilmente el suyo propio. OneNote es una excelente manera de recopilar información oportuna que necesita cada día para realizar las tareas. Por ejemplo, muchos equipos usan OneNote como punto de recopilación para reuniones semanales, notas del proyecto, ideas, planes e informes de estado. Puede organizar claramente esta información dispare mediante páginas, secciones y pestañas.

La belleza de OneNote es que puedes acceder al contenido desde prácticamente cualquier dispositivo, ya sea un escritorio, un portátil, una tableta o un teléfono inteligente. Y no tiene que preocuparse por guardar o sincronizar porque OneNote lo hace por usted.

Para obtener más información, consulte [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Procedimientos recomendados para usar Skype Empresarial y Lync Online

Las siguientes son instrucciones generales para usar Skype Empresarial o Lync Online cuando la red es lenta:

- Use la mensajería instantánea siempre que pueda porque funciona bien en una red lenta.

- Evite realizar llamadas telefónicas a través de una red privada virtual (VPN) o conexiones de servicio de acceso remoto (RAS).

- Asegúrese de que el dispositivo de audio está aprobado. Para obtener más información, vea [Teléfonos y dispositivos calificados para Microsoft Lync](/skypeforbusiness/lync-cert/ip-phones).

- Al usar PowerPoint en una presentación en línea, reduzca el tamaño y la complejidad de las diapositivas. Para obtener más información, consulte [Sugerencias para mejorar el rendimiento de la presentación](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949).

- El rendimiento del vídeo depende en gran medida del rendimiento de la red. Evite el uso de vídeo si la red es lenta.

Para obtener más información, vea [Mala calidad de audio o vídeo en Lync Online](https://support.microsoft.com/kb/2386655) o cómo [solucionar problemas de conexión en Skype Empresarial](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).

## <a name="best-practices-for-using-sharepoint-lists"></a>Procedimientos recomendados para usar listas de SharePoint

Trabajar con datos de lista sin conexión para "limpiar", analizar o notificar datos es una excelente manera de minimizar el impacto de una red lenta. Puede leer y escribir la mayoría de las listas de Microsoft Access 2019 y Microsoft Access 2016 vinculándolas a ellas. También puede exportar una lista a una tabla de Excel, lo que crea una conexión de datos unidireccional entre la tabla Excel y la lista. Obtenga información sobre cómo [trabajar sin conexión con tablas vinculadas a listas de SharePoint](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).

Para obtener más información, consulte la sección "Más información sobre la administración de listas grandes" en [Administración de listas y bibliotecas grandes en Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).

## <a name="best-practices-for-customizing-web-pages"></a>Procedimientos recomendados para personalizar páginas web

Al personalizar una página web, puede provocar involuntariamente un rendimiento deficiente con la página. Una serie de factores pueden tener un impacto, como la complejidad y el tamaño de la página, cuántos elementos web se agregan, cuántos elementos de lista o biblioteca se muestran inicialmente y la forma en que se codifica la página.

Para obtener más información, consulte [Tune SharePoint Online performance (Ajustar el rendimiento de SharePoint Online](tune-sharepoint-online-performance.md)).

## <a name="best-practices-for-using-project-online"></a>Procedimientos recomendados para usar Project Online

Las siguientes directrices pueden ayudar a mejorar el rendimiento de la red.

- Project Online y SharePoint Online requieren sincronización, lo que puede llevar mucho tiempo. Si los equipos del proyecto tienen una rotación baja, deshabilite Project Site Sync para mejorar el rendimiento de las páginas de Project publicar y Project detalles. Limite la sincronización de Active Directory a grupos de recursos que realmente necesitan usar el sistema y supervise los posibles problemas de permisos después de la sincronización de grupos grandes.

- Si su organización usa sitios de proyecto, créelos a petición en lugar de automáticamente. Esto acelera la primera experiencia de publicación y evita la creación de sitios y contenido innecesarios.

- Project Páginas de detalles (PDP) puede desencadenar una actualización de todo el proyecto e iniciar acciones de flujo de trabajo, que pueden ser operaciones que consumen mucho rendimiento. Para evitar desencadenar dos procesos de actualización al mismo tiempo en el mismo PDP, evite actualizar los campos de calendario (Fecha de inicio, Fecha de finalización, Fecha de estado y Fecha actual) y los campos no programados (nombre del proyecto, descripción y propietario).

- Reduzca el número de campos elementos web y personalizados que se muestran en cada PDP. Cree un PDP dedicado con los únicos campos que requieren actualización para mejorar la carga y ahorrar tiempo.

- Cuando use OData para la generación de informes, limite la cantidad de datos que consulta en tiempo de ejecución mediante el filtrado del lado servidor.

Para obtener más información, vea [Ajustar el rendimiento Project Online](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).

## <a name="whats-the-best-way-to-report-problems"></a>¿Cuál es la mejor manera de notificar problemas?

Microsoft mejora continuamente el rendimiento general de Office 365 mediante la supervisión de la red, la medición del ancho de banda y la latencia, la mejora del tiempo de carga de las páginas, la reducción de la E/S de disco, el rediseño de las páginas para usar la estrategia de descarga mínima, la adición de hardware a los centros de datos y la adición de más centros de datos. Para obtener más información sobre cómo comprobar el estado actual y notificar problemas, consulte [Cómo comprobar Office 365 estado del servicio](view-service-health.md).

## <a name="see-also"></a>Vea también

[Planeamiento de red y ajuste del rendimiento para Office 365](network-planning-and-performance.md)

[Principios de conectividad de red de Office 365](microsoft-365-network-connectivity-principles.md)

[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
