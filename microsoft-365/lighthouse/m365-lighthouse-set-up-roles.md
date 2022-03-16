---
title: Configurar roles para administrar inquilinos de clientes
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo configurar roles para administrar inquilinos de clientes.
ms.openlocfilehash: 948e6909f0fc8d743c84662de6c8a2d9c0bc88e3
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512245"
---
# <a name="set-up-roles-to-manage-customer-tenants"></a>Configurar roles para administrar inquilinos de clientes

Los proveedores de servicios administrados (MSP) pueden habilitar el acceso granular y con límite de tiempo a sus inquilinos de clientes en Microsoft 365 Lighthouse mediante la configuración de privilegios de administrador delegados pormenorizados (GDAP) en el Centro de partners. GDAP ofrece a los MSP un alto nivel de control y flexibilidad al proporcionar acceso al cliente a través de Azure Active Directory [(Azure AD) funciones integradas](/azure/active-directory/roles/permissions-reference). La [asignación de los roles con](/azure/active-directory/roles/delegate-by-task) privilegios mínimos por tarea a través de GDAP a técnicos msp reduce el riesgo de seguridad tanto para los MSP como para los clientes. Habilite GDAP para asignar roles más granulares a los técnicos que usan Lighthouse y adopten un enfoque con privilegios mínimos para la seguridad en todos los inquilinos de clientes.

