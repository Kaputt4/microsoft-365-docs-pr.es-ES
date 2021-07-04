---
title: Use permisos básicos para obtener acceso a Centro de seguridad de Microsoft Defender
description: Obtenga información sobre cómo usar permisos básicos para obtener acceso al portal de Microsoft Defender para endpoints.
keywords: asignar roles de usuario, asignar acceso de lectura y escritura, asignar acceso de solo lectura, usuario, roles de usuario, roles
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290200"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Uso de permisos básicos para acceder al portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- Azure Active Directory
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Consulte las instrucciones siguientes para usar la administración de permisos básicos.

Puede usar cualquiera de las siguientes soluciones:
- Azure PowerShell
- Portal de Azure

Para el control granular sobre los permisos, [cambie al control de](rbac.md)acceso basado en roles .

## <a name="assign-user-access-using-azure-powershell"></a>Asignar acceso de usuario mediante Azure PowerShell
Puede asignar usuarios con uno de los siguientes niveles de permisos:
- Acceso completo (lectura y escritura)
- Acceso de solo lectura

### <a name="before-you-begin"></a>Antes de empezar

- Instale Azure PowerShell. Para obtener más información, vea [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).<br>

    > [!NOTE]
    > Debe ejecutar los cmdlets de PowerShell en una línea de comandos con privilegios elevados.

- Conectar a su Azure Active Directory. Para obtener más información, [vea Conectar-MsolService](/powershell/module/msonline/connect-msolservice).

**Acceso completo** <br>
Los usuarios con acceso completo pueden iniciar sesión, ver toda la información del sistema y resolver alertas, enviar archivos para un análisis profundo y descargar el paquete de incorporación.
La asignación de derechos de acceso completo requiere agregar los usuarios a los roles integrados "Administrador de seguridad" o "Administrador global" de AAD.

**Acceso de solo lectura** <br>
Los usuarios con acceso de solo lectura pueden iniciar sesión, ver todas las alertas e información relacionada.
No podrán cambiar los estados de alerta, enviar archivos para un análisis profundo o realizar operaciones de cambio de estado.
La asignación de derechos de acceso de solo lectura requiere agregar los usuarios al rol integrado de Azure AD "Lector de seguridad".

Siga estos pasos para asignar roles de seguridad:

- Para **obtener acceso de lectura y** escritura, asigne usuarios al rol de administrador de seguridad mediante el siguiente comando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- Para **el acceso de solo** lectura, asigne usuarios al rol de lector de seguridad mediante el siguiente comando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Para obtener más información, vea [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).

## <a name="assign-user-access-using-the-azure-portal"></a>Asignar acceso de usuario mediante Azure Portal

Para obtener más información, vea [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="related-topic"></a>Tema relacionado

- [Administrar el acceso al portal con RBAC](rbac.md)
