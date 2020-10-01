---
title: Identidad solo de nube de Microsoft 365
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
description: Describe cómo crear usuarios y grupos cuando la suscripción de Microsoft 365 usa identidad solo de nube.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327932"
---
# <a name="microsoft-365-cloud-only-identity"></a>Identidad solo de nube de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Con la identidad solo de nube, todos los usuarios, grupos y contactos se almacenan en el inquilino de Azure Active Directory (Azure AD) de la suscripción a Microsoft 365. Estos son los componentes básicos de la identidad solo de la nube.
 
![Los componentes básicos de la identidad solo de nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

Los usuarios y sus cuentas de usuario en las organizaciones se pueden clasificar de varias formas. Por ejemplo, algunos son empleados y tienen un estado permanente. Algunos son proveedores, contratistas o asociados que tienen un estado temporal. Algunos son usuarios externos que no tienen cuentas de usuario, pero tienen que seguir concedido el acceso a servicios y recursos específicos para admitir la interacción y la colaboración. Por ejemplo:

- Cuentas de espacio empresarial que representan a usuarios de su organización a los que asigna una licencia para servicios en la nube

- Cuentas entre empresas (B2B) que representan a usuarios externos a la organización a los que invita a participar en colaboración

Tomar en existencias los tipos de usuarios de la organización. ¿Cuáles son las agrupaciones? Por ejemplo, puede agrupar a los usuarios por una función o un propósito de alto nivel para su organización.

Además, algunos servicios en la nube se pueden compartir con usuarios externos a la organización sin cuentas de usuario. También necesitará identificar estos grupos de usuarios.

Puede usar grupos en Azure AD para varios fines que simplifican la administración del entorno de la nube. Por ejemplo, con los grupos de Azure AD, puede:

- Use licencias basadas en grupos para asignar licencias para Microsoft 365 a sus cuentas de usuario automáticamente en cuanto se agreguen como miembros.
- Agregue cuentas de usuario a grupos específicos de forma dinámica según los atributos de la cuenta de usuario, como el nombre del Departamento.
- Aprovisionar automáticamente a los usuarios para aplicaciones de software como servicio (SaaS) y para proteger el acceso a esas aplicaciones con multi-factor Authentication (MFA) y otras directivas de acceso condicional.
- Aprovisionar permisos y niveles de acceso para los sitios de grupo de SharePoint Online.

## <a name="next-steps-for-cloud-only-identity"></a>Pasos siguientes para la identidad solo de la nube

- [Administrar cuentas de usuario](manage-microsoft-365-accounts.md)
- [Asignar licencias a cuentas de usuario](assign-licenses-to-user-accounts.md)
- [Administrar grupos y pertenencia a grupos](manage-microsoft-365-groups.md)
- [Administración de contraseñas de cuentas de usuario](manage-microsoft-365-passwords.md)
