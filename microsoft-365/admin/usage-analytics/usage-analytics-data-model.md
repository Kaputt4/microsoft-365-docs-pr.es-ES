---
title: Modelo de datos de análisis de uso de Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: 'Obtenga información sobre cómo el análisis de uso se conecta a una API y proporciona una tendencia mensual del uso de varios servicios de Microsoft 365.  '
ms.openlocfilehash: 4954b463946ba436afd14390526eefe188447a46
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730495"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Modelo de datos de análisis de uso de Microsoft 365

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Datos de las tablas de análisis de uso de Microsoft 365

El análisis de uso de Microsoft 365 se conecta a una API que expone un modelo de datos multidimensional. Las API que usa el análisis de uso de Microsoft 365 para generar sus datos proceden de las distintas API de Graph disponibles con carácter general. La función de la API de análisis de uso de Microsoft 365 por sí sola no está disponible con carácter general.
  
> [!NOTE]
> Para obtener más información, consulte [Trabajar con informes de uso de Microsoft 365 en Microsoft Graph](/graph/api/resources/report). 
  
Esta API proporciona información sobre la tendencia mensual de uso de los distintos servicios de Microsoft 365. Para obtener los datos exactos de la API, vea la tabla en la sección siguiente.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Tablas de datos devueltas por la API de informes de Microsoft 365

|**Nombre de tabla**|**Información en la tabla**|**Intervalo de fechas**|
|:-----|:-----|:-----|
|Uso de productos de espacio empresarial  <br/> |Contiene totales mensuales de usuarios activos habilitados, usuarios retenidos mes a mes, usuarios por primera vez y usuarios activos acumulados.  <br/> |Contiene datos agregados mensuales de un período acumulado de 12 meses, incluido el mes parcial actual.  <br/> |
|Actividad de producto de espacio empresarial  <br/> |Contiene totales mensuales de actividades y recuento de usuarios activos para varias actividades dentro de los productos.  <br/> Vea [Definición de usuario activo](active-user-in-usage-reports.md) para obtener información sobre las actividades dentro de un producto que se devuelven en esa tabla de datos.  <br/> |Contiene datos agregados mensuales de un período acumulado de 12 meses, incluido el mes parcial actual.  <br/> |
|Licencias de Office de espacio empresarial  <br/> |Contiene datos sobre el número de suscripciones de Microsoft Office asignadas a los usuarios.  <br/> |Contiene datos de estado de fin de mes para un período gradual de 12 meses, incluido el mes parcial actual.  <br/> |
|Uso de buzones de espacio empresarial  <br/> |Contiene datos sobre el buzón del usuario, para el recuento total de buzones y cómo se usa el almacenamiento.  <br/> |Contiene datos de estado de fin de mes para un período gradual de 12 meses, incluido el mes parcial actual.  <br/> |
|Uso de clientes de espacio empresarial  <br/> |Contiene datos sobre el número de usuarios que usan de forma activa dispositivos o clientes específicos para conectarse a Exchange Online, Skype Empresarial y Yammer.  <br/> |Contiene datos agregados mensuales de un período acumulado de 12 meses, incluido el mes parcial actual.  <br/> |
|Uso de SharePoint Online de espacio empresarial  <br/> |Contiene datos sobre los sitios de SharePoint, que abarcan sitios de grupo o equipo, como el número total de sitios, el número de documentos de un sitio, el número de archivos por tipo de actividad y almacenamiento usado.  <br/> |Contiene datos de estado de fin de mes para un período gradual de 12 meses, incluido el mes parcial actual.  <br/> |
|Uso de OneDrive para la Empresa de espacio empresarial  <br/> |Contiene datos sobre las cuentas de OneDrive, como el número de cuentas, el número de documentos en cuentas de OneDrive, el almacenamiento usado y el número de archivos por tipo de actividad.  <br/> |Contiene datos de estado de fin de mes para un período gradual de 12 meses, incluido el mes parcial actual.  <br/> |
|Uso de Grupos de Microsoft 365 de inquilinos  <br/> |Contiene datos sobre Grupos de Microsoft 365 uso, incluidos Mailbox, SharePoint y Yammer.  <br/> |Contiene datos de estado de fin de mes para un período gradual de 12 meses, incluido el mes parcial actual.  <br/> |
|Activación de Office de espacio empresarial  <br/> |Contiene datos sobre el número de activaciones de suscripción de Office, el recuento de activación por dispositivo (Android/iOS/Mac/PC), las activaciones por plan de servicio, por ejemplo, Aplicaciones Microsoft 365 para empresas, Visio y Project.  <br/> |Contiene datos de estado de fin de mes para un período gradual de 12 meses, incluido el mes parcial actual.  <br/> |
|Estado de usuario  <br/> |Contiene metadatos sobre usuarios, incluido el nombre para mostrar del usuario, los productos asignados, la ubicación, el departamento, el puesto y la compañía. Estos datos se tratan de los usuarios a los que se les asignó una licencia durante el último mes completo. Cada usuario se representa de forma única mediante un identificador de usuario.  <br/> |Estos datos son sobre usuarios que tenían asignada una licencia durante el último mes completo.  <br/> |
|Actividad de usuario  <br/> |Contiene información de nivel por usuario sobre la actividad realizada por los usuarios con licencia.  <br/> Vea [Definición de usuario activo](active-user-in-usage-reports.md) para obtener información sobre las actividades dentro de un producto que se devuelven en esa tabla de datos.  <br/> |Estos datos tratan sobre los usuarios que realizaron alguna actividad en uno de los servicios durante el último mes completo.  <br/> |
   
