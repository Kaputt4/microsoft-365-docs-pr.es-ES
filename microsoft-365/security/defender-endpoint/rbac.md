---
title: Usar el control de acceso basado en roles para conceder acceso personalizado a Microsoft 365 Defender portal
description: Cree roles y grupos dentro de las operaciones de seguridad para conceder acceso al portal.
keywords: rbac, role, based, access, control, groups, control, tier, aad
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8c1ff743aa6c9c215c3894185a4096c9a35a16e0
ms.sourcegitcommit: 6b24f65c987e5ca06e6d5f4fc10804cdbe68b034
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2021
ms.locfileid: "61320832"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Administrar el acceso al portal mediante el control de acceso basado en roles

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Azure Active Directory
- Office 365

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

Con el control de acceso basado en roles (RBAC), puede crear roles y grupos dentro del equipo de operaciones de seguridad para conceder el acceso adecuado al portal. En función de los roles y grupos que cree, tiene un control preciso sobre lo que los usuarios con acceso al portal pueden ver y hacer. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bJ2a]

Los grandes equipos de operaciones de seguridad distribuidas geográficamente suelen adoptar un modelo basado en niveles para asignar y autorizar el acceso a portales de seguridad. Los niveles típicos incluyen los tres niveles siguientes:

Nivel|Descripción|
:---|:---|
Nivel 1|**Equipo de operaciones de seguridad local/equipo de TI** <br> Este equipo normalmente realiza una triage e investiga las alertas contenidas en su geolocalización y escala al nivel 2 en los casos en los que se requiere una corrección activa.|
Nivel 2|**Equipo de operaciones de seguridad regional** <br> Este equipo puede ver todos los dispositivos de su región y realizar acciones de corrección.|
Nivel 3|**Equipo de operaciones de seguridad global** <br> Este equipo está formado por expertos en seguridad y están autorizados a ver y realizar todas las acciones desde el portal.|

> [!NOTE]
> Para los activos de nivel 0, consulte [Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-configure) para que los administradores de seguridad proporcionen un control más detallado de Microsoft Defender para endpoint y Microsoft 365 Defender.  

Defender for Endpoint RBAC está diseñado para admitir el modelo de opciones basado en roles o niveles y le proporciona un control detallado sobre qué roles pueden ver, los dispositivos a los que pueden acceder y las acciones que pueden realizar. El marco RBAC se centra en los siguientes controles:

- **Controlar quién puede realizar una acción específica**
  - Crea roles personalizados y controla a qué capacidades de Defender for Endpoint pueden acceder con granularidad.
- **Controlar quién puede ver información sobre grupos o grupos de dispositivos específicos**
  - [Cree grupos de](machine-groups.md) dispositivos por criterios específicos, como nombres, etiquetas, dominios y otros, y, a continuación, conceda acceso a los roles mediante un grupo de usuarios Azure Active Directory (Azure AD).

Para implementar el acceso basado en roles, deberá definir roles de administrador, asignar los permisos correspondientes y asignar Azure AD grupos de usuarios asignados a los roles.

### <a name="before-you-begin"></a>Antes de empezar

Antes de usar RBAC, es importante que comprenda los roles que pueden conceder permisos y las consecuencias de activar RBAC.

> [!WARNING]
> Antes de habilitar la característica, es importante que tenga un rol de administrador global o de administrador de seguridad en Azure AD y que tenga los grupos de Azure AD listos para reducir el riesgo de que se bloquee el portal. 

Cuando inicie sesión por primera vez en el portal de Microsoft 365 Defender, se le concede acceso completo o acceso de solo lectura. Los derechos de acceso completos se conceden a los usuarios con roles de administrador de seguridad o administrador global en Azure AD. El acceso de solo lectura se concede a los usuarios con un rol lector de seguridad en Azure AD. 

Alguien con un rol de administrador global de Defender for Endpoint tiene acceso sin restricciones a todos los dispositivos, independientemente de su asociación de grupo de dispositivos y las Azure AD grupos de usuarios.

> [!WARNING]
> Inicialmente, solo aquellos con derechos de administrador global o administrador de seguridad de Azure AD podrán crear y asignar roles en el portal de Microsoft 365 Defender, por lo tanto, es importante tener los grupos adecuados listos en Azure AD.
>
> **Al activar el control de acceso basado en roles, los usuarios con permisos de solo lectura (por ejemplo, los usuarios asignados Azure AD un rol de lector de seguridad) perderán el acceso hasta que se les asigne un rol.** 
>
>A los usuarios con permisos de administrador se les asigna automáticamente el rol de administrador global de Defender for Endpoint integrado predeterminado con permisos completos. Después de participar en el uso de RBAC, puede asignar usuarios adicionales que no estén Azure AD administradores globales o de seguridad al rol de administrador global Defender for Endpoint. 
>
> Después de participar en el uso de RBAC, no puede volver a los roles iniciales como cuando inició sesión por primera vez en el portal.

## <a name="related-topic"></a>Tema relacionado

- [Roles RBAC](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [Crear y administrar grupos de dispositivos en Microsoft Defender para endpoint](machine-groups.md)
