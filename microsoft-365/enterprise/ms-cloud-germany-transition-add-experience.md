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
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930420"
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
| Quitar confianzas de usuario de confianza de Microsoft Cloud Deutschland AD FS. | Una vez completado el recorte a Azure AD, la organización usa completamente los servicios Office 365 y ya no está conectada a Microsoft Cloud Deutschland. En este punto, el cliente debe quitar la confianza de usuario de confianza a los puntos de conexión de Microsoft Cloud Deutschland. Esto solo se puede hacer cuando ninguna de las aplicaciones del cliente apunta a puntos de conexión de Microsoft Cloud Deutschland cuando Azure AD se aprovecha como proveedor de identidades (IdP). | Organizaciones de autenticación federada | 
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

## <a name="custom-dns-updates"></a>Actualizaciones dns personalizadas
**Se aplica a:**  Todos los clientes que administran sus propias zonas DNS

| Pasos | Descripción | Impacto |
|:------|:-------|:-------|
| Actualice los servicios DNS locales para los Office 365 de servicios locales. | Las entradas DNS administradas por el cliente que apuntan a Microsoft Cloud Deutschland deben actualizarse para que apunten a los puntos de conexión Office 365 servicios globales. Consulte Dominios [en el centro de administración Microsoft 365 y](https://admin.microsoft.com/Adminportal/Home#/Domains) aplique los cambios en la configuración de DNS. | Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||

## <a name="third-party-services"></a>Servicios de terceros
**Se aplica a:** Clientes que usan servicios de terceros para Office 365 de servicios

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Actualice los partners y los servicios de terceros para los Office 365 de servicios de terceros. | <ul><li>Los servicios y asociados de terceros que apuntan a Office 365 Alemania deben actualizarse para que apunten a los puntos de conexión Office 365 de servicios. Ejemplo: vuelva a registrar, en alineación con sus proveedores y asociados, la versión de la aplicación de galería de aplicaciones, si está disponible. </li><li>Apunte todas las aplicaciones personalizadas que aprovechan Graph API de `graph.microsoft.de` a `graph.microsoft.com` . Otras API con puntos de conexión modificados también deben actualizarse, si se aprovechan. </li><li>Cambie todas las aplicaciones empresariales que no son de primera persona para redirigir a los puntos de conexión mundiales. </li></ul>| Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en clientes de software. |
||||