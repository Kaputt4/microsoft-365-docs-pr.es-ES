---
title: Introducción a los permisos en Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: magarlan, chrigreen
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga más información sobre los requisitos de permisos de Lighthouse.
ms.openlocfilehash: 0762529ed64ad83c7a38a2ba90037e90f4cdac39
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659507"
---
# <a name="overview-of-permissions-in-microsoft-365-lighthouse"></a>Introducción a los permisos en Microsoft 365 Lighthouse

El acceso delegado a los inquilinos del cliente es necesario para que los proveedores de servicios administrados (CSP) usen Microsoft 365 Lighthouse. Los privilegios de Administración delegados granulares (GDAP) proporcionan a los MSP un alto nivel de control y flexibilidad al proporcionar acceso al cliente a través de [roles integrados de Azure Active Directory (Azure AD](/azure/active-directory/roles/permissions-reference)). La asignación de los roles con privilegios mínimos por tarea mediante GDAP a los técnicos de MSP reduce el riesgo de seguridad tanto para los MSP como para los clientes. Para obtener más información sobre los roles con privilegios mínimos por tarea, consulte [Roles con privilegios mínimos: Centro](/partner-center/gdap-least-privileged-roles-by-task) de partners y [Roles con privilegios mínimos por tarea en Azure Active Directory](/azure/active-directory/roles/delegate-by-task). Para obtener más información sobre cómo configurar una relación GDAP con un inquilino de cliente, consulte [Obtención de permisos de administrador pormenorizados para administrar el servicio de un cliente: Centro de partners.](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)