Expanda las secciones siguientes para ver información detallada de cada tabla de datos.
  
### <a name="data-table---user-state"></a>Tabla de datos: Estado de usuario

En esta tabla se proporcionan detalles de nivel de usuario para todos los usuarios que tienen asignada una licencia durante el último mes completo. Recupera datos de Azure Active Directory.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|UserId  <br/> |Identificador de usuario único que representa a un usuario y permite la unión con otras tablas de datos dentro del conjunto de datos.  <br/> |
|Timeframe  <br/> |Valor del mes de los datos de esta tabla.  <br/> |
|UPN  <br/> |Nombre principal de usuario que identifica de forma única al usuario para poder unirse a otros orígenes de datos externos.  <br/> |
|DisplayName  <br/> |El nombre para mostrar del usuario.  <br/> |
|IDType  <br/> |El tipo de identificador se establece en 1 si el usuario es un usuario de Yammer que se conecta mediante su identificador de Yammer o 0 si se conecta a Yammer mediante su identificador de Microsoft 365.  <br/> El valor es 1 para representar que este usuario se conecta a Yammer con su identificador de Yammer y no con su identificador de Microsoft 365  <br/> |
|HasLicenseEXO  <br/> |Establézcalo en true si al usuario se le asigna una licencia y se habilita para usar Exchange el último día del mes.  <br/> |
|HasLicenseODB  <br/> |Establézcalo en true si al usuario se le asigna una licencia y se habilita para usar OneDrive para la Empresa el último día del mes.  <br/> |
|HasLicenseSPO  <br/> |Establézcalo en true si al usuario se le asigna una licencia y se habilita para usar SharePoint Online el último día del mes.  <br/> |
|HasLicenseYAM  <br/> |Establézcalo en true si al usuario se le asigna una licencia y se habilita para usar Yammer el último día del mes.  <br/> |
|HasLicenseSFB  <br/> |Establézcalo en true si al usuario se le asigna una licencia y se habilita para usar Skype Empresarial el último día del mes.  <br/> |
|HasLicenseTeams  <br/> |Establézcalo en true si al usuario se le asigna una licencia y permite usar Microsoft Teams el último día del mes.  <br/> |
|Empresa  <br/> |Los datos de la compañía representados en Azure Active Directory para el usuario.  <br/> |
|Department  <br/> |Los datos de departamento representados en Azure Active Directory para el usuario.  <br/> |
|LocationCity  <br/> |Los datos de ciudad representados en Azure Active Directory para el usuario.  <br/> |
|LocationCountry  <br/> |Los datos de país representados en Azure Active Directory para el usuario.  <br/> |
|LocationState  <br/> |Los datos de estado representados en Azure Active Directory para el usuario.  <br/> |
|LocationOffice  <br/> |La oficina del usuario.  <br/> |
|Title  <br/> |Los datos de puesto representados en Azure Active Directory para el usuario.  <br/> |
|Deleted  <br/> |True si el usuario se ha eliminado de Microsoft 365 en ese último mes completo.  <br/> |
|DeletedDate  <br/> |Fecha en la que se eliminó el usuario de Microsoft 365.  <br/> |
|YAM_State  <br/> |Los estados del usuario en el sistema de Yammer pueden estar activos, eliminados o suspendidos.  <br/> |
|YAM_ActivationDate  <br/> |Fecha en que el usuario cambió al estado "activo" en Yammer.  <br/> |
|YAM_DeletionDate  <br/> |Fecha en que el usuario cambió al estado "eliminado" en Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |Fecha en que el usuario cambió al estado "suspendido" en Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Tabla de datos: Actividad de usuario

