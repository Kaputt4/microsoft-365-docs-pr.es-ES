---
title: Introducción a los permisos en Microsoft 365 Lighthouse
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
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Para proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga más información sobre los requisitos de permisos de Lighthouse.
ms.openlocfilehash: 25f38b8cbc0c6815139fd6afd3616cfaa7df48e1
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2022
ms.locfileid: "64595418"
---
# <a name="overview-of-permissions-in-microsoft-365-lighthouse"></a>Introducción a los permisos en Microsoft 365 Lighthouse

El acceso delegado a los inquilinos de clientes es necesario para que los proveedores de servicios administrados (MSP) usen Microsoft 365 Lighthouse. Los privilegios de administrador delegados pormenorizados (GDAP) proporcionan a los MSP un alto nivel de control y flexibilidad al proporcionar acceso al cliente a través de roles integrados Azure Active Directory [(Azure AD](/azure/active-directory/roles/permissions-reference)). La asignación de los roles con privilegios mínimos por tarea a través de GDAP a técnicos msp reduce el riesgo de seguridad tanto para los MSP como para los clientes. Para obtener más información sobre los roles con privilegios mínimos por tarea, vea Roles con privilegios mínimos[: Centro](/partner-center/gdap-least-privileged-roles-by-task) de partners y Roles con privilegios mínimos por [tarea en Azure Active Directory](/azure/active-directory/roles/delegate-by-task). Para obtener más información sobre cómo configurar una relación de GDAP con un inquilino de cliente, vea Obtener permisos de administrador granulares para administrar el servicio de un cliente [: Centro de partners.](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)

