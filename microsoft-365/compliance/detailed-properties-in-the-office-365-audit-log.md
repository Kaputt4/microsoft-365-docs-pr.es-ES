---
title: Propiedades detalladas del registro de auditoría
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: En este artículo se proporcionan descripciones de propiedades adicionales incluidas al exportar los resultados de un registro de auditoría de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 250db03e7d330ed013909925b44f8d9843f1197d
ms.sourcegitcommit: 5480982967a90ca3060a59676a6b29155f2de861
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49350706"
---
# <a name="detailed-properties-in-the-audit-log"></a>Propiedades detalladas del registro de auditoría

Al exportar los resultados de una búsqueda de registro de auditoría desde el Centro de seguridad y cumplimiento de &, tiene la opción de descargar todos los resultados que cumplen los criterios de búsqueda. Para ello, seleccione Exportar **resultados** Descargue \> **todos los resultados** en la página **Búsqueda del registro de** auditoría. Para obtener más información, vea [Buscar en el registro de auditoría.](search-the-audit-log-in-security-and-compliance.md)
  
 Al exportar todos los resultados de una búsqueda de registro de auditoría, los datos sin procesar del registro de auditoría unificado se copian en un archivo de valores separados por comas (CSV) que se descarga en el equipo local. Este archivo contiene información adicional de cada registro de auditoría en una columna denominada **AuditData**. Esta columna contiene una propiedad de varios valores para varias propiedades del registro de auditoría. Cada uno de los **pares de valor de la propiedad:** en esta propiedad de varios valores se separan mediante una coma. 
  
