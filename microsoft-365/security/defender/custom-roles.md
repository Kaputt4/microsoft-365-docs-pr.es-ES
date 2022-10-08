---
title: Roles personalizados para el control de acceso basado en rol
description: Aprenda a administrar roles personalizados en el portal de Microsoft 365 Defender
keywords: access, permissions, Microsoft 365 Defender, M365, security, Defender for Cloud Apps, Microsoft Defender para punto de conexión, scope, scoping, RBAC, roles-based access, custom roles-based access, roles-based auth, RBAC in MDO, roles, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 446c69b9f62effd1e2248d643afdf58eed3d11d4
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68055554"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Roles personalizados en el control de acceso basado en rol para Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**

- Microsoft 365 Defender
 
Hay dos tipos de roles que se pueden usar para acceder a Microsoft 365 Defender:
- **Roles globales de Azure Active Directory (AD)**
- **Roles personalizados**

El acceso a Microsoft 365 Defender se puede administrar colectivamente mediante [roles globales en Azure Active Directory (AAD)](m365d-permissions.md)

Si necesita mayor flexibilidad y control sobre el acceso a datos de productos específicos, Microsoft 365 Defender acceso también se puede administrar con la creación de roles personalizados a través de cada portal de seguridad respectivo.  

Por ejemplo, un rol personalizado creado a través de Microsoft Defender para punto de conexión permitiría el acceso a los datos de producto pertinentes, incluidos los datos de punto de conexión en el portal de Microsoft 365 Defender. De forma similar, un rol personalizado creado a través de Microsoft Defender para Office 365 permitiría el acceso a los datos de producto pertinentes, incluidos Email & datos de colaboración en el portal de Microsoft 365 Defender.

Los usuarios con roles personalizados existentes pueden acceder a los datos del portal de Microsoft 365 Defender según sus permisos de carga de trabajo existentes sin que se requiera ninguna configuración adicional.

## <a name="create-and-manage-custom-roles"></a>Creación y administración de roles personalizados
Los roles y permisos personalizados se pueden crear y administrar individualmente a través de cada uno de los siguientes portales de seguridad: 

- Microsoft Defender para punto de conexión: [edición de roles en Microsoft Defender para punto de conexión](../defender-endpoint/user-roles.md)
- Microsoft Defender para Office 365: [permisos en el Centro de cumplimiento de seguridad &](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Defender for Cloud Apps: [administrar el acceso de administrador](/cloud-app-security/manage-admins)

Cada rol personalizado creado a través de un portal individual permite el acceso a los datos del portal de productos correspondiente. Por ejemplo, un rol personalizado creado a través de Microsoft Defender para punto de conexión solo permitirá el acceso a los datos de Defender para punto de conexión.

> [!TIP]
> También se puede acceder a los permisos y roles a través del portal de Microsoft 365 Defender seleccionando Permisos & roles en el panel de navegación. El acceso a Microsoft Defender for Cloud Apps se administra a través del portal de Defender for Cloud Apps y controla también el acceso a Microsoft Defender for Identity.  Consulte [Microsoft Defender for Cloud Apps](/cloud-app-security/manage-admins)

> [!NOTE]
> Los roles personalizados creados en Microsoft Defender for Cloud Apps también tienen acceso a Microsoft Defender for Identity datos. Los usuarios con roles de Microsoft Defender for Cloud Apps administrador de grupos de usuarios o administrador de aplicaciones o instancias no pueden acceder a Microsoft Defender for Cloud Apps datos a través del portal de Microsoft 365 Defender.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-defender-portal"></a>Administración de permisos y roles en el portal de Microsoft 365 Defender
Los permisos y roles también se pueden administrar en el portal de Microsoft 365 Defender:

1. Inicie sesión en el portal de Microsoft 365 Defender en security.microsoft.com.
2. En el panel de navegación, seleccione **Permisos y roles**.
3. En el encabezado **Permisos** , seleccione **Roles**.

> [!NOTE]
> Esto solo se aplica a Defender para Office 365 y Defender para punto de conexión. El acceso a otras cargas de trabajo debe realizarse en sus portales pertinentes.


## <a name="required-roles-and-permissions"></a>Permisos y roles necesarios
En la tabla siguiente se describen los roles y permisos necesarios para acceder a cada experiencia unificada de cada carga de trabajo. Los roles definidos en la tabla siguiente hacen referencia a los roles personalizados en portales individuales y no están conectados a roles globales en Azure AD, aunque tenga un nombre similar.

> [!NOTE]
> La administración de incidentes requiere permisos de administración para todos los productos que forman parte del incidente.
 
| **Se requiere uno de los siguientes roles para Microsoft 365 Defender**  | **Se requiere uno de los siguientes roles para Defender para punto de conexión.**  | **Se requiere uno de los siguientes roles para Defender para Office 365** | **Se requiere uno de los siguientes roles para Defender for Cloud Apps.** | 
|---------|---------|---------|---------|
| Visualización de datos de investigación: <ul><li>Página alerta</li> <li>Cola de alertas</li> <li>Incidentes</li>  <li>Cola de incidentes</li> <li>Centro de actividades</li></ul>| Ver operaciones de seguridad de datos | <ul><li>Ver solo administrar alertas </li> <li>Configuración de la organización</li><li>Registros de auditoría</li> <li>Visualización de registros de auditoría de solo visualización</li> <li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo visualización</li></ul>  | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li> <li>Lector global</li></ul> |
| Visualización de datos de búsqueda | Ver operaciones de seguridad de datos | <ul><li>Lector de seguridad</li> <li>Administrador de seguridad</li> <li>Destinatarios de solo visualización</li> | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li> <li>Lector global</li></ul> |
| Administración de alertas e incidentes | Investigación de alertas | <ul><li>Administrar alertas</li> <li>Administrador de seguridad</li> | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li></ul> |
| Corrección del centro de acciones | Acciones de corrección activas: operaciones de seguridad | Búsqueda y purga | |
| Configuración de detecciones personalizadas | Administrar la configuración de seguridad |<ul><li>Administrar alertas</li> <li>Administrador de seguridad</li></ul> | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li> <li>Lector global</li></ul> |
| Análisis de amenazas | Datos de alertas e incidentes: <ul><li>Ver operaciones de seguridad de datos</li></ul>Mitigaciones de Administración de vulnerabilidades de Defender:<ul><li>Visualización de datos: administración de amenazas y vulnerabilidades</li></ul> | Datos de alertas e incidentes:<ul> <li>Ver solo administrar alertas</li> <li>Administrar alertas</li> <li>Configuración de la organización</li><li>Registros de auditoría</li> <li>Visualización de registros de auditoría de solo visualización</li><li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo visualización</li> </ul> Intentos de correo electrónico impedidos: <ul><li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo visualización</li> | No disponible para los usuarios de Defender for Cloud Apps o MDI |

Por ejemplo, para ver los datos de búsqueda de Microsoft Defender para punto de conexión, se requieren permisos para ver las operaciones de seguridad de datos.  

De forma similar, para ver los datos de búsqueda de Microsoft Defender para Office 365, los usuarios requerirían uno de los siguientes roles:  

- Visualización de las operaciones de seguridad de datos
- Lector de seguridad
- Administrador de seguridad
- Destinatarios de solo visualización

## <a name="related-topics"></a>Temas relacionados
- [Roles de RBAC](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [Administrar el acceso a Microsoft 365 Defender](m365d-permissions.md)
- [Administración del acceso de administrador para Defender for Cloud Apps](/cloud-app-security/manage-admins)
