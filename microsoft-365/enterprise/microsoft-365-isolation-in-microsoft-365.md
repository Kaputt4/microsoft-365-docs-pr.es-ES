---
title: Aislamiento y control de acceso en Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: 'Resumen: una explicación del aislamiento y el control de acceso dentro de las distintas aplicaciones de Microsoft 365.'
ms.openlocfilehash: 53f60c09b94bdcc2515bcc5ff70dfbcd47f42bb4
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332333"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Aislamiento y control de acceso en Microsoft 365

Azure Active Directory (Azure AD) y Microsoft 365 usan un modelo de datos muy complejo que incluye decenas de servicios, cientos de entidades, miles de relaciones y decenas de miles de atributos. En un nivel alto, Azure AD y los directorios de servicio son los contenedores de inquilinos y destinatarios que se mantienen sincronizados mediante protocolos de replicación basados en estado. Además de la información de directorio que se mantiene en Azure AD, cada una de las cargas de trabajo de servicio tiene su propia infraestructura de servicios de directorio.
 
![Sincronización de datos del espacio empresarial de Microsoft 365](../media/office-365-isolation-tenant-data-sync.png)

Dentro de este modelo, no hay un único origen de datos de directorio. Los sistemas específicos poseen datos individuales, pero ningún sistema único contiene todos los datos. Los servicios de Microsoft 365 colaboran con Azure AD en este modelo de datos. Azure AD es el "sistema de verdad" para los datos compartidos, que normalmente son datos pequeños y estáticos que usan todos los servicios. El modelo federado usado en Microsoft 365 y Azure AD proporciona la vista compartida de los datos.

Microsoft 365 usa tanto el almacenamiento físico como el almacenamiento en la nube de Azure. Exchange Online (incluido Exchange Online Protection) y Skype Empresarial usan su propio almacenamiento para los datos de los clientes. SharePoint Online usa tanto SQL Server almacenamiento como Azure Storage, por lo que es necesario un aislamiento adicional de los datos de los clientes en el nivel de almacenamiento.

## <a name="exchange-online"></a>Exchange Online

Exchange Online almacena datos de clientes en buzones. Los buzones se hospedan en bases de datos del Motor de almacenamiento extensible (ESE) denominadas bases de datos de buzones de correo. Esto incluye buzones de usuario, buzones vinculados, buzones compartidos y buzones de carpetas públicas. Los buzones de usuario incluyen contenido guardado de Skype Empresarial, como historiales de conversaciones.

El contenido del buzón de usuario incluye:

- Correos electrónicos y datos adjuntos de correo electrónico
- Calendario e información de disponibilidad
- Contactos
- Tareas
- Notas
- Grupos
- Datos de inferencia

Cada base de datos de buzones de Exchange Online contiene buzones de varios inquilinos. Un código de autorización protege cada buzón, incluido dentro de un arrendamiento. De forma predeterminada, solo el usuario asignado tiene acceso a un buzón. La lista de control de acceso (ACL) que protege un buzón contiene una identidad autenticada por Azure AD en el nivel de inquilino. Los buzones de cada inquilino se limitan a las identidades autenticadas en el proveedor de autenticación del inquilino, que incluye solo a los usuarios de ese inquilino. Los usuarios del espacio empresarial B no pueden obtener de ninguna manera el contenido del espacio empresarial A, a menos que el inquilino A lo apruebe explícitamente.

## <a name="skype-for-business"></a>Skype Empresarial

Skype Empresarial almacena datos en varios lugares:

