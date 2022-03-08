---
title: Configurar Microsoft 365 Lighthouse seguridad del portal
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo configurar la seguridad del portal.
ms.openlocfilehash: 8f8ec851d2ce6795565530e120f3704128336ea2
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323127"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>Configurar Microsoft 365 Lighthouse seguridad del portal

Proteger el acceso a los datos de los clientes cuando un proveedor de servicios administrados (MSP) ha delegado permisos de acceso a sus inquilinos es una prioridad de ciberseguridad. Microsoft 365 Lighthouse incluye funciones necesarias y opcionales que le ayudarán a configurar la seguridad del portal de Faro. Debe configurar roles específicos con la autenticación multifactor (MFA) habilitada para poder tener acceso a Lighthouse. Opcionalmente, puede configurar Azure AD Privileged Identity Management (PIM) y acceso condicional.

## <a name="set-up-multifactor-authentication-mfa"></a>Configurar la autenticación multifactor (MFA)

Como se mencionó en la entrada de blog [$word Pa$$word importa](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984):

> "La contraseña no importa, pero MFA sí. Según nuestros estudios, es más del 99,9 % menos probable que su cuenta se vea comprometida si usa MFA".

Cuando los usuarios tienen acceso a Lighthouse por primera vez, se les pedirá que configuren MFA si su cuenta de Microsoft 365 aún no la tiene configurada. Los usuarios no podrán acceder a Lighthouse hasta que se complete el paso de configuración de MFA requerido. Para obtener más información sobre los métodos de autenticación, consulte [Configurar el Microsoft 365 inicio de sesión para la autenticación multifactor](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

## <a name="set-up-role-based-access-control"></a>Configurar el control de acceso basado en roles

El control de acceso basado en roles (RBAC) concede acceso a recursos o información basado en roles de usuario. El acceso a los datos y la configuración del inquilino del cliente en Lighthouse está restringido a roles específicos del programa Proveedor de soluciones en la nube (CSP). Para configurar roles RBAC en Lighthouse, se recomienda usar privilegios de administrador delegados pormenorizados (GDAP) para implementar asignaciones pormenorizados para los usuarios.

Para empezar con GDAP, consulte [Configurar roles para administrar inquilinos de clientes](m365-lighthouse-set-up-roles.md).

Los técnicos msp también pueden tener acceso a Lighthouse mediante roles de agente de administración o agente de soporte técnico mediante privilegios de administrador delegados (DAP).

Para las acciones no relacionadas con el inquilino del cliente en Lighthouse (por ejemplo, incorporación, desactivación/reactivación del cliente, administración de etiquetas, revisión de registros), los técnicos msp deben tener un rol asignado en el inquilino asociado. En el vínculo del artículo anterior se detallan dichos roles y sus permisos en Lighthouse.

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Configurar Azure AD Privileged Identity Management (PIM)

Los MSP pueden minimizar el número de personas que tienen acceso a roles de privilegios altos para proteger la información o los recursos mediante PIM. PIM reduce la posibilidad de que una persona malintencionada obtenga acceso a recursos o usuarios autorizados que inadvertidamente impacten en un recurso confidencial. Los MSP también pueden conceder a los usuarios roles de privilegios altos justo a tiempo para obtener acceso a recursos, realizar cambios amplios y supervisar lo que los usuarios designados hacen con su acceso con privilegios. 

> [!NOTE]
> El Azure AD PIM requiere una licencia Azure AD Premium P2 en el inquilino asociado.

Los siguientes pasos elevan a los usuarios de inquilinos asociados a roles de privilegios más altos con ámbito de tiempo mediante PIM:

1. Cree un grupo asignable de roles como se describe en el artículo Crear un grupo para asignar [roles en Azure Active Directory](/azure/active-directory/roles/groups-create-eligible).

2. Vaya a [Azure AD:](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) todos los grupos y agregue el nuevo grupo como miembro de un grupo de seguridad para roles de privilegios altos (por ejemplo, grupo de seguridad agentes de administración para DAP o un grupo de seguridad similarmente respectivo para roles GDAP).

3. Configure el acceso con privilegios al nuevo grupo, tal como se describe en el artículo Asignar propietarios y miembros elegibles [para grupos de acceso con privilegios](/azure/active-directory/privileged-identity-management/groups-assign-member-owner).

Para obtener más información sobre PIM, consulta [¿Qué Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="set-up-risk-based-azure-ad-conditional-access"></a>Configurar el acceso condicional basado en Azure AD riesgos

Los MSP pueden usar el acceso condicional basado en riesgos para asegurarse de que los miembros del personal demuestren su identidad mediante MFA y cambiando su contraseña cuando se detecta como un usuario de riesgo (con credenciales filtradas o por Azure AD inteligencia de amenazas). Los usuarios también deben iniciar sesión desde una ubicación conocida o un dispositivo registrado cuando se detecta como un inicio de sesión arriesgado. Otros comportamientos de riesgo incluyen iniciar sesión desde una dirección IP malintencionada o anónima o desde una ubicación de viaje atípica o imposible, usar un token anómalo, usar una contraseña de un spray de contraseña o mostrar otro comportamiento de inicio de sesión inusual. Según el nivel de riesgo de un usuario, los MSP también pueden optar por bloquear el acceso al iniciar sesión. Para obtener más información sobre los riesgos, consulte [¿Qué es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks) 

> [!NOTE]
> El acceso condicional requiere una Azure AD Premium P2 en el inquilino asociado. Para configurar el acceso condicional, consulte [Configuring Azure Active Directory Conditional Access](/appcenter/general/configuring-aad-conditional-access).

## <a name="related-content"></a>Contenido relacionado

[Permisos de restablecimiento de contraseña](/azure/active-directory/roles/permissions-reference#password-reset-permissions) (artículo)\
[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)\
[Introducción a Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (artículo)\
[Registrarse para Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)