---
title: Actividades posteriores a la migración de Microsoft Cloud Deutschland
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
description: 'Resumen: actividades posteriores a la migración después de pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 745589c1c997540094fc4a770e437de89015f88a
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591761"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Actividades posteriores a la migración de Microsoft Cloud Deutschland

Las secciones siguientes proporcionan actividades posteriores a la migración para varios servicios después de pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.

## <a name="azure-ad"></a>Azure AD

### <a name="azure-ad-connect"></a>Azure AD Connect
**Se aplica a:** Todos los clientes sincronizan identidades con Azure AD connect

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Actualice Azure AD Connect. | Una vez completado el recorte a Azure AD, la organización usa completamente los servicios de Office 365 y ya no está conectada a Microsoft Cloud Deutschland. En este momento, el cliente debe asegurarse de que el proceso de sincronización delta se ha finalizado y, después, cambiar el valor de cadena de `AzureInstance` 3 (Microsoft Cloud Deutschland) a 0 en la ruta de acceso del Registro `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Cambie el valor de `AzureInstance` , la clave del Registro. Si no lo hace, los objetos no se sincronizarán después de que los puntos de conexión de Microsoft Cloud Deutschland ya no estén disponibles. |
|||||

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Autenticación federada de Azure AD con AD FS
**Se aplica a:** Todos los clientes que usan autenticación federada con AD FS

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Quitar confianzas de usuario de confianza de Microsoft Cloud Deutschland AD FS. | Una vez completado el recorte a Azure AD, la organización usa completamente los servicios de Office 365 y ya no está conectada a Microsoft Cloud Deutschland. En este punto, el cliente debe quitar la confianza de usuario de confianza a los puntos de conexión de Microsoft Cloud Deutschland. Esto solo se puede hacer cuando ninguna de las aplicaciones del cliente apunta a puntos de conexión de Microsoft Cloud Deutschland cuando Azure AD se aprovecha como proveedor de identidades (IdP). | Organizaciones de autenticación federada | Ninguno. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Aprobaciones de grupo
**Se aplica a:** Usuarios finales cuyas solicitudes de aprobación de grupo de Azure AD no se aprobaron en los últimos 30 días antes de la migración 

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Las solicitudes para unirse a un grupo de Azure AD en los últimos 30 días antes de la migración tendrán que volver a solicitarse si la solicitud original no se aprobó. | Los clientes del usuario final tendrán que usar el panel de Access para enviar una solicitud para unirse de nuevo a un grupo de Azure AD si dichas solicitudes no se aprobaron en los últimos 30 días antes de la migración. |  Como usuario final: <ol><li>Vaya al [panel De acceso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Busque un grupo de Azure AD para el que la aprobación de pertenencia estaba pendiente durante los 30 días antes de la migración.</li><li>Solicitar unirse de nuevo al grupo de Azure AD.</li></ol> Las solicitudes para unirse a un grupo que están activos menos de 30 días antes de la migración no se pueden aprobar, a menos que se soliciten de nuevo después de la migración. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>Actualizaciones dns personalizadas
**Se aplica a:**  Todos los clientes que administran sus propias zonas DNS

| Pasos | Descripción | Impacto |
|:------|:-------|:-------|
| Actualice los servicios DNS locales para los puntos de conexión de servicios de Office 365. | Las entradas DNS administradas por el cliente que apuntan a Microsoft Cloud Deutschland deben actualizarse para que apunten a los extremos de servicios globales de Office 365. | Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

## <a name="third-party-services"></a>Servicios de terceros
**Se aplica a:** Clientes que usan servicios de terceros para puntos de conexión de servicios de Office 365

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Actualice los partners y servicios de terceros para los puntos de conexión de servicios de Office 365. | <ul><li>Los servicios y asociados de terceros que apunten a Office 365 Germany deben actualizarse para que apunten a los extremos de servicios de Office 365. Ejemplo: vuelva a registrar, en alineación con sus proveedores y asociados, la versión de la aplicación de galería de aplicaciones, si está disponible. </li><li>Apunte todas las aplicaciones personalizadas que aprovechan la API de Graph `graph.microsoft.de` de `graph.microsoft.com` a . Otras API con puntos de conexión modificados también deben actualizarse, si se aprovechan. </li><li>Cambie todas las aplicaciones empresariales que no son de primera persona para redirigir a los puntos de conexión mundiales. </li></ul>| Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

## <a name="sharepoint-online"></a>SharePoint en linea
**Se aplica a**: Clientes que usan flujos de trabajo de SharePoint 2013

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Vuelva a publicar flujos de trabajo de SharePoint 2013. | En el trabajo previo a la migración, se redujo el número de flujos de trabajo de SharePoint 2013. Ahora, una vez completada la migración, el cliente puede volver a publicar los flujos de trabajo. | Se trata de una acción necesaria. Si no lo hace, puede provocar confusión del usuario y llamadas al servicio de ayuda. |
| Compartir elementos a través de Outlook | El uso compartido de elementos en SharePoint Online y OneDrive para la Empresa a través de Outlook ya no funciona después de la transferencia del espacio empresarial. |<ul><li>En SharePoint Online y OneDrive para la Empresa, puede compartir elementos a través de Outlook. Después de presionar el botón de Outlook, se crea un vínculo que se puede compartir y se inserta en un nuevo mensaje en Outlook Web App.</li><li>Después de la extensión del espacio empresarial, este método de uso compartido no funcionará. Reconocemos que se trata de un problema conocido. Sin embargo, dado que esta característica de Outlook está en la ruta de desuso, no se planea solucionar el problema hasta que se desaproteje. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange en línea
**Se aplica a**: Clientes que usan una configuración híbrida de Exchange

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Vuelva a ejecutar el Asistente para configuración híbrida (HCW) en los servicios de Office 365. | La configuración de HCW existente está pensada para admitir Microsoft Cloud Deutschland. Una vez completada la migración de los servicios exchange, desasociamos la configuración local de Microsoft Cloud Deutschland. |<ul><li>Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en clientes de software. Antes de que comience la migración de buzones de Exchange (con 5 o más días de aviso), notifique a los clientes que deben detener y eliminar cualquier movimiento de incorporación o desaborde de sus buzones.  Si no lo hacen, verán errores en sus solicitudes de movimiento. </li><li>Una vez completada la migración de buzones de Exchange, notifique a los clientes que pueden reanudar los movimientos de incorporación y de salida. <br> Es posible que la ejecución de **Test-MigrationServerAvailabiilty**, un cmdlet de PowerShell, durante la migración de Exchange desde Microsoft Cloud Deutschland a los servicios de Office 365 no funcione. Sin embargo, funcionará correctamente una vez completada la migración. </li><li>Si los clientes tienen problemas con las credenciales o la autorización después de migrar los buzones, los usuarios pueden volver a escribir sus credenciales de administrador local en el extremo de migración ejecutando o estableciendo lo mismo mediante el Panel de `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` control de Exchange (ECP). </li></ul>|