Esta tabla contiene datos sobre los usuarios que realizaron alguna actividad en uno de los servicios del mes anterior.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|Userid  <br/> |Identificador de usuario único que representa a un usuario y permite la unión con otras tablas de datos dentro del conjunto de datos.  <br/> |
|IDType  <br/> |El tipo de identificador se establece en 1 si el usuario es un usuario de Yammer que se conecta mediante su identificador de Yammer o 0 si se conecta a Yammer mediante su identificador de Microsoft 365.  <br/> El valor es 1 para representar que este usuario se conecta a Yammer con su identificador de Yammer y no con su identificador de Microsoft 365  <br/> |
|Timeframe  <br/> |Valor de mes de los datos que se representan en esta tabla.  <br/> |
|EXO_EmailSent  <br/> |Número de correos electrónicos enviados.  <br/> |
|EXO_EmailReceived  <br/> |Número de correos electrónicos recibidos.  <br/> |
|EXO_EmailRead  <br/> |Número de actividad de lectura de correos electrónicos que el usuario realizó, podría ser varias veces leer un correo electrónico ya leído o un correo electrónico recibido anteriormente.  <br/> |
|EXO_AppointmentCreated  <br/> |Número de citas creadas.  <br/> |
|EXO_MeetingAccepted  <br/> |Número de reuniones aceptadas.  <br/> |
|EXO_MeetingCancelled  <br/> |Número de reuniones canceladas.  <br/> |
|EXO_MeetingDeclined  <br/> |Número de reuniones rechazadas.  <br/> |
|EXO_MeetingSent  <br/> |Número de reuniones enviadas.  <br/> |
|ODB_FileViewedModified  <br/> |Número de archivos con el que interactuó el usuario en cualquier cuenta de OneDrive para la Empresa (por ejemplo, los archivos que creó, actualizó, eliminó, visualizó o descargó).  <br/> |
|ODB_FileSynched  <br/> |Número de archivos que sincronizó el usuario en cualquier cuenta de OneDrive para la Empresa.  <br/> |
|ODB_FileSharedInternally  <br/> |Número de archivos que este usuario ha compartido internamente desde cualquier OneDrive para la Empresa o con usuarios dentro de grupos (que pueden incluir usuarios externos).  <br/> |
|ODB_FileSharedExternally  <br/> |Número de archivos que compartió de forma externa el usuario desde cualquier cuenta de OneDrive para la Empresa.  <br/> |
|ODB_AccessedByOwner  <br/> |Número de sitios con los que el usuario interactuó y que residen en su propio OneDrive para la Empresa.  <br/> |
|ODB_AccessedByOthers  <br/> |Número de sitios con los que interactuó este usuario que residen en la OneDrive para la Empresa de otro usuario.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Número de archivos con los que este usuario interactuó en cualquier sitio de grupo.  <br/> |
|SPO_GroupFileSynched  <br/> |Número de archivos que sincronizó el usuario en cualquier sitio de grupo.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |Recuento de archivos que se han compartido con usuarios de la organización o con usuarios dentro de grupos (que pueden incluir usuarios externos).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Número de archivos que compartió el usuario de forma externa desde cualquier sitio de grupo.  <br/> |
|SPO_GroupAccessedByOwner  <br/> |Número de sitios con los que interactuó el usuario que residen en un sitio de grupo del que es propietario.  <br/> |
|SPO_GroupAccessedByOthers  <br/> |Número de sitios con los que interactuó el usuario que residen en un sitio de grupo del que es propietario otro usuario.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Número de archivos con los que este usuario interactuó en cualquier otro sitio.  <br/> |
|SPO_OtherFileSynched  <br/> |Número de archivos que este usuario sincronice desde cualquier otro sitio.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Número de archivos que este usuario ha compartido internamente desde cualquier otro sitio o con usuarios dentro de grupos (que pueden incluir usuarios externos). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Número de archivos compartidos externamente por este usuario desde cualquier otro sitio.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Número de sitios con los que el usuario interactuó que residen en otro sitio que posee.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Número de sitios con los que interactuó el usuario que residen en otro sitio que posee otro usuario.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Número de archivos con los que interactuó el usuario en cualquier sitio de grupo.  <br/> |
|SPO_TeamFileSynched  <br/> |Número de archivos que sincronizó el usuario desde cualquier sitio de grupo.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Número de archivos que este usuario ha compartido internamente desde cualquier sitio de equipo o con usuarios dentro de grupos (que pueden incluir usuarios externos).  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Número de archivos que compartió de forma externa el usuario desde cualquier sitio de grupo.  <br/> |
|SPO_TeamAccessedByOwner  <br/> |Número de sitios con los que interactuó el usuario que residen en un sitio de equipo del que es propietario.  <br/> |
|SPO_TeamAccessedByOthers  <br/> |Número de sitios con los que interactuó el usuario que residen en un sitio de equipo del que es propietario otro usuario.  <br/> |
|Teams_ChatMessages  <br/> |Número de mensajes de chat enviados.  <br/> |
|Teams_ChannelMessage  <br/> |Número de mensajes publicados en los canales.  <br/> |
|Teams_CallParticipate  <br/> |Número de llamadas en las que participó el usuario.  <br/> |
|Teams_MeetingParticipate  <br/> |Número de reuniones a las que se unió el usuario.  <br/> |
|Teams_HasOtherAction  <br/> |Valor booleano si el usuario realizó otras acciones en Microsoft Teams.  <br/> |
|YAM_MessagePost  <br/> |Número de mensajes de Yammer publicados por este usuario.  <br/> |
|YAM_MessageLiked  <br/> |Número de mensajes de Yammer que le han gustado a este usuario.  <br/> |
|YAM_MessageRead  <br/> |Número de mensajes de Yammer leídos por este usuario.  <br/> |
|SFB_P2PSummary  <br/> |Número de sesiones de punto a punto en las que participó el usuario.  <br/> |
|SFB_ConfOrgSummary  <br/> |Número de sesiones de conferencia que organizó el usuario.  <br/> |
|SFB_ConfPartSummary  <br/> |Número de sesiones de conferencia en las que participó el usuario.  <br/> |