Se recomienda asignar roles a grupos de técnicos MSP en función de las tareas que cada grupo debe realizar en nombre del cliente. Por ejemplo, es posible que los técnicos de Service Desk necesiten leer los datos del inquilino del cliente o restablecer las contraseñas de usuario. En cambio, es posible que los ingenieros de escalación necesiten tomar más acciones correctivas para actualizar la configuración de seguridad del inquilino del cliente. Es una práctica recomendada asignar el rol menos permisivo necesario para completar una tarea de modo que los datos de clientes y asociados se mantienen seguros. Se recomienda usar Privileged Identity Management (PIM) para habilitar el acceso con ámbito de tiempo al rol Administrador global, si es necesario. Dar acceso global a demasiados usuarios es un riesgo para la seguridad y se recomienda limitarlo tanto como sea posible. Para obtener más información sobre cómo habilitar PIM, consulte [Configurar Azure AD PIM.](m365-lighthouse-configure-portal-security.md#set-up-azure-ad-privileged-identity-management-pim)

En la tabla de la siguiente sección se describen los roles GDAP que conceden permiso para leer datos de clientes y tomar medidas en los inquilinos del cliente en Lighthouse. Vea [Permisos en el espacio empresarial](#permissions-in-the-partner-tenant) asociado en este artículo para ver los roles adicionales necesarios para administrar entidades de Lighthouse (por ejemplo, etiquetas y solicitudes de servicio de Lighthouse).

> [!NOTE]
>GDAP se encuentra actualmente en [versión preliminar](/partner-center/announcements/2022-february#6) técnica (versión preliminar pública) para permitir a los partners asignar permisos pormenorizados antes de que GDAP esté disponible en general. Comprueba [Problemas conocidos](m365-lighthouse-known-issues.md) si tienes un problema al acceder o realizar una acción en Lighthouse.

## <a name="example-msp-service-tiers-and-recommended-gdap-roles"></a>Niveles de servicio MSP de ejemplo y roles GDAP recomendados

En la tabla siguiente se enumeran los roles GDAP recomendados para algunos niveles de servicio MSP de ejemplo y las acciones que dichos roles pueden realizar en las distintas páginas de Faro.

|| AccountManagers&nbsp;| ServiceDeskTechnician&nbsp;&nbsp; |SystemAdministrators&nbsp; | EscalationEngineers&nbsp;|
|---|---|---|---|---|
| **Roles GDAP recomendados** |<ul><li>Administrador del servicio de asistencia</li></ul> |<ul><li>Lector de seguridad<br>+</li><li>Administrador del servicio de asistencia</li></ul> |<ul><li>Lector global<br>+</li><li>Administrador de usuarios<br>+</li><li>Administrador de autenticación</li></ul> |<ul><li>Lector global<br>+</li><li>Administrador de usuarios<br>+</li><li>Intune administrador<br>+</li><li>Administrador de seguridad</li></ul>|
|**Lighthousepageallowedactions&nbsp;&nbsp;+&nbsp;&nbsp;**  |
| **Inicio**  | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | 
| **Inquilinos**     | <ul><li>Ver lista de inquilinos</li><li>Actualizar contactos de clientes y sitio web</li><li>Ver planes de implementación</li></ul>  | <ul><li>Ver lista de inquilinos</li><li>Actualizar contactos de clientes y sitio web</li><li>Ver planes de implementación</li></ul>   |  <ul><li>Ver lista de inquilinos</li><li>Actualizar contactos de clientes y sitio web</li><li>Ver planes de implementación</li><li>Ver Microsoft 365 de servicios</li></ul> | <ul><li>Ver lista de inquilinos</li><li>Actualizar contactos de clientes y sitio web</li><li>Ver planes de implementación</li><li>Ver Microsoft 365 de servicios</li></ul>  |
| **Usuarios**   | <ul><li>Ver datos de nivel de inquilino (no específicos del usuario)</li><li>Buscar cuentas de usuario entre inquilinos</li><li>Restablecer contraseña para usuarios que no son administradores*</li></ul>  | <ul><li>Ver todos los datos específicos del usuario</li><li>Buscar cuentas de usuario entre inquilinos</li><li>Restablecer contraseña para usuarios que no son administradores*</li></ul>|  <ul><li>Ver todos los datos específicos del usuario</li><li>Buscar cuentas de usuario entre inquilinos</li><li>Restablecer contraseña para usuarios que no son administradores*</i><li>Bloquear inicio de sesión</li></ul>  | <ul><li>Ver todos los datos específicos del usuario</li><li>Buscar cuentas de usuario entre inquilinos</li><li>Restablecer contraseña para usuarios que no son administradores*</li><li>Bloquear inicio de sesión</li><li>Confirmar usuarios en peligro</li><li>Descartar riesgos para los usuarios</li></ul> |
| **Devices**    | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li><li>Sincronizar dispositivo</li><li>Reiniciar el dispositivo</li><li>Recopilar diagnósticos</li></ul>|
| **Administración de amenazas**  | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li><li>Ejecutar examen completo</li><li>Ejecutar examen rápido</li><li>Actualizar protección antivirus</li><li>Reiniciar dispositivo</li></ul>|
| **Líneas base**    | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul>  | <ul><li>Ver todos los datos</li></ul> |
| **Windows 365** | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> | <ul><li>Ver todos los datos</li></ul> |
| **Estado del servicio****|  
|**Registros de auditoría****|

*Vea [Permisos de restablecimiento de contraseña para](/azure/active-directory/roles/permissions-reference#password-reset-permissions) una tabla que enumera los roles necesarios para restablecer las contraseñas de los administradores de inquilinos de clientes.

**Se necesitan otros roles y permisos para ver los registros de auditoría y estado del servicio. Para obtener más información, vea [Permissions in the partner tenant](#permissions-in-the-partner-tenant).

> [!NOTE]
> Si recibe un mensaje en Lighthouse que indica que no tiene permiso para ver o editar información, se le asigna un rol que no tiene los permisos adecuados para realizar la acción. Tendrás que contactar con un administrador de tu inquilino asociado que pueda asignarte el rol adecuado para la acción que estás intentando realizar.

## <a name="delegated-admin-privileges-dap-in-lighthouse"></a>Privilegios de administrador delegados (DAP) en Lighthouse

GDAP reemplazará finalmente DAP como el método principal para configurar el acceso delegado para los inquilinos del cliente. Sin embargo, si GDAP no se ha configurado, los técnicos de MSP aún pueden tener acceso a Lighthouse mediante el uso de los roles agente de soporte técnico o agente de administración concedidos a través de DAP. Para los clientes donde coexisten GDAP y DAP, los roles concedidos a los técnicos msp a través de GDAP tienen prioridad. Para obtener más información sobre la desuso de GDAP o DAP, consulte Preguntas más frecuentes de [GDAP](/partner-center/gdap-faq) o anuncios del Centro de partners para [fechas](/partner-center/announcements/2022-march#15) y escalas de tiempo.

Para los clientes con DAP y sin GDAP, el rol Agente de administración concede permisos para ver todos los datos del inquilino y realizar cualquier acción en Lighthouse (vea a continuación otras acciones que también requieren un rol en el inquilino asociado).

El rol Agente de soporte técnico concede permisos para ver todos los datos del inquilino y tomar medidas limitadas en Lighthouse, como restablecer contraseñas de usuario, bloquear inicios de sesión de usuario y actualizar la información de contacto del cliente y los sitios web.

Dados los amplios permisos concedidos a los usuarios asociados con roles de DAP, se recomienda adoptar GDAP lo antes posible. 

## <a name="permissions-in-the-partner-tenant"></a>Permisos en el inquilino asociado

Para determinadas acciones en Lighthouse, se requieren asignaciones de roles en el espacio empresarial asociado. En la tabla siguiente se enumeran los roles de inquilino de asociados y sus permisos asociados.

| Roles de inquilino de partners | Permisos |
|--|--|
| Administrador global del inquilino asociado | <ul><li>Regístrate en Lighthouse en el Centro de administración de Microsoft 365.</li><li>Aceptar modificaciones de contrato de partner durante la experiencia de primera ejecución.</li><li>Activar e desactivar un espacio empresarial.</li><li>Crear, actualizar y eliminar etiquetas.</li><li>Asignar y quitar etiquetas de un inquilino de cliente.</li></ul> |
| Miembro del espacio empresarial asociado con al menos Azure AD rol asignado con el siguiente conjunto de propiedades:<br>**microsoft.office365.supportTickets/allEntities/allTasks**<br>(Para obtener una lista completa de Azure AD funciones, [vea Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)). | Crear solicitudes de servicio de Lighthouse. |
| Miembro del inquilino asociado que *cumple los* dos requisitos siguientes: <ul><li>Tiene al menos un Azure AD rol asignado con la siguiente propiedad establecida:<br>**microsoft.office365.serviceHealth/allEntities/allTasks**<br>(Para obtener una lista completa de Azure AD funciones, [vea Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)).</li><li>Tiene al menos un rol delegado de DAP asignado (agente de administración o agente de soporte técnico)</li></ul> | Ver información de estado del servicio. |

## <a name="related-content"></a>Contenido relacionado

[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)  
[Preguntas más frecuentes sobre privilegios de administración delegados (DAP)](/partner-center/dap-faq) (artículo)  
[Asignar roles y permisos a usuarios](/partner-center/permissions-overview) (artículo)  
[Introducción a Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (artículo)  
[Registrarse para obtener Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (artículo)  
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
