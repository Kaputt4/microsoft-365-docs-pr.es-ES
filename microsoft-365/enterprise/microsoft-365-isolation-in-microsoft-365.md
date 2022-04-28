---
title: Aislamiento y control de acceso en Microsoft 365
ms.author: robmazz
author: robmazz
manager: scotv
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: 'Resumen: explicación del aislamiento y el control de acceso dentro de las distintas aplicaciones de Microsoft 365.'
ms.openlocfilehash: dbb5ceb8b0e1e4ef6bb80ba2c3c771fc6d6cac5b
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099397"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Aislamiento y control de acceso en Microsoft 365

Azure Active Directory (Azure AD) y Microsoft 365 usan un modelo de datos muy complejo que incluye decenas de servicios, cientos de entidades, miles de relaciones y decenas de miles de atributos. En un nivel alto, Azure AD y los directorios de servicio son los contenedores de inquilinos y destinatarios que se mantienen sincronizados mediante protocolos de replicación basados en estado. Además de la información de directorio contenida en Azure AD, cada una de las cargas de trabajo de servicio tiene su propia infraestructura de servicios de directorio.
 
![Microsoft 365 sincronización de datos de inquilinos.](../media/office-365-isolation-tenant-data-sync.png)

En este modelo, no hay ningún origen único de datos de directorio. Determinados sistemas poseen fragmentos de datos individuales, pero ningún sistema único contiene todos los datos. Microsoft 365 servicios cooperan con Azure AD en este modelo de datos. Azure AD es el "sistema de verdad" para los datos compartidos, que normalmente son datos pequeños y estáticos que usan todos los servicios. El modelo federado que se usa en Microsoft 365 y Azure AD proporciona la vista compartida de los datos.

Microsoft 365 usa almacenamiento físico y almacenamiento en la nube de Azure. Exchange Online (incluidos los Exchange Online Protection) y Skype Empresarial usan su propio almacenamiento para los datos del cliente. SharePoint Online usa SQL Server almacenamiento y Azure Storage, de ahí la necesidad de aislamiento adicional de los datos de los clientes en el nivel de almacenamiento.

## <a name="exchange-online"></a>Exchange Online

Exchange Online almacena los datos del cliente en buzones de correo. Los buzones se hospedan en bases de datos extensibles del motor de Storage (ESE) denominadas bases de datos de buzones. Esto incluye buzones de usuario, buzones vinculados, buzones compartidos y buzones de carpetas públicas. Los buzones de usuario incluyen contenido Skype Empresarial guardado, como historiales de conversaciones.

El contenido del buzón de usuario incluye:

- Correos electrónicos y datos adjuntos de correo electrónico
- Calendario e información de disponibilidad
- Contactos
- Tareas
- Notas
- Grupos
- Datos de inferencia

Cada base de datos de buzones de correo de Exchange Online contiene buzones de varios inquilinos. Un código de autorización protege cada buzón de correo, incluido dentro de un inquilino. De forma predeterminada, solo el usuario asignado tiene acceso a un buzón. La lista de control de acceso (ACL) que protege un buzón contiene una identidad autenticada por Azure AD en el nivel de inquilino. Los buzones de cada inquilino se limitan a las identidades autenticadas en el proveedor de autenticación del inquilino, que incluye solo a los usuarios de ese inquilino. El contenido del inquilino A no puede obtenerse de ninguna manera por los usuarios del inquilino B, a menos que el inquilino A lo apruebe explícitamente.

## <a name="skype-for-business"></a>Skype Empresarial

Skype Empresarial almacena datos en varios lugares:

