---
title: Acerca de los roles de administrador de Intune en el Centro de administración de Microsoft 365
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom: ''
description: El Centro de administración de Microsoft 365 permite administrar algunos roles de Microsoft Intune, que se asignan a funciones empresariales y conceden permisos para realizar tareas específicas.
ms.openlocfilehash: d3f7ff980bb87ac70fb2400f55ff54bdbd511eab
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "67614954"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Roles de administrador de Intune en el Centro de administración de Microsoft 365

Su suscripción de Microsoft 365 u Office 365 incluye un conjunto de roles de administrador que puede asignar a cualquier usuario de su organización mediante el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Cada rol de administrador se asigna a una función empresarial común y da permisos a los usuarios de su organización para realizar tareas específicas en los centros de administración. Dado esto, esos roles son solo un subconjunto de todos los roles disponibles en el centro de administración de Intune, que incluye roles adicionales específicos de Intune.

Antes de agregar roles específicos de Intune, se deben asignar roles en Azure AD. Para ver estos roles, elija **Endpoint Manager > Roles de administración de inquilinos > roles > todos los roles >**. Podrá administrar el rol en las siguientes páginas:

- Propiedades: el nombre, la descripción, los permisos y las etiquetas de ámbito para el rol.
- Asignaciones: lista de asignaciones de roles que definen qué usuarios tienen acceso a qué usuarios o dispositivos. Un rol puede tener varias asignaciones y un usuario puede tener varias asignaciones.

## <a name="about-roles-based-access-control-in-intune"></a>Acerca del control de acceso basado en roles en Intune

El control de acceso basado en roles (RBAC) le ayuda a administrar quién tiene acceso a los recursos de su organización y qué pueden hacer con esos recursos. Mediante la asignación de roles a los usuarios de Intune, puede limitar lo que pueden ver y cambiar. Hay roles integrados y personalizados, y cada rol tiene un conjunto de permisos que determinan a qué usuarios con ese rol pueden acceder o cambiar dentro de la organización. La siguiente información tratará ambos tipos de roles en Intune.

Para crear, editar o asignar roles, la cuenta debe tener uno de los siguientes permisos en Azure AD:

- **Administrador global**
- **Administrador de servicios de Intune** (también conocido como **administrador de Intune**, pero no debe confundirse con el rol de **administrador de roles de Intune** integrado).

Obtenga más información sobre [los roles de Azure Active Directory y RBAC](/azure/active-directory/roles/permissions-reference.md).

## <a name="microsoft-intune-built-in-roles"></a>Roles integrados de Microsoft Intune

Los roles integrados usan reglas predefinidas basadas en escenarios comunes de Intune. Como alternativa, los roles personalizados se basan en reglas definidas de forma estricta por el usuario. 

Estos son los roles integrados que puede asignar:

|Rol de administrador     |¿A quién se le debe asignar este rol?  |
|---------|---------|
|**Administrador de aplicaciones**     |   Asigne el rol de administrador de aplicaciones a los usuarios que administran el ciclo de vida de la aplicación para aplicaciones móviles, configuran aplicaciones administradas por directivas y ven la información de dispositivo y los perfiles de configuración.  |
|**Operador de asistencia**     |   Asigne el rol del operador de asistencia a los usuarios que asignen aplicaciones y directivas a usuarios y dispositivos. |
|**Administrador de roles de Intune**    |   Asigne el rol de administrador de Intune a los usuarios que puedan asignar permisos de Intune a otros administradores y puedan administrar roles de Intune personalizados e integrados.   |
|**Administrador de directivas y perfiles**     |   Asigne el rol de administrador de directivas y perfiles para que los usuarios administren directivas de cumplimiento, perfiles de configuración y la inscripción de Apple.   |
|**Operador de solo lectura**     |   Asigne el rol de operador de solo lectura a los usuarios que solo puedan ver usuarios, dispositivos, detalles de inscripción y configuraciones.   |
|**Administrador escolar**     |   Asigne el rol de administrador de la escuela a los usuarios para obtener acceso completo para administrar dispositivos, aplicaciones y configuraciones Windows 10-11 e iOS en Intune for Education.   |
|**Administrador de equipo en la nube**     |   Un administrador de equipos en la nube tiene acceso de lectura y escritura a todas las características de equipos en la nube ubicadas en la hoja de equipos en la nube.   |
|**Lector de equipo en la nube**     |   Un lector de equipos en la nube tiene acceso de lectura a todas las características de equipos en la nube ubicadas en la hoja de equipos en la nube.   |

## <a name="microsoft-intune-custom-roles"></a>Roles personalizados de Microsoft Intune

Puede crear roles personalizados en Intune que incluyan los permisos necesarios para una función de trabajo específica. Por ejemplo, si un grupo del departamento de TI administra las aplicaciones, las directivas y los perfiles de configuración, puede agregar todos los permisos juntos en un rol personalizado. Después de crear un rol personalizado, puede asignarlo a todos los usuarios que necesiten esos permisos.

Al igual que con los roles integrados, para crear, editar o asignar roles, la cuenta debe tener uno de los siguientes permisos en Azure AD:

- **Administrador global**
- **Administrador de servicios de Intune** (también conocido como **administrador de Intune**, pero no debe confundirse con el rol de **administrador de roles de Intune** integrado).

Para crear un rol personalizado:

1. En el Centro de administración de Microsoft Endpoint Manager, elija **Administración de inquilinos > Roles > Todos los roles > Crear**.

