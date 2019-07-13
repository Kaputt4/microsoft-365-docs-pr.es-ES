---
title: Detalles de inquilinos de Azure Active Directory
description: En este tema se describen los cambios realizados en la cuenta de AAD al inscribirse en el escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643951"
---
# <a name="azure-active-directory-tenant-details"></a>Detalles de inquilinos de Azure Active Directory
{Gory detalles sobre cuentas, llamadas API, perms, etc., etc.}


## <a name="data-transmitted-to-and-from-your-aad-account"></a>Datos que se transmiten a y desde la cuenta de AAD


Datos enviados a su cuenta desde Microsoft:

- Nombres de grupo
- Configuración de la Directiva de seguridad
- Pedidos de dispositivo
- Cuentas de usuario (msadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)
- Asignación de licencias de E5 a las cuentas de usuario
- Directivas de Windows Update para anillos de actualización

Datos enviados a Microsoft desde su cuenta:

- Datos de actualización de dispositivos, uso y confiabilidad
- Datos de confiabilidad y de implementación de aplicaciones
- Actualización y datos de implementación de la Directiva de seguridad
- Usuarios asignados a dispositivos  

Los datos transmitidos desde su cuenta se almacenan en Azure SQL Databases en el inquilino de Microsoft hospedado en Estados Unidos. Los datos se almacenan y controlan de acuerdo con las directivas descritas en {Microsoft Azure Security}. 

## <a name="api-permissions-and-calls"></a>Permisos y llamadas de la API

**Durante la inscripción:**

Permisos de API:
- DeviceManagementServiceConfig.ReadWrite.All
- Directory.AccessAsUser.All
- User.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- DeviceManagementManagedDevices.ReadWrite.All
- Group.ReadWrite.All

Llamadas a la API:
- PUBLICAR/organization/{organizationId}/setMobileDeviceManagementAuthority
- GET/POST/directoryRoles/{id}/members
- GET/POST/users
- GET/POST/Groups
- REVISIÓN/Groups/{ID}
- GET/POST/deviceManagement/deviceConfigurations
- OBTENER/deviceManagement/detectedApps

**Tras la inscripción, durante la administración ordinaria:**

Permisos de API:
- DeviceManagementManagedDevices.ReadWrite.All
- DeviceManagementApps.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- Reports.Read.All
- User.ReadWrite.All
- Group.ReadWrite.All
- Directory.AccessAsUser.All

Llamadas a la API:
- GET/POST/directoryRoles/{id}/members
- GET/PATCH/POST/users
- GET/POST/Groups
- REVISIÓN/Groups/{ID}
- GET/POST/deviceManagement/deviceConfigurations
- GET/POST/deviceAppManagement/mobileApps
- OBTENER/deviceManagement/detectedApps
- OBTENER/Devices
- POST/users/{ID | userPrincipalName}/assignLicense
- OBTENER/subscribedSkus

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Cuentas usadas por el escritorio administrado por Microsoft





| Cuenta | Descripción  | Acceso condicional  | Autenticación multifactor  | Por qué es correcto |
|---------|---------|---------|---------|--------------|
| msadmin @ * onmmicrosoft. com | Cuenta de servicio limitada con privilegios de administrador, usada como Microsoft Intune y usuario administrador {¿qué es esto?} para definir y configurar el inquilino para los dispositivos de escritorio modernos de Microsoft.No tiene permisos de inicio de sesión interactivo; realiza operaciones solo a través del servicio.  | Excluido porque no se origina en la red        | Excluido porque no hay inicio de sesión interactivo        | Contraseña almacenada en el almacén de claves de Azure |
| MSTest @ * onmmicrosoft. com     |         |         |         |
| mssupport @ * onmmicrosoft. com     |         |         |         |
| msadminint @ * onmmicrosoft. com     |         |         |         |
