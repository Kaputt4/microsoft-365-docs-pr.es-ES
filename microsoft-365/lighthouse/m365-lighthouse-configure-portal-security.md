---
title: Configuración de la seguridad del portal de Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: vivkuma
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo configurar la seguridad del portal.
ms.openlocfilehash: dbadd9742e8b477bf4fa97e2556c37b0a3e3fe3b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193221"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>Configuración de la seguridad del portal de Microsoft 365 Lighthouse

Proteger el acceso a los datos del cliente cuando un proveedor de servicios administrados (MSP) tiene permisos de acceso delegados a sus inquilinos es una prioridad de ciberseguridad. Microsoft 365 Lighthouse incluye funcionalidades necesarias y opcionales para ayudarle a configurar la seguridad del portal de Lighthouse. Debe configurar roles específicos con la autenticación multifactor (MFA) habilitada para poder acceder a Lighthouse. Opcionalmente, puede configurar Azure AD Privileged Identity Management (PIM) y el acceso condicional.

## <a name="set-up-multifactor-authentication-mfa"></a>Configuración de la autenticación multifactor (MFA)

Como se mencionó en la entrada de blog [Your Pa$$word doesn't matter](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984):

> "La contraseña no importa, pero MFA sí. Según nuestros estudios, su cuenta tiene más de un 99,9 % menos de probabilidades de verse comprometida si usa MFA".

Cuando los usuarios accedan a Lighthouse por primera vez, se les pedirá que configuren MFA si su cuenta de Microsoft 365 aún no la tiene configurada. Los usuarios no podrán acceder a Lighthouse hasta que se complete el paso de configuración de MFA necesario. Para más información sobre los métodos de autenticación, consulte [Configuración del inicio de sesión de Microsoft 365 para la autenticación multifactor](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

## <a name="set-up-role-based-access-control"></a>Configuración del control de acceso basado en rol

El control de acceso basado en rol (RBAC) concede acceso a recursos o información en función de los roles de usuario. El acceso a los datos y la configuración del inquilino del cliente en Lighthouse está restringido a roles específicos del programa Proveedor de soluciones en la nube (CSP). Para configurar roles de RBAC en Lighthouse, se recomienda usar privilegios de Administración delegados granulares (GDAP) para implementar asignaciones pormenorizadas para los usuarios. Los privilegios de Administración delegados (DAP) siguen siendo necesarios para que el inquilino se incorpore correctamente, pero los clientes solo de GDAP pronto podrán incorporarse sin dependencias de DAP. Los permisos GDAP tienen prioridad cuando DAP y GDAP coexisten para un cliente.

Para configurar una relación GDAP, consulte [Obtención de permisos de administrador granulares para administrar el servicio de un cliente](/partner-center/gdap-obtain-admin-permissions-to-manage-customer). Para obtener más información sobre qué roles se recomiendan usar Lighthouse, consulte [Información general sobre los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md).

Los técnicos de MSP también pueden acceder a Lighthouse mediante los roles de agente de Administración o agente del departamento de soporte técnico a través de privilegios delegados de Administración (DAP).

Para las acciones relacionadas con inquilinos que no son del cliente en Lighthouse (por ejemplo, incorporación, desactivación o reactivación del cliente, administración de etiquetas, revisión de registros), los técnicos de MSP deben tener un rol asignado en el inquilino del asociado. Consulte [Introducción a los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md) para obtener más información sobre los roles de inquilino de asociados.

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Configuración de azure AD Privileged Identity Management (PIM)

Los CSP pueden minimizar el número de personas que tienen acceso a roles con privilegios elevados para proteger la información o los recursos mediante PIM. PIM reduce la posibilidad de que una persona malintencionada obtenga acceso a recursos o usuarios autorizados que afecten involuntariamente a un recurso confidencial. Los CSP también pueden conceder a los usuarios roles de privilegios elevados Just-In-Time para acceder a los recursos, realizar cambios amplios y supervisar lo que hacen los usuarios designados con su acceso con privilegios.

> [!NOTE]
> El uso de PIM de Azure AD requiere una licencia de Azure AD Premium P2 en el inquilino del asociado.

Los pasos siguientes elevan a los usuarios de inquilinos asociados a roles de privilegios más altos con ámbito de tiempo mediante PIM:

1. Cree un grupo asignable de roles como se describe en el artículo [Creación de un grupo para asignar roles en Azure Active Directory](/azure/active-directory/roles/groups-create-eligible).

2. Vaya a [Azure AD: todos los grupos](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) y agregue el nuevo grupo como miembro de un grupo de seguridad para roles con privilegios elevados (por ejemplo, Administración grupo de seguridad Agentes para DAP o un grupo de seguridad correspondiente similar para roles GDAP).

3. Configure el acceso con privilegios al nuevo grupo como se describe en el artículo [Asignación de propietarios y miembros aptos para grupos de acceso con privilegios](/azure/active-directory/privileged-identity-management/groups-assign-member-owner).

Para más información sobre PIM, consulte [¿Qué es Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="set-up-risk-based-azure-ad-conditional-access"></a>Configuración del acceso condicional de Azure AD basado en riesgos

Los MSP pueden usar el acceso condicional basado en riesgos para asegurarse de que sus miembros del personal demuestren su identidad mediante MFA y cambiando su contraseña cuando se detecte como un usuario de riesgo (con credenciales filtradas o por inteligencia sobre amenazas de Azure AD). Los usuarios también deben iniciar sesión desde una ubicación conocida o desde un dispositivo registrado cuando se detecta como un inicio de sesión de riesgo. Otros comportamientos de riesgo incluyen el inicio de sesión desde una dirección IP malintencionada o anónima o desde una ubicación de viaje atípica o imposible, el uso de un token anómalo, el uso de una contraseña de difusión de contraseñas o la exhibición de otro comportamiento de inicio de sesión inusual. En función del nivel de riesgo de un usuario, los CSP también pueden optar por bloquear el acceso al iniciar sesión. Para obtener más información sobre los riesgos, consulte [¿Qué es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks)

> [!NOTE]
> El acceso condicional requiere una licencia de Azure AD Premium P2 en el inquilino del asociado. Para configurar el acceso condicional, consulte [Configuración del acceso condicional de Azure Active Directory](/appcenter/general/configuring-aad-conditional-access).

## <a name="related-content"></a>Contenido relacionado

[Permisos de restablecimiento de contraseña](/azure/active-directory/roles/permissions-reference#password-reset-permissions) (artículo)\
[Introducción a los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md) (artículo)\
[Vea los roles de Azure Active Directory en Microsoft 365 Lighthouse](m365-lighthouse-view-your-roles.md) (artículo)\
[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)\
[Introducción a Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (artículo)\
[Registrarse para obtener Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (artículo)\
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)