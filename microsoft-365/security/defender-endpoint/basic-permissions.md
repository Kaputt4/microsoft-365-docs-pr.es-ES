---
title: Uso de permisos básicos para acceder a Centro de seguridad de Microsoft Defender
description: Obtenga información sobre cómo usar permisos básicos para acceder al portal de Microsoft Defender para punto de conexión.
keywords: asignar roles de usuario, asignar acceso de lectura y escritura, asignar acceso de solo lectura, usuario, roles de usuario, roles
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.prod: m365-security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 57fec13384a825620633be7d59a312a4ff5926f8
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67797258"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Uso de permisos básicos para acceder al portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- Azure Active Directory
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-basicaccess-abovefoldlink)

Consulte las instrucciones siguientes para usar la administración básica de permisos.

Puede usar cualquiera de las siguientes soluciones:

- Azure PowerShell
- Portal de Azure

Para obtener un control pormenorizado sobre los permisos, [cambie al control de acceso basado en rol](rbac.md).

## <a name="assign-user-access-using-azure-powershell"></a>Asignar acceso de usuario mediante Azure PowerShell

Puede asignar usuarios con uno de los siguientes niveles de permisos:

- Acceso completo (lectura y escritura)
- Acceso de solo lectura

### <a name="before-you-begin"></a>Antes de empezar

- Instale Azure PowerShell. Para obtener más información, consulte [Instalación y configuración de Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).

  > [!NOTE]
  > Debe ejecutar los cmdlets de PowerShell en una línea de comandos con privilegios elevados.

- Conéctese a Azure Active Directory. Para obtener más información, vea [Connect-MsolService](/powershell/module/msonline/connect-msolservice).

  - **Acceso completo**: los usuarios con acceso completo pueden iniciar sesión, ver toda la información del sistema y resolver alertas, enviar archivos para un análisis profundo y descargar el paquete de incorporación. La asignación de derechos de acceso completo requiere agregar los usuarios a los roles integrados de AAD "Administrador de seguridad" o "Administrador global".
  - **Acceso de solo lectura**: los usuarios con acceso de solo lectura pueden iniciar sesión, ver todas las alertas e información relacionada.

    No podrán cambiar los estados de alerta, enviar archivos para un análisis profundo ni realizar ninguna operación de cambio de estado.

    La asignación de derechos de acceso de solo lectura requiere agregar los usuarios al rol integrado "Lector de seguridad" de Azure AD.

Siga estos pasos para asignar roles de seguridad:

- Para obtener acceso de **lectura y escritura** , asigne usuarios al rol de administrador de seguridad mediante el siguiente comando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```

- Para el acceso **de solo lectura** , asigne usuarios al rol de lector de seguridad mediante el siguiente comando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Para obtener más información, consulte [Adición o eliminación de miembros del grupo mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).

## <a name="assign-user-access-using-the-azure-portal"></a>Asignar acceso de usuario mediante el Azure Portal

Para obtener más información, consulte [Asignación de roles de administrador y no administrador a usuarios con Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="related-topic"></a>Tema relacionado

- [Administrar el acceso al portal con RBAC](rbac.md)
