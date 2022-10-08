---
title: Identidad solo en la nube de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- scotvorg
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Describe cómo crear usuarios y grupos cuando la suscripción de Microsoft 365 usa una identidad de solo nube.
ms.openlocfilehash: 17298d6f6c07ddfa571610d6038326bcf9ec91cf
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68198501"
---
# <a name="microsoft-365-cloud-only-identity"></a>Identidad solo en la nube de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Si ha elegido el modelo de identidad solo en la nube, ya tiene un inquilino de Azure Active Directory (Azure AD) para que la suscripción de Microsoft 365 almacene todos los usuarios, grupos y contactos. Después de configurar la protección para las cuentas de administrador en el [paso 2](protect-your-global-administrator-accounts.md) y las cuentas de usuario en el [paso 3](microsoft-365-secure-sign-in.md) de esta solución, ya está listo para empezar a crear las nuevas cuentas y grupos que su organización necesita.

Estos son los componentes básicos de la identidad solo en la nube.
 
![Componentes básicos de la identidad solo en la nube.](../media/about-microsoft-365-identity/cloud-only-identity.png)

Los usuarios y sus cuentas de usuario de las organizaciones se pueden clasificar de varias maneras. Por ejemplo, algunos son empleados y tienen un estado permanente. Algunos son proveedores, contratistas o asociados que tienen un estado temporal. Algunos son usuarios externos que no tienen cuentas de usuario, pero que todavía deben tener acceso a servicios y recursos específicos para admitir la interacción y la colaboración. Por ejemplo:

- Cuentas de espacio empresarial que representan a usuarios de su organización a los que asigna una licencia para servicios en la nube

- Cuentas entre empresas (B2B) que representan a usuarios externos a la organización a los que invita a participar en colaboración

Haga un balance de los tipos de usuarios de su organización. ¿Cuáles son las agrupaciones? Por ejemplo, puede agrupar usuarios por función o propósito de alto nivel para su organización.

Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.

Puede usar grupos en Azure AD para varios fines que simplifiquen la administración del entorno en la nube. Por ejemplo, con los grupos de Azure AD, puede hacer lo siguiente:

- Use licencias basadas en grupos para asignar licencias de Microsoft 365 a las cuentas de usuario automáticamente en cuanto se agreguen como miembros.
- Agregue cuentas de usuario a grupos específicos dinámicamente en función de los atributos de la cuenta de usuario, como el nombre del departamento.
- Aprovisione automáticamente usuarios para aplicaciones de software como servicio (SaaS) y para proteger el acceso a esas aplicaciones con autenticación multifactor (MFA) y otras directivas de acceso condicional.
- Aprovisione permisos y niveles de acceso para equipos y sitios de equipo de SharePoint Online.

## <a name="next-steps-for-cloud-only-identity"></a>Pasos siguientes para la identidad solo en la nube

- [Administrar cuentas de usuario](manage-microsoft-365-accounts.md)
- [Asignar licencias a cuentas de usuario](assign-licenses-to-user-accounts.md)
- [Administración de grupos y pertenencia a grupos](manage-microsoft-365-groups.md)
- [Administración de contraseñas de cuenta de usuario](manage-microsoft-365-passwords.md)
