---
title: Roles personalizados para el control de acceso basado en roles
description: Obtenga información sobre cómo administrar roles personalizados en el Centro de seguridad de Microsoft 365
keywords: access, permissions, MTP, Microsoft Threat Protection, M365, security, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, scope, scoping, RBAC, roles-based access, custom roles-based access, roles-based auth, RBAC in MDO, roles, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 35ac4e26406fe6fde1385008b527dc4865e0392b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928933"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Roles personalizados en el control de acceso basado en roles para Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**

- Microsoft 365 Defender
 
Hay dos tipos de roles que se pueden usar para acceder a Microsoft 365 Defender:
- **Roles globales de Azure Active Directory (AD)**
- **Roles personalizados**

El acceso a Microsoft 365 Defender se puede administrar colectivamente mediante [roles globales en Azure Active Directory (AAD)](mtp-permissions.md)

Si necesita mayor flexibilidad y control sobre el acceso a datos de productos específicos, el acceso de Microsoft 365 Defender también se puede administrar con la creación de roles personalizados a través de cada portal de seguridad respectivo.  

Por ejemplo, un rol personalizado creado a través de Microsoft Defender para Endpoint permitiría el acceso a los datos del producto relevantes, incluidos los datos de extremo en el Centro de seguridad de Microsoft 365. Del mismo modo, un rol personalizado creado a través de Microsoft Defender para Office 365 permitiría el acceso a los datos del producto relevantes, incluidos los datos de colaboración de correo electrónico & dentro del centro de seguridad de Microsoft 365.

Los usuarios con roles personalizados existentes pueden tener acceso a datos en el Centro de seguridad de Microsoft 365 según sus permisos de carga de trabajo existentes sin necesidad de configuración adicional.

## <a name="create-and-manage-custom-roles"></a>Crear y administrar roles personalizados
Los roles y permisos personalizados se pueden crear y administrar individualmente a través de cada uno de los siguientes portales de seguridad: 

- Microsoft Defender para endpoint: [editar roles en Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- Microsoft Defender para Office 365: [permisos en el Centro de seguridad & cumplimiento](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security: [administrar el acceso de administrador](/cloud-app-security/manage-admins)

Cada rol personalizado creado a través de un portal individual permite el acceso a los datos del portal de productos relevante. Por ejemplo, un rol personalizado creado a través de Microsoft Defender para endpoint solo permitirá el acceso a Defender para los datos de punto de conexión.

> [!TIP]
> También se puede obtener acceso a los permisos y roles a través del Centro de seguridad de Microsoft 365 seleccionando Permisos & roles en el panel de navegación. El acceso a Microsoft Cloud App Security (MCAS) se administra a través del portal de MCAS y controla también el acceso a Microsoft Defender for Identity.  Consulta [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> Los roles personalizados creados en Microsoft Cloud App Security también tienen acceso a los datos de Identidad de Microsoft Defender. Los usuarios con roles de administrador de grupo de usuarios o administración de aplicaciones o instancias de Microsoft Cloud App Security no pueden acceder a los datos de Microsoft Cloud App Security a través del Centro de seguridad de Microsoft 365.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Administrar permisos y roles en el Centro de seguridad de Microsoft 365
Los permisos y roles también se pueden administrar en el Centro de seguridad de Microsoft 365:

1. Inicie sesión en el Centro de seguridad de Microsoft 365 en security.microsoft.com.
2. En el panel de navegación, seleccione **Permisos & roles**.
3. En el **encabezado Permissions,** seleccione **Roles**.

> [!NOTE]
> Esto solo se aplica a Defender para Office 365 y Defender para endpoint. El acceso a otras cargas de trabajo debe realizarse en sus portales relevantes.


## <a name="required-roles-and-permissions"></a>Permisos y roles necesarios
En la tabla siguiente se describen los roles y permisos necesarios para tener acceso a cada experiencia unificada en cada carga de trabajo. Los roles definidos en la tabla siguiente hacen referencia a roles personalizados en portales individuales y no están conectados a roles globales en Azure AD, incluso si tienen un nombre similar.

> [!NOTE]
> La administración de incidentes requiere permisos de administración para todos los productos que forman parte del incidente.
 
| **Uno de los siguientes roles son necesarios para Microsoft 365 Defender**  | **Uno de los siguientes roles son necesarios para Defender for Endpoint**  | **Uno de los siguientes roles son necesarios para Defender para Office 365** | **Uno de los siguientes roles son necesarios para Cloud App Security** | 
|---------|---------|---------|---------|
| Visualización de datos de investigación: <ul><li>Página alerta</li> <li>Cola de alertas</li> <li>Incidentes</li>  <li>Cola de incidentes</li> <li>Centro de acciones</li></ul>| Ver operaciones de seguridad de datos | <ul><li>Administrar alertas de solo vista </li> <li>Configuración de la organización</li><li>Registros de auditoría</li> <li>Registros de auditoría de solo vista</li> <li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo vista</li></ul>  | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li> <li>Lector global</li></ul> |
| Visualización de datos de búsqueda | Ver operaciones de seguridad de datos | <ul><li>Lector de seguridad</li> <li>Administrador de seguridad</li> <li>Destinatarios de solo vista</li> | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li> <li>Lector global</li></ul> |
| Administración de alertas e incidentes | Investigación de alertas | <ul><li>Administrar alertas</li> <li>Administrador de seguridad</li> | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li></ul> |
| Corrección del centro de acciones | Acciones de corrección activas: operaciones de seguridad | Buscar y purgar | |
| Configuración de detecciones personalizadas | Administrar la configuración de seguridad |<ul><li>Administrar alertas</li> <li>Administrador de seguridad</li></ul> | <ul><li>Administrador global</li> <li>Administrador de seguridad</li> <li>Administrador de cumplimiento</li> <li>Operador de seguridad</li> <li>Lector de seguridad</li> <li>Lector global</li></ul> |
| Análisis de amenazas | Datos de alertas e incidentes: <ul><li>Ver operaciones de seguridad de datos</li></ul>Mitigaciones de TVM:<ul><li>Ver datos: administración de amenazas y vulnerabilidades</li></ul> | Datos de alertas e incidentes:<ul> <li>Administrar alertas de solo vista</li> <li>Administrar alertas</li> <li>Configuración de la organización</li><li>Registros de auditoría</li> <li>Registros de auditoría de solo vista</li><li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo vista</li> </ul> Intentos de correo electrónico impedidos: <ul><li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo vista</li> | No disponible para usuarios MCAS o MDI |

Por ejemplo, para ver los datos de búsqueda de Microsoft Defender para endpoint, es necesario ver permisos de operaciones de seguridad de datos.  

Del mismo modo, para ver los datos de búsqueda de Microsoft Defender para Office 365, los usuarios requerirían uno de los siguientes roles:  

- Ver operaciones de seguridad de datos
- Lector de seguridad
- Administrador de seguridad
- Destinatarios de solo vista

## <a name="related-topics"></a>Temas relacionados
- [Administrar el acceso a Microsoft 365 Defender](mtp-permissions.md)
- [Administrar el acceso de administrador para MCAS](/cloud-app-security/manage-admins)