> [!NOTE]
> Teams_HasOtherAction significa que el usuario se considera activo, pero tiene un valor cero para los mensajes de chat, las llamadas 1:1, los mensajes de canal, el total de reuniones y las reuniones organizadas.
   
### <a name="data-table---tenant-product-usage"></a>Tabla de datos: Uso de producto de espacio empresarial

En esta tabla se proporcionan datos de adopción mes a mes en términos de usuarios habilitados, activos, devueltos y por primera vez para cada producto dentro de Microsoft 365. Los valores de Microsoft 365 representan el uso activo en cualquiera de los productos.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|Product  <br/> |Nombre de los productos para los que se resume la información de uso. El valor de Microsoft 365 en la columna product representa la actividad en cualquiera de los productos.  <br/> |
|Timeframe  <br/> |Month value. There will be one row per product per month for the last 12 months including the current partial month.  <br/> |
|EnabledUsers  <br/> |Número de usuarios habilitados para usar el producto para el valor de período de tiempo; si un usuario se ha habilitado para parte del mes, se siguen contando.  <br/> |
|ActiveUsers  <br/> |Número de usuarios que realizaron una actividad intencionada en el producto para el valor de período de tiempo.  <br/> A user is counted as active for a product in a particular month, if they have performed one of the key activities in the product. The key activities are available in the **Tenant Product Activity** table.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuarios habilitados para usar un producto y que usaron el producto hasta el mes del período de tiempo como mínimo una vez desde que se inició la recopilación de datos en el nuevo sistema de uso.  <br/> |
|MoMReturningUsers  <br/> |Número de usuarios que estuvieron activos en el mes del período de tiempo y que también estuvieron activos en el mes anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuarios que estuvieron activos por primera vez en el período de tiempo desde la recopilación de datos el nuevo sistema de uso.  <br/> Un usuario se contabiliza como nuevo en un mes específico si detectamos su actividad por primera vez desde el inicio de la recopilación de datos en este nuevo sistema de informes. Una vez que se cuenta como usuario por primera vez, incluso si este usuario tiene una gran brecha en su actividad, nunca se volverá a contar como usuario por primera vez.  <br/> |
|ContentDate  <br/> |Si en el período de tiempo se muestra el mes actual, este valor representará la fecha más reciente del mes actual para los que están disponibles los datos.  <br/> Si en el período de tiempo se muestra el mes anterior, este valor representará la última fecha del mes del período de tiempo.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Tabla de datos: Actividad de producto de espacio empresarial

En esta tabla se proporcionan totales mensuales de actividad y número de usuarios activos para varias actividades dentro de los productos.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|Timeframe  <br/> |Month value. There will be one row per product per month for the last 12 months including the current partial month.  <br/> |
|Producto  <br/> |Nombre del producto en Microsoft 365 para el que están disponibles los datos de uso.  <br/> |
|Actividad  <br/> |Nombre de la actividad de un producto usado para presentar el uso activo de un producto.  <br/> |
|ActivityCount  <br/> |Este es el número total de acciones contabilizadas para cada actividad realizada en el producto en todos los usuarios activos.  <br/> **Nota:** Para actividades de SharePoint Online y OneDrive para la Empresa, este valor representa el número de documentos distintos con los que interactuaron los usuarios.  <br/> |
|ActiveUserCount  <br/> |Número de usuarios que realizó la actividad en el producto.  <br/> |
|TotalDurationInMinute  <br/> |Duración en minutos de todos los usuarios activos que usaron una sesión de audio o vídeo en una actividad de Skype Empresarial correspondiente.  <br/> |
|ContentDate  <br/> |Si en el período de tiempo se muestra el mes actual, este valor representará la fecha más reciente del mes actual para los que están disponibles los datos.  <br/> Si en el período de tiempo se muestra el mes anterior, este valor representará la última fecha del mes del período de tiempo.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Tabla de datos: Uso de buzón de espacio empresarial

Esta tabla consta de datos de resumen en todos los usuarios con licencia Exchange Online que tienen un buzón de usuario. Contiene el estado de fin de mes de todos los buzones de usuario. Los datos de esta tabla no se aditivan en varios meses. Los datos del mes más reciente de esta tabla representan el estado más reciente.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|TotalMailboxes  <br/> |Número de buzones de usuario para la suscripción de Microsoft 365.  <br/> |
|IssueWarningQuota  <br/> |Cuota total para emitir advertencias en todos los buzones de correo de todos los usuarios.  <br/> |
|ProhibitSendQuota  <br/> |Cuota total para prohibir el envío en todos los buzones de usuario.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Cuota total para prohibir la cuota de envío y recepción en todos los buzones de usuario.  <br/> |
|TotalItemBytes  <br/> |Cantidad de almacenamiento usado en todos los buzones de usuario en bytes.  <br/> |
|MailboxesNoWarning  <br/> |Número de buzones de usuario que estaban por debajo del límite de advertencia de almacenamiento.  <br/> |
|MailboxesIssueWarning  <br/> |Número de buzones de usuario en los que se emitió una advertencia por la cuota de almacenamiento.  <br/> |
|MailboxesExceedSendQuota  <br/> |Número de buzones de usuario que superaron la cuota de envío.  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |Número de buzones de usuario que han superado la cuota de envío y recepción.  <br/> |
|DeletedMailboxes  <br/> |Número de buzones de usuario eliminados en un período de tiempo.  <br/> |
|Timeframe  <br/> |Valor del mes.  <br/> |
|ContentDate  <br/> |Si en el período de tiempo se muestra el mes actual, este valor representará la fecha más reciente del mes actual para los que están disponibles los datos.  <br/> Si en el período de tiempo se muestra el mes anterior, este valor representará la última fecha del mes del período de tiempo.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Tabla de datos: Uso de cliente de espacio empresarial

