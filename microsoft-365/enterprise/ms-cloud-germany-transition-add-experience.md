---
title: Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland (avanzado)
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
description: 'Resumen: información adicional de la experiencia del cliente al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: b38ed865306eb676c8f57c1dcbb4541fae43c8df
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604001"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland (avanzado) 

Las migraciones de inquilinos de Microsoft Cloud Deutschland a la región alemana de los servicios de Office 365 de Microsoft se ejecutan como un conjunto de fases y sus acciones configuradas para cada carga de trabajo. Esta figura muestra las nueve fases de migración a los nuevos centros de datos alemanes.

![Las nueve fases de migración a los nuevos centros de datos de Alemania](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

En las secciones siguientes se proporciona información adicional sobre las experiencias de los clientes al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.

## <a name="office-365-portal-services"></a>Servicios del portal de Office 365

Entre la fase 2 de 9 y la fase 3 de 9, es posible que el Portal de partners no sea accesible. Durante este tiempo, es posible que el partner no pueda tener acceso a la información de los inquilinos en el Portal de partners. Dado que cada migración es diferente, la duración de la accesibilidad podría ser en horas.

### <a name="prework-for-azure-ad-phase-2"></a>Trabajo previo para Azure AD (fase 2)

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Inquilino de Azure AD en Microsoft Cloud Deutschland copiado en Servicios de Office 365. | Azure AD copia el espacio empresarial en los servicios de Office 365. Se conservan los identificadores de inquilino y de usuario. Las llamadas de servicio de Azure AD se redirigen desde Microsoft Cloud Deutschland a los servicios de Office 365 y son transparentes para los servicios. | Todos los clientes de Office | - Las solicitudes de interesados (DSR) del Reglamento general de protección de datos (RGPD) se ejecutan desde el Portal de administración de Azure para futuras solicitudes. Los datos de diagnóstico heredados o que no son del cliente que residen en Microsoft Cloud Deutschland se eliminan en o antes de que transcurren 30 días. <br><br> - Los clientes que usan autenticaciones federadas con Servicios de federación de Active Directory (AD FS) no deben realizar cambios en los URI del emisor que se usan para todas las autenticaciones con Active Directory local durante la migración. Cambiar los URI del emisor provocará errores de autenticación para los usuarios del dominio. Los URI del emisor se pueden cambiar directamente en AD  FS o cuando un dominio se convierte de administrado a _federado_ y viceversa. Se recomienda que los clientes no agreguen, quiten o conviertan un dominio federado en el inquilino de Azure AD que se ha migrado. Los URI del emisor se pueden cambiar una vez completada la migración. <br><br> - Solicitudes de autenticación multifactor (MFA) que usan la presentación de Microsoft Authenticator como objectid de usuario (GUID) mientras el inquilino se copia en los servicios de Office 365. Las solicitudes MFA se realizarán según lo esperado a pesar de este comportamiento de presentación.  Las cuentas de Microsoft Authenticator que se activaron mediante puntos de conexión de servicios de Office 365 mostrarán el nombre principal de usuario (UPN).  Las cuentas agregadas mediante puntos de conexión de Microsoft Cloud Deutschland mostrarán el ObjectID del usuario, pero funcionarán con puntos de conexión de servicios de Microsoft Cloud Deutschland y Office 365.  |
| Migración de recursos de Azure. | Los clientes que usan recursos de Office 365 y Azure (por ejemplo, redes, proceso y almacenamiento) realizarán la migración de recursos a la instancia de servicios de Office 365. Esta migración es una responsabilidad de los clientes. Las publicaciones del Centro de mensajes marcarán el inicio. La migración debe completarse antes de finalizar la organización de Azure AD en el entorno de servicios de Office 365. | Clientes de Azure | Para las migraciones de Azure, consulte el libro de reproducción de migración de Azure, Información general sobre las instrucciones [de migración para Azure Germany](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

### <a name="exchange-online-before-phase-5"></a>Exchange Online antes de la fase 5

**Se aplica a:** Todos los clientes que usan una configuración híbrida de Exchange con servidores exchange locales

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Establecer AuthServer local que señale al servicio STS global. | Esto garantiza que las solicitudes de los usuarios que migran a Microsoft Cloud Deutschland para solicitudes de disponibilidad de Exchange destinadas al entorno local híbrido se autentican para obtener acceso al servicio local. Del mismo modo, se garantizará la autenticación de solicitudes desde locales a puntos de conexión de servicios de Office 365. | Una vez completada la migración de Azure AD, el administrador de la topología local de Exchange (híbrida) debe agregar un nuevo extremo de servicio de autenticación para los servicios de Office 365. Con este comando de Exchange PowerShell, reemplace por el identificador de inquilino de su organización (que se encuentra en `<TenantID>` Azure Portal en Azure Active **Directory**).<br><br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Si no se completa esta tarea, es posible que las solicitudes híbridas de disponibilidad no proporcionen información a los usuarios de buzones que se han migrado de Microsoft Cloud Deutschland a los servicios de Office 365.  |
|Detener o eliminar cualquier movimiento de buzón de correo de incorporación o de salida, es decir, no mover buzones entre Exchange local y Exchange Online  | Esto garantiza que las solicitudes de movimiento del buzón no fallen con un error. | Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

<!--
    Question from ckinder
    Not clear if this has to be done before, during or after phase 5
-->

**Se aplica a:** Todos los clientes que almacenan fotos de usuario en Exchange Online y usan **Set-UserPhoto**:

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| La nueva región "Alemania" se agrega a una configuración existente de la organización de Exchange Online y los buzones se mueven a los servicios de Office 365. | La configuración de Exchange Online agrega la nueva región alemana local a la organización de transición. Esta región de servicios de Office 365 se establece como predeterminada, lo que permite al servicio de equilibrio de carga interno redistribuir buzones a la región predeterminada adecuada en los servicios de Office 365. En esta transición, los usuarios de ambos lados (servicios de Alemania u Office 365) están en la misma organización y pueden usar cualquier extremo de dirección URL. | Si se ha migrado un buzón de usuario pero no se ha migrado un buzón de administrador, o viceversa, los administradores no podrán ejecutar **Set-UserPhoto**, un cmdlet de PowerShell. En esta situación, un administrador debe pasar una cadena adicional durante la configuración de la conexión `ConnectionUri` mediante la sintaxis siguiente: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> donde es el marcador de posición del identificador de correo electrónico del usuario cuya foto debe `<user_email>` cambiarse mediante **Set-UserPhoto**. |
||||

## <a name="during-migration"></a>Durante la migración

### <a name="sharepoint-online-phase-4"></a>Fase 4 de SharePoint Online

**Se aplica a:** Todos los clientes que usan eDiscovery

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| SharePoint y OneDrive se transiciónn. | SharePoint y OneDrive se migran de Microsoft Cloud Deutschland a los servicios globales de Office 365 en la fase 4. Las direcciones URL existentes de Microsoft Cloud Deutschland se conservan ( `contoso.sharepoint.de` ). Los tokens emitidos por los servicios de Microsoft Cloud Deutschland u Office 365 son válidos durante la transición. | Los flujos de trabajo de SharePoint 2013 a bordo se romperán durante la migración y deben volver a publicarse después de la migración. |
||||

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>Fase 4 de exhibición de documentos electrónicos al final de la fase 9

**Se aplica a:** Todos los clientes que usan eDiscovery

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Desde la fase 4 hasta que se complete la fase 9, las búsquedas de exhibición de documentos electrónicos producirán un error o devolverán 0 resultados para las ubicaciones de SharePoint Online, OneDrive para la Empresa y Exchange Online que se han migrado. | Durante la migración, los clientes pueden seguir crear casos, retenciones, búsquedas y exportaciones en el Centro de seguridad [& cumplimiento,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)incluida [la búsqueda de contenido.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  Sin embargo, las búsquedas en las ubicaciones de SharePoint Online, OneDrive para la Empresa y Exchange Online que se han migrado devolverán 0 resultados o producirán un error. Para obtener información sobre la corrección, consulte la _columna Impacto._ | En caso de que una búsqueda devuelva cero resultados o un error durante la migración, haga lo siguiente para SharePoint Online: <ul><li>Descargue sitios directamente desde el sitio de SharePoint Online/ OneDrive para la Empresa siguiendo las instrucciones de Descargar archivos y carpetas [de OneDrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Este método requerirá permisos de administrador de SharePoint Online o permisos de solo lectura en el sitio.</li><li>Si se superan los límites, como se explica en Descargar archivos y carpetas de OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)los clientes pueden usar el cliente de sincronización de OneDrive para la Empresa siguiendo las instrucciones de Sincronizar archivos de SharePoint y Teams con el [equipo.](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)</li><li>Para obtener más información, [vea Exhibición de](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) documentos electrónicos local en Exchange Server |
||||

## <a name="post-migration"></a>Después de la migración

### <a name="azure-ad-phase-9"></a>Fase 9 de Azure AD

**Se aplica a:** Todos los clientes sincronizan identidades con Azure AD connect

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Actualice Azure AD Connect. | Una vez completado el recorte a Azure AD, la organización usa completamente los servicios de Office 365 y ya no está conectada a Microsoft Cloud Deutschland. En este momento, el cliente debe asegurarse de que el proceso de sincronización delta se ha finalizado y, después, cambiar el valor de cadena de `AzureInstance` 3 (Microsoft Cloud Deutschland) a 0 en la ruta de acceso del Registro `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Cambie el valor de `AzureInstance` , la clave del Registro. Si no lo hace, los objetos no se sincronizarán después de que los puntos de conexión de Microsoft Cloud Deutschland ya no estén disponibles. |
|||||

**Se aplica a:** Todos los clientes que usan autenticación federada con ADFS

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Quitar confianzas de usuario de confianza de Microsoft Cloud Deutschland AD FS. | Una vez completado el recorte a Azure AD, la organización usa completamente los servicios de Office 365 y ya no está conectada a Microsoft Cloud Deutschland. En este punto, el cliente debe quitar la confianza de usuario de confianza a los puntos de conexión de Microsoft Cloud Deutschland. Esto solo se puede hacer cuando ninguna aplicación del cliente apunta a puntos de conexión de Microsoft Cloud Deutschland cuando Azure AD se aprovecha como proveedor de identidades (IdP). | Organizaciones de autenticación federada | Ninguno. |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
Para Azure AD:

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Las solicitudes para unirse a un grupo de Azure AD en los últimos 30 días antes de la migración tendrán que volver a solicitarse si la solicitud original no se aprobó. | Los clientes del usuario final tendrán que usar el panel de Access para enviar una solicitud para unirse de nuevo a un grupo de Azure AD si dichas solicitudes no se aprobaron en los últimos 30 días antes de la migración. | Usuarios finales cuyas solicitudes de aprobación de grupo de Azure AD no se aprobaron en los últimos 30 días antes de la migración |  Como usuario final: <ol><li>Vaya al [panel De acceso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Busque un grupo de Azure AD para el que la aprobación de pertenencia estaba pendiente en 30 días antes de la migración.</li><li>Solicitar unirse de nuevo al grupo de Azure AD.</li></ol> Las solicitudes para unirse a un grupo que están activos menos de 30 días antes de la migración no se pueden aprobar, a menos que se vuelvan a solicitar después de la migración. |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Se aplica a:**  Todos los clientes que administran sus propias zonas DNS

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Actualice los servicios DNS locales para los puntos de conexión de servicios de Office 365. | Las entradas DNS administradas por el cliente que apuntan a Microsoft Cloud Deutschland deben actualizarse para que apunten a los extremos de servicios globales de Office 365. | Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

Para servicios de terceros para puntos de conexión de servicios de Office 365:

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Actualice los partners y servicios de terceros para los puntos de conexión de servicios de Office 365. | <ul><li>Los servicios y asociados de terceros que apunten a Office 365 Germany deben actualizarse para que apunten a los extremos de servicios de Office 365. Ejemplo: vuelva a registrar, en alineación con sus proveedores y asociados, la versión de la aplicación de galería de aplicaciones, si está disponible. </li><li>Apunte todas las aplicaciones personalizadas que aprovechan la API de Graph `graph.microsoft.de` de `graph.microsoft.com` a . Otras API con puntos de conexión modificados también deben actualizarse, si se aprovechan. </li><li>Cambie todas las aplicaciones empresariales que no son de primera persona para redirigir a los puntos de conexión mundiales. </li></ul>| Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

### <a name="sharepoint-online-post-migration"></a>Migración posterior a SharePoint Online

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Vuelva a publicar flujos de trabajo de SharePoint 2013. | En el trabajo previo a la migración, se redujo el número de flujos de trabajo de SharePoint 2013. Ahora, una vez completada la migración, el cliente puede volver a publicar los flujos de trabajo. | Se trata de una acción necesaria. Si no lo hace, puede provocar confusión del usuario y llamadas al servicio de ayuda. |
| Compartir elementos a través de Outlook | El uso compartido de elementos en SharePoint Online y OneDrive para la Empresa a través de Outlook ya no funciona después de la transferencia del espacio empresarial. |<ul><li>En SharePoint Online y OneDrive para la Empresa, puede compartir elementos a través de Outlook. Después de presionar el botón de Outlook, se crea un vínculo que se puede compartir y se inserta en un nuevo mensaje en Outlook Web App.</li><li>Después de la extensión del espacio empresarial, este método de uso compartido no funcionará. Reconocemos que se trata de un problema conocido. Sin embargo, dado que esta característica de Outlook está en la ruta de desuso, no se planea solucionar el problema hasta que se desaproteje. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Migración posterior a Exchange Online

Si usa una configuración híbrida de Exchange:

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Vuelva a ejecutar el Asistente para configuración híbrida (HCW) en los servicios de Office 365. | La configuración de HCW existente está pensada para admitir Microsoft Cloud Deutschland. Una vez completada la migración de los servicios exchange, desasociamos la configuración local de Microsoft Cloud Deutschland. |<ul><li>Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en clientes de software. Antes de que comience la migración de buzones de Exchange (con 5 o más días de aviso), notifique a los clientes que deben detener y eliminar cualquier movimiento de incorporación o desaborde de sus buzones.  Si no lo hacen, verán errores en sus solicitudes de movimiento. </li><li>Una vez completada la migración de buzones de Exchange, notifique a los clientes que pueden reanudar los movimientos de incorporación y de salida. <br> Es posible que la ejecución de **Test-MigrationServerAvailabiilty**, un cmdlet de PowerShell, durante la migración de Exchange desde Microsoft Cloud Deutschland a los servicios de Office 365 no funcione. Sin embargo, funcionará correctamente una vez completada la migración. </li><li>Si los clientes tienen problemas con las credenciales o la autorización después de migrar los buzones, los usuarios pueden volver a escribir sus credenciales de administrador local en el extremo de migración ejecutando o estableciendo lo mismo mediante el Panel de `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` control de Exchange (ECP). </li></ul>|

### <a name="ediscovery-post-migration"></a>eDiscovery post migration

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
|  Todas las ubicaciones de SharePoint Online, OneDrive para la Empresa y Exchange Online se han migrado junto con el Centro de seguridad y cumplimiento (SCC). | Toda la actividad de exhibición de documentos electrónicos debe ejecutarse desde el espacio empresarial mundial. Las búsquedas ahora serán 100% correctas.  Cualquier error o error debe seguir los canales de soporte técnico normales. | Todos los clientes que usan eDiscovery | Ninguno. |
| Quitar directivas de retención de toda la organización que se crearon durante los pasos previos a la migración | Los clientes pueden quitar las directivas de retención de toda la organización que se crearon durante el trabajo previo a la migración de los clientes. | Todos los clientes que aplicaron una directiva de retención como parte de los pasos previos a la migración. | Ninguno. |
|||||

## <a name="next-step"></a>Paso siguiente

[Comprender las acciones y los impactos de las fases de migración](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar a través de la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