- La información de cuentas y usuarios, que incluye puntos de conexión, identificadores de inquilino, planes de marcado, configuración de itinerancia, estado de presencia, listas de contactos, etc., se almacena en los servidores de Active Directory de Skype Empresarial y en varios servidores de bases de datos de Skype Empresarial. Las listas de contactos se almacenan en el buzón de Exchange Online del usuario si el usuario está habilitado para ambos productos o en servidores de Skype Empresarial si el usuario no lo está. Los servidores de bases de datos de Skype Empresarial no están particionados por inquilino, pero el aislamiento multiinquilino de los datos se aplica a través del control de acceso basado en roles (RBAC).
- El contenido de la reunión y los datos cargados se almacenan en recursos compartidos del Sistema de archivos distribuido (DFS). Este contenido también se puede archivar en Exchange Online si está habilitado. Los recursos compartidos DFS no están particionados por inquilino. el contenido se protege con ACL y la multiinquilino se aplica a través de RBAC.
- Los registros de detalles de llamadas, que son el historial de actividades, como el historial de llamadas, las sesiones de mensajería instantánea, el uso compartido de aplicaciones, el historial de mensajería instantánea, etc., también se pueden almacenar en Exchange Online, pero la mayoría de los registros de detalles de llamadas se almacenan temporalmente en servidores de registro de detalles de llamadas (CDR). El contenido no se particiona por inquilino, pero la multiinquilino se aplica a través de RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online tiene varios mecanismos independientes que proporcionan aislamiento de datos. Almacena objetos como código abstracto en las bases de datos de la aplicación. Por ejemplo, cuando un usuario carga un archivo en SharePoint Online, el archivo se desensambla, se traduce en código de aplicación y se almacena en varias tablas en varias bases de datos.

Si un usuario puede obtener acceso directo al almacenamiento que contiene los datos, el contenido no se puede interpretar para un usuario o cualquier otro sistema que no sea SharePoint Online. Estos mecanismos incluyen propiedades y control de acceso de seguridad. Todos los recursos de SharePoint Online están protegidos por el código de autorización y la directiva RBAC, incluido dentro de un arrendamiento. La lista de control de acceso (ACL) que protege un recurso contiene una identidad autenticada en el nivel de inquilino. Los datos de SharePoint Online para un inquilino se limitan a las identidades autenticadas por el proveedor de autenticación para el inquilino.

Además de las ACL, una propiedad de nivel de inquilino que especifica el proveedor de autenticación (que es Azure AD específico del inquilino), se escribe una vez y no se puede cambiar una vez establecida. Una vez establecida la propiedad de inquilino del proveedor de autenticación para un inquilino, no se puede cambiar con ninguna API expuesta a un inquilino.

Se usa *un SubscriptionId* único para cada inquilino. Todos los sitios de cliente son propiedad de un inquilino y se les asigna *un SubscriptionId* único para el inquilino. La *propiedad SubscriptionId* de un sitio se escribe una vez y es permanente. Una vez asignado a un inquilino, un sitio no se puede mover a otro inquilino. SubscriptionId *es* la clave que se usa para crear el ámbito de seguridad para el proveedor de autenticación y está vinculado al inquilino.

SharePoint Online usa SQL Server Azure Storage para el almacenamiento de metadatos de contenido. La clave de partición del almacén de contenido es *SiteId* en SQL. Al ejecutar una consulta SQL, SharePoint Online usa un *SiteId* comprobado como parte de una comprobación *subscriptionId* de nivel de inquilino.

SharePoint Online almacena contenido de archivos cifrados en blobs de Microsoft Azure. Cada granja de servidores de SharePoint Online tiene su propia cuenta de Microsoft Azure y todos los blobs guardados en Azure se cifran individualmente con una clave almacenada en el SQL de contenido. La clave de cifrado protegida en el código por la capa de autorización y no expuesta directamente al usuario final. SharePoint Online tiene supervisión en tiempo real para detectar cuándo una solicitud HTTP lee o escribe datos para más de un inquilino. Se realiza un seguimiento de la identidad de solicitud *SubscriptionId* con *el SubscriptionId* del recurso al que se ha accedido. Las solicitudes de acceso a los recursos de más de un inquilino nunca deben suceder por parte de los usuarios finales. Las solicitudes de servicio en un entorno multiinquilino son la única excepción. Por ejemplo, el rastreador de búsqueda extrae los cambios de contenido de una base de datos completa a la vez. Esto suele implicar la consulta de sitios de más de un inquilino en una sola solicitud de servicio, que se realiza por motivos de eficiencia.

