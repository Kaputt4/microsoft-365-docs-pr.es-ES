---
title: Propiedades detalladas del registro de auditoría
description: En este artículo se proporcionan descripciones de propiedades adicionales incluidas al exportar los resultados de un registro de auditoría de Office 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- audit
search.appverid:
- MOE150
- BCS160
- MET150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 59e5e3b5317cd2497563a1b0842361eb387e43a1
ms.sourcegitcommit: 4dfb5de8c61847b8ddd10410ad20d34860eed8f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68129769"
---
# <a name="detailed-properties-in-the-audit-log"></a>Propiedades detalladas del registro de auditoría

Al exportar los resultados de una búsqueda de registros de auditoría desde el portal de cumplimiento Microsoft Purview, tiene la opción de descargar todos los resultados que cumplan los criterios de búsqueda. Para ello, seleccione **Exportar resultados** \> **Descargar todos los resultados** en la página **Búsqueda de registros de auditoría** . Para obtener más información, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).
  
 Cuando exporta todos los resultados de una búsqueda de registros de auditoría, los datos sin procesar del registro de auditoría unificado se copian en un archivo de valores separados por comas (CSV) que se descarga en el equipo local. Este archivo contiene información adicional de cada registro de auditoría de una columna denominada **AuditData**. Esta columna contiene una propiedad de varios valores para varias propiedades del registro de auditoría. Cada una de las **propiedades:** los pares de valores de esta propiedad multivalor se separan por comas. 
  
En la tabla siguiente se describen las propiedades que se incluyen (en función del servicio en el que se produce un evento) en la columna **AuditData** de varias propiedades. El **servicio Office 365 que tiene esta** columna de propiedad indica el servicio y el tipo de actividad (usuario o administrador) que incluye la propiedad. Para obtener información más detallada sobre estas propiedades o sobre las propiedades que pueden no aparecer en este tema, consulte [Esquema de api de actividad de administración](/office/office-365-management-api/office-365-management-activity-api-schema).
  
> [!TIP]
> Puede usar la característica de transformación JSON en Power Query en Excel para dividir la columna **AuditData** en varias columnas para que cada propiedad tenga su propia columna. Esto le permitirá ordenar y filtrar en una o más de estas propiedades. Para obtener información sobre cómo hacerlo, consulte [Exportación, configuración y visualización de registros de auditoría](export-view-audit-log-records.md). 
  