Si los técnicos msp todavía tienen acceso a entornos de clientes con los roles de agente de soporte técnico o agente de administración concedidos a través de privilegios de administrador delegados (DAP), consulte [DAP en Lighthouse](#dap-in-lighthouse) en este artículo. Si ambos GDAP y DAP coexisten, los roles concedidos a los usuarios a través de GDAP tienen prioridad para los clientes donde se ha establecido una relación GDAP.

## <a name="set-up-gdap-in-lighthouse"></a>Configurar GDAP en Lighthouse

> [!NOTE]
> GDAP se encuentra actualmente en [versión preliminar](/partner-center/announcements/2022-february#6) técnica (versión preliminar pública) para permitir a los partners asignar permisos pormenorizados antes de que GDAP esté disponible en general.

Los pasos de alto nivel siguientes son necesarios para crear una relación GDAP con un cliente. Para obtener más información sobre GDAP, vea [Introduction to granular delegated admin privileges (GDAP).](/partner-center/gdap-introduction)

1. [Clasifice a los usuarios](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) en grupos de seguridad dentro del espacio empresarial asociado Azure AD.

2. [Crear y enviar una solicitud de relación GDAP](/partner-center/gdap-obtain-admin-permissions-to-manage-customer) al cliente.

3. Asegúrese de que [el cliente aprueba la solicitud de relación GDAP](/partner-center/gdap-customer-approval).

4. [Asigne los grupos de seguridad relevantes](/partner-center/gdap-assign-azure-ad-roles#grant-permissions-to-security-groups) a la relación GDAP.

5. Asigne los roles [Azure Active Directory integrados adecuados](/azure/active-directory/roles/permissions-reference) a los grupos de seguridad de Lighthouse alineados para la administración de clientes.

Se recomienda asignar nombres a los grupos de seguridad en función de las tareas que los técnicos msp manejan en Lighthouse. Por ejemplo, puede crear grupos de seguridad para técnicos de soporte técnico, administradores de sistemas e ingenieros de escalación. Se recomienda usar los roles descritos en la tabla siguiente para administrar Lighthouse.

### <a name="example-security-groups"></a>Grupos de seguridad de ejemplo

||Técnicos del departamento de soporte técnico |Administradores del sistema |Ingenieros de escalación|
|--------------------|-------------|-------------|------------|
|**Roles GDAP recomendados** |<ul><li>Administrador del servicio de asistencia</li><li>Lector de seguridad</li></ul>   |<ul><li>Administrador de usuarios</li><li>Administrador de autenticación</li><li>Lector global</li><li>Administrador de Intune</li><li>Administrador de seguridad</li></ul>   |Administrador global  |
|**Tareas** |Lea la información del cliente en Lighthouse y lleve a cabo acciones limitadas (por ejemplo, restablecer contraseñas de usuario o actualizar información de contacto)   |Mantener la seguridad del cliente mediante acciones correctivas en Lighthouse (por ejemplo, reiniciar dispositivos).   |Lleve a cabo acciones con privilegios cuando sea necesario para proteger el inquilino del cliente (por ejemplo, bloquear el inicio de sesión de un administrador en peligro).  |

Para obtener descripciones de permisos específicos, [vea Azure AD roles integrados](/azure/active-directory/roles/permissions-reference). Para las tareas y roles específicos del asociado, vea [Roles con privilegios mínimos](/partner-center/gdap-least-privileged-roles-by-task).

## <a name="dap-in-lighthouse"></a>DAP en El faro

DAP restringe el acceso a los clientes de Lighthouse con dos roles: Agente de administración y Agente de soporte técnico. Puede comprobar qué usuarios del espacio empresarial asociado tienen los roles Agente de administración o Agente de soporte técnico revisando las pertenencias a grupos de seguridad en la [página Azure AD Todos los](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) grupos. Para revisar qué clientes aún tienen DAP en su lugar, vea [Monitoring administrative relationships and self-service DAP removal](/partner-center/dap-monitor-self-serve-removal).

Para los clientes con DAP y sin GDAP, el rol Agente de administración concede permisos para ver toda la información del inquilino y realizar cualquier acción en Lighthouse (vea a continuación otras acciones que también requieren un rol en el inquilino asociado). 

El rol Agente de soporte técnico concede permisos para ver toda la información del inquilino y tomar medidas limitadas en Lighthouse (como restablecer contraseñas de usuario, bloquear los inicios de sesión de usuario y actualizar la información de contacto del cliente y los sitios web).

Dados los amplios permisos concedidos a los usuarios asociados con DAP, se recomienda adoptar GDAP lo antes posible. Ambos modelos coexisten, pero GDAP reemplazará finalmente a DAP y los permisos de GDAP tienen prioridad sobre los permisos de DAP durante el período de transición. Para obtener más información, consulte [Preguntas más frecuentes sobre GDAP](/partner-center/gdap-faq).

## <a name="other-roles-and-permissions"></a>Otros roles y permisos

Para determinadas acciones en Lighthouse, se requieren asignaciones de roles en el espacio empresarial asociado. En la tabla siguiente se enumeran los roles de inquilino de asociados y sus permisos asociados.<br><br>

| Roles de inquilino de partners | Permisos |
|--|--|
| Administrador global del inquilino asociado | <ul><li>Regístrate en Lighthouse en el Centro de administración de Microsoft 365.</li><li>Aceptar modificaciones de contrato de partner durante la experiencia de primera ejecución.</li><li>Activar e desactivar un espacio empresarial.</li><li>Crear, actualizar y eliminar etiquetas.</li><li>Asignar y quitar etiquetas de un inquilino de cliente.</li></ul> |
| Miembro del inquilino asociado con al menos un rol Azure AD asignado con el siguiente conjunto de propiedades: **microsoft.office365.supportTickets/allEntities/allTasks**<br>(Para obtener una lista completa de Azure AD funciones, [vea Azure AD roles integrados](/azure/active-directory/roles/permissions-reference). | Crear solicitudes de servicio de Lighthouse. |
| Miembro del inquilino asociado que *cumple los* dos requisitos siguientes: <ul><li>Tiene al menos un Azure AD rol asignado con el siguiente conjunto de propiedades: **microsoft.office365.serviceHealth/allEntities/allTasks**<br>(Para obtener una lista completa de Azure AD funciones, [vea Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)</li><li>Tiene al menos un rol delegado de DAP asignado (agente de administración o agente de soporte técnico)</li></ul> | Ver información de estado del servicio. |

## <a name="next-steps"></a>Pasos siguientes

Después de crear roles, debe configurar la seguridad adicional del portal de Lighthouse, específicamente la autenticación multifactor (MFA) y, opcionalmente, Azure AD identity management (PIM). Para obtener más información, vea [Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md).

## <a name="related-content"></a>Contenido relacionado

[Roles con privilegios mínimos por tarea](/partner-center/gdap-least-privileged-roles-by-task?branch=pr-en-us-2577) (artículo)  
[Preguntas más frecuentes sobre privilegios de administración delegados (DAP)](/partner-center/dap-faq) (artículo)  
[Asignar roles y permisos a usuarios](/partner-center/permissions-overview) (artículo)  
[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)  
[Introducción a Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (artículo)  
[Registrarse para obtener Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (artículo)  
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
