---
title: Acerca de los roles de administrador de Intune en el Centro de administración de Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
description: Los roles de administrador se asignan a funciones empresariales y dan permisos para realizar tareas específicas en el centro de administración. Por ejemplo, el Administrador de servicios abre vales de soporte técnico con Microsoft.
ms.openlocfilehash: 6ee5c8410b64bffe66ee69e5c4468a9eda601cd8
ms.sourcegitcommit: 23e186b46b27a6a4863f507a52a11105afae9726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64882206"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Roles de administrador de Intune en el Centro de administración de Microsoft 365

Su suscripción de Microsoft 365 u Office 365 incluye un conjunto de roles de administrador que puede asignar a los usuarios de su organización mediante el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Cada rol de administrador se asigna a funciones empresariales comunes y concede a los usuarios de su organización permisos para realizar tareas específicas en los centros de administración.

El Centro de administración de Microsoft 365 le permite administrar algunos roles de Microsoft Intune. Sin embargo, estos roles son un subconjunto de los roles disponibles en el centro de administración de Intune. ¿Busca las descripciones detalladas de roles para Microsoft Intune? Consulte [Control de acceso basado en roles (RBAC) con Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

Para obtener más información sobre la asignación de roles en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">Centro de administración de Microsoft 365</a>, vea [Asignar roles de administrador](assign-admin-roles.md).

En el Centro de administración de Microsoft 365, puede ir a **Roles** y seleccionar cualquier rol para abrir su respectivo panel de detalles. Seleccione la pestaña **Permisos** para ver la lista detallada de lo que tienen permiso para hacer los administradores con ese rol asignado. Seleccione la pestaña **Asignado** o **Administradores asignados** para agregar usuarios a los roles.

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Roles de Microsoft Intune disponibles en el Centro de administración de Microsoft 365

|Rol de administrador     |¿A quién se le debe asignar este rol?  |
|---------|---------|
|Administrador de aplicaciones     |   Asigne el rol de administrador de aplicaciones a los usuarios que administran el ciclo de vida de la aplicación para aplicaciones móviles, configuran aplicaciones administradas por directivas y ven la información de dispositivo y los perfiles de configuración.  |
|Operador de asistencia     |   Asigne el rol del operador de asistencia a los usuarios que asignen aplicaciones y directivas a usuarios y dispositivos. |
|Administrador de roles de Intune    |   Asigne el rol de administrador de Intune a los usuarios que puedan asignar permisos de Intune a otros administradores y puedan administrar roles de Intune personalizados e integrados.   |
|Administrador de directivas y perfiles     |   Asigne el rol de administrador de directivas y perfiles para que los usuarios administren directivas de cumplimiento, perfiles de configuración y la inscripción de Apple.   |
|Operador de solo lectura     |   Asigne el rol de operador de solo lectura a los usuarios que solo puedan ver usuarios, dispositivos, detalles de inscripción y configuraciones.   |
|Administrador escolar     |   Asigne al rol de administrador escolar a usuarios para que tengan acceso completo a la administración de dispositivos, aplicaciones y configuraciones de Windows 10 e iOS en Intune para la Educación.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Administración delegada para Microsoft Partners

Si está trabajando con un Microsoft partner, puede asignarles roles de administrador. A su vez, pueden asignar a los usuarios de su empresa (o de la suya propia) roles de administrador. Es posible que quiera que lo hagan, por ejemplo, si están configurando y administrando su organización en línea por usted.
  
Un partner puede asignar estos roles: 
  
- Administración completa, que tiene privilegios equivalentes a los de un administrador global, con la excepción de administrar la autenticación multifactor mediante el Centro de Partners.

- Administración limitada, que tiene privilegios equivalentes a los de un administrador del departamento de soporte técnico.

Antes de que el partner pueda asignar estos roles a los usuarios, tendrá que agregar al partner como administrador delegado a su cuenta. Este proceso lo iniciará el partner autorizado. Le enviará un correo electrónico para preguntarle si quiere concederle permiso para actuar como administrador delegado. Para obtener instrucciones, consulte [Autorizar o quitar relaciones de partner](../misc/add-partner.md).
  
## <a name="related-content"></a>Contenido relacionado

[Acerca de los roles de administrador en Microsoft 365](about-admin-roles.md) (artículo)\
[Asignar roles de administrador](assign-admin-roles.md) (artículo)\
[Informes de actividad del Centro de administración de Microsoft 365](../activity-reports/activity-reports.md) (artículo)
