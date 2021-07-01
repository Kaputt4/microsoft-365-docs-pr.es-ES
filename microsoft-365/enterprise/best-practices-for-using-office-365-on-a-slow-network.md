---
title: Procedimientos recomendados para usar Office 365 en una red lenta
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
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
description: Este artículo le guía a través de los procedimientos recomendados que puede adoptar para usar Office 365 en una red lenta.
ms.openlocfilehash: d217ee8bb40898716844717e84db112f356f6672
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226028"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Procedimientos recomendados para usar Office 365 en una red lenta

¿No sería bueno que la conexión a Internet siempre fuera rápida y nunca bajara? Tal vez ese día llegará. Pero mientras tanto, hay cosas prácticas que puede hacer para trabajar alrededor de una red desastrosa y seguir trabajando día a día. Aunque Office 365 es un servicio basado en la nube, también proporciona muchas formas de trabajar con el contenido sin conexión y mantener los cambios sincronizados sin problemas. Además, a veces es más eficaz trabajar con contenido sin conexión solo porque las aplicaciones se ejecutan más rápido y la interfaz de usuario es más dinámica. El punto es este: Office 365 te ofrece lo mejor de ambos mundos. Este es el modo de aprovecharlo.

> [!TIP]
> ¿Desea ver lo lenta (o rápida) que es la conexión de red? Pruebe la [prueba de velocidad de OOKLA](https://www.speedtest.net/) o la aplicación de prueba de velocidad de [red](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70).

## <a name="why-is-my-network-so-slow"></a>¿Por qué mi red es tan lenta?

Aunque no tiene control sobre el rendimiento de la red en sí, ayuda a comprender lo que sucede en segundo plano. Internet es enormemente complejo, pero hay algunos conceptos que pueden ayudarle a comprender la situación mucho mejor. Seguir los procedimientos recomendados de este artículo puede ayudar a solucionar problemas de rendimiento y reducir la frustración.

### <a name="major-factors-that-affect-network-performance"></a>Factores principales que afectan al rendimiento de la red

![Factores de rendimiento de red](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)

 **Ancho de banda y latencia:** las dos medidas más importantes del rendimiento de la red son el ancho de banda y la latencia:

- El ancho de banda es la velocidad de rendimiento medida en bits por segundo. Más grande es mejor. El ancho de banda es como una canalización de agua. Cuanto mayor sea la canalización, más agua podrá "pasar" por ella.

- La latencia es el tiempo que tarda el contenido en llegar desde un servidor o servicio al dispositivo y se mide en milisegundos. Más rápido es mejor. La latencia puede deberse a varios factores, como un ancho de banda bajo, una conexión escasa o el tiempo de transmisión.

 **Problemas comunes:** además del ancho de banda y la latencia, otros problemas tienen un impacto en el rendimiento de la red y a menudo son impredecibles. El rendimiento de la red puede fluctuar en función de la hora del día o de la ubicación física. La red puede quedar obstruida cuando se producen determinados eventos que pico el uso de Internet, como un desastre natural o un evento público importante. El tamaño y la complejidad de la página que se va a cargar y el número y el tamaño de los archivos que se transfieren tienen un impacto directo en el rendimiento. Una conexión WiFi puede degradarse temporalmente: por ejemplo, sondea una gran reunión de conferencia de miles solicitando a todos que tuiteen al mismo tiempo.

 **Consideraciones para una** red de satélite: una red de satélite es útil cuando una red terrestre no es viable, como el país de atrás, un crucero o un área científica remota. Estas redes dependen de satélites situados en una órbita geosynchrónica a 22.000 millas sobre el ecuador. Sin embargo, una transmisión realmente recorre unas 90.000 millas, por lo que una red satélite tiene una latencia más lenta (500 ms o más) que una red terrestre (de 20 a 50 ms). En las mejores condiciones, es posible que no observes esta latencia, pero para descargar archivos grandes, transmitir vídeos y reproducir juegos, probablemente lo harás. Otro problema es el "desvanecimiento de lluvia" en el que el tiempo intenso, como tormentas de truenos y tormentas de nieve, puede interrumpir temporalmente la transmisión por satélite.

## <a name="are-you-sure-its-the-network"></a>¿Está seguro de que es la red?

Siempre que experimentes problemas de rendimiento, primero asegúrate de que el dispositivo no sea la causa raíz del problema. Hay dos cosas que puede hacer que puedan mejorar mucho:

- Asegúrate de que el dispositivo se ejecuta bien y de que no hay malware en el equipo.

- Si es posible, compre más memoria. Agregar memoria es la forma más sencilla y a menudo más eficaz de mejorar el rendimiento en el dispositivo. Es especialmente útil cuando se trabaja con archivos y vídeos grandes.

Para obtener más información, [vea Windows Performance and maintenance](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) and Sugerencias to improve PC performance in [Windows 10](https://support.microsoft.com/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Procedimientos recomendados para usar el explorador

El explorador es la puerta de enlace a Office 365, por lo que puede tener un impacto en el rendimiento, especialmente con el tiempo que se tarda en cargar una página y la frecuencia con la que se realiza un viaje de ida y vuelta al servicio Office 365 web.

### <a name="browsers-in-general"></a>Exploradores en general

Estas son algunas sugerencias para exploradores en general:

- Deshabilite los complementos del explorador que puedan afectar al rendimiento o que realmente no necesite.

- Aumente el tamaño de caché de los archivos temporales de Internet.

- Una vez que haya iniciado sesión en su cuenta laboral o educativa, mantenga la ventana del explorador abierta durante todo el día. Puedes abrir otras pestañas y ventanas sin volver a iniciar sesión. Si necesitas iniciar sesión en otra cuenta, usa Exploración privada.

- Una vez que se descargue y abra cada página, manténlas abiertas mediante pestañas. Es fácil navegar entre pestañas y usar la página más adelante en el día. Actualice una página solo si necesita los datos más recientes de esa página.

- Si una página tarda demasiado en abrirse, detenga la descarga de la página (presione ESC) y, a continuación, actualice la página (presione F5).

- Cuando sea posible, reduzca los viajes de ida y vuelta a Office 365. Por ejemplo, en lugar de paginar a través de listas o bibliotecas, use la búsqueda para buscar archivos en una biblioteca grande y filtrar en una lista para obtener directamente los resultados que desee. O bien, cree vistas que minimicen el tiempo de carga de la página. Para obtener más información, vea [Manage large lists and libraries in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Si el rendimiento del vídeo es bajo, es posible que puedas descargar el vídeo y verlo en el dispositivo. Un vínculo de descarga puede estar disponible o puede hacer clic con el botón secundario en el vínculo de vídeo y seleccionar **Guardar destino como**.

### <a name="browser-specific"></a>Específico del explorador

Estas son algunas sugerencias para su explorador específico:

- **Internet Explorer:** actualice a Internet Explorer versión 11 o posterior para obtener mejoras sustanciales de rendimiento con respecto a las versiones anteriores. Para obtener más información, consulte [Guía de solución de problemas para Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).
- **FireFox:** Para obtener más información, consulta [Firefox es lento o deja de funcionar](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging).
- **Safari**: Para obtener más información, [consulta Apple - Safari](https://www.apple.com/safari/).
- **Chrome:** Para obtener más información, consulta [La Ayuda de Chrome](https://support.google.com/chrome/?hl=en).

## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Procedimientos recomendados para usar Outlook y Outlook Web App

Leer, escribir y organizar el correo electrónico es una parte importante del día de todos. Tanto Outlook como Outlook Web App (OWA) ofrecen compatibilidad sin conexión. El uso de una aplicación de correo electrónico en el teléfono inteligente es otra alternativa útil. Use las siguientes opciones que mejor se adapten a sus necesidades:

- Actualice a la versión más reciente de Outlook para obtener mejoras sustanciales de rendimiento con respecto a las versiones anteriores.

- Outlook Web App permite crear mensajes, contactos y eventos de calendario sin conexión que se cargan cuando OWA puede conectarse a Office 365. Para obtener más información acerca de cómo configurar y usar OWA en modo sin conexión, vea [Using Outlook Web App offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- Outlook permite trabajar en modo caché, en el que se conecta automáticamente siempre que sea posible. Puede hacer que Outlook todo el buzón o solo una parte de él. Para obtener más información, vea Activar el modo [Exchange caché](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) y Trabajar sin conexión en [Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook también ofrece un modo sin conexión. Para usar esto, primero debe configurar el modo almacenado en caché para que la información de su cuenta se copie en el equipo. En modo sin conexión, Outlook intentará conectarse con la configuración de envío y recepción, o cuando se configura manualmente para que funcione en línea. Para obtener más información, vea [Trabajar](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)sin conexión para evitar cargos por conexión de [datos,](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)Cambiar la configuración de envío y recepción cuando trabaje sin conexión y Cambiar de trabajar sin conexión a [en línea.](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)

- Si tienes un teléfono inteligente, puedes usarlo para realizar una triaje del correo electrónico y el calendario a través de la red del operador de telefonía.

> [!NOTE]
> Esta es una guía sobre cuándo usar Outlook o OWA. Si el espacio en disco no es un problema en el dispositivo, Outlook tiene un conjunto completo de características y puede funcionar mejor para ti. Si el espacio en disco es un problema en el dispositivo, considera la posibilidad de usar OWA, que tiene un subconjunto de características, pero que también funciona mejor en una situación en línea. Por supuesto, se puede usar porque funcionan bien juntos.

## <a name="best-practices-for-using-onedrive-for-business"></a>Procedimientos recomendados para usar OneDrive para la Empresa

OneDrive para la Empresa está diseñado desde cero para trabajar con los archivos en línea y sin conexión. Una vez configurado, la sincronización de los cambios se produce de forma automática y confiable en cualquier lugar y cada vez que se realicen. Si la red es lenta, puede trabajar con la versión sin conexión de los archivos.

La OneDrive para la Empresa de sincronización viene con una SharePoint online y una suscripción Office 365 [](https://support.microsoft.com/kb/2903984) empresa, o puedes descargar la OneDrive para la Empresa de sincronización de forma gratuita. Esta aplicación también es más rápida que usar los comandos **Abrir en el Explorador** o **Upload** comandos. Para obtener más información, vea [Configurar el equipo para sincronizar](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)los archivos OneDrive para la Empresa en Office 365 .

Estas son algunas instrucciones adicionales para usar la OneDrive para la Empresa de sincronización:

- Si está sincronizando una biblioteca grande por primera vez, inicie la sincronización durante horas de espera, por ejemplo, durante la noche.
- Puedes usar stop [syncing a library with the OneDrive para la Empresa app](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) feature to temporarily stop syncing updates. Sin embargo, use esta característica durante períodos breves, como unas pocas horas a la vez, para evitar hacer cola en un gran número de actualizaciones y para minimizar el riesgo de conflictos de combinación si varias personas trabajan en el mismo documento.

## <a name="best-practices-for-using-onenote"></a>Procedimientos recomendados para usar OneNote

Cada SharePoint de grupo tiene un bloc de notas integrado OneNote y puede crear fácilmente el suyo propio. OneNote es una excelente manera de recopilar información a tiempo que necesita todos los días para realizar tareas. Por ejemplo, muchos equipos usan OneNote como punto de recopilación para reuniones semanales, notas del proyecto, ideas, planes e informes de estado. Puede organizar esta información de forma clara mediante páginas, secciones y pestañas.

La mejor OneNote es que puedes acceder al contenido desde prácticamente cualquier dispositivo, ya sea un escritorio, un portátil, una tableta o un teléfono inteligente. Y no tiene que preocuparse por guardar o sincronizar porque OneNote lo hace por usted.

Para obtener más información, [vea Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Procedimientos recomendados para usar Skype Empresarial y Lync Online

Las siguientes son instrucciones generales para usar Skype Empresarial o Lync Online cuando la red es lenta:

- Usa la mensajería instantánea siempre que puedas porque funciona bien en una red lenta.

- Evite realizar llamadas telefónicas a través de una red privada virtual (VPN) o conexiones del servicio de acceso remoto (RAS).

- Asegúrate de que el dispositivo de audio esté aprobado. Para obtener más información, vea [Teléfonos y dispositivos calificados para Microsoft Lync](/skypeforbusiness/lync-cert/ip-phones).

- Al usar PowerPoint en una presentación en línea, reduzca el tamaño y la complejidad de las diapositivas. Para obtener más información, [vea Sugerencias para mejorar el rendimiento de la presentación](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949).

- El rendimiento de vídeo depende mucho del rendimiento de la red. Evite usar vídeo si la red es lenta.

Para obtener más información, vea [Mala calidad de audio](https://support.microsoft.com/kb/2386655)o vídeo en Lync Online o cómo solucionar problemas de conexión en [Skype Empresarial](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).

## <a name="best-practices-for-using-sharepoint-lists"></a>Procedimientos recomendados para usar SharePoint listas

Trabajar con datos de lista sin conexión para "limpiar", analizar o informar datos es una excelente manera de minimizar el impacto de una red lenta. Puede leer y escribir la mayoría de las listas de Microsoft Access 2019 y Microsoft Access 2016 vincularlas. También puede exportar una lista a una tabla Excel, que crea una conexión de datos uni-way entre la tabla Excel y la lista. Obtenga información sobre [cómo trabajar sin conexión con tablas vinculadas a SharePoint listas](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).

Para obtener más información, vea la sección "Más información sobre la administración de listas grandes" en [Manage large lists and libraries in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).

## <a name="best-practices-for-customizing-web-pages"></a>Procedimientos recomendados para personalizar páginas web

Al personalizar una página web, puede causar accidentalmente un rendimiento deficiente con la página. Varios factores pueden tener un impacto, como la complejidad y el tamaño de la página, cuántos elementos web se agregan, cuántos elementos de lista o biblioteca se muestran inicialmente y la forma en que codifica la página.

Para obtener más información, vea [Tune SharePoint Online performance](tune-sharepoint-online-performance.md).

## <a name="best-practices-for-using-project-online"></a>Procedimientos recomendados para usar Project Online

Las siguientes directrices pueden ayudar a mejorar el rendimiento de la red.

- Project Online y SharePoint Online requieren sincronización, lo que puede llevar mucho tiempo. Si los equipos de proyecto tienen un bajo volumen de negocio, deshabilite la sincronización Project sitio para mejorar el rendimiento Project publicar y Project páginas de detalles. Limitar la sincronización de Active Directory a grupos de recursos que realmente necesitan usar el sistema y supervisar los posibles problemas de permisos después de la sincronización de grupos grandes.

- Si su organización usa sitios de proyecto, creelos a petición en lugar de hacerlo automáticamente. Esto acelera la primera experiencia de publicación y evita la creación de sitios y contenido innecesarios.

- Project Las páginas de detalles (PDP) pueden desencadenar una actualización de todo el proyecto y iniciar acciones de flujo de trabajo, que pueden ser operaciones de alto rendimiento. Para evitar desencadenar dos procesos de actualización al mismo tiempo en el mismo PDP, evite actualizar los campos de calendario (Fecha de inicio, Fecha de finalización, Fecha de estado y Fecha actual) y los campos no programados (nombre del proyecto, descripción y propietario).

- Reduzca el número de campos elementos web y personalizados que se muestran en cada PDP. Cree un PDP dedicado con los únicos campos que requieren actualización para mejorar la carga y ahorrar tiempo.

- Cuando use OData para los informes, limite la cantidad de datos que consulta en tiempo de ejecución mediante el filtrado del lado servidor.

Para obtener más información, vea [Tune Project Online performance](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).

## <a name="whats-the-best-way-to-report-problems"></a>¿Cuál es la mejor manera de informar de problemas?

Microsoft mejora continuamente el rendimiento general de Office 365 mediante la supervisión de la red, la medición del ancho de banda y la latencia, la mejora del tiempo de carga de la página, la reducción de E/S de disco, el rediseño de páginas para usar la estrategia de descarga mínima, la adición de hardware a los centros de datos y la adición de más centros de datos. Para obtener más información sobre cómo comprobar el estado actual y los problemas de informes, vea [How to check Office 365 service health](view-service-health.md).

## <a name="see-also"></a>Vea también

[Planeamiento de red y ajuste del rendimiento para Office 365](network-planning-and-performance.md)

[Principios de conectividad de red de Office 365](microsoft-365-network-connectivity-principles.md)

[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
