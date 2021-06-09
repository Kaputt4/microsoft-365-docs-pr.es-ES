---
title: Microsoft 365 identidad de solo nube
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
description: Describe cómo crear usuarios y grupos cuando la suscripción Microsoft 365 está usando la identidad de solo nube.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327932"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365 identidad de solo nube

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Con la identidad de solo nube, todos los usuarios, grupos y contactos se almacenan en el inquilino de Azure Active Directory (Azure AD) de su Microsoft 365 suscripción. Estos son los componentes básicos de la identidad de solo nube.
 
![Los componentes básicos de la identidad de solo nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

Los usuarios y sus cuentas de usuario en las organizaciones se pueden clasificar de varias maneras. Por ejemplo, algunos son empleados y tienen un estado permanente. Algunos son proveedores, contratistas o socios que tienen un estado temporal. Algunos son usuarios externos que no tienen cuentas de usuario, pero que aún deben tener acceso a servicios y recursos específicos para admitir la interacción y la colaboración. Por ejemplo:

- Cuentas de espacio empresarial que representan a usuarios de su organización a los que asigna una licencia para servicios en la nube

- Cuentas entre empresas (B2B) que representan a usuarios externos a la organización a los que invita a participar en colaboración

Hacer un balance de los tipos de usuarios de la organización. ¿Cuáles son las agrupaciones? Por ejemplo, puede agrupar usuarios por función o propósito de alto nivel para su organización.

Además, algunos servicios en la nube se pueden compartir con usuarios externos a la organización sin cuentas de usuario. También necesitará identificar estos grupos de usuarios.

Puede usar grupos en Azure AD para varios fines que simplifican la administración del entorno en la nube. Por ejemplo, con los grupos de Azure AD, puede:

- Use licencias basadas en grupos para asignar licencias de Microsoft 365 a sus cuentas de usuario automáticamente en cuanto se agregan como miembros.
- Agregue cuentas de usuario a grupos específicos dinámicamente en función de los atributos de cuenta de usuario, como el nombre del departamento.
- Aprovisionar automáticamente a los usuarios para aplicaciones de Software como Servicio (SaaS) y proteger el acceso a esas aplicaciones con autenticación multifactor (MFA) y otras directivas de acceso condicional.
- Aprovisione permisos y niveles de acceso para SharePoint de grupo en línea.

## <a name="next-steps-for-cloud-only-identity"></a>Pasos siguientes para la identidad de solo nube

- [Administrar cuentas de usuario](manage-microsoft-365-accounts.md)
- [Asignar licencias a cuentas de usuario](assign-licenses-to-user-accounts.md)
- [Administrar grupos y pertenencia a grupos](manage-microsoft-365-groups.md)
- [Administrar contraseñas de cuentas de usuario](manage-microsoft-365-passwords.md)
