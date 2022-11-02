---
title: Permisos en el portal de cumplimiento de Microsoft Purview
description: Obtenga información sobre la administración de permisos en el portal de cumplimiento Microsoft Purview.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
ms.custom:
- admindeeplinkCOMPLIANCE
- admindeeplinkEXCHANGE
ms.openlocfilehash: 9e372ce41b3c1e037dfd6b1d740af785cb437ac0
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812369"
---
# <a name="permissions-in-the-microsoft-purview-compliance-portal"></a>Permisos en el portal de cumplimiento de Microsoft Purview

El portal de cumplimiento Microsoft Purview admite la administración directa de permisos para los usuarios que realizan tareas de cumplimiento en Microsoft 365. Esta actualización significa que ya no tendrá que usar el Centro de cumplimiento de Office 365 Security & para administrar los permisos de las soluciones de cumplimiento. Con la nueva página **Permisos** del portal de cumplimiento, puede administrar permisos a los usuarios para tareas de cumplimiento en características como administración de dispositivos, Prevención de pérdida de datos de Microsoft Purview, eDiscovery, administración de riesgos internos, retención y muchas otras. Los usuarios solo pueden realizar las tareas de cumplimiento a las que les conceda acceso explícitamente.

Para ver la pestaña **Permisos** en el portal de cumplimiento, los usuarios deben ser administradores globales o tener asignado el rol *Administración de* roles (un rol solo se asigna al grupo de roles *Administración de la organización* ). El rol *Administración de* roles permite a los usuarios ver, crear y modificar grupos de roles.

![Página Permisos en portal de cumplimiento Microsoft Purview.](../media/m365-compliance-center-permissions.png)

Los permisos del portal de cumplimiento se basan en el modelo de permisos de control de acceso basado en rol (RBAC). RBAC es el mismo modelo de permisos que usan la mayoría de los servicios de Microsoft 365, por lo que si está familiarizado con la estructura de permisos de estos servicios, le resultará familiar conceder permisos en el portal de cumplimiento. Es importante recordar que los permisos administrados en el portal de cumplimiento no cubren la administración de todos los permisos necesarios en cada servicio individual. Seguirá teniendo que administrar determinados permisos específicos del servicio en el centro de administración para el servicio específico. Por ejemplo, si necesita asignar permisos para el archivado, la auditoría y las directivas de retención de MRM, tendrá que administrar estos permisos en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="relationship-of-members-roles-and-role-groups"></a>Relación de los miembros, los roles y los grupos de roles

Un rol concede permisos para realizar un conjunto de tareas; por ejemplo, el rol Administración de casos permite a los usuarios trabajar con casos de eDiscovery.

Un grupo de roles es un conjunto de roles que permiten a los usuarios realizar sus trabajos en las soluciones de cumplimiento del portal de cumplimiento. Por ejemplo, al agregar usuarios al grupo de roles *Insider Risk Management* , los administradores, analistas, investigadores y auditores designados se configuran para los permisos de administración de riesgos internos necesarios en un solo grupo. El portal de cumplimiento incluye grupos de roles predeterminados para tareas y funciones para cada solución de cumplimiento a la que tendrá que asignar personas. Por lo general, se recomienda simplemente agregar usuarios individuales como miembros a los grupos de roles de cumplimiento predeterminados según sea necesario.

![Diagrama que muestra la relación de los grupos de roles con los roles y miembros.](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-compliance-portal"></a>Permisos necesarios para usar características en el portal de cumplimiento

Para ver todos los grupos de roles predeterminados que están disponibles en el portal de cumplimiento y los roles asignados a los grupos de roles de forma predeterminada, consulte [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

La administración de permisos en el portal de cumplimiento solo proporciona a los usuarios acceso a las características de cumplimiento que están disponibles en el portal de cumplimiento. Si desea conceder permisos a otras características que no están en el portal de cumplimiento, como las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), deberá usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

## <a name="azure-roles-in-the-compliance-portal"></a>Roles de Azure en el portal de cumplimiento

Los roles que aparecen en la sección **Roles** de **Azure AD** >  de la página **Permisos** del portal de cumplimiento son roles de Azure Active Directory. Estos roles están diseñados para alinearse con las funciones de trabajo en el grupo de TI de su organización, lo que facilita otorgar a una persona todos los permisos necesarios para realizar su trabajo. Puede ver los usuarios asignados actualmente a cada rol seleccionando un rol de Administración y viendo los detalles del panel de roles. Para administrar miembros de un rol de Azure AD, seleccione Administrar miembros en Azure AD. Esta opción le redirige al portal de administración de Azure.

|Role|Descripción|
|:---|:----------|
|**Administrador global**|Acceso a todas las características administrativas en todos los servicios de Microsoft 365. Los administradores globales son los únicos que pueden asignar otros roles de administrador. Para más información, consulte [Administrador global / Administrador de empresa](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administrador de datos de cumplimiento**|Keep track of your organization's data across Microsoft 365, make sure it's protected, and get insights into any issues to help mitigate risks. For more information, see [Compliance Data Administrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Administrador de cumplimiento**|Help your organization stay compliant with any regulatory requirements, manage eDiscovery cases, and maintain data governance policies across Microsoft 365 locations, identities, and apps. For more information, see [Compliance Administrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operador de seguridad**|Ver, investigar y responder a las amenazas activas a usuarios, dispositivos y contenido de Microsoft 365. Para obtener más información, vea [Operador de seguridad de seguridad](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Lector de seguridad**|View and investigate active threats to your Microsoft 365 users, devices, and content, but (unlike the Security operator) they do not have permissions to respond by taking action. For more information, see [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Administrador de seguridad**|Control your organization's overall security by managing security policies, reviewing security analytics and reports across Microsoft 365 products, and staying up-to-speed on the threat landscape. For more information, see [Security Administrator](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Lector global**|La versión de solo lectura del rol de **Administrador global**. Ver todas las configuraciones e información administrativa en Microsoft 365. Para más información, vea [Lector global](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Administrador de simulación de ataque**|Create and manage all aspects of attack simulation creation, launch/scheduling of a simulation, and the review of simulation results. For more information, see [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Autor de carga de ataque**|Crea cargas de ataques pero no las inicia ni programa. Para más información, consulte [Autor de carga de ataques](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

## <a name="add-users-to-a-compliance-role-group"></a>Agregar usuarios a un grupo de roles de cumplimiento

Complete los pasos siguientes para agregar usuarios a un grupo de roles de cumplimiento:

1. Inicie sesión en el área de permisos del portal de cumplimiento con las credenciales de una cuenta de administrador de su organización de Microsoft 365 y vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a> para seleccionar el vínculo para ver y administrar roles de cumplimiento en Microsoft 365.
1. Expanda la sección **Centro de cumplimiento** y seleccione **Roles**.
1. En la página **Roles del Centro de cumplimiento** , seleccione un grupo de roles de cumplimiento al que desea agregar usuarios y, a continuación, seleccione **Editar grupo de roles** en el panel de detalles.
1. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.
1. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que quiera agregar al grupo de roles.
1. Seleccione **Agregar** y, después, **Listo**.
1. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="remove-users-from-a-compliance-role-group"></a>Eliminación de usuarios de un grupo de roles de cumplimiento

Complete los pasos siguientes para quitar usuarios de un grupo de roles de cumplimiento:

1. Inicie sesión en el área de permisos del portal de cumplimiento con las credenciales de una cuenta de administrador de su organización de Microsoft 365 y vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a> para seleccionar el vínculo para ver y administrar roles de cumplimiento en Microsoft 365.
1. Expanda la sección Centro de cumplimiento y seleccione **Roles**.
1. En la página **Roles del Centro de cumplimiento** , seleccione un grupo de roles de cumplimiento del que desea quitar usuarios y, a continuación, seleccione **Editar grupo de roles** en el panel de detalles.
1. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.
1. Seleccione **Quitar** y, a continuación, active la casilla para todos los usuarios que quiera quitar del grupo de roles.
1. Seleccione **Quitar** y, a continuación, seleccione **Listo**.
1. Seleccione **Guardar** para quitar los usuarios del grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="create-a-custom-role-group"></a>Creación de un grupo de roles personalizado

Complete los pasos siguientes para crear un grupo de roles personalizado:

1. Inicie sesión en el área de permisos del portal de cumplimiento con las credenciales de una cuenta de administrador de la organización de Microsoft 365 y vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a>.
1. En la página **Permisos & roles** , seleccione **Centro de cumplimiento > Roles**.
1. En la página **Roles del Centro de cumplimiento** , seleccione **Crear**.
1. En la página **Nombre del grupo de roles** , escriba un nombre para el grupo de roles personalizado en el campo **Nombre** . El nombre del grupo de roles no se puede cambiar después de crear el grupo de roles. Si es necesario, escriba una descripción para el grupo de roles personalizado en el campo **Descripción** . Seleccione **Siguiente** para continuar.
1. En la página **Elegir roles** , seleccione **Elegir roles**.
1. Seleccione **Agregar** y, a continuación, elija los roles que se van a agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar el grupo de roles y, a continuación, seleccione **Listo**.
1. Seleccione **Siguiente** para continuar.
1. En la página **Elegir miembros** , seleccione **Elegir miembros**.
1. Seleccione **Agregar** y, a continuación, elija los miembros que se van a agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar los miembros y, a continuación, seleccione **Listo**.
1. Seleccione **Siguiente** para continuar.
1. En la página **Revisar la configuración** , revise los detalles del grupo de roles personalizado. Si necesita editar la información, seleccione **Editar** en la sección correspondiente. Cuando toda la configuración sea correcta, seleccione **Crear grupo** de roles para crear el grupo de roles personalizado o seleccione **Cancelar** para descartar los cambios y no crear el grupo de roles personalizado.

## <a name="update-a-custom-role-group"></a>Actualización de un grupo de roles personalizado

Complete los pasos siguientes para actualizar un grupo de roles personalizado:

1. Inicie sesión en el área de permisos del portal de cumplimiento con las credenciales de una cuenta de administrador de la organización de Microsoft 365 y vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a>.
1. En la página **Permisos & roles** , seleccione **Centro de cumplimiento > Roles**.
1. En la página **Roles del Centro de cumplimiento** y seleccione el grupo de roles que se va a actualizar.
1. En el panel de detalles del grupo de roles seleccionado, seleccione **Editar grupo de roles**.
1. En la página **Editar nombre de grupo de roles** , actualice la descripción del grupo de roles personalizado en el campo **Descripción** . No se puede cambiar el nombre del grupo de roles personalizado.
1. En la página **Elegir roles** , seleccione **Editar** para actualizar los roles asignados a los grupos de roles.
1. Seleccione **Agregar** y, a continuación, elija los roles que se van a agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar el grupo de roles y, a continuación, seleccione **Listo**.
1. En la página **Elegir miembros** , seleccione **Editar**.
1. Seleccione **Agregar** y, a continuación, elija los miembros que se van a agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar los miembros y, a continuación, seleccione **Listo**.
1. Seleccione **Guardar** para guardar los valores *de Descripción*, *Grupos de roles* y *Miembros actualizados* .
1. En el panel de detalles del grupo de roles seleccionado, seleccione **Cerrar**.

## <a name="delete-a-custom-role-group"></a>Eliminación de un grupo de roles personalizado

Complete los pasos siguientes para actualizar un grupo de roles personalizado:

1. Inicie sesión en el área de permisos del portal de cumplimiento con las credenciales de una cuenta de administrador de la organización de Microsoft 365 y vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a>.
1. En la página **Permisos & roles** , seleccione **Centro de cumplimiento > Roles**.
1. En la página **Roles del Centro de cumplimiento** y seleccione el grupo de roles que se va a actualizar.
1. En el panel de detalles del grupo de roles seleccionado, seleccione **Eliminar grupo de roles**.
1. En el cuadro de diálogo **Advertencia** , seleccione **Sí** para eliminar el grupo de roles o seleccione **No** para cancelar el proceso de eliminación.
