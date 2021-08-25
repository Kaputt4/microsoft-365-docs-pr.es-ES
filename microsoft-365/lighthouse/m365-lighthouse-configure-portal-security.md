---
title: Configurar Microsoft 365 Lighthouse seguridad del portal
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo configurar la seguridad del portal.
ms.openlocfilehash: 9701ecc002144f791be6caad1e93230be5a83bf0
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "58508087"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>Configurar Microsoft 365 Lighthouse seguridad del portal

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Proteger el acceso a los datos de los clientes cuando un proveedor de servicios administrados (MSP) ha delegado permisos de acceso a sus inquilinos es una prioridad de ciberseguridad. Microsoft 365 Lighthouse incluye funciones necesarias y opcionales que le ayudarán a configurar la seguridad del portal de Lighthouse.

## <a name="set-up-multifactor-authentication-mfa"></a>Configurar la autenticación multifactor (MFA)

Como se mencionó en la entrada de blog [Su pa$$word no importa:](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)

> "La contraseña no importa, pero MFA sí. Según nuestros estudios, es más del 99,9 % menos probable que su cuenta se vea comprometida si usa MFA".

Cuando los usuarios tengan acceso a Lighthouse por primera vez, se les pedirá que configuren MFA si su cuenta de Microsoft 365 aún no la tiene configurada. Los usuarios no podrán acceder a Lighthouse hasta que se complete el paso de configuración de MFA requerido. Para obtener más información acerca de los métodos de autenticación, vea Configurar el Microsoft 365 inicio de sesión [para la autenticación multifactor](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

## <a name="set-up-roles-to-manage-customer-tenants"></a>Configurar roles para administrar inquilinos de clientes

El acceso a los datos y la configuración del inquilino del cliente en Lighthouse está restringido a los roles agente de administración y agente de soporte técnico desde el programa proveedor de soluciones en la nube (CSP).

Puede comprobar qué usuarios del espacio empresarial asociado tienen los roles Agente de administración y Agente de soporte técnico revisando las pertenencias a grupos de seguridad en la página [Azure AD – Todos los](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) grupos. Para obtener información sobre cómo asignar roles de programa CSP y otros permisos a los usuarios, vea [Asignar roles y permisos a los usuarios](/partner-center/permissions-overview). Como MSP, si aún no tiene privilegios de acceso delegados a los inquilinos del cliente, obtenga información sobre cómo obtenerlos en el artículo Obtener permisos para administrar el servicio o la suscripción de un [cliente.](/partner-center/customers-revoke-admin-privileges)

En la tabla siguiente se enumeran las distintas páginas de Lighthouse y los permisos necesarios para ver y actuar sobre los datos del inquilino del cliente y la configuración de los roles Agente de administración y Agente de soporte técnico.<br><br>

| Página de Faro | Permisos del agente de administración | Permisos del agente de soporte técnico |
|--|--|--|
| Inicio | <ul><li>Ver todas </li></ul> | <ul><li>Ver todas </li></ul> |
| Espacios empresariales | <ul><li>Ver todas </li><li>Actualizar contactos de clientes y sitio web</li><li>Ver y aplicar planes de implementación</li></ul> | <ul><li>Ver todas </li><li>Actualizar contactos de clientes y sitio web</li><li>Ver planes de implementación</li></ul> |
| Usuarios | <ul><li>Ver todas </li><li>Restablecer contraseña</li><li>Bloquear inicio de sesión</li><li>Habilitar MFA</li></ul> | <ul><li>Ver todas </li><li>Restablecer contraseña</li><li>Bloquear inicio de sesión</li></ul> |
| Dispositivos | <ul><li>Ver todas </li></ul> | <ul><li>Ver todas </li></ul> |
| Amenazas | <ul><li>Ver todas </li><li>Ejecutar examen rápido</li><li>Ejecutar examen completo</li><li>Reiniciar dispositivo</li><li>Actualizar antivirus</li></ul> | <ul><li>Ver todas </li></ul> |
| Líneas base | <ul><li>Ver todas </li></ul> | <ul><li>Ver todas </li></ul> |
| Estado del servicio | <ul><li>Ver todos*</li></ul> | <ul><li>Ver todos*</li></ul> |

> [!NOTE]
> Actualmente, para realizar las acciones marcadas con * en la tabla, los usuarios también tendrán que tener el rol de Azure AD en el inquilino asociado con la siguiente propiedad establecida: **microsoft.office365.serviceHealth/allEntities/allTasks**. Para obtener una lista de los roles de Azure AD, vea [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).

Dados los amplios permisos asociados con el rol agente [](/azure/active-directory/develop/secure-least-privileged-access) de administración, se recomienda respetar el principio de acceso con privilegios mínimos al designar un usuario de inquilino asociado como agente de administración frente a agente de soporte técnico. Una forma de hacerlo es asignar el rol agente del departamento de soporte técnico a los usuarios de inquilinos asociados necesarios. Esto les permite ver los datos y la configuración del cliente, pero no realizar cambios generales. A continuación, cuando sea necesario, use las funciones de aprobación de acceso just-in-time de Azure AD Privileged Identity Management (PIM) para proporcionar a los usuarios un rol de agente de administración con ámbito de tiempo.

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Configurar Azure AD Privileged Identity Management (PIM)

Los MSP pueden minimizar el número de personas que tienen acceso a información o recursos seguros mediante Azure AD Privileged Identity Management (PIM). PIM reduce la posibilidad de que una persona malintencionada obtenga acceso a recursos o usuarios autorizados que inadvertidamente impacten en un recurso confidencial. Los MSP también pueden conceder a los usuarios acceso con privilegios justo a tiempo a los recursos y supervisar lo que los usuarios designados hacen con su acceso con privilegios.

> [!NOTE]
> El uso de PIM de Azure AD requiere Azure AD Premium P2 licencia en el inquilino asociado.

Los siguientes pasos elevan a los usuarios de inquilinos asociados a roles de agente de administración con ámbito de tiempo mediante PIM de Azure AD:

1. Cree un grupo asignable de roles como se describe en el artículo Crear un grupo para asignar [roles en Azure Active Directory](/azure/active-directory/roles/groups-create-eligible).

2. Vaya a [Azure AD: todos los grupos](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) y agregue el nuevo grupo como miembro del grupo Agentes de administración.

3. Configure el acceso con privilegios al nuevo grupo, tal como se describe en el artículo Asignar propietarios y miembros elegibles [para grupos de acceso con privilegios.](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)

Para obtener más información, vea [What is Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>Otros roles y permisos

En la tabla siguiente se enumeran los roles de inquilino de asociados y sus permisos asociados.<br><br>

| Roles de inquilino de partners | Permisos dentro del espacio empresarial asociado |
|--|--|
| Administrador global del inquilino asociado | <ul><li>Regístrate en Lighthouse en el Centro de administración de Microsoft 365.</li><li>Aceptar modificaciones de contrato de partner durante la experiencia de primera ejecución.</li><li>Ver inquilinos de clientes en la página Inquilinos.\*</li><li>Activar e desactivar un espacio empresarial.\*</li><li>Actualizar los contactos del cliente y el sitio web.\*</li><li>Crear, actualizar y eliminar etiquetas.\*</li><li>Asignar y quitar etiquetas de un inquilino de cliente.\*</li></ul> |
| Administrador del inquilino asociado con al menos uno<br> Rol de Azure AD asignado con el siguiente conjunto de propiedades:<br> **microsoft.office365.supportTickets/allEntities/allTasks**<br> (Para obtener una lista de los roles de Azure AD, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).) | <ul><li>Crear solicitudes de servicio de Lighthouse.</li></ul> |

> [!NOTE]
> Actualmente, para realizar las acciones marcadas con * en la tabla, el administrador global debe asumir el rol Agente de administración.

## <a name="related-content"></a>Contenido relacionado

[Introducción a Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (artículo)\
[Registrarse para Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)