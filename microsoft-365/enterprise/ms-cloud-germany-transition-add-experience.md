---
title: Acciones y efectos de las fases de migración para la migración desde Microsoft Cloud Alemania (avanzado)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: información adicional de la experiencia del usuario al cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de datos en alemán.'
ms.openlocfilehash: 3f22ca9c380b3271d0c186be1f50fae4a0ea5bb9
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688198"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Acciones y efectos de las fases de migración para la migración desde Microsoft Cloud Alemania (avanzado) 

En las siguientes secciones se proporciona información adicional sobre las experiencias de los clientes al cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de datos en alemán.

## <a name="services"></a>Servicios

### <a name="azure-ad"></a>Azure AD

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Inquilino de Azure AD en Microsoft Cloud Alemania se ha copiado en Office 365 Services. | Azure AD copia el espacio empresarial en los servicios de Office 365. Se conservan los identificadores de inquilino y de usuario. Las llamadas de servicio de Azure AD se redirigen desde Microsoft Cloud Alemania a Office 365 Services y son transparentes para los servicios. | Todos los clientes de Office | : El Reglamento General de protección de datos (RGPD) las solicitudes de interesados de datos (interesado) se ejecutan desde el portal de administración de Azure para solicitudes futuras. Cualquier dato de diagnóstico heredado o no de cliente que resida en Microsoft Cloud Alemania se elimina en o antes de que transcurran 30 días. <br><br> -Los clientes que usan las autenticaciones federadas con los servicios de Federación de Active Directory (AD FS) no deberían realizar cambios en las URI del emisor que se usan para todas las autenticaciones con Active Directory local durante la migración. Cambiar los URI del emisor conducirá a errores de autenticación para los usuarios del dominio. Los URI del emisor se pueden cambiar directamente en AD FS o cuando un dominio se convierte de _administrado_ a _federado_ y viceversa. Se recomienda a los clientes no agregar, quitar o convertir un dominio federado en el inquilino de Azure AD que se ha migrado. Los URI del emisor se pueden cambiar una vez que la migración se haya completado completamente. <br><br> -Solicitudes de autenticación multifactor (MFA) que usen Microsoft Authenticator display como el ObjectID del usuario (un GUID) mientras el inquilino se copia en los servicios de Office 365. Las solicitudes de MFA funcionarán según lo esperado a pesar de este comportamiento de visualización.  Las cuentas de Microsoft Authenticator que se activaron con los extremos de servicios de Office 365 mostrarán el nombre principal de usuario (UPN).  Las cuentas agregadas con los extremos de Alemania de Microsoft Cloud mostrarán el ObjectID de usuario, pero funcionarán con los extremos de Microsoft Cloud Alemania y servicios de Office 365.  |
| Establecer AuthServer local que apunte al servicio de STS global. | Esto garantiza que las solicitudes de los usuarios que migren a Microsoft Cloud Alemania para las solicitudes de disponibilidad de Exchange que tengan como destino el entorno local híbrido se autentiquen para tener acceso al servicio local. De forma similar, Esto garantizará la autenticación de las solicitudes de los extremos de servicios locales a Office 365. | Clientes de Exchange Online con implementaciones híbridas (locales) | Una vez completada la migración de Azure AD, el administrador de la topología de Exchange local (híbrido) debe agregar un nuevo punto de conexión de servicio de autenticación para los servicios de Office 365. Con este comando de Exchange PowerShell, reemplace `<TenantID>` con el identificador de inquilino de su organización (se encuentra en Azure portal en **Azure Active Directory**). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Si no se completa esta tarea, es posible que las solicitudes de disponibilidad híbrida no puedan proporcionar información para los usuarios de buzones de correo que se han migrado desde Microsoft Cloud Alemania a los servicios de Office 365.  |
| Migración de recursos de Azure. | Los clientes que usan los recursos de Office 365 y Azure (por ejemplo, red, cálculo y almacenamiento) realizarán la migración de recursos a la instancia de servicios de Office 365. Esta migración es responsabilidad de los clientes. Las publicaciones del centro de mensajes señalarán el inicio. La migración se debe completar antes de la finalización de la organización de Azure AD en el entorno de servicios de Office 365. | Clientes de Azure | Para las migraciones de Azure, vea la guía de migración de Azure, introducción a la [Guía de migración para Azure Germany](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

### <a name="exchange-online"></a>Exchange en línea

Si está usando **set-UserPhoto**:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| La nueva región de Alemania se agrega a la configuración de la organización existente y los buzones de correo se mueven a los servicios de Office 365. | La configuración de Exchange Online agrega la nueva región alemana go-local a la organización de transición. Esta región de servicios de Office 365 está configurada como predeterminada, lo que permite que el servicio de equilibrio de carga interno redistribuya los buzones de correo a la región predeterminada adecuada en los servicios de Office 365. En esta transición, los usuarios de cada lado (los servicios de Alemania o Office 365) están en la misma organización y pueden usar cualquier punto de conexión de dirección URL. |  Exchange en línea | Si se ha migrado un buzón de usuario pero no se ha migrado un buzón de administrador, o viceversa, los administradores no podrán ejecutar **set-UserPhoto**, un cmdlet de PowerShell. En esta situación, el administrador debe pasar una cadena adicional `ConnectionUri` durante la conexión configurada mediante la siguiente sintaxis: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> donde `<user_email>` es el marcador de posición para el identificador de correo electrónico del usuario cuya foto tiene que cambiarse mediante **set-UserPhoto**. |
|||||

Si está usando una implementación híbrida local:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
|Detenga o elimine los movimientos de incorporación o de descarga de los buzones de correo.  | Esto garantiza que no se produzca un error en las solicitudes de movimiento. | Clientes de Exchange Online con implementaciones híbridas (locales) | Acción necesaria. De lo contrario, se puede producir un error en el servicio o en los clientes de software. |
|||||

### <a name="dynamics"></a>Dynamics

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Recursos de Microsoft Dynamics | Los clientes con Microsoft Dynamics serán los encargados de ingeniería o FastTrack para realizar la transición de Dynamics a la instancia de servicios de Office 365. | Clientes de Microsoft Dynamics 365 | -Después de la migración, el administrador valida la organización. <br><br> -El administrador modifica los flujos de trabajo, según sea necesario. <br><br> -El administrador borra el modo AdminOnly según corresponda. <br><br> -El administrador cambia el tipo de organización del _espacio aislado_, según corresponda <br><br> -Notifique a los usuarios finales de la nueva dirección URL para que tengan acceso a la instancia (org). <br><br> -Actualizar las conexiones entrantes a la nueva dirección URL del extremo. <br><br> -El servicio de Dynamics no estará disponible para los usuarios durante la transición. <br><br> -Los usuarios deben validar el estado y las características de la organización después de la migración de cada organización.  |
|||||

\* (i) los clientes con Microsoft Dynamics 365 deben realizar acciones en este escenario de migración tal como se define en el proceso de migración proporcionado. (II) un error del cliente en emprender una acción significará que Microsoft no podrá completar la migración. (III) cuando Microsoft no puede completar la migración debido a la inacción del cliente, la suscripción del cliente expirará el 29 de octubre de 2021. 


### <a name="power-bi"></a>Power BI

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Migración de recursos de Power BI | Los clientes con Microsoft Power BI serán ocupados por ingeniería o FastTrack después de desencadenar manualmente una herramienta de migración de PBI para migrar Power BI a la instancia de servicios de Office 365.\*\* | Clientes de Microsoft Power BI | - _No_ se realizará la transición de los siguientes elementos de Power BI y tendrá que volver a crearlos: <br><br> -Conjuntos de la configuración en tiempo real (por ejemplo, conjuntos de valores de streaming o push). <br> -Origen de datos y configuración de puerta de enlace de datos de Power BI local. <br> -Los informes creados con los conjuntos de los datasets en tiempo real no estarán disponibles después de la migración y deben volver a crearse. <br><br> -Los servicios de Power BI no estarán disponibles para los usuarios durante la transición. La no disponibilidad del servicio no debe ser superior a 24 horas. <br><br> -Los usuarios tendrán que volver a configurar los orígenes de datos y sus puertas de enlace de datos locales con el servicio de Power BI después de la migración.  Hasta que lo hagan, los usuarios no podrán usar estos orígenes de datos para realizar la actualización programada ni dirigir consultas directas con estos orígenes de datos. <br><br> -Los espacios de trabajo Premium y las capacidades no se pueden migrar. Los clientes necesitan eliminar todas las capacidades antes de la migración y volver a crearlas después de la migración. Mueva los espacios de trabajo de nuevo a la capacidad que desee.  |
|||||

\*\* (i) los clientes con Microsoft Power BI deben realizar acciones en este escenario de migración tal como se define en el proceso de migración proporcionado. (II) un error del cliente en emprender una acción significará que Microsoft no podrá completar la migración. (III) cuando Microsoft no puede completar la migración debido a la inacción del cliente, la suscripción del cliente expirará el 29 de octubre de 2021. 


### <a name="office-apps"></a>Aplicaciones de Office

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Clientes, Office Online durante el traslado del cliente de Office, Azure AD finaliza el ámbito del inquilino para apuntar a los servicios de Office 365. | Este cambio de configuración permite a los clientes de Office actualizar y apuntar a los puntos de conexión de servicios de Office 365. | Todos los clientes de Office | -Quitar MSOID CName del DNS de propiedad del cliente, si existe. <br><br> -Notifique a los usuarios que deben cerrar _todas las_ aplicaciones de Office y, a continuación, volver a iniciar sesión (o forzar a los clientes a reiniciarse y usuarios que inicien sesión) para permitir que los clientes de Office recojan el cambio. <br><br> -Notificar a los usuarios y al personal del servicio de asistencia que los usuarios *pueden* ver un banner de Office que les pide que reactiven las aplicaciones de Office en un plazo de 72 horas a partir del traslado. <br><br> -Todas las aplicaciones de Office en equipos personales deben estar cerradas y los usuarios deben cerrar sesión de nuevo. En la barra de activación amarilla, inicie sesión para reactivarlo con los servicios de Office 365. <br><br> -Los equipos compartidos requerirán acciones similares a las de los equipos personales y no requerirán un procedimiento especial. <br><br> -En dispositivos móviles, los usuarios deben cerrar la sesión de las aplicaciones, cerrarlas y, a continuación, volver a iniciar sesión. |
|||||

## <a name="during-migration"></a>Durante la migración


### <a name="exchange-online"></a>Exchange en línea

Para la exhibición de documentos electrónicos:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Durante la migración, se producirá un error en las búsquedas de eDiscovery o se devolverán 0 resultados para las ubicaciones de SharePoint Online, OneDrive para la empresa y Exchange online que se hayan migrado. | Durante la migración, los clientes pueden seguir creando casos, suspensiones, búsquedas y exportaciones en el [centro de cumplimiento de & de seguridad](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations), incluida la búsqueda de [contenido](https://docs.microsoft.com/microsoft-365/compliance/search-for-content).  Sin embargo, las búsquedas en SharePoint Online, OneDrive para la empresa y las ubicaciones de Exchange online que se han migrado devolverán 0 resultados o producirá un error. Para la corrección, vea la columna _impacto_ . | Todos los clientes que usan eDiscovery |  En el caso de que una búsqueda devuelva 0 resultados o un error durante la migración, realice la siguiente acción para SharePoint Online: <br><br>  Descargue sitios directamente desde el sitio de SharePoint Online o OneDrive para la empresa siguiendo las instrucciones de [descargar archivos y carpetas de onedrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Este método requerirá permisos de administrador de SharePoint Online o permisos de solo lectura en el sitio. <br><br> Si se superan los límites, tal y como se explica en [descargar archivos y carpetas de onedrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), los clientes pueden usar el cliente de sincronización de onedrive para la empresa siguiendo las instrucciones de [sincronización de archivos de SharePoint y Teams con el equipo](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88). <br><br> -Exchange Online <br><br> - [Exhibición de documentos electrónicos local en Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="sharepoint-online"></a>SharePoint Online

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Se realiza la transición de SharePoint y OneDrive. | SharePoint y OneDrive se migran desde Microsoft Cloud Alemania a los servicios de Office 365 en esta fase. Se conservan las URL de Alemania de Microsoft Cloud existentes ( `contoso.sharepoint.de` ). Los tokens emitidos por Microsoft Cloud Alemania u Office 365 Services son válidos durante la transición. | Clientes de SharePoint | Inflight SharePoint 2013 flujos de trabajo se romperán durante la migración y deben volver a publicarse después de la migración. |
|||||

### <a name="skype-for-business-online"></a>Skype Empresarial Online

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Migración de Skype empresarial a Microsoft Teams. | Los clientes existentes de Skype empresarial se migran a los servicios de Office 365 en Europa y, a continuación, se pasan a Microsoft Teams en la región de Alemania de los servicios de Office 365. | Clientes de Skype empresarial |  PowerShell usará para administrar la configuración y las directivas del espacio empresarial y los usuarios. Cuando se conecte a una sesión de PowerShell, agregue lo siguiente: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>Después de la migración

### <a name="azure-ad"></a>Azure AD

Para entornos híbridos:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Actualizar Azure AD Connect. | Una vez finalizado el corte en Azure AD, la organización usa por completo los servicios de Office 365 y ya no está conectado a la nube de Microsoft Alemania. En este punto, el cliente debe asegurarse de que el proceso de sincronización Delta se haya finalizado y, después de eso, cambie el valor de cadena de `AzureInstance` 3 (Microsoft Cloud Alemania) a 0 en la ruta del registro `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Organizaciones híbridas de Azure AD: organizaciones conectadas | Cambie el valor de `AzureInstance` la clave del registro. Si no lo hace, los objetos no se sincronizarán después de que los extremos de Alemania en la nube de Microsoft ya no estén disponibles. |
|||||

Para la autenticación federada:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Quitar las relaciones de confianza para usuario autenticado de Microsoft Cloud Alemania AD FS. | Una vez finalizado el corte en Azure AD, la organización usa por completo los servicios de Office 365 y ya no está conectado a la nube de Microsoft Alemania. En este momento, el cliente debe quitar la relación de confianza para usuario autenticado a los extremos de Alemania en la nube de Microsoft. Esto solo puede hacerse cuando no haya aplicaciones del cliente que apunten a los puntos de conexión de Microsoft Cloud Alemania cuando se aproveche Azure AD como un proveedor de identidades (IdP). | Organizaciones de autenticación federada | Ninguna. |
|||||

Para Azure AD:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Las solicitudes para unirse a un grupo de Azure AD en los últimos 30 días antes de la migración deberán solicitarse de nuevo si la solicitud original no se aprobó. | Los clientes del usuario final deberán usar el panel de acceso para enviar una solicitud para volver a unirse a un grupo de Azure AD si esas solicitudes no se han aprobado en los últimos 30 días antes de la migración. | Usuarios finales cuyas solicitudes de aprobación de grupos de Azure AD no se han aprobado en los últimos 30 días antes de la migración |  Como usuario final: <ol><li>Vaya al [Panel de acceso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Busque un grupo de Azure AD para el que haya pendiente la aprobación de pertenencia en los 30 días anteriores a la migración.</li><li>Solicitud para volver a unirse al grupo de Azure AD.</li></ol> Las solicitudes para unirse a un grupo que están activas menos de 30 días antes de la migración no se pueden aprobar, a menos que se vuelvan a solicitar después de la migración. |
|||||

Para DNS:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Actualizar los servicios DNS locales para los extremos de servicios de Office 365. | Las entradas DNS administradas por el cliente que señalan a Office 365 Germany deben actualizarse para que apunten a los puntos de conexión de servicios de 365 de Office. | Todos los clientes de Office | Acción necesaria. De lo contrario, se puede producir un error en el servicio o en los clientes de software. |
|||||

Para servicios de terceros para los extremos de servicios de Office 365:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Actualice los asociados y los servicios de terceros para los extremos de servicios de Office 365. | -Los servicios y socios de terceros que apuntan a Office 365 Germany deben actualizarse para que apunten a los puntos de conexión de servicios de 365 de Office. Ejemplo: vuelva a registrarse, en alineación con los proveedores y Partners, la versión de las aplicaciones de la aplicación de galería, si está disponible. <br><br> -Point todas las aplicaciones personalizadas que aprovechan la API de Graph de `graph.microsoft.de` a `graph.microsoft.com` . Si se aprovechan, también se deben actualizar otras API con los extremos cambiados. <br><br> -Cambie todas las aplicaciones empresariales que no sean de primera empresa para redirigir a los puntos de conexión en todo el mundo.  | Todos los clientes de Office | Acción necesaria. De lo contrario, se puede producir un error en el servicio o en los clientes de software. |
|||||

### <a name="exchange-online"></a>Exchange en línea

Si está usando una configuración híbrida de Exchange:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Vuelva a ejecutar el Asistente para la configuración híbrida (HCW) con los servicios de Office 365. | La configuración existente de HCW está destinada a admitir Microsoft Cloud Alemania. Una vez completada la migración de los servicios de Exchange, Desacoplamos la configuración local de la nube de Microsoft Alemania. | Clientes de Exchange online que ejecutan una implementación híbrida | -Acción necesaria. De lo contrario, se puede producir un error en el servicio o en los clientes de software. Antes de que se inicie la migración de buzones de correo de Exchange (con 5 o más días de aviso), notifique a los clientes que deben detener y eliminar los movimientos de incorporación o retirada de sus buzones.  Si no es así, verán errores en sus solicitudes de movimiento. <br><br> -Una vez completada la migración de buzones de Exchange, notifique a los clientes que pueden reanudar los movimientos de incorporación y de descarga. <br> Es posible que la ejecución de **Test-MigrationServerAvailabiilty**, un cmdlet de PowerShell, durante la migración de Exchange desde la nube de Microsoft Alemania a Office 365 servicios no funcione. Sin embargo, funcionará correctamente una vez completada la migración. <br><br> Si los clientes tienen problemas con credenciales o autorización después de migrar los buzones, los usuarios pueden volver a escribir sus credenciales de administrador local en el punto de conexión de migración al ejecutar `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` o establecer lo mismo mediante el panel de control de Exchange (ECP).  |

Para la exhibición de documentos electrónicos:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
|  Todas las ubicaciones de SharePoint Online, OneDrive para la empresa y Exchange Online se han migrado junto con el centro de seguridad y cumplimiento (SCC). | Toda la actividad de eDiscovery debe ejecutarse desde el inquilino en todo el mundo. Las búsquedas ahora serán 100% correctamente.  Los errores o errores deben seguir los canales de soporte normales. | Todos los clientes que usan eDiscovery | Ninguna. |
| Eliminación de las directivas de retención de toda la organización que se crearon durante los pasos previos a la migración | Los clientes pueden quitar las directivas de retención de toda la organización que se crearon durante el trabajo previo a la migración de los clientes. | Todos los clientes que aplicaron una directiva de retención como parte de los pasos previos a la migración. | Ninguna. |
|||||

### <a name="sharepoint-online"></a>SharePoint Online

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Volver a publicar flujos de trabajo de SharePoint 2013. | En el trabajo previo a la migración, se redujo el número de flujos de trabajo de SharePoint 2013. Ahora que la migración se ha completado, el cliente puede volver a publicar los flujos de trabajo. | Todos los clientes de Office | Se trata de una acción necesaria. Si no lo hace, es posible que se produzcan confusión en el usuario y se llame al servicio de asistencia. |
| Compartir elementos a través de Outlook | Compartir elementos a través de Outlook ya no funciona tras el traslado de inquilino. | SharePoint Online y OneDrive para la Empresa | -En SharePoint Online y OneDrive para la empresa, puede compartir elementos a través de Outlook. Después de presionar el botón de Outlook, se crea un vínculo que se pueden compartir y se inserta en un mensaje nuevo en Outlook Web App. <br><br> -Después de la transferencia del espacio empresarial, este método de uso compartido no funcionará. Reconocemos que se trata de un problema conocido. Sin embargo, dado que esta característica de Outlook está en la ruta de desuso, la solución del problema no se planea hasta que se deshace el desuso. |

## <a name="next-step"></a>Paso siguiente

[Descripción de las acciones y los efectos de las fases de migración](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Desplazarse por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-trabajo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