1. En la página **Datos básicos**, escriba un nombre y una descripción para el nuevo rol y, después, elija **Siguiente**.

1. En la página **Permisos**, elija los permisos que quiera usar con este rol.

1. En la página **Ámbito (etiquetas)**, seleccione las etiquetas para este rol. Cuando este rol se asigna a un usuario, el usuario puede acceder a los recursos que también tienen estas etiquetas. Elija **Siguiente**.

1. Cuando haya terminado, en la página **Revisar y crear** elija **Crear**. El nuevo rol se muestra en la lista de la hoja **Roles de Intune: Todos los roles**.

Para copiar un rol:

1. En el Centro de administración de Microsoft Endpoint Manager, elija **Administración de inquilinos > Roles > Todos los roles >** active la casilla correspondiente a un rol en la lista > **Duplicar**.

1. En la página **Datos básicos**, escriba un nombre. Asegúrese de usar un nombre único.

1. Todos los permisos y etiquetas de ámbito del rol original estarán ya seleccionados. Posteriormente, puede cambiar el **nombre, la descripción, los permisos y el ámbito (etiquetas)** del rol duplicado.

1. Una vez realizados todos los cambios que quiere, elija Siguiente para ir a la página Revisar y crear. Seleccione **Crear**.

> [!Note]
>Para poder administrar Intune, debe tener asignada una licencia de Intune. Como alternativa, puede permitir que los usuarios sin licencia administren Intune estableciendo **Permitir el acceso a los administradores sin licencia** en **Sí**.

## <a name="how-to-assign-a-role"></a>Asignación de un rol

Puede asignar un rol integrado o personalizado a un usuario de Intune. Para crear, editar o asignar roles, la cuenta debe tener uno de los siguientes permisos en Azure AD:

- **Administrador global**
- **Administrador de servicios de Intune** (también conocido como **administrador de Intune**, pero no debe confundirse con el rol de **administrador de roles de Intune** integrado).

1. En el Centro de administración de Microsoft Endpoint Manager, elija **Administración de inquilinos > Roles > Todos los roles**.

1. En la hoja **roles de Endpoint Manager- Todos los roles**, elija el rol integrado que desea asignar > Asignaciones > + Asignar.

1. En la página **Datos básicos**, escriba un nombre de asignación y una descripción de asignación opcional y, a continuación, elija **Siguiente**.

1. En la página **Grupos de administración**, seleccione el grupo que contiene el usuario al que quiere conceder los permisos. Elija **Siguiente**.

1. En la página **Ámbito (grupos),** elija un grupo que contenga los usuarios y dispositivos que el miembro anterior podrá administrar. También tiene la opción de elegir todos los usuarios o todos los dispositivos. Elija **Siguiente**.

> [!Note]
> **Todos los usuarios** y **Todos los dispositivos** son **grupos virtuales de Intune** y no grupos de seguridad de Azure Active Directory (Azure AD). Como resultado, para fines de asignación de **ámbitos (grupos)**, no puede usarlos como elementos primarios de los grupos de seguridad de Azure AD. Si necesita tanto **Todos los usuarios** como **Todos los dispositivos**, además de los grupos de seguridad específicos de Azure AD, para la asignación de **ámbitos (grupos)**, debe agregarlos por separado con asignaciones independientes. De lo contrario, incluso si la asignación de ámbitos (grupos) de un rol se establece en **Todos los usuarios**, el administrador de este rol no tendrá acceso a los grupos de usuarios específicos de Azure AD. Se admite el anidamiento en los grupos de seguridad de Azure AD.

6. En la página **Ámbito (etiquetas)**, elija las etiquetas donde se aplicará esta asignación de roles. Elija **Siguiente**.

7. Cuando haya terminado, elija **Crear** en la página **Revisar y crear**. La nueva asignación se muestra en la lista de asignaciones.

> [!Note]
> Cuando se crean grupos de ámbito y se asigna una etiqueta de ámbito, solo se pueden establecer como destino los grupos que aparecen en el ámbito (grupos) de la asignación de roles.

## <a name="delegated-administration-for-microsoft-partners"></a>Administración delegada para Microsoft Partners

Si está trabajando con un asociado de Microsoft, puede asignarles roles de administrador. Por su parte, los partners pueden asignar roles de administrador a los usuarios en sus propias empresas o bien en la suya. Es posible que quiera que lo hagan, por ejemplo, si están configurando y administrando su organización en línea por usted.
  
Un partner puede asignar estos roles: 
  
- Administración completa, que tiene privilegios equivalentes a un administrador global, excepto para administrar la autenticación multifactor a través del Centro de partners.

- Administración limitada, que tiene privilegios equivalentes a los de un administrador del departamento de soporte técnico.

Antes de que el partner pueda asignar estos roles a los usuarios, tendrá que agregar al partner como administrador delegado a su cuenta. Este proceso lo iniciará el partner autorizado. Le enviará un correo electrónico para preguntarle si quiere concederle permiso para actuar como administrador delegado. Para obtener instrucciones, consulte [Autorizar o quitar relaciones de partner](../admin/misc/add-partner.md).
  
## <a name="related-content"></a>Contenido relacionado

[Acerca de los roles de administrador en Microsoft 365](../admin/add-users/about-admin-roles.md) (artículo)\
[Asignar roles de administrador](../admin/add-users/assign-admin-roles.md) (artículo)\
[Informes de actividad del Centro de administración de Microsoft 365](../admin/activity-reports/activity-reports.md) (artículo)