En esta tabla se proporcionan datos de resumen mensuales sobre los clientes que los usuarios usan para conectarse a Exchange Online, Skype Empresarial y Yammer. Esta tabla aún no tiene datos de uso de cliente para SharePoint Online y OneDrive para la Empresa.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|Producto  <br/> |Nombre del producto en Microsoft 365 para el que están disponibles los datos de uso del cliente.  <br/> |
|ClientId  <br/> |Nombre de cada dispositivo usado para conectarse al producto.  <br/> |
|UserCount  <br/> |Número de usuarios que usó cada uno de los clientes de cada producto.  <br/> |
|Timeframe  <br/> |Valor del mes  <br/> |
|ContentDate  <br/> |Si en el período de tiempo se muestra el mes actual, este valor representará la fecha más reciente del mes actual para los que están disponibles los datos.  <br/> Si en el período de tiempo se muestra el mes anterior, este valor representará la última fecha del mes del período de tiempo.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Tabla de datos: Uso de SharePoint Online de espacio empresarial

Esta tabla consiste en los datos de resumen de mes a mes sobre el uso o la actividad de sitios de SharePoint Online. Esto solo cubre los sitios de grupo. El estado de fin de mes de los sitios de SharePoint Online se representa en esta columna, por ejemplo, si un usuario creó cinco documentos y usó 10 MB para el almacenamiento total, y luego eliminó algunos archivos y agregó más archivos para que al final del mes el estado de los archivos sea siete en total que usan cinco MB de almacenamiento,  el valor de representado en esta tabla es el estado de fin de mes. Esta tabla está oculta para evitar contabilizar duplicados de agregaciones y se usa como origen para crear dos tablas de referencia.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|SiteType  <br/> |Valor de tamaño de sitio (cualquiera/equipo/grupo) ("cualquiera" representa uno de estos dos tipos de sitio).  <br/> |
|TotalSites  <br/> |Número de sitios que existían al final del período de tiempo.  <br/> |
|DocumentCount  <br/> |Número total de documentos que existían en el sitio al final del período de tiempo.  <br/> |
|Diplansed  <br/> |Suma del total de almacenamiento usado en todos los sitios al final del período de tiempo.  <br/> |
|ActivityType  <br/> |Número de sitios que registraron los diferentes tipos de actividad de archivos (cualquiera/archivos activos/archivos compartidos ext. o int./archivos sincronizados).  <br/> Representa cualquiera de la actividad de archivo que se realizó.  <br/> |
|SitesWithOwnerActivities  <br/> |Número de sitios activos donde el propietario del sitio realizó una actividad de archivos específica en sus propios sitios. Puede obtener el propietario del sitio desde el comando de PowerShell **get-sposite**. Esta es la persona responsable del sitio.   <br/> |
|SitesWithNonOwnerActivities  <br/> |Número de sitios activos sumados del mes donde los usuarios distintos al propietario del sitio realizaron una actividad de archivos específica en los sitios. Puede obtener el propietario del sitio desde el comando de PowerShell **get-sposite**. Esta es la persona responsable del sitio. <br/> |
|ActivityTotalSites  <br/> |Number of sites that recorded any activity during the timeframe. If a site that had activity earlier in the timeframe, and was deleted by the end of the timeframe, it would still be counted in the active site total for that timeframe.  <br/> |
|Timeframe  <br/> |This column has the date value. Used as Many to one relationship for Calendar table.  <br/> |
|ContentDate  <br/> |Si en el período de tiempo se muestra el mes actual, este valor representará la fecha más reciente del mes actual para los que están disponibles los datos.  <br/> Si en el período de tiempo se muestra el mes anterior, este valor representará la última fecha del mes del período de tiempo.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Tabla de datos: uso de OneDrive para inquilinos

