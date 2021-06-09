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
description: 'Resumen: actividades posteriores a la migración después de pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 servicios en la nueva región del centro de datos alemán.'
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899369"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Actividades posteriores a la migración de Microsoft Cloud Deutschland

Las secciones siguientes proporcionan actividades posteriores a la migración para varios servicios después de pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 servicios en la nueva región del centro de datos alemán.

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Autenticación federada de Azure AD con AD FS
**Se aplica a:** Todos los clientes que usan autenticación federada con AD FS

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Quitar confianzas de usuario de confianza de Microsoft Cloud Deutschland AD FS. | Una vez completado el recorte a Azure AD, la organización usa completamente los servicios Office 365 y ya no está conectada a Microsoft Cloud Deutschland. En este punto, el cliente debe quitar la confianza de usuario de confianza a los puntos de conexión de Microsoft Cloud Deutschland. Esto solo se puede hacer cuando ninguna de las aplicaciones del cliente apunta a puntos de conexión de Microsoft Cloud Deutschland cuando Azure AD se aprovecha como proveedor de identidades (IdP). | Organizaciones de autenticación federada | Ninguno. |
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
| Actualice los servicios DNS locales para los Office 365 de servicios locales. | Las entradas DNS administradas por el cliente que apuntan a Microsoft Cloud Deutschland deben actualizarse para que apunten a los puntos de conexión Office 365 servicios globales. | Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

## <a name="third-party-services"></a>Servicios de terceros
**Se aplica a:** Clientes que usan servicios de terceros para Office 365 de servicios

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Actualice los partners y los servicios de terceros para los Office 365 de servicios de terceros. | <ul><li>Los servicios y asociados de terceros que apuntan a Office 365 Alemania deben actualizarse para que apunten a los puntos de conexión Office 365 de servicios. Ejemplo: vuelva a registrar, en alineación con sus proveedores y asociados, la versión de la aplicación de galería de aplicaciones, si está disponible. </li><li>Apunte todas las aplicaciones personalizadas que aprovechan Graph API de `graph.microsoft.de` a `graph.microsoft.com` . Otras API con puntos de conexión modificados también deben actualizarse, si se aprovechan. </li><li>Cambie todas las aplicaciones empresariales que no son de primera persona para redirigir a los puntos de conexión mundiales. </li></ul>| Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**Se aplica a**: Clientes que usan SharePoint flujos de trabajo de 2013

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Vuelva a publicar SharePoint flujos de trabajo de 2013. | En el trabajo previo a la migración, se redujo el número de SharePoint flujos de trabajo de 2013. Ahora, una vez completada la migración, el cliente puede volver a publicar los flujos de trabajo. | Se trata de una acción necesaria. Si no lo hace, puede provocar confusión del usuario y llamadas al servicio de ayuda. |
| Compartir elementos mediante Outlook | Compartir elementos en SharePoint Online y OneDrive para la Empresa a través de Outlook ya no funciona después del recorte del espacio empresarial. |<ul><li>En SharePoint Online y OneDrive para la Empresa, puede compartir elementos a través de Outlook. Después de presionar el Outlook, se crea un vínculo que se puede compartir y se inserta en un nuevo mensaje en el Outlook Web App.</li><li>Después de la extensión del espacio empresarial, este método de uso compartido no funcionará. Reconocemos que se trata de un problema conocido. Sin embargo, dado Outlook esta característica está en la ruta de desuso, la solución del problema no está planeada hasta que se desaproteba. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**Se aplica a**: Clientes que usan una configuración Exchange híbrida

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Vuelva a ejecutar el Asistente para configuración híbrida (HCW) en Office 365 servicios. | La configuración de HCW existente está pensada para admitir Microsoft Cloud Deutschland. Una vez completada la migración de Exchange, desasociamos la configuración local de Microsoft Cloud Deutschland. |<ul><li>Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en clientes de software. Antes de Exchange migración de buzones de correo (con 5 o más días de aviso), notifique a los clientes que deben detener y eliminar cualquier movimiento de incorporación o salida de sus buzones.  Si no lo hacen, verán errores en sus solicitudes de movimiento. </li><li>Una Exchange migración de buzones de correo completa, notifique a los clientes que pueden reanudar los movimientos de incorporación y de salida. <br> Es posible que la ejecución de **Test-MigrationServerAvailabiilty**, un cmdlet de PowerShell, durante la migración de Exchange de Microsoft Cloud Deutschland a Office 365 servicios no funcionen. Sin embargo, funcionará correctamente una vez completada la migración. </li><li>Si los clientes tienen problemas con las credenciales o la autorización después de migrar los buzones, los usuarios pueden volver a escribir sus credenciales de administrador local en el extremo de migración ejecutando o estableciendo lo mismo mediante el Panel de control de Exchange `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` (ECP). </li></ul>|