- La información de usuario y cuenta, que incluye puntos de conexión, identificadores de inquilino, planes de marcado, configuración de itinerancia, estado de presencia, listas de contactos, etc., se almacena en el Skype Empresarial servidores de Active Directory y en varios servidores de base de datos Skype Empresarial. Las listas de contactos se almacenan en el buzón de Exchange Online del usuario si el usuario está habilitado para ambos productos o en Skype Empresarial servidores si el usuario no lo está. Skype Empresarial los servidores de bases de datos no están particionados por inquilino, pero el aislamiento multiinquilino de datos se aplica a través del control de acceso basado en rol (RBAC).
- El contenido de la reunión y los datos cargados se almacenan en recursos compartidos del sistema de archivos distribuido (DFS). Este contenido también se puede archivar en Exchange Online si está habilitado. Los recursos compartidos DFS no tienen particiones por inquilino. el contenido está protegido con ACL y el multiinquilino se aplica a través de RBAC.
- Los registros de detalles de llamadas, que son el historial de actividad, como el historial de llamadas, las sesiones de mensajería instantánea, el uso compartido de aplicaciones, el historial de mensajería instantánea, etc., también se pueden almacenar en Exchange Online, pero la mayoría de los registros de detalles de llamadas se almacenan temporalmente en los servidores de registros de detalles de llamada (CDR). El contenido no se particiona por inquilino, pero el multiinquilino se aplica a través de RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online tiene varios mecanismos independientes que proporcionan aislamiento de datos. Almacena objetos como código abstracto dentro de las bases de datos de la aplicación. Por ejemplo, cuando un usuario carga un archivo en SharePoint Online, el archivo se desensambla, se traduce en código de aplicación y se almacena en varias tablas en varias bases de datos.

Si un usuario puede obtener acceso directo al almacenamiento que contiene los datos, el contenido no se puede interpretar para un usuario ni para ningún sistema que no sea SharePoint Online. Estos mecanismos incluyen el control de acceso de seguridad y las propiedades. Todos los recursos de SharePoint Online están protegidos por el código de autorización y la directiva de RBAC, incluidos los de un inquilino. La lista de control de acceso (ACL) que protege un recurso contiene una identidad autenticada en el nivel de inquilino. SharePoint los datos en línea de un inquilino se limitan a las identidades autenticadas por el proveedor de autenticación para el inquilino.

Además de las ACL, una propiedad de nivel de inquilino que especifica el proveedor de autenticación (que es el Azure AD específico del inquilino), se escribe una vez y no se puede cambiar una vez establecida. Una vez establecida la propiedad de inquilino del proveedor de autenticación para un inquilino, no se puede cambiar mediante ninguna API expuesta a un inquilino.

Se usa *un SubscriptionId* único para cada inquilino. Todos los sitios de cliente pertenecen a un inquilino y se les asigna un *SubscriptionId* único para el inquilino. La propiedad *SubscriptionId* de un sitio se escribe una vez y es permanente. Una vez asignado a un inquilino, un sitio no se puede mover a otro inquilino. *SubscriptionId* es la clave que se usa para crear el ámbito de seguridad para el proveedor de autenticación y está asociada al inquilino.

SharePoint Online usa SQL Server y Azure Storage para el almacenamiento de metadatos de contenido. La clave de partición del almacén de contenido es *SiteId* en SQL. Al ejecutar una consulta de SQL, SharePoint Online usa un *SiteId* comprobado como parte de una comprobación *SubscriptionId* de nivel de inquilino.

SharePoint Online almacena contenido de archivos cifrados en blobs Microsoft Azure. Cada granja de SharePoint Online tiene su propia cuenta de Microsoft Azure y todos los blobs guardados en Azure se cifran individualmente con una clave almacenada en el almacén de contenido de SQL. Clave de cifrado protegida en el código por la capa de autorización y no expuesta directamente al usuario final. SharePoint Online tiene supervisión en tiempo real para detectar cuándo una solicitud HTTP lee o escribe datos para más de un inquilino. Se realiza un seguimiento de *la identidad de solicitud SubscriptionId* con el *SubscriptionId* del recurso al que se accede. Las solicitudes de acceso a recursos de más de un inquilino nunca deben producirse por parte de los usuarios finales. Las solicitudes de servicio en un entorno multiinquilino son la única excepción. Por ejemplo, el rastreador de búsqueda extrae los cambios de contenido de una base de datos completa a la vez. Esto suele implicar la consulta de sitios de más de un inquilino en una única solicitud de servicio, lo que se realiza por motivos de eficacia.

## <a name="teams"></a>Teams

Los datos de Teams se almacenan de forma diferente, en función del tipo de contenido. 

Consulte la [sesión de interrupción de Ignite en Microsoft Teams arquitectura](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) para obtener una explicación detallada.

### <a name="core-teams-customer-data"></a>Datos principales Teams cliente

Si su inquilino está aprovisionado en Australia, Canadá, la Unión Europea, Francia, Alemania, India, Japón, Sudáfrica, Corea del Sur, Suiza (que incluye Liechtenstein), Emiratos Árabes Unidos, Reino Unido o el Estados Unidos, Microsoft almacena los siguientes datos de clientes en reposo solo dentro de esa ubicación:

- Teams chats, conversaciones de equipo y canal, imágenes, mensajes de correo de voz y contactos.
- Contenido del sitio de SharePoint Online y archivos almacenados en el sitio.
- Archivos cargados en OneDrive para trabajo o escuela.

#### <a name="chat-channel-messages-team-structure"></a>Chat, mensajes de canal, estructura de equipo

Cada equipo de Teams está respaldado por un grupo de Microsoft 365 y su sitio SharePoint y Exchange buzón. Los chats privados (incluidos los chats de grupo), los mensajes enviados como parte de una conversación en un canal y la estructura de los equipos y canales se almacenan en un servicio de chat que se ejecuta en Azure. Los datos también se almacenan en una carpeta oculta en los buzones de usuario y grupo para habilitar Information Protection características.

#### <a name="voicemail-and-contacts"></a>Correo de voz y contactos

Los mensajes de voz se almacenan en Exchange. Los contactos se almacenan en el almacén de datos en la nube basado en Exchange. Exchange y el almacén en la nube basado en Exchange ya proporcionan residencia de datos en cada una de las zonas geográficas del centro de datos en todo el mundo. Para todos los equipos, el correo de voz y los contactos se almacenan en el país para Australia, Canadá, Francia, Alemania, India, Japón, Emiratos Árabes Unidos, Reino Unido, Sudáfrica, Corea del Sur, Suiza (que incluye Liechtenstein) y el Estados Unidos. Para todos los demás países, los archivos se almacenan en ee. UU., Europa o Asia-Pacific ubicación en función de la afinidad de inquilino.

#### <a name="images-and-media"></a>Imágenes y medios

Los medios que se usan en los chats (excepto los GIF giphy que no se almacenan pero que son un vínculo de referencia a la dirección URL del servicio Giphy original, Giphy es un servicio que no es de Microsoft) se almacenan en un servicio multimedia basado en Azure que se implementa en las mismas ubicaciones que el servicio de chat.

#### <a name="files"></a>Archivos

Los archivos (incluidos OneNote y Wiki) que alguien comparte en un canal se almacenan en el sitio SharePoint del equipo. Los archivos compartidos en un chat privado o un chat durante una reunión o llamada se cargan y almacenan en el OneDrive para la cuenta profesional o educativa del usuario que comparte el archivo. Exchange, SharePoint y OneDrive ya proporcionan residencia de datos en cada una de las zonas geográficas del centro de datos en todo el mundo. Por lo tanto, para los clientes existentes, todos los archivos, OneNote cuadernos, Teams contenido wiki y buzones que forman parte de la experiencia de Teams ya se almacenan en la ubicación en función de la afinidad de inquilino. Los archivos se almacenan en el país para Australia, Canadá, Francia, Alemania, India, Japón, Emiratos Árabes Unidos, Reino Unido, Sudáfrica, Corea del Sur y Suiza (que incluye Liechtenstein). Para todos los demás países, los archivos se almacenan en la ubicación de EE. UU., Europa o Asia Pacífico en función de la afinidad de inquilino.