Se recomienda asignar roles a grupos de técnicos de MSP en función de las tareas que cada grupo debe realizar en nombre del cliente. Por ejemplo, es posible que los técnicos de Service Desk solo necesiten leer los datos del inquilino del cliente o restablecer las contraseñas de usuario. Por el contrario, es posible que los ingenieros de escalación deba realizar más acciones correctivas para actualizar la configuración de seguridad del inquilino del cliente. Se recomienda asignar el rol menos permisivo necesario para completar una tarea para que los datos de clientes y asociados se mantengan seguros. Se recomienda usar Privileged Identity Management (PIM) para habilitar el acceso con ámbito de tiempo al rol de administrador global, si es necesario. Dar acceso global a demasiados usuarios supone un riesgo de seguridad y se recomienda limitarlo tanto como sea posible. Para obtener más información sobre cómo habilitar PIM, consulte [Configuración de PIM de Azure AD.](m365-lighthouse-configure-portal-security.md#set-up-azure-ad-privileged-identity-management-pim)

En las tablas de la sección siguiente se describen los roles de GDAP que conceden permiso para leer los datos de los clientes y realizar acciones en los inquilinos del cliente en Lighthouse. Consulte [Permisos en el inquilino del asociado](#permissions-in-the-partner-tenant) en este artículo para ver los roles adicionales necesarios para administrar entidades de Lighthouse (por ejemplo, etiquetas y solicitudes de servicio de Lighthouse).

## <a name="example-msp-service-tiers-recommended-gdap-roles-and-permissions"></a>Niveles de servicio MSP de ejemplo, roles de GDAP recomendados y permisos

En la tabla siguiente se enumeran los roles de GDAP recomendados para algunos niveles de servicio MSP de ejemplo. 

|| Administradores de cuentas| Técnicos de Service Desk | Administradores del sistema | Ingenieros de escalación|
|---|---|---|---|---|
| **Roles de GDAP recomendados** |<ul><li>Administrador del servicio de asistencia</li></ul> |<ul><li>Lector de seguridad<br>+</li><li>Administrador del servicio de asistencia</li></ul> |<ul><li>Lector global<br>+</li><li>Administrador de usuarios<br>+</li><li>Administrador de autenticación</li></ul> |<ul><li>Lector global<br>+</li><li>Administrador de usuarios<br>+</li><li>Administrador de Intune<br>+</li><li>Administrador de seguridad</li></ul>|

En la tabla siguiente se enumeran las acciones que los niveles de servicio MSP de ejemplo pueden realizar en las distintas páginas de Lighthouse según lo determinado por sus roles GDAP asignados (que se indican en la tabla anterior).

| Página de Lighthouse | Acciones permitidas por los administradores de cuentas| Acciones permitidas por los técnicos de Service Desk |Acciones permitidas por los administradores del sistema | Acciones permitidas de los ingenieros de escalación|
|---|---|---|---|---|
| Home  | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | 
| Espacios empresariales     | <ul><li>Ver lista de inquilinos</li><li>Actualizar los contactos de los clientes y el sitio web</li><li>Ver planes de implementación</li></ul>  | <ul><li>Ver lista de inquilinos</li><li>Actualizar los contactos de los clientes y el sitio web</li><li>Ver planes de implementación</li></ul>   |  <ul><li>Ver lista de inquilinos</li><li>Actualizar los contactos de los clientes y el sitio web</li><li>Ver planes de implementación</li><li>Visualización del uso de servicios de Microsoft 365</li></ul> | <ul><li>Ver lista de inquilinos</li><li>Actualizar los contactos de los clientes y el sitio web</li><li>Ver planes de implementación</li><li>Visualización del uso de servicios de Microsoft 365</li></ul>  |
| Usuarios   | <ul><li>Visualización de datos de nivel de inquilino (no específicos del usuario)</li><li>Búsqueda de cuentas de usuario entre inquilinos</li><li>Restablecimiento de contraseña para usuarios que no son administradores*</li></ul>  | <ul><li>Ver todos los datos específicos del usuario</li><li>Búsqueda de cuentas de usuario entre inquilinos</li><li>Restablecimiento de contraseña para usuarios que no son administradores*</li></ul>|  <ul><li>Ver todos los datos específicos del usuario</li><li>Búsqueda de cuentas de usuario entre inquilinos</li><li>Restablecimiento de contraseña para usuarios que no son administradores*</i><li>Bloquear inicio de sesión</li></ul>  | <ul><li>Ver todos los datos específicos del usuario</li><li>Búsqueda de cuentas de usuario entre inquilinos</li><li>Restablecimiento de contraseña para usuarios que no son administradores*</li><li>Bloquear inicio de sesión</li><li>Confirmación de usuarios en peligro</li><li>Descartar el riesgo para los usuarios</li></ul> |
| Dispositivos    | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li><li>Sincronizar dispositivo</li><li>Reiniciar el dispositivo</li><li>Recopilar diagnósticos</li></ul>|
| Administración de amenazas  | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li><li>Ejecución del examen completo</li><li>Ejecución del examen rápido</li><li>Actualización de la protección antivirus</li><li>Reiniciar dispositivo</li></ul>|
| Líneas base    | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul>  | <ul><li>Ver todos los datos</li></ul> |
| Windows 365 | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> |
| Estado del servicio**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A |
| Registros de auditoría**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A |

*Consulte [Permisos de restablecimiento de contraseña](/azure/active-directory/roles/permissions-reference#password-reset-permissions) para obtener una tabla en la que se enumeran los roles necesarios para restablecer las contraseñas de los administradores de inquilinos del cliente.

**Se requieren diferentes roles y permisos para ver los registros de Estado del servicio y auditoría. Para obtener más información, consulte [Permisos en el inquilino del asociado](#permissions-in-the-partner-tenant).

> [!NOTE]
> Si recibe un mensaje en Lighthouse que indica que no tiene permiso para ver o editar información, se le asigna un rol que no tiene los permisos adecuados para realizar la acción. Tendrá que ponerse en contacto con un administrador del inquilino del asociado que pueda asignarle el rol adecuado para la acción que intenta realizar.

## <a name="delegated-admin-privileges-dap-in-lighthouse"></a>Privilegios de Administración delegados (DAP) en Lighthouse

GDAP eventualmente reemplazará DAP como método principal para configurar el acceso delegado para los inquilinos del cliente. Sin embargo, si no se ha configurado GDAP, los técnicos de MSP pueden seguir accediendo a Lighthouse mediante el agente del departamento de soporte técnico o los roles de agente de Administración concedidos a través de DAP. Para los clientes en los que coexisten GDAP y DAP, los roles concedidos a los técnicos de MSP a través de GDAP tienen prioridad. Para obtener más información sobre el [desuso](/partner-center/announcements/2022-march#15) de GDAP o DAP, consulte [preguntas más frecuentes sobre GDAP](/partner-center/gdap-faq) o anuncios del Centro de partners para conocer fechas y escalas de tiempo.

Para los clientes con DAP y sin GDAP, el rol de agente de Administración concede permisos para ver todos los datos del inquilino y realizar cualquier acción en Lighthouse (consulte a continuación otras acciones que también requieren un rol en el inquilino del asociado).

El rol Agente del departamento de soporte técnico concede permisos para ver todos los datos de inquilino y realizar acciones limitadas en Lighthouse, como restablecer contraseñas de usuario, bloquear inicios de sesión de usuario y actualizar la información de contacto del cliente y los sitios web.

Dados los amplios permisos concedidos a los usuarios asociados con roles DAP, se recomienda adoptar GDAP lo antes posible. 

## <a name="permissions-in-the-partner-tenant"></a>Permisos en el inquilino del asociado

Para determinadas acciones de Lighthouse, se requieren asignaciones de roles en el inquilino del asociado. En la tabla siguiente se enumeran los roles de inquilino de asociados y sus permisos asociados.

| Roles de inquilino de asociados | Permisos |
|--|--|
| Administrador global del inquilino del asociado | <ul><li>Regístrese en Lighthouse en el Centro de administración de Microsoft 365.</li><li>Acepte las modificaciones del contrato de asociado durante la experiencia de primera ejecución.</li><li>Active e inactiva un inquilino.</li><li>Crear, actualizar y eliminar etiquetas.</li><li>Asigne y quite etiquetas de un inquilino de cliente.</li><li>Revisión de los registros de auditoría</li></ul> |
| Miembro de inquilino asociado con al menos un rol de Azure AD asignado con el siguiente conjunto de propiedades:<br>**microsoft.office365.supportTickets/allEntities/allTasks**<br>(Para obtener una lista completa de los roles de Azure AD, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference)). | Cree solicitudes de servicio de Lighthouse. |
| Miembro del inquilino asociado que cumple *los dos* requisitos siguientes: <ul><li>Tiene al menos un rol de Azure AD asignado con la siguiente propiedad establecida:<br>**microsoft.office365.serviceHealth/allEntities/allTasks**<br>(Para obtener una lista completa de los roles de Azure AD, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference)).</li><li>Tiene asignado al menos un rol delegado de DAP (agente de Administración o agente del departamento de soporte técnico)</li></ul> | Ver la información de estado del servicio. |

## <a name="related-content"></a>Contenido relacionado

[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)  
[Preguntas más frecuentes sobre privilegios de administración delegados (DAP)](/partner-center/dap-faq) (artículo)  
[Visualización de los roles de Azure Active Directory en Microsoft 365 Lighthouse](m365-lighthouse-view-your-roles.md) (artículo)  
[Asignación de roles y permisos a los usuarios](/partner-center/permissions-overview) (artículo)  
[Información general de Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (artículo)  
[Registrarse para obtener Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (artículo)  
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)