## <a name="teams"></a>Teams

Los datos de Teams se almacenan de forma diferente, según el tipo de contenido. 

Consulte la sesión [de interrupción de Ignite](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) sobre la arquitectura de Microsoft Teams para obtener una explicación detallada.

### <a name="core-teams-customer-data"></a>Datos de clientes principales de Teams

Si su espacio empresarial está aprovisionado en Australia, Canadá, la Unión Europea, Francia, Alemania, India, Japón, Sudáfrica, Corea del Sur, Suiza (que incluye Liechtenstein), Los Emiratos Árabes Unidos, Reino Unido o Estados Unidos, Microsoft almacena los siguientes datos de cliente en reposo solo en esa ubicación:

- Chats de Teams, conversaciones de equipo y canal, imágenes, mensajes de correo de voz y contactos.
- Contenido del sitio de SharePoint Online y archivos almacenados en el sitio.
- Archivos cargados en OneDrive para trabajo o escuela.

#### <a name="chat-channel-messages-team-structure"></a>Chat, mensajes de canal, estructura del equipo

Cada equipo de Teams cuenta con el respaldo de un grupo de Microsoft 365 y su sitio de SharePoint y buzón de Exchange. Los chats privados (incluidos los chats de grupo), los mensajes enviados como parte de una conversación en un canal y la estructura de los equipos y canales se almacenan en un servicio de chat que se ejecuta en Azure. Los datos también se almacenan en una carpeta oculta en los buzones de usuario y grupo para habilitar las características de Information Protection.

#### <a name="voicemail-and-contacts"></a>Correo de voz y contactos

Los correos de voz se almacenan en Exchange. Los contactos se almacenan en el almacén de datos en la nube basado en Exchange. Exchange y el almacén en la nube basado en Exchange ya proporcionan residencia de datos en cada una de las ubicaciones geográficas del centro de datos mundial. Para todos los equipos, el correo de voz y los contactos se almacenan en el país para Australia, Canadá, Francia, Alemania, India, Japón, Emiratos Árabes Unidos, Reino Unido, Sudáfrica, Corea del Sur, Suiza (que incluye Liechtenstein) y Estados Unidos. Para todos los demás países, los archivos se almacenan en Estados Unidos, Europa o Asia-Pacific en función de la afinidad de inquilinos.

#### <a name="images-and-media"></a>Imágenes y medios

Los medios usados en chats (excepto los GIF de Giphy que no se almacenan pero son un vínculo de referencia a la dirección URL del servicio Giphy original, Giphy es un servicio que no es de Microsoft) se almacena en un servicio multimedia basado en Azure que se implementa en las mismas ubicaciones que el servicio de chat.

#### <a name="files"></a>Archivos

Los archivos (incluidos OneNote y Wiki) que alguien comparte en un canal se almacenan en el sitio de SharePoint del equipo. Los archivos compartidos en un chat privado o en un chat durante una reunión o llamada se cargan y almacenan en la cuenta de OneDrive para el trabajo o la escuela del usuario que comparte el archivo. Exchange, SharePoint y OneDrive ya proporcionan residencia de datos en cada una de las ubicaciones geográficas de centros de datos en todo el mundo. Por lo tanto, para los clientes existentes, todos los archivos, blocs de notas de OneNote, contenido wiki de Teams y buzones que forman parte de la experiencia de Teams ya se almacenan en la ubicación en función de la afinidad de su espacio empresarial. Los archivos se almacenan en el país para Australia, Canadá, Francia, Alemania, India, Japón, Los Emiratos Árabes Unidos, Reino Unido, Sudáfrica, Corea del Sur y Suiza (que incluye Liechtenstein). Para todos los demás países, los archivos se almacenan en la ubicación de Estados Unidos, Europa o Asia Pacífico en función de la afinidad de inquilinos.