|**Propiedad**|**Descripción**|**Servicio de Microsoft 365 que tiene esta propiedad**|
|:-----|:-----|:-----|
|Actor|La cuenta de usuario o servicio que realizó la acción.|Azure Active Directory|
|AddOnName|Nombre de un complemento que se agregó, quitó o actualizó en un equipo. El tipo de complementos de Microsoft Teams es un bot, un conector o una pestaña.|Microsoft Teams|
|AddOnType|Tipo de un complemento que se agregó, quitó o actualizó en un equipo. Los siguientes valores indican el tipo de complemento.  <br/> **1** : indica un bot.<br/> **2** : indica un conector.<br/> **3** : indica una pestaña.|Microsoft Teams|
|AzureActiveDirectoryEventType|Tipo de evento de Azure Active Directory. Los siguientes valores indican el tipo de evento.  <br/> **0** : indica un evento de inicio de sesión de cuenta.<br/> **1** : indica un evento de seguridad de la aplicación de Azure.|Azure Active Directory|
|ChannelGuid|Identificador de un canal de Microsoft Teams. El equipo en el que se encuentra el canal se identifica mediante las propiedades **TeamName** y **TeamGuid** .|Microsoft Teams|
|ChannelName|Nombre de un canal de Microsoft Teams. El equipo en el que se encuentra el canal se identifica mediante las propiedades **TeamName** y **TeamGuid** .|Microsoft Teams|
|Client|El dispositivo cliente, el sistema operativo del dispositivo y el explorador de dispositivos utilizados para el evento de inicio de sesión (por ejemplo, Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Información sobre el cliente de correo electrónico que se usó para realizar la operación, como una versión del explorador, la versión de Outlook y la información del dispositivo móvil|Exchange (actividad de buzón)|
|ClientIP|La dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.<br/><br/> Para ciertos servicios, el valor que se visualiza en esta propiedad puede ser la dirección IP de una aplicación de confianza (por ejemplo, Office en las aplicaciones web) que llama al servicio en nombre de un usuario y no la dirección IP del dispositivo utilizado por la persona que realizó la actividad. <br/><br/>Además, para la actividad de administrador (o actividad realizada por una cuenta del sistema) para eventos relacionados con Azure Active Directory, la dirección IP no se registra y el valor de la propiedad ClientIP es `null`. |Azure Active Directory, Exchange, SharePoint|
|CreationTime|La fecha y hora en formato Hora universal coordinada (UTC) en las que el usuario ha realizado la actividad.|Todo|
|DestinationFileExtension|La extensión del archivo que se copia o mueve. Esta propiedad solo se muestra para las actividades de usuario FileCopied y FileMoved.|SharePoint|
|DestinationFileName|El nombre del archivo se copia o mueve. Esta propiedad solo se muestra para las acciones FileCopied y FileMoved.|SharePoint|
|DestinationRelativeUrl|La dirección URL de la carpeta de destino donde se copia o se mueve un archivo. La combinación de los valores de **SiteURL**, **DestinationRelativeURL** y la propiedad **DestinationFileName** es la misma que el valor de la propiedad **ObjectID** , que es el nombre de la ruta de acceso completa del archivo que se copió. Esta propiedad solo se muestra para las actividades de usuario FileCopied y FileMoved.|SharePoint|
|EventSource|Identifica que un evento se produjo en SharePoint. Los valores posibles son **SharePoint** y **ObjectModel**.|SharePoint|
|ExternalAccess|En el caso de la actividad de administrador de Exchange, especifica si el cmdlet lo ejecutó un usuario de su organización, el personal del centro de datos de Microsoft o una cuenta de servicio del centro de datos o un administrador delegado. El valor **False** indica que el cmdlet lo ejecutó algún usuario de su organización. El valor **True** indica que el cmdlet lo ejecutó el personal del centros de datos, una cuenta de servicio del centro de datos o un administrador delegado.  <br/> En el caso de la actividad de buzón de Exchange, especifica si un usuario fuera de la organización ha accedido a un buzón de correo.|Exchange|
|ExtendedProperties|Propiedades extendidas para un evento de Azure Active Directory.|Azure Active Directory|
|Id.|Identificador de la entrada del informe. El identificador identifica de forma única la entrada del informe.|Todo|
|InternalLogonType|Reservado para uso interno.|Exchange (actividad de buzón)|
|ItemType|El tipo de objeto al que se obtuvo acceso o que se modificó. Entre los valores posibles se incluyen **File**, **Folder**, **Web**, **Site**, **Tenant** y **DocumentLibrary**.|SharePoint|
|LoginStatus|Identifica los errores de inicio de sesión que podrían haberse producido.|Azure Active Directory|
|LogonType|Tipo de acceso al buzón. Los siguientes valores indican el tipo de usuario que ha accedido al buzón.  <br/><br/> **0** : indica el propietario de un buzón.<br/> **1** : indica un administrador.<br/> **2** : indica un delegado. <br/>**3** : indica el servicio de transporte en el centro de datos de Microsoft.<br/> **4** : indica una cuenta de servicio en el centro de datos de Microsoft. <br/>**6** : indica un administrador delegado.|Exchange (actividad de buzón)|
|MailboxGuid|El GUID de Exchange del buzón al que se obtuvo acceso.|Exchange (actividad de buzón)|
|MailboxOwnerUPN|La dirección de correo electrónico del propietario del buzón al que se obtuvo acceso.|Exchange (actividad de buzón)|
|Members|Enumera los usuarios que se han agregado o quitado de un equipo. Los siguientes valores indican el tipo de rol asignado al usuario.  <br/><br/> **1** : indica el rol Propietario.<br/> **2** - Indica el rol del miembro.<br/> **3**- Indica el rol del invitado. <br/><br/>La propiedad Miembros también incluye el nombre de su organización y la dirección de correo electrónico del miembro.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|La propiedad se incluye para los eventos de administración, como agregar un usuario como miembro de un sitio o un grupo de administradores de colección de sitios. La propiedad incluye el nombre de la propiedad que se modificó (por ejemplo, el grupo De sitio Administración) el nuevo valor de la propiedad modificada (por ejemplo, el usuario que se agregó como administrador del sitio y el valor anterior del objeto modificado.|Todo (actividad de administrador)|
|ObjectId|Para el registro de auditoría de Exchange, el nombre del objeto modificado por el cmdlet.  <br/> Para la actividad de SharePoint, el nombre completo de la ruta de acceso url del archivo o carpeta al que accede un usuario.  <br/> Para la actividad de Azure AD, el nombre de la cuenta de usuario que se modificó.|Todo|
|Operación|El nombre de la actividad de usuario o administrador. El valor de esta propiedad corresponde al valor que se seleccionó en la lista desplegable **Actividades** . Si se seleccionó **Mostrar resultados para todas las actividades** , el informe incluirá entradas para todas las actividades de usuario y administrador de todos los servicios. Para obtener una descripción de las operaciones o actividades que se registran en el registro de auditoría, consulte la pestaña **Actividades auditadas** en [Buscar el registro de auditoría en el Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> Esta propiedad identifica el nombre del cmdlet ejecutado para la actividad de administración de Exchange.|Todo|
|OrganizationId|GUID de la organización.|Todo|
|Path|El nombre de la carpeta del buzón donde se encuentra el mensaje al que se obtuvo acceso. Esta propiedad también identifica la carpeta en la que se crea un mensaje o se copia o se mueve a.|Exchange (actividad de buzón)|
|Parameters|Para la actividad de administrador de Exchange, el nombre y el valor de todos los parámetros que se usaron con el cmdlet que se identifica en la propiedad Operation.|Exchange (actividad de administrador)|
|RecordType|El tipo de operación indicado por el registro. Esta propiedad indica el servicio o característica en el que se desencadenó la operación. Para obtener una lista de tipos de registro y su valor ENUM correspondiente (que es el valor mostrado en la propiedad **RecordType** en un registro de auditoría), consulte [Tipo de registro de](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype) auditoría.| 
|ResultStatus|Indica si la acción (especificada en la propiedad **Operation** ) se realizó correctamente o no.  <br/> Para la actividad de administrador de Exchange, el valor es **True** (correcto) o **False** (error).|Todo  <br/>|
|SecurityComplianceCenterEventType|Indica que la actividad era un evento del portal de cumplimiento. Todas las actividades del centro de cumplimiento tendrán un valor de **0** para esta propiedad.|Centro de seguridad y cumplimiento|
|SharingType|Tipo de permisos de uso compartido que se asignaron al usuario con el que se compartió el recurso. Este usuario se identifica en la propiedad **UserSharedWith** .|SharePoint|
|Site|El GUID del sitio donde se encuentra el archivo o la carpeta a la que obtuvo acceso el usuario.|SharePoint|
|SiteUrl|La dirección URL del sitio donde se encuentra el archivo o la carpeta a la que obtuvo acceso el usuario.|SharePoint|
|SourceFileExtension|La extensión del archivo al que obtuvo acceso el usuario. Esta propiedad está en blanco si el objeto al que se obtuvo acceso es una carpeta.|SharePoint|
|SourceFileName|El nombre del archivo o carpeta al que obtuvo acceso el usuario.|SharePoint|
|SourceRelativeUrl|La dirección URL de la carpeta que contiene el archivo al que obtuvo acceso el usuario. La combinación de los valores de **SiteURL**, **SourceRelativeURL** y la propiedad **SourceFileName** es la misma que el valor de la propiedad **ObjectID** , que es el nombre de la ruta de acceso completa para el archivo al que accede el usuario.|SharePoint|
|Subject|La línea de asunto del mensaje al que se obtuvo acceso.|Exchange (actividad de buzón)|
|TabType| Tipo de pestaña agregada, quitada o actualizada en un equipo. Los valores posibles de esta propiedad son:  <br/><br/> **Pin de Excel** : una pestaña de Excel.  <br/> **Extensión** : todas las aplicaciones de terceros y de terceros; como programación de clases, VSTS y formularios.  <br/> **Notas** : pestaña De OneNote.  <br/> **Pdfpin** : una pestaña PDF.  <br/> **Powerbi** : una pestaña de Power BI.  <br/> **Powerpointpin** : una pestaña de PowerPoint.  <br/> **Sharepointfiles** : una pestaña de SharePoint.  <br/> **Página web** : pestaña de sitio web anclado.  <br/> **Wiki-tab** : una pestaña wiki.  <br/> **Wordpin** : una pestaña de Word.|Microsoft Teams|
|Target|El usuario en el que se realizó la acción (identificada en la propiedad **Operation** ). Por ejemplo, si se agrega un usuario invitado a SharePoint o a un equipo de Microsoft, ese usuario aparecería en esta propiedad.|Azure Active Directory|
|TeamGuid|Identificador de un equipo en Microsoft Teams.|Microsoft Teams|
|TeamName|Nombre de un equipo en Microsoft Teams.|Microsoft Teams|
|UserAgent|Información sobre el explorador del usuario. Esta información la proporciona el explorador.|SharePoint|
|UserDomain|Información de identidad sobre la organización del inquilino del usuario (actor) que realizó la acción.|Azure Active Directory|
|UserId|El usuario que realizó la acción (especificada en la propiedad **Operation** ) que provocó que se registrara el registro. Los registros de auditoría de la actividad realizada por las cuentas del sistema (como SHAREPOINT\system o NT AUTHORITY\SYSTEM) también se incluyen en el registro de auditoría. Otro valor común para la propiedad UserId es app@sharepoint. Esto indica que el "usuario" que llevó a cabo esta actividad era una aplicación que tiene los permisos necesarios en SharePoint para realizar acciones en toda la organización (como buscar en un sitio de SharePoint o en una cuenta de OneDrive) en nombre de un usuario, un administrador o un servicio. <br/><br/>Para obtener más información, consulte:<br/> [El usuario de SharePoint de la aplicación\@en los registros de auditoría](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records)<br/> o <br/>[Cuentas del sistema en registros de auditoría de buzones de Exchange](search-the-audit-log-in-security-and-compliance.md#system-accounts-in-exchange-mailbox-audit-records). |Todo|
|UserKey|Un identificador alternativo para el usuario identificado en la propiedad **UserID** . Por ejemplo, esta propiedad se rellena con el identificador único de passport (PUID) para los eventos realizados por los usuarios en SharePoint. Esta propiedad también puede especificar el mismo valor que la propiedad **UserID** para los eventos que se producen en otros servicios y eventos realizados por cuentas del sistema.|Todo|
|UserType|El tipo de usuario que llevó a cabo la operación. Los siguientes valores indican el tipo de usuario. <br/> <br/> **0** : un usuario normal. <br/>**2** : administrador de la organización de Microsoft 365. <sup>1</sup> <br/>**3** : una cuenta de sistema de centro de datos o administrador del centro de datos de Microsoft. <br/>**4** - Una cuenta del sistema. <br/>**5** - Una aplicación. <br/>**6** - Una entidad de servicio.<br/>**7** - Una directiva personalizada.<br/>**8** - Una directiva del sistema.|Todo|
|Versión|Indica el número de versión de la actividad (identificada por la propiedad **Operation** ) que se registra.|Todo|
|Carga de trabajo|Servicio de Microsoft 365 donde se produjo la actividad.|Todo|
||||

> [!NOTE]
><sup>1</sup> Para eventos relacionados con Azure Active Directory, el valor de un administrador no se usa en un registro de auditoría. Los registros de auditoría de las actividades realizadas por los administradores indicarán que un usuario normal (por ejemplo, **UserType: 0**) realizó la actividad. La propiedad **UserID** identificará a la persona (usuario o administrador normal) que realizó la actividad.