Esta tabla proporciona datos sobre las cuentas de OneDrive, como el número de cuentas, el número de documentos en las cuentas de OneDrive, el almacenamiento usado y el número de archivos por tipo de actividad. En esta tabla se representa el estado de fin de mes de las cuentas de OneDrive para la Empresa. Por ejemplo, si un usuario creó cinco documentos que usaron 10 MB de almacenamiento y luego eliminó algunos y agregó más archivos para que a finales de mes tenga siete archivos que usen cinco MB de almacenamiento, el valor de fin de mes se representará en esta tabla al final del mes.
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|SiteType  <br/> |El valor es "OneDrive".  <br/> |
|TotalSites  <br/> |Número de cuentas de OneDrive para la Empresa que existían al final del período de tiempo.  <br/> |
|DocumentCount  <br/> |Número total de documentos que existían en todas las cuentas de OneDrive para la Empresa al final del período de tiempo.  <br/> |
|Diplansed  <br/> |El almacenamiento total usado se suma en toda la cuenta de OneDrive al final del período de tiempo.  <br/> |
|ActivityType  <br/> |Número de cuentas que registraron los diferentes tipos de actividad de archivos (cualquiera/archivos activos/archivos compartidos ext. o int./archivos sincronizados).  <br/> "Cualquiera" representa cualquier actividad de archivo que se realizó.  <br/> |
|SitesWithOwnerActivities  <br/> |Número de cuentas activas de OneDrive para la Empresa en las que el propietario de la cuenta realizó una actividad de archivos específica en su propia cuenta.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Número de cuentas de OneDrive para la Empresa donde usuarios distintos al propietario de la cuenta realizaron actividades de archivos.  <br/> |
|ActivityTotalSites  <br/> |Number of OneDrive for Business accounts that recorded any activity during the timeframe. If a OneDrive for Business account had activity earlier in the timeframe, and was deleted by the end of the timeframe, it would still be counted in the active OneDrive for Business account for that timeframe.  <br/> |
|Timeframe  <br/> |This column has the date value. Used as Many to one relationship for Calendar table.  <br/> |
|ContentDate  <br/> |Si en el período de tiempo se muestra el mes actual, este valor representará la fecha más reciente del mes actual para los que están disponibles los datos.  <br/> Si en el período de tiempo se muestra el mes anterior, este valor representará la última fecha del mes del período de tiempo.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Tabla de datos: uso de Grupos de Microsoft 365 de inquilinos

En esta tabla se proporcionan datos sobre cómo se usa Grupos de Microsoft 365 en toda la organización.
  
****

