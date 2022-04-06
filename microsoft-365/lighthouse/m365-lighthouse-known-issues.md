---
title: Problemas conocidos con Microsoft 365 Lighthouse
f1.keywords: NOCSH
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, vea una lista de problemas conocidos para Lighthouse por área de características.
ms.openlocfilehash: 3151937d4552da09c9cfd6808db2bad8bafbbc46
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2022
ms.locfileid: "64594673"
---
# <a name="known-issues-with-microsoft-365-lighthouse"></a>Problemas conocidos con Microsoft 365 Lighthouse

En este artículo se enumeran los problemas conocidos Microsoft 365 Lighthouse por área de características. Para obtener más información acerca de Lighthouse, consulte [Overview of Microsoft 365 Lighthouse](m365-lighthouse-overview.md).

## <a name="users"></a>Usuarios

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Helpdesk Agent no puede restablecer una contraseña de usuario** | Los técnicos del Proveedor de servicios administrados (MSP) que son miembros del grupo Agente de soporte técnico no pueden restablecer las contraseñas de los usuarios de los inquilinos de clientes. Cuando intentan restablecer la contraseña de un usuario, obtienen el siguiente mensaje de error: "No tiene permiso para hacerlo. [Más información](m365-lighthouse-configure-portal-security.md)" | Para evitar el problema de permisos, los agentes del departamento de soporte técnico deben restablecer las contraseñas mediante el Centro de administración de Microsoft 365 o Azure Active Directory. |

## <a name="devices"></a>Dispositivos

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Aparece la directiva eliminada** | Después de eliminar una directiva de cumplimiento de dispositivos Intune, seguirá siendo visible temporalmente en Lighthouse. Si los técnicos msp intentan hacer una comparación de directivas que incluye una directiva que se ha eliminado, los técnicos obtienen el siguiente error: "Algo salió mal. Actualice la página e inténtelo de nuevo". | Para resolver el error, desactive la directiva eliminada de la comparación de directivas y compare solo las directivas existentes. |

## <a name="threat-management"></a>Administración de amenazas

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Falta el nombre de la amenaza** | Cuando los técnicos de MSP ven la lista de amenazas de la página Administración de amenazas, es posible que algunas amenazas falte el nombre de la amenaza. Esto ocurrirá cuando el dispositivo en el que se detectó la amenaza se quitó recientemente de Intune. | El problema se resolverá en un plazo de 48 horas. No se requieren pasos adicionales. |

## <a name="baselines"></a>Líneas base

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Configuración en conflicto al comparar pasos de implementación de MFA y autenticación heredada de bloques** | Si un inquilino de cliente ha implementado la autenticación heredada de bloques y uno de los pasos de implementación de MFA, una prueba de comparación describirá erróneamente esta configuración como conflictiva. | No se requiere ninguna solución alternativa. La configuración no entra en conflicto y los usuarios del inquilino del cliente no se verán afectados. |

## <a name="windows-365"></a>Windows 365

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Error de aprovisionamiento de reintentos** | Los técnicos msp obtienen un mensaje de error "No tiene permisos para hacerlo" al intentar reintentar el aprovisionamiento de un equipo en la nube. | Para evitar este problema, inicie sesión en el inquilino del cliente y, a continuación, reprovisione equipos en la nube desde el Centro de administración de Microsoft Endpoint Manger. Para obtener instrucciones, [consulta Reprovision a Cloud PC](/windows-365/enterprise/reprovision-cloud-pc). |

## <a name="audit-logs"></a>Registros de auditoría


| Problema | Descripción | Solución |
|--|--|--|
| **Las acciones Desactivar y Reactivar no aparecen en los registros de auditoría** | Actualmente, las siguientes actividades no se notifican en la página Registros de auditoría de Lighthouse: <ul><li>Nombre: offboardTenant \| Action: Inactivate a un cliente</li> <li>Nombre: resetTenantOnboardingStatus Action \| : Reactive customer</li></ul> | No hay ninguna solución alternativa, pero estamos trabajando en una corrección. Estas actividades aparecerán en los registros de auditoría una vez que se implemente la corrección en el servicio. |
| **Filter no muestra todos los usuarios** | Cuando los técnicos de MSP intentan filtrar mediante **Iniciado** por, la lista de todos los nombres de entidad de seguridad de usuario (UPN) (correspondientes a los id. de correo electrónico de los técnicos que iniciaron acciones generando registros de auditoría) no se muestra completamente debajo del filtro.<br><br>Tenga en cuenta que los propios registros de auditoría se mostrarán por completo; solo se afecta la capacidad de filtrarlos mediante **Iniciado** por. | No hay ninguna solución alternativa, pero estamos trabajando en una corrección. El filtro volverá a su comportamiento esperado, mostrando la lista completa de UPN por la que filtrar, una vez que se implemente la corrección en el servicio. |

