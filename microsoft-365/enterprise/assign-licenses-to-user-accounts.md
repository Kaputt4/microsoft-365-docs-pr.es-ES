---
title: Asignar Microsoft 365 a cuentas de usuario
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Describe cómo asignar licencias Microsoft 365 a cuentas de usuario, ya sea individualmente o en función de la pertenencia a grupos.
ms.openlocfilehash: e2550f7532c332de3a6d2939a2249788aa04bf1122d00359f860bf8cae349b6f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53855220"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Asignar Microsoft 365 a cuentas de usuario

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para el modelo de identidad de solo nube, puede asignar licencias de Microsoft 365 a las cuentas de usuario a medida que se crean, en función de cómo las cree.

Para el modelo de identidad híbrida, cuando las cuentas de usuario de Servicios de dominio de Active Directory (AD DS) se sincronizan por primera vez, no se les asigna automáticamente una ubicación o una Microsoft 365 licencia. **Debe configurar cada cuenta de usuario con una ubicación de usuario antes o junto con la asignación de una licencia.**

En cualquier caso, debe asignar una licencia a cuentas de usuario para que los usuarios puedan acceder a Microsoft 365 servicios, como correo electrónico y Microsoft Teams.

Puede asignar licencias a cuentas de usuario de forma individual o automática a través de la pertenencia a grupos.

Para asignar Microsoft 365 a cuentas de usuario individuales, puede usar:

- [Centro de administración de Microsoft 365](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Centro de administración de Azure AD

## <a name="group-based-licensing"></a>Licencias basadas en grupos

Puede configurar grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones a todos los miembros del grupo. Esto se conoce como *licencias basadas en grupos*. Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.

Asegúrese de que tiene suficientes licencias para todos los miembros del grupo. Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.

>[!Note]
>No configure las licencias basadas en grupos para los grupos que contengan cuentas entre empresas (B2B) de Azure.
>

Para obtener más información, consulte [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Pasos siguientes

Con el conjunto adecuado de cuentas de usuario a las que se han asignado licencias, ya está listo para:

- [Implementar la seguridad](../security/office-365-security/security-roadmap.md)
- [Implementar software cliente, como Aplicaciones Microsoft 365](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Configurar la administración de dispositivos](device-management-roadmap-microsoft-365.md)
- [Configurar servicios y aplicaciones](configure-services-and-applications.md)