---
title: Cambio de un plan de Microsoft 365 E a un plan de Microsoft 365 F
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre lo que se debe tener en cuenta y cómo prepararse si se va a cambiar a algunos de los usuarios de un plan de Microsoft 365 E a un plan de Microsoft 365 F.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 4b8580759cef1319a53eb425d20a2b0fb87d7016
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786681"
---
# <a name="changing-from-a-microsoft-365-e-plan-to-a-microsoft-365-f-plan"></a>Cambio de un plan de Microsoft 365 E a un plan de Microsoft 365 F

Si está pensando en cambiar a algunos de los usuarios de un plan de Microsoft 365 E a un plan de Microsoft 365 [F3](https://www.microsoft.com/microsoft-365/enterprise/f3) o [F1](https://www.microsoft.com/microsoft-365/enterprise/f1), este artículo proporciona instrucciones para preparar a la organización para el cambio. El cambio de un plan E a un plan F afecta a los servicios y características a los que los usuarios tienen acceso.

Los planes E están diseñados para trabajadores de la información (empleados que normalmente trabajan en un escritorio) y los planes F están diseñados para el personal de primera línea (empleados que se desplazan, que a menudo trabajan desde dispositivos móviles y directamente con clientes o con el público en general). Cada plan ir evolucionando con el tiempo para adaptarse más tanto a los trabajadores de la información como al personal de primera línea. Para obtener más información, consulte [Descripción de los tipos de usuario y las licencias del personal de primera línea](flw-licensing-options.md).

Obtendrá información general sobre lo que sucederá cuando los usuarios cambien a un plan F, cómo prepararse para dicho cambio y qué hacer después de cambiar de planes para llevar a cabo la transición del personal de primera línea de la organización.

## <a name="understand-the-key-differences-between-e-and-f-plans"></a>Comprender las principales diferencias entre los planes E y F

Empiece por familiarizarse con las diferencias en el servicio y las características de los planes.

Algunas diferencias clave incluyen:

- Los planes F no incluyen aplicaciones de escritorio de Office ni la aplicación de escritorio de Outlook.
- Los planes F se limitan a los dispositivos con pantallas integradas de menos de 10,1 pulgadas en aplicaciones móviles de Office.
- Los planes F [anclan aplicaciones del personal de primera línea](pin-teams-apps-based-on-license.md) como Walkie-talkie, Tasks, Turnos y Aprobaciones de forma predeterminada en Microsoft Teams.

En esta sección, hemos incluido más información sobre estas diferencias clave y hemos resaltado otras diferencias a las que se debe prestar atención. Tenga en cuenta que esta no es una lista completa. Para obtener más información:

- Consulte [Comparación de planes de trabajo modernos](https://go.microsoft.com/fwlink/p/?linkid=2139145) para obtener una comparación detallada de lo que se incluye tanto en los planes E como en los planes F.
- Consulte [disponibilidad del servicio](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-availability-within-each-microsoft-365-and-office-365-plan) y [disponibilidad de características en todos los planes](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description#feature-availability-across-some-plans) para obtener una lista de la disponibilidad de servicios y características en los planes E y F.

### <a name="office-apps"></a>Aplicaciones de Office

Las aplicaciones de escritorio de Office no se incluyen en los planes F3 y F1. El personal de primera línea puede usar tanto Office para la Web como las aplicaciones móviles de Office para realizar las tareas. Tenga en cuenta que los usuarios con F3 tienen acceso total a los documentos de Office para la Web y los usuarios con F1 tienen acceso de solo lectura.

|Servicio o característica|Microsoft 365 E3/E5  |Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Aplicaciones de escritorio de Office (Word, Excel, OneNote, PowerPoint, Access, Publisher)|Sí|No|No|
|Office para la Web (Word, Excel, OneNote, PowerPoint)|Sí|Sí|Solo lectura|
|Aplicaciones móviles de Office (Word, Excel, PowerPoint, Outlook, OneNote)|Sí|Sí&sup1;|Solo lectura|

&sup1;Edición de archivos compatibles con dispositivos con pantallas integradas inferiores a 10,1 pulgadas.

#### <a name="office-for-the-web"></a>Office para la web

Con Office para la Web, el personal de primera línea usa un explorador web para abrir archivos de Word, Excel, OneNote y PowerPoint.

Estas son algunas diferencias que debe tener en cuenta al usar Office para la Web. Para obtener una comparación detallada de las diferentes características de Office para la Web y de las aplicaciones de escritorio de Office, consulte [Descripción del servicio de Office para la Web](/office365/servicedescriptions/office-online-service-description/office-online-service-description).

|Servicio o característica|Algunas de las diferencias |Más información|
|---------|---------|---------|
|**Word para la web**|<ul><li> Se pueden abrir y editar documentos habilitados para macros (.docm) y plantillas (.dotm), pero las macros no se ejecutan.</li><li>Se pueden abrir pero no editar documentos protegidos con permisos definidos por el usuario (UDP) de Information Rights Management (IRM).</li></ul>|<ul><li>[Descripción del servicio de Word para la Web](/office365/servicedescriptions/office-online-service-description/word-online)</li><li>[Diferencias entre el uso de un documento en el explorador y en Word](https://support.microsoft.com//office/differences-between-using-a-document-in-the-browser-and-in-word-3e863ce3-e82c-4211-8f97-5b33c36c55f8).</li></ul>|
|**Excel para la web**|<ul><li>Se pueden abrir y editar libros habilitados para macros (.xlsm), pero las macros no se ejecutan.</li><li>[Limitaciones del tamaño de los archivos](https://support.microsoft.com/office/file-size-limits-for-workbooks-in-sharepoint-9e5bc6f8-018f-415a-b890-5452687b325e)<ul><li>Para ver o interactuar con un libro almacenado en SharePoint Online, el tamaño del libro debe ser inferior a 100 MB. </li><li>Para abrir un libro adjunto a un mensaje de correo electrónico en Outlook en la Web, el tamaño del libro debe ser inferior a 10 MB.</li></ul></ul>|<ul><li>[Descripción del servicio de Excel para la Web](/office365/servicedescriptions/office-online-service-description/excel-online)</li><li>[Diferencias entre usar un libro en el explorador y en Excel](https://support.microsoft.com/office/differences-between-using-a-workbook-in-the-browser-and-in-excel-f0dc28ed-b85d-4e1d-be6d-5878005db3b6)</li><li>La mayoría de las funciones de Excel se pueden llevar a cabo en un explorador tal como se hace en Excel. Para obtener una lista de excepciones, vea [Funciones en Excel y en Excel para la Web](https://support.microsoft.com/office/differences-between-using-a-workbook-in-the-browser-and-in-excel-f0dc28ed-b85d-4e1d-be6d-5878005db3b6#__functions).</li></ul>|
|**OneNote para la web**|<ul><li>La búsqueda está limitada a la sección actual.</li><li>Alejar y alejar no está disponible. Los usuarios podrán usar la característica de zoom de su explorador.</li></ul>|<ul><li>[Descripción del servicio de OneNote para la Web](/office365/servicedescriptions/office-online-service-description/onenote-online)</li><li>[Diferencias entre el uso de un bloc de notas en el explorador y en OneNote](https://support.microsoft.com/office/differences-between-using-a-notebook-in-the-browser-and-in-onenote-a3d1fc13-ac74-456b-b391-b633a62aa83f)</li></ul>|
|**PowerPoint para la web**|<ul><li>Se pueden abrir archivos de hasta 2 GB.</li><li>Se pueden abrir y editar presentaciones habilitadas para macros (.pptm, .potm, .ppsm), pero las macros no se ejecutan.</li></ul>|<ul><li>[Descripción del servicio de PowerPoint para la Web](/office365/servicedescriptions/office-online-service-description/powerpoint-online)</li><li>[Cómo se comportan ciertas características en PowerPoint basado en la web](https://support.microsoft.com/office/how-certain-features-behave-in-web-based-powerpoint-a931f0c8-1305-4428-8f7c-9cfa00ef28c5)</li></ul>|

#### <a name="office-mobile"></a>Office Mobile

El personal de primera línea puede obtener Office en los dispositivos móviles de dos maneras:

- Al instalar la aplicación móvil de Office que combina Word, Excel y PowerPoint.
- Al instalar aplicaciones móviles de Office individuales como Word, Excel, PowerPoint y OneNote.

Para obtener más información, consulte [Instalar y configurar Office en Android](https://support.microsoft.com/office/install-and-set-up-office-on-an-android-cafe9d6f-8b0c-4b03-b20a-12438a82a22d) e [Instalar y configurar Office en un iPhone o iPad](https://support.microsoft.com/office/install-and-set-up-office-on-an-iphone-or-ipad-9df6d10c-7281-4671-8666-6ca8e339b628).

Para obtener más información sobre las características que están disponibles en Office Mobile, consulte [Lo que se puede hacer con las aplicaciones de Office en dispositivos móviles con una suscripción de Microsoft 365](https://support.microsoft.com/office/what-you-can-do-in-the-office-apps-on-mobile-devices-with-a-microsoft-365-subscription-9ef8b63a-05fd-4f9c-bac5-29da046833ea).

#### <a name="email"></a>Correo electrónico

Los usuarios con F3 tienen un buzón de 2 GB al que pueden acceder a través de Outlook en la Web. Para obtener una comparación de las características de Outlook en la Web y de la aplicación de escritorio de Outlook, vea [Comparar Outlook para PC, Outlook en la Web y Outlook para iOS y Android](https://support.microsoft.com/office/compare-outlook-for-pc-outlook-on-the-web-and-outlook-for-ios-android-b26a7bf5-0ac7-48ba-97af-984e0645dde5).

Los usuarios con F1 no tienen derecho a buzón. Aunque se aprovisiona un buzón de correo para los usuarios a través del plan de Quiosco de Exchange, no tienen derecho a usarlo. Se recomienda [deshabilitar Outlook en la Web](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) para los usuarios con F1.

|Servicio o característica|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Buzón de correo Exchange Online|Sí (buzón de 100 GB)|Sí (buzón de 2 GB)|No&sup1;|
|Aplicación de escritorio de Outlook|Sí|No|No|
|Buzón de archivo|Sí|No|No|
|Acceso delegado|Sí|No|No|

&sup1;F1 incluye el plan de Quiosco de Exchange para habilitar solo el calendario de Teams y no incluye derechos de buzón.

Para obtener más información, consulte [Descripción del servicio de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).

#### <a name="teams"></a>Teams

Los planes F3 y F1 incluyen la aplicación de escritorio, la aplicación móvil y la aplicación web de Teams para facilitar la comunicación y colaboración del personal de primera línea. El personal de primera línea tiene acceso a las características de Teams, como reuniones, chat, canales, contenido y aplicaciones. Sin embargo, no podrá crear eventos en directo ni seminarios web ni usar las funcionalidades de Teléfono Teams.

|Servicio o característica|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Eventos en directo|Sí|No|No|
|Seminarios web|Sí|No|No|
|Teléfono Teams|Sí|No|No|

#### <a name="sharepoint"></a>SharePoint

Los usuarios con F3 y F1 pueden colaborar en documentos y acceder a los recursos de toda la organización, como materiales de entrenamiento almacenados en SharePoint. Tenga en cuenta que los planes F3 y F1 no incluyen buzones de sitio ni sitios personales.

|Servicio o característica|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Site mailbox|Sí|No|No|
|Sitio personal|Sí|No|No|

Para obtener más información sobre los límites de SharePoint, consulte [Límites de SharePoint](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).

#### <a name="content-services"></a>Servicios de contenido

Los usuarios con F3 y F1 disponen de 2 GB de almacenamiento en OneDrive para almacenar y compartir archivos. Para obtener más información, consulte [Descripción del servicio de OneDrive](/office365/servicedescriptions/onedrive-for-business-service-description).

|Servicio o característica|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|OneDrive|Almacenamiento ilimitado&sup1;|2 GB de almacenamiento|2 GB de almacenamiento|
|Microsoft Stream|Sí|Sí&sup2;|Sí&sup2;|
|Sway|Sí|Sí|No|
|Visio para la web|Sí|Sí|Solo lectura|
|Delve|Sí|No|No|

&sup1;Hasta 5 TB de almacenamiento inicial en OneDrive por usuario en función de la [cuota predeterminada](/onedrive/set-default-storage-space) del inquilino para las suscripciones con más de cinco usuarios. Se puede solicitar más almacenamiento.</br>
&sup2;Los usuarios pueden grabar reuniones y consumir contenido de Stream, pero no pueden publicar ni compartir en Stream.

#### <a name="insights-and-analytics"></a>Insights y Análisis

|Servicio o característica|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Ideas Viva|Sí|No|No|
|Power BI|Sí|No|No|

#### <a name="work-management-and-automation"></a>Administración y automatización del trabajo

|Servicio o característica|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Power Apps|Sí|Sí|No|
|Power Automate|Sí|Sí|No|
|Power Virtual Agents|Sí|Sí|No|
|Dataverse para Teams|Sí|Sí|No|
|Microsoft Forms|Sí&sup1;|Sí&sup1;|No|
|Microsoft To Do|Sí|Sí|No|

&sup1;Los usuarios con licencia pueden crear, compartir y gestionar formularios. No se necesita una licencia para completar o responder a un formulario.

#### <a name="windows"></a>Windows

|Servicio o característica|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Windows 11 Enterprise|Sí|Sí&sup1;|No|

&sup1;Sin Canal de mantenimiento a largo plazo (LTSC) ni Microsoft Desktop Optimization Pack (MDOP). Infraestructura de escritorio virtual (VDI) solo para usuarios con licencia de un dispositivo compartido con Calidad de servicio (QoS), (excepto Para Azure Virtual Desktop).

## <a name="what-to-expect"></a>Qué esperar

En la tabla siguiente se enumeran los aspectos importantes que se deben tener en cuenta y las acciones recomendadas que se deben realizar durante el proceso de cambio. Use esta información para poder identificar qué hacer antes del cambio y planificar qué hacer una vez completado dicho cambio. 

Nos referiremos a esta tabla en secciones posteriores de este artículo.

|Servicio o característica |Antes del cambio|Después del cambio|
|---------|---------|---------|
|Aplicaciones de Office| <ul><li>Identifique los archivos almacenados en los equipos locales de los usuarios y ayude a los usuarios a moverlos a OneDrive.</li><li>Tenga en cuenta que las aplicaciones de escritorio de Office pasarán al modo de funcionalidad reducida después de cambiar a un plan F. Prepárese para desinstalar las aplicaciones de escritorio de Office después del cambio.</li></ul>| Usuarios:</br> <ul><li>Iniciar sesión en [office.com](https://www.office.com) para acceder a Office para la Web.</li><li>[Instalar y usar las aplicaciones móviles de Office](https://support.microsoft.com/office/set-up-office-apps-and-email-on-a-mobile-device-7dabb6cb-0046-40b6-81fe-767e0b1f014f) (si es que aún no se ha hecho).</li><li>Los usuarios también pueden colaborar directamente en documentos de bibliotecas de documentos de SharePoint, OneDrive, Teams y Yammer.</li></ul>Administradores:<ul><li>Desinstalar las aplicaciones de escritorio de Office de los equipos de los usuarios.</li></ul>      |
|Email, Exchange, Outlook|<ul><li>Identificar los buzones de correo de usuario de más de 2 GB mediante el cmdlet [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps) de Exchange PowerShell y, luego, reducir el tamaño del buzón, según sea necesario. Para más información, consulte [Límites de almacenamiento de buzones en Outlook en la Web](https://support.microsoft.com/office/mailbox-storage-limits-in-outlook-on-the-web-f170fe90-b859-4034-bcda-e186fc6a26f5).</li><li>Si los usuarios tienen un buzón de archivo:</li><ul><li>Volver a mover el contenido del buzón de archivo al buzón del usuario.</li><li>Comprueben si hay directivas de archivo que puedan mover automáticamente el correo electrónico en función de la antigüedad de los mensajes mediante el cmdlet [Get-EXOMailbox](/powershell/module/exchange/get-exomailbox?view=exchange-ps) Exchange Online PowerShell.</li></ul> <li>Identificar el acceso y el uso del buzón de sitio.</li><li>Aplicación de escritorio de Outlook, datos y configuración:</li><ul><li>Identificar usuarios y equipos que usan archivos de datos de Outlook (.pst).</li><li>Identificar y documentar las reglas existentes de solo cliente de Outlook.</li><li>Exportar firmas de correo electrónico.</li></ul></ul>|Usuarios:</br><ul><li>Iniciar sesión en [office.com](https://www.office.com) para acceder a Outlook en la Web.</li><li>[Configurar el correo electrónico en dispositivos móviles](https://support.microsoft.com/office/set-up-office-apps-and-email-on-a-mobile-device-7dabb6cb-0046-40b6-81fe-767e0b1f014f) (si aún no se ha hecho).</li><li>Comprobar y actualizar las firmas de correo.</li><li>Comprobar y actualizar las reglas de buzón.</li></ul>Administradores:<ul><li> [Deshabilitar Outlook en la Web](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) para los usuarios con F1 y pedirles que no accedan al buzón a través de ningún otro método.</li></ul>|
|Teams | <ul><li>Identificar el uso de eventos en directo y seminarios web.</li><li>Identificar a los usuarios que tienen habilitado Teléfono Teams. Si los usuarios usan esta característica, quizás no deban realizar la transición a un plan F.</li></ul>      ||
|OneDrive | <ul><li>Identificar a los usuarios que usan alrededor de 2 GB o más de almacenamiento. (OneDrive se convertirá en solo lectura para los usuarios que superen el límite de 2 GB después del cambio a un plan F).</li><li>Ayude a los usuarios a reducir el número de archivos almacenados en OneDrive y la cantidad total de almacenamiento utilizado.</li><li>Asegúrese de que todos los archivos están totalmente sincronizados desde los equipos de los usuarios a OneDrive.</li></ul>| |

## <a name="prepare-to-switch-plans"></a>Prepararse para cambiar de planes

### <a name="create-a-change-management-strategy"></a>Crear una estrategia de administración de cambios

Una estrategia de administración de cambios óptima incluye cómo se comunicarse, entrenar y dar soporte a los usuarios antes y después de cambiarlos a un plan F. Por ejemplo, estos son algunos aspectos que se deben tener en cuenta:

- ¿Cómo se les dará a conocer a los usuarios el cambio?
- ¿Cómo sabrán los usuarios las diferencias en los servicios y características? El cambio a un plan F podría necesitar un mayor esfuerzo en el entrenamiento, ya que requiere un cambio de comportamiento.
- ¿Cómo obtendrán los usuarios ayuda y soporte técnico?

Al crear la estrategia, tenga en cuenta las preferencias de comunicación y de entrenamiento. Para ayudar a garantizar una transición correcta, adapte la mensajería, entrenamiento y soporte técnico a las necesidades específicas del personal de primera línea y de la cultura de la empresa.

Estas son algunas ideas que le ayudarán a planear la estrategia.

|Comunicación|Formación|Soporte técnico|
|---------|---------|---------|
|<ul><li>Correo electrónico</li><li>Supervisores de departamentos o de tiendas</li><li>Expertos</li><li>Equipos y canales</li><li>Comunidades de Yammer</li></ul> |<ul><li>Recursos de vídeo, aprendizaje y ayuda en línea de Microsoft</li><li>Formación interna</li></ul>|<ul><li>Departamento de soporte técnico interno</li><li>Sitio de intranet de autoservicio</li><li>Recursos de vídeo, aprendizaje y ayuda en línea de Microsoft</li><li>Gerentes y expertos</li></ul>         |

Quizás quiera consultar estos recursos de adopción para ayudarle en la interacción y entrenamiento de los usuarios:

- [Microsoft 365: Adopción de Microsoft](https://adoption.microsoft.com/microsoft-365/)
- [Teams para personal de primera línea: Adopción de Microsoft](https://adoption.microsoft.com/microsoft-teams/frontline-workers/)

### <a name="back-up-or-prepare-data"></a>Copia de seguridad o preparación de datos

Identifique y realice copias de seguridad o prepare los datos que los usuarios desean conservar. Siga las instrucciones de la sección [Qué esperar](#what-to-expect) que se encuentra en este artículo y complete las acciones recomendadas en la columna **Antes del cambio** de la tabla para cada uno de los componentes siguientes:

- Aplicaciones de Office
- Email, Exchange, Outlook
- Teams
- OneDrive

Para obtener más información, consulte [Copia de seguridad de los datos antes de cambiar de plan](/microsoft-365/commerce/subscriptions/move-users-different-subscription).

## <a name="switch-users-to-a-microsoft-365-f-plan"></a>Cambiar usuarios a un plan de Microsoft 365 F

Puede usar el centro de administración de Microsoft 365 para cambiar manualmente los planes o usar scripts mediante cmdlets de PowerShell. Sea cual sea el método que elija, es importante completar la asignación de cambios de licencia en una sola operación. Es decir, quitar una licencia E existente y reemplazarla asignando una licencia F en la misma operación.

Evite quitar una licencia existente para un usuario y, luego, reasignarle una nueva más adelante. Esto puede afectar a los datos de un usuario. Para obtener más información, consulte [¿Qué ocurre con los datos de un usuario al quitarle la licencia?](/microsoft-365/admin/manage/remove-licenses-from-users?view=o365-worldwide#what-happens-to-a-users-data-when-you-remove-their-license).

Para obtener instrucciones paso a paso sobre cómo cambiar los planes en el centro de administración de Microsoft, consulte [Cambiar los planes de Microsoft de forma manual](/microsoft-365/commerce/subscriptions/change-plans-manually).

## <a name="what-to-do-after-switching-plans"></a>Qué hacer después de cambiar de plan

Siga las instrucciones de la sección [Qué esperar](#what-to-expect) que se encuentra en este artículo y complete las acciones recomendadas en la columna **Después del cambio** de la tabla para cada uno de los componentes siguientes:

- Aplicaciones de Office
- Email, Exchange, Outlook
- Teams
- OneDrive

Comunique a los usuarios que el cambio se ha completado y hágales saber cómo obtener ayuda según lo que se haya definido en la estrategia de administración de cambios. Quizás es conveniente incluir los vínculos a los [recursos de ayuda y formación](#user-setup-help-and-learning-resources) para ayudarles en la transición.

## <a name="user-setup-help-and-learning-resources"></a>Recursos de configuración, ayuda y formación del usuario

Estos son algunos vínculos a los recursos de configuración, ayuda y formación que puede compartir con el personal de primera línea para brindarles entrenamiento y soporte técnico.

|Aplicación|Vínculos |
|---------|---------|
|Office para la web|<ul><li>[Aprendizaje de Office para la Web](https://support.microsoft.com/office/office-for-the-web-training-e315b031-2bd5-40a1-99ca-264ebf2c8f96)</li><li>[Introducción a Office para la Web en Microsoft 365](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)</li></ul>|
|Outlook en la Web|<ul><li>[Familiarizarse con Outlook en la Web](https://support.microsoft.com/office/get-to-know-outlook-on-the-web-3f1a229b-0d60-438f-b515-dd7a28026bc1)</li><li>[Obtener ayuda con Outlook en la Web](https://support.microsoft.com/office/get-help-with-outlook-on-the-web-cf659288-35cc-4c6c-8c75-e8e4317fda11)</li><li>[Vídeos de Outlook en la Web](https://support.microsoft.com/office/learn-more-about-outlook-on-the-web-adbacbab-fe59-4259-a550-6cb7f85f19ec)</li></ul>|
|Office Mobile|Configuración:</br><ul><li>[Configurar las aplicaciones de Office y de correo electrónico en Android](https://support.microsoft.com/office/set-up-office-apps-and-email-on-android-6ef2ebf2-fc2d-474a-be4a-5a801365c87f)</li><li>[Configurar las aplicaciones de Office y de correo electrónico en dispositivos iOS](https://support.microsoft.com/office/set-up-the-office-app-and-outlook-on-ios-devices-0402b37e-49c4-4419-a030-f34c2013041f)</li></ul>Ayuda de la aplicación móvil de Office:<ul><li>[Ayuda de la aplicación móvil de Office para Android](https://support.microsoft.com/office/microsoft-office-app-for-android-0383d031-a1c6-46c9-b734-53cd1d22765b)</li><li>[Ayuda de la aplicación de Office para iOS](https://support.microsoft.com/office/microsoft-office-app-for-ios-c8880c05-883a-46b6-ad32-9bffa31228d0)</li></ul>Ayuda de la aplicación móvil de Office individual:<ul><li>[Word para teléfonos Android](https://support.microsoft.com/office/word-for-android-phones-help-764afb31-ad50-4645-8f51-820ecf731d8f), [Word para tabletas Android](https://support.microsoft.com/office/word-for-android-tablets-help-8a0dcd56-fb32-4e0d-95d8-997c066125c8),[Word para iPhone](https://support.microsoft.com/office/word-for-iphone-help-d41a5299-f6fa-4cca-b529-46a8069c5796), [Word para iPad](https://support.microsoft.com/office/word-for-ipad-help-6567cf2a-c949-4213-912d-f7a14f6264c5)</li><li>[Excel para teléfonos Android](https://support.microsoft.com/office/excel-for-android-phones-help-f818cb37-bfac-485d-8480-363b3da40596), [Excel para tabletas Android](https://support.microsoft.com/office/word-for-android-tablets-help-8a0dcd56-fb32-4e0d-95d8-997c066125c8), [Excel para iPhone](https://support.microsoft.com/office/excel-for-iphone-help-b367819b-05b4-4a56-ab1c-678da62e1fd3), [Excel para iPad](https://support.microsoft.com/office/excel-for-ipad-help-6b5dc2e1-a8e4-48e6-bb69-cb9a3964bc91)</li><li>[PowerPoint para teléfonos Android](https://support.microsoft.com/office/powerpoint-for-android-phones-help-f6714e00-0ee2-48d1-bd3d-e1997565861f), [PowerPoint para tabletas Android](https://support.microsoft.com/office/powerpoint-for-android-tablets-help-2ada1d22-3784-4943-bc47-9d1ede42875c), [PowerPoint para iPhone](https://support.microsoft.com/office/powerpoint-for-iphone-help-754fcb37-783b-4e8a-afca-edb900221b8b), [PowerPoint para iPad](https://support.microsoft.com/office/powerpoint-for-ipad-help-b75ce3bb-03e3-46df-a792-647573fef84a)</li><li>[OneNote para Android](https://support.microsoft.com/office/microsoft-onenote-for-android-46b4b49d-2bef-4746-9c30-6abb5e20b688), [OneNote para iPhone](https://support.microsoft.com/office/microsoft-onenote-for-iphone-b93a0ea8-1285-4d31-a7c5-86a849731902), [OneNote para iPad](https://support.microsoft.com/office/microsoft-onenote-help-ipad-f44e5bcd-5203-4553-9de4-0c56e6500825)</li></ul>
|Teams|<ul><li>[Vídeos de aprendizaje de Teams](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)</li><li>[Ayuda y formación de Teams](https://support.microsoft.com/teams)</li></ul>|

