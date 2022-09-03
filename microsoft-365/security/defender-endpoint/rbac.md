---
title: Uso del control de acceso basado en rol para conceder acceso específico a Microsoft 365 Defender portal
description: Cree roles y grupos dentro de las operaciones de seguridad para conceder acceso al portal.
keywords: rbac, role, based, access, control, groups, control, tier, aad
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 97388c93008112c6131365d9887e1995ad2efe47
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585210"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Administración del acceso al portal mediante el control de acceso basado en rol

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Azure Active Directory
- Office 365

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

Con el control de acceso basado en rol (RBAC), puede crear roles y grupos dentro del equipo de operaciones de seguridad para conceder el acceso adecuado al portal. En función de los roles y grupos que cree, tiene un control específico sobre lo que los usuarios con acceso al portal pueden ver y hacer. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bJ2a]

Los equipos de operaciones de seguridad distribuidas geográficamente de gran tamaño suelen adoptar un modelo basado en niveles para asignar y autorizar el acceso a los portales de seguridad. Los niveles típicos incluyen los tres niveles siguientes:

Nivel|Descripción|
:---|:---|
Nivel 1|**Equipo de operaciones de seguridad local/equipo de TI** <br> Este equipo suele evaluar e investigar las alertas contenidas en su geolocalización y se escala al nivel 2 en los casos en los que se requiere una corrección activa.|
Nivel 2|**Equipo de operaciones de seguridad regional** <br> Este equipo puede ver todos los dispositivos de su región y realizar acciones de corrección.|
Nivel 3|**Equipo de operaciones de seguridad global** <br> Este equipo está formado por expertos en seguridad y está autorizado para ver y realizar todas las acciones desde el portal.|

> [!NOTE]
> En el caso de los recursos de nivel 0, consulte [Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-configure) para administradores de seguridad para proporcionar un control más pormenorizado de Microsoft Defender para punto de conexión y Microsoft 365 Defender.  

RBAC de Defender para punto de conexión está diseñado para admitir el modelo de nivel o basado en rol que prefiera y proporciona un control pormenorizado sobre qué roles pueden ver, los dispositivos a los que pueden acceder y las acciones que pueden realizar. El marco de RBAC se centra en los siguientes controles:

- **Controlar quién puede realizar una acción específica**
  - Cree roles personalizados y controle a qué funcionalidades de Defender para punto de conexión pueden acceder con granularidad.
- **Controlar quién puede ver información sobre grupos o grupos de dispositivos específicos**
  - [Cree grupos de dispositivos](machine-groups.md) por criterios específicos, como nombres, etiquetas, dominios y otros, y, a continuación, conceda acceso de rol a ellos mediante un grupo de usuarios específico de Azure Active Directory (Azure AD).

Para implementar el acceso basado en rol, deberá definir roles de administrador, asignar los permisos correspondientes y asignar grupos de usuarios de Azure AD asignados a los roles.

### <a name="before-you-begin"></a>Antes de empezar

Antes de usar RBAC, es importante que comprenda los roles que pueden conceder permisos y las consecuencias de activar RBAC.

> [!WARNING]
> Antes de habilitar la característica, es importante que tenga un rol de administrador global o administrador de seguridad en Azure AD y que tenga los grupos de Azure AD listos para reducir el riesgo de que se bloquee el portal. 

La primera vez que inicie sesión en el portal de Microsoft 365 Defender, se le concederá acceso completo o acceso de solo lectura. Los derechos de acceso completo se conceden a los usuarios con roles de administrador de seguridad o administrador global en Azure AD. El acceso de solo lectura se concede a los usuarios con un rol lector de seguridad en Azure AD. 

Alguien con un rol de Administrador global de Defender para punto de conexión tiene acceso sin restricciones a todos los dispositivos, independientemente de su asociación de grupos de dispositivos y de las asignaciones de grupos de usuarios de Azure AD.

> [!WARNING]
> Inicialmente, solo los usuarios con derechos de administrador global o administrador de seguridad de Azure AD podrán crear y asignar roles en el portal de Microsoft 365 Defender, por lo que es importante tener los grupos adecuados listos en Azure AD.
>
> **Al activar el control de acceso basado en rol, los usuarios con permisos de solo lectura (por ejemplo, los usuarios asignados al rol lector de seguridad de Azure AD) perderán el acceso hasta que se asignen a un rol.** 
>
>A los usuarios con permisos de administrador se les asigna automáticamente el rol de administrador global integrado predeterminado de Defender para punto de conexión con permisos completos. Después de participar en el uso de RBAC, puede asignar usuarios adicionales que no sean administradores globales de Azure AD o administradores de seguridad al rol de administrador global de Defender para punto de conexión. 
>
> Después de participar en el uso de RBAC, no puede volver a los roles iniciales como cuando inició sesión por primera vez en el portal.

## <a name="related-topic"></a>Tema relacionado

- [Roles de RBAC](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [Creación y administración de grupos de dispositivos en Microsoft Defender para punto de conexión](machine-groups.md)