En la tabla siguiente se describen las propiedades que se incluyen (según el servicio en el que se produzca un evento) en la columna **AuditData** de varias propiedades. El **servicio de Office 365** que tiene esta columna de propiedad indica el servicio y el tipo de actividad (usuario o administrador) que incluye la propiedad. Para obtener información más detallada sobre estas propiedades o sobre las propiedades que pueden no aparecer en este tema, vea El esquema de [la API de actividad de administración.](https://go.microsoft.com/fwlink/p/?LinkId=717993)
  
> [!TIP]
> Puede usar la característica de transformación JSON en Power Query en Excel para dividir la columna **AuditData** en varias columnas para que cada propiedad tenga su propia columna. Esto le permitirá ordenar y filtrar en una o más de estas propiedades. Para obtener información sobre cómo hacerlo, vea [Exportar, configurar y ver registros de registro de auditoría.](export-view-audit-log-records.md) 
  
|**Propiedad**|**Descripción**|**Servicio de Microsoft 365 que tiene esta propiedad**|
|:-----|:-----|:-----|
|Actor|El usuario o la cuenta de servicio que realizó la acción.|Azure Active Directory|
|AddOnName|El nombre de un complemento que se agregó, quitó o actualizó en un equipo. El tipo de complementos en Microsoft Teams es un bot, un conector o una pestaña.|Microsoft Teams|
|AddOnType|El tipo de un complemento que se agregó, quitó o actualizó en un equipo. Los siguientes valores indican el tipo de complemento.  <br/> **1:** indica un bot.<br/> **2:** indica un conector.<br/> **3:** indica una pestaña.|Microsoft Teams|
|AzureActiveDirectoryEventType|El tipo de evento de Azure Active Directory. Los siguientes valores indican el tipo de evento.  <br/> **0:** indica un evento de inicio de sesión de cuenta.<br/> **1:** indica un evento de seguridad de la aplicación de Azure.|Azure Active Directory|
|ChannelGuid|Identificador de un canal de Microsoft Teams. El equipo en el que se encuentra el canal se identifica mediante las **propiedades TeamName** y **TeamGuid.**|Microsoft Teams|
|ChannelName|El nombre de un canal de Microsoft Teams. El equipo en el que se encuentra el canal se identifica mediante las **propiedades TeamName** y **TeamGuid.**|Microsoft Teams|
|Client|El dispositivo cliente, el sistema operativo del dispositivo y el explorador del dispositivo usado para el evento de inicio de sesión (por ejemplo, Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Información sobre el cliente de correo electrónico que se usó para realizar la operación, como una versión del explorador, la versión de Outlook y la información del dispositivo móvil.|Exchange (actividad del buzón)|
|ClientIP|La dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.<br/><br/> Para ciertos servicios, el valor que se visualiza en esta propiedad puede ser la dirección IP de una aplicación de confianza (por ejemplo, Office en las aplicaciones web) que llama al servicio en nombre de un usuario y no la dirección IP del dispositivo utilizado por la persona que realizó la actividad. <br/><br/>Además, para la actividad de administrador (o la actividad realizada por una cuenta del sistema) para eventos relacionados con Azure Active Directory, la dirección IP no se registra y el valor de la propiedad ClientIP es `null` . |Azure Active Directory, Exchange, SharePoint|
|CreationTime|La fecha y hora en formato Hora universal coordinada (UTC) en las que el usuario ha realizado la actividad.|Todo|
|DestinationFileExtension|La extensión del archivo que se copia o mueve. Esta propiedad se muestra solo para las actividades de usuario FileCopied y FileMoved.|SharePoint|
|DestinationFileName|El nombre del archivo se copia o se mueve. Esta propiedad se muestra solo para las acciones FileCopied y FileMoved.|SharePoint|
|DestinationRelativeUrl|La dirección URL de la carpeta de destino donde se copia o se mueve un archivo. La combinación de los valores de **SiteURL**, **DestinationRelativeURL** y **DestinationFileName** es la misma que el valor de la propiedad **ObjectID,** que es el nombre de la ruta de acceso completa del archivo que se copió. Esta propiedad se muestra solo para las actividades de usuario FileCopied y FileMoved.|SharePoint|
|EventSource|Identifica que un evento se produjo en SharePoint. Los valores posibles **son SharePoint** y **ObjectModel**.|SharePoint|
|ExternalAccess|Para la actividad de administración de Exchange, especifica si un usuario de la organización, el personal del centro de datos de Microsoft, una cuenta de servicio de centro de datos o un administrador delegado ejecutaron el cmdlet. El valor **False** indica que el cmdlet lo ejecutó algún usuario de su organización. El valor **True** indica que el cmdlet lo ejecutó el personal del centros de datos, una cuenta de servicio del centro de datos o un administrador delegado.  <br/> Para la actividad del buzón de Exchange, especifica si un usuario externo a la organización ha accedido a un buzón.|Exchange|
|ExtendedProperties|Las propiedades extendidas de un evento de Azure Active Directory.|Azure Active Directory|
|ID|Identificador de la entrada del informe. El identificador identifica de forma única la entrada del informe.|Todo|
|InternalLogonType|Reservado para uso interno.|Exchange (actividad del buzón)|
|ItemType|El tipo de objeto al que se obtuvo acceso o que se modificó. Los valores **posibles son File**, **Folder**, **Web**, **Site**, **Tenant** y **DocumentLibrary**.|SharePoint|
|LoginStatus|Identifica los errores de inicio de sesión que pueden haber ocurrido.|Azure Active Directory|
|LogonType|El tipo de acceso al buzón. Los siguientes valores indican el tipo de usuario que ha accedido al buzón.  <br/><br/> **0:** indica el propietario de un buzón.<br/> **1:** indica un administrador.<br/> **2:** indica un delegado. <br/>**3:** indica el servicio de transporte en el centro de datos de Microsoft.<br/> **4:** indica una cuenta de servicio en el centro de datos de Microsoft. <br/>**6:** indica un administrador delegado.|Exchange (actividad del buzón)|
|MailboxGuid|El GUID de Exchange del buzón al que se obtuvo acceso.|Exchange (actividad del buzón)|
|MailboxOwnerUPN|La dirección de correo electrónico del propietario del buzón al que se obtuvo acceso.|Exchange (actividad del buzón)|
|Miembros|Enumera los usuarios que se han agregado o quitado de un equipo. Los siguientes valores indican el tipo de rol asignado al usuario.  <br/><br/> **1:** indica el rol Propietario.<br/> **2** - Indica el rol del miembro.<br/> **3**- Indica el rol del invitado. <br/><br/>La propiedad Miembros también incluye el nombre de su organización y la dirección de correo electrónico del miembro.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|La propiedad se incluye para los eventos de administración, como agregar un usuario como miembro de un sitio o un grupo de administradores de colección de sitios. La propiedad incluye el nombre de la propiedad que se modificó (por ejemplo, el grupo Administrador del sitio) el nuevo valor de la propiedad modificada (por ejemplo, el usuario que se agregó como administrador del sitio y el valor anterior del objeto modificado).|Todo (actividad de administrador)|
|ObjectId|Para el registro de auditoría de Exchange, el nombre del objeto modificado por el cmdlet.  <br/> Para la actividad de SharePoint, el nombre de la ruta de acceso url completa del archivo o carpeta al que tiene acceso un usuario.  <br/> Para la actividad de Azure AD, el nombre de la cuenta de usuario que se modificó.|Todo|
|Operación|El nombre de la actividad de usuario o administrador. El valor de esta propiedad corresponde al valor  seleccionado en la lista desplegable Actividades. Si **se ha seleccionado Mostrar resultados** de todas las actividades, el informe incluirá entradas para todas las actividades de usuario y administrador de todos los servicios. Para obtener una descripción de las operaciones o actividades  que se registran en el registro de auditoría, vea la pestaña Actividades auditadas en Buscar el registro de auditoría en [Office 365.](search-the-audit-log-in-security-and-compliance.md)  <br/> Esta propiedad identifica el nombre del cmdlet ejecutado para la actividad de administración de Exchange.|Todo|
|OrganizationId|Guid de la organización.|Todo|
|Path|El nombre de la carpeta del buzón donde se encuentra el mensaje al que se obtuvo acceso. Esta propiedad también identifica la carpeta en la que se crea o se copia o mueve un mensaje.|Exchange (actividad del buzón)|
|Parámetros|Para la actividad de administración de Exchange, el nombre y el valor de todos los parámetros que se usaron con el cmdlet identificado en la propiedad Operation.|Exchange (actividad de administrador)|
|RecordType|El tipo de operación indicado por el registro. Esta propiedad indica el servicio o la característica en la que se desencadenó la operación. Para obtener una lista de tipos de registro y su valor ENUM correspondiente (que es el valor mostrado en la propiedad **RecordType** en un registro de auditoría), vea El tipo de registro [de registro de auditoría](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).| 
|ResultStatus|Indica si la acción (especificada en la **propiedad Operation)** se ha realizado correctamente o no.  <br/> Para la actividad de administración de Exchange, el valor es **True** (correcto) o **False** (con error).|Todo  <br/>|
|SecurityComplianceCenterEventType|Indica que la actividad fue un evento del Centro de & cumplimiento. Todas las & del Centro de seguridad y cumplimiento tendrán un valor de **0** para esta propiedad.|Centro de seguridad y cumplimiento|
|SharingType|El tipo de permisos de uso compartido que se asignó al usuario con el que se compartió el recurso. Este usuario se identifica en la **propiedad UserSharedWith.**|SharePoint|
|Site|El GUID del sitio donde se encuentra el archivo o la carpeta a la que obtuvo acceso el usuario.|SharePoint|
|SiteUrl|La dirección URL del sitio donde se encuentra el archivo o la carpeta a la que obtuvo acceso el usuario.|SharePoint|
|SourceFileExtension|La extensión del archivo al que obtuvo acceso el usuario. Esta propiedad está en blanco si el objeto al que se obtuvo acceso es una carpeta.|SharePoint|
|SourceFileName|El nombre del archivo o carpeta al que obtuvo acceso el usuario.|SharePoint|
|SourceRelativeUrl|La dirección URL de la carpeta que contiene el archivo al que obtuvo acceso el usuario. La combinación de los valores de **SiteURL**, **SourceRelativeURL** y **SourceFileName** es la misma que el valor de la propiedad **ObjectID,** que es el nombre de la ruta de acceso completa para el archivo al que tiene acceso el usuario.|SharePoint|
|Subject|La línea de asunto del mensaje al que se obtuvo acceso.|Exchange (actividad del buzón)|
|TabType| Tipo de pestaña agregada, eliminada o actualizada en un equipo. Los valores posibles de esta propiedad son:  <br/><br/> **Pin de Excel:** una pestaña de Excel.  <br/> **Extensión:** todas las aplicaciones de terceros y de terceros; como programación de clases, VSTS y formularios.  <br/> **Notas:** pestaña de OneNote.  <br/> **Pdfpin:** pestaña PDF.  <br/> **Powerbi:** una pestaña de Power BI.  <br/> **Powerpointpin:** una pestaña de PowerPoint.  <br/> **Sharepointfiles:** una pestaña de SharePoint.  <br/> **Página** web: una pestaña de sitio web anclado.  <br/> **Pestaña Wiki:** una pestaña wiki.  <br/> **Wordpin:** una pestaña de Word.|Microsoft Teams|
|Target|El usuario en el que se realizó la acción (identificada en la **propiedad Operation).** Por ejemplo, si se agrega un usuario invitado a SharePoint o a Un equipo de Microsoft, ese usuario aparecerá en esta propiedad.|Azure Active Directory|
|TeamGuid|El identificador de un equipo en Microsoft Teams.|Microsoft Teams|
|TeamName|El nombre de un equipo en Microsoft Teams.|Microsoft Teams|
|UserAgent|Información sobre el explorador del usuario. El explorador proporciona esta información.|SharePoint|
|UserDomain|Información de identidad sobre la organización del inquilino del usuario (actor) que realizó la acción.|Azure Active Directory|
|UserId|El usuario que realizó la acción (especificada en la **propiedad Operation)** que hizo que se registrara el registro. Los registros de auditoría de la actividad realizada por cuentas del sistema (como SHAREPOINT\system o NT AUTHORITY\SYSTEM) también se incluyen en el registro de auditoría. Otro valor común para la propiedad UserId es app@sharepoint. Esto indica que el "usuario" que llevó a cabo esta actividad era una aplicación que tiene los permisos necesarios en SharePoint para realizar acciones en toda la organización (como buscar en un sitio de SharePoint o en una cuenta de OneDrive) en nombre de un usuario, un administrador o un servicio. Para obtener más información, lea [El usuario app\@sharepoint en los registros de auditoría](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records). |Todo|
|UserKey|Un identificador alternativo para el usuario identificado en la **propiedad UserID.** Por ejemplo, esta propiedad se rellena con el identificador único (PUID) de Passport para los eventos realizados por los usuarios en SharePoint. Esta propiedad también puede especificar el mismo valor que la propiedad **UserID** para los eventos que se producen en otros servicios y eventos realizados por cuentas del sistema.|Todo|
|UserSharedWith|El usuario con el que se compartió un recurso. Esta propiedad se incluye si el valor de la **propiedad Operation** es **SharingSet**. Este usuario también aparece en la columna **Compartido con** del informe.|SharePoint|
|UserType|El tipo de usuario que llevó a cabo la operación. Los siguientes valores indican el tipo de usuario. <br/> <br/> **0:** un usuario normal. <br/>**2-** Un administrador de su organización de Microsoft 365. <sup>1</sup> <br/>**3:** una cuenta de sistema de centro de datos o administrador de centro de datos de Microsoft. <br/>**4-** Una cuenta del sistema. <br/>**5:** una aplicación. <br/>**6:** una entidad de servicio.<br/>**7:** una directiva personalizada.<br/>**8:** una directiva del sistema.|Todo|
|Versión|Indica el número de versión de la actividad (identificada por la **propiedad Operation)** que se registra.|Todo|
|Carga de trabajo|El servicio de Microsoft 365 donde se produjo la actividad.|Todo|
||||

> [!NOTE]
><sup>1</sup> Para eventos relacionados con Azure Active Directory, el valor de un administrador no se usa en un registro de auditoría. Los registros de auditoría de las actividades realizadas por los administradores indicarán que un usuario normal (por ejemplo, **UserType: 0)** realizó la actividad. La **propiedad UserID** identificará a la persona (usuario normal o administrador) que realizó la actividad.<br/>

Las propiedades descritas anteriormente también se muestran al hacer clic en **Más información** al ver los detalles de un evento específico.
  
![Haga clic en Obtener más información para ver las propiedades detalladas del registro de eventos de auditoría.](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