|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|Plazo  <br/> |Valor del mes. Verá una fila por producto y mes para los últimos 12 meses, incluido el mes parcial actual.  <br/> |
|GroupType  <br/> |Tipo de grupo (privado/público/cualquiera).  <br/> |
|TotalGroups  <br/> |Número de grupos en cada tipo de grupo.  <br/> |
|ActiveGroups  <br/> |Número de grupos activos.  <br/> |
|MBX_TotalGroups  <br/> |Número de grupos de buzones.  <br/> |
|MBX_ActiveGroups  <br/> |Número de grupos de buzones activos.  <br/> |
|MBX_TotalActivities  <br/> |Número de actividades de buzón de correo.  <br/> |
|MBX_TotalItems  <br/> |Número de elementos de buzón de correo.  <br/> |
|MBX_StorageUsed  <br/> |Cantidad de almacenamiento de buzón usado.  <br/> |
|SPO_TotalGroups  <br/> |Número de grupos de SharePoint.  <br/> |
|SPO_ActiveGroups  <br/> |Número de grupos de SharePoint activos.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Número de grupos de SharePoint a los que se ha accedido a las actividades de archivos.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Número de grupos de SharePoint que tienen actividades sincronizadas de archivos.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Número de grupos de SharePoint que tienen actividades compartidas internamente o con grupos (que pueden incluir usuarios externos).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Número de grupos de SharePoint que han compartido actividades externamente.  <br/> |
|SPO_TotalActivities  <br/> |Número de actividades de SharePoint.  <br/> |
|SPO_FileAccessedActivities  <br/> |Número de actividades a las que se ha accedido al archivo de SharePoint.  <br/> |
|SPO_FileSyncedActivities  <br/> |Número de actividades sincronizadas de archivos de SharePoint.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Número de actividades compartidas de archivos de SharePoint internamente o con grupos (que pueden incluir miembros externos).  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Número de actividades compartidas de archivos de SharePoint externamente.  <br/> |
|SPO_TotalFiles  <br/> |Número de archivos de SharePoint.  <br/> |
|SPO_ActiveFiles  <br/> |Número de archivos de SharePoint activos.  <br/> |
|SPO_StorageUsed  <br/> |Cantidad de almacenamiento de SharePoint usado.  <br/> |
|YAM_TotalGroups  <br/> |Número de grupos de Yammer.  <br/> |
|YAM_ActiveGroups  <br/> |Número de grupos de Yammer activos.  <br/> |
|YAM_LikedActiveGroups  <br/> |Número de grupos de Yammer que tienen actividades similares.  <br/> |
|YAM_PostedActiveGroups  <br/> |Número de grupos de Yammer que tienen actividades posteriores.  <br/> |
|YAM_ReadActiveGroups  <br/> |Número de grupos de Yammer que tienen actividades de lectura.  <br/> |
|YAM_TotalActivities  <br/> |Número de actividades de Yammer.  <br/> |
|YAM_LikedActivities  <br/> |Número de actividades similares a Yammer.  <br/> |
|YAM_PostedActivties  <br/> |Número de actividades de publicación de Yammer.  <br/> |
|YAM_ReadActivites  <br/> |Número de actividades de lectura de Yammer.  <br/> |

### <a name="data-table---tenant-office-licenses"></a>Tabla de datos: Licencias de Office para inquilinos

En esta tabla se proporcionan datos de resumen mensuales sobre la asignación de licencias para los usuarios. 
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|LicenseName  <br/> |Nombre de la licencia.  <br/> |
|AssignedCount  <br/> |Número de licencias asignadas.  <br/> |
|Timeframe  <br/> |Valor del mes.  <br/> |

### <a name="data-table---tenant-office-activation"></a>Tabla de datos: Activación de Office de espacio empresarial

En la tabla se proporcionan datos sobre el número de activaciones de suscripción de Office en los planes de servicio, por ejemplo, Aplicaciones Microsoft 365 para empresas, Visio y Project. También proporciona datos sobre el número de activaciones por dispositivo (Android/iOS/Mac/PC).
  
|**Nombre de columna**|**Descripción de columna**|
|:-----|:-----|
|ServicePlanName  <br/> |Proporciona una lista de los valores de nombres de plan de servicio y un recuento de activaciones por dispositivo, como se muestra en las columnas siguientes.  <br/> |
|TotalEnabled  <br/> |Número de usuarios habilitados por nombre de plan de servicio al final del período de tiempo.  <br/> |
|TotalActivatedUsers  <br/> |Número de usuarios que activaron cada plan de servicio al final del período de tiempo.  <br/> |
|AndroidCount  <br/> |Número de activaciones por plan de servicio de dispositivos Android al final del período de tiempo.  <br/> |
|iOSCount  <br/> |Número de activaciones por plan de servicio de dispositivos iOS al final del período de tiempo.  <br/> |
|MacCount  <br/> |Número de activaciones por plan de servicio de dispositivos Mac al final del período de tiempo.  <br/> |
|PcCount  <br/> |Número de activaciones por plan de servicio de dispositivos PC al final del período de tiempo.  <br/> |
|WinRtCount  <br/> |Número de activaciones por plan de servicio de dispositivos con Windows Mobile al final del período de tiempo.  <br/> |
|Timeframe  <br/> |This column has the date value. Used as Many to one relationship for Calendar table.  <br/> |
|ContentDate  <br/> |Si en el período de tiempo se muestra el mes actual, este valor representará la fecha más reciente del mes actual para los que están disponibles los datos.  <br/> Si en el período de tiempo se muestra el mes anterior, este valor representará la última fecha del mes del período de tiempo.  <br/> |