## <a name="delegated-admin-privilegesdap"></a>Privilegios de administrador delegados (DAP)

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Retraso de permisos al cambiar roles de DAP** | Si se agrega o quita un técnico MSP del grupo Agente de administración o Agente de soporte técnico, puede haber un retraso en reflejar los permisos adecuados en Lighthouse. | El problema se resolverá en 30 minutos. No se requieren pasos adicionales. |

## <a name="granular-delegated-admin-privilegesgdap"></a>Privilegios de administrador delegados pormenorizados (GDAP)

> [!NOTE]
> GDAP se encuentra actualmente en [versión preliminar](/partner-center/announcements/2022-february#6) técnica (versión preliminar pública) para permitir a los partners asignar permisos pormenorizados antes de que GDAP esté disponible en general.

Actualmente, DAP es necesario para incorporar clientes a Lighthouse. También se recomienda establecer GDAP con los clientes para habilitar un acceso delegado más seguro. Mientras QUE DAP y GDAP coexisten, GDAP tendrá prioridad para los clientes en los que ambos modelos estén en su lugar. Pronto, los clientes con solo GDAP (y sin DAP) podrán incorporarse a Lighthouse.<br><br>

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Varios problemas de permisos de GDAP en Lighthouse** | Ciertos roles GDAP por sí mismos no conceden el mismo nivel de acceso a los datos de clientes en Lighthouse que en una experiencia de inquilino único. Si alguno de los siguientes roles se asigna individualmente (esto es, no en combinación con otros roles GDAP) a los técnicos msp, pueden encontrar errores, incluidos:<ul><li>Los administradores de seguridad de GDAP no pueden ver usuarios arriesgados, descartar riesgos o confirmar usuarios en peligro dentro de Lighthouse.</li><li>Los lectores de seguridad de GDAP no pueden ver usuarios arriesgados dentro de Lighthouse.</li><li>Los administradores globales de GDAP ven un mensaje de error al intentar ver el estado del servicio en Lighthouse.</li><li>Los administradores globales de GDAP experimentan problemas para implementar los pasos del plan de implementación en Lighthouse.</li></ul> | La solución alternativa consiste en asignar una combinación de roles GDAP a los técnicos msp en función del nivel de acceso a los datos del cliente que necesiten. Para obtener una lista de los roles GDAP recomendados para usar Lighthouse, vea [Overview of permissions in Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md).<br><br>Para los problemas en los que incluso los permisos de administrador global de GDAP no permiten el uso de una característica en Lighthouse, la solución alternativa es obtener acceso al centro de administración adecuado desde el inquilino del cliente para administrar el cliente (por ejemplo, acceder al Centro de administración de Microsoft 365 desde el inquilino del cliente para comprobar el estado del servicio). Para obtener instrucciones sobre cómo modificar una relación de GDAP, vea Obtener permisos de [administrador granulares para administrar el servicio de un cliente: Centro de partners](/partner-center/gdap-obtain-admin-permissions-to-manage-customer). |

## <a name="localization"></a>Localización

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Problemas de traducción** | Es posible que los usuarios experimenten problemas de traducción de idioma cuando el idioma de su explorador o su selección de idioma en Lighthouse no sea inglés. | Para minimizar los problemas de traducción en Lighthouse, asegúrese de que la selección de idioma del explorador coincide con la de la configuración de idioma en el portal de Faro. Para cambiar la selección de idioma en Faro, inicie sesión en Faro y seleccione el icono de engranaje en la parte superior de la página para abrir la página Configuración del portal, seleccione **Idioma + región** y, a continuación, seleccione el idioma y los formatos regionales adecuados. |

## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)\
[Solucionar problemas y resolver mensajes de error en Microsoft 365 Lighthouse](m365-lighthouse-troubleshoot.md) (artículo)\
[Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md) (artículo)