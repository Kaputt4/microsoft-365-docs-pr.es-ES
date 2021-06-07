---
title: Permisos en el centro de Microsoft 365 cumplimiento
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Obtenga información sobre la administración de permisos en el Microsoft 365 de cumplimiento.
ms.collection: M365-security-compliance
ms.openlocfilehash: 72575fce5f7d43354715c77016a8f444e539887f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772544"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Permisos en el centro de Microsoft 365 cumplimiento

El Microsoft 365 de cumplimiento se ha actualizado recientemente y ahora admite la administración directa de permisos para los usuarios que realizan tareas de cumplimiento en Microsoft 365. Esta actualización significa que Office 365 ya no tendrá que usar el Centro de seguridad & cumplimiento para administrar los permisos de las soluciones de cumplimiento. Con la nueva página Permisos en el centro de cumplimiento de Microsoft 365, puede administrar permisos a los usuarios para tareas de cumplimiento en características como administración de **dispositivos,** prevención de pérdida de datos, exhibición de documentos electrónicos, administración de riesgos insider, retención y muchas otras. Los usuarios solo pueden realizar las tareas de cumplimiento a las que se les conceda acceso explícitamente.

Para ver la pestaña Permisos en el centro de cumplimiento de Microsoft 365, los  usuarios deben ser administradores globales  o deben tener asignado el rol administración de roles (un rol se asigna solo al grupo de roles Administración de la organización).  El *rol Administración de* roles permite a los usuarios ver, crear y modificar grupos de roles.

![Página permisos en el centro Microsoft 365 cumplimiento](../media/m365-compliance-center-permissions.png)

Los permisos del centro Microsoft 365 cumplimiento se basan en el modelo de permisos de control de acceso basado en roles (RBAC). RBAC es el mismo modelo de permisos que usa la mayoría de los servicios de Microsoft 365, por lo que si está familiarizado con la estructura de permisos de estos servicios, la concesión de permisos en el centro de cumplimiento de Microsoft 365 será familiar. Es importante recordar que los permisos administrados en el centro de cumplimiento de Microsoft 365 no cubren la administración de todos los permisos necesarios en cada servicio individual. Todavía tendrá que administrar ciertos permisos específicos del servicio en el Centro de administración para el servicio específico. Por ejemplo, si necesita asignar permisos para las directivas de archivado, auditoría y retención, deberá administrar estos permisos en el Centro de administración de Exchange administración.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relación de los miembros, los roles y los grupos de roles

Un rol concede permisos para realizar un conjunto de tareas; por ejemplo, el rol Administración de casos permite a los usuarios trabajar con casos de exhibición de documentos electrónicos.

Un grupo de roles es un conjunto de roles que permiten a los usuarios realizar su trabajo en las soluciones de cumplimiento del centro Microsoft 365 cumplimiento. Por ejemplo, al agregar usuarios al grupo de roles De administración de riesgos de *Insider,* los administradores, analistas, investigadores y auditores designados se configuran para los permisos de administración de riesgos insider necesarios en un solo grupo. El Microsoft 365 de cumplimiento incluye grupos de roles predeterminados para tareas y funciones para cada solución de cumplimiento a la que necesite asignar personas. Por lo general, se recomienda simplemente agregar usuarios individuales como miembros a los grupos de roles de cumplimiento predeterminados según sea necesario.

![Diagrama que muestra la relación de los grupos de roles con los roles y los miembros](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>Permisos necesarios para usar características en el centro de Microsoft 365 cumplimiento

Para ver todos los grupos de roles predeterminados que están disponibles en el centro de cumplimiento de Microsoft 365 y los roles que se asignan a los grupos de roles de forma predeterminada, vea permisos en el Centro de seguridad [& cumplimiento](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

La administración de permisos en el Microsoft 365 de cumplimiento solo proporciona a los usuarios acceso a las características de cumplimiento que están disponibles en el centro Microsoft 365 cumplimiento. Si desea conceder permisos a otras características que no están en el centro de cumplimiento de Microsoft 365, como las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), deberá usar el Centro de administración de Exchange.

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Roles de Azure en el centro Microsoft 365 cumplimiento

Los roles que aparecen en la sección **Roles de Azure AD** de la Microsoft 365 de permisos del centro de cumplimiento son Azure Active Directory  >   roles.  Estos roles están diseñados para alinearse con las funciones de trabajo en el grupo de TI de su organización, lo que facilita otorgar a una persona todos los permisos necesarios para realizar su trabajo. Puede ver los usuarios asignados actualmente a cada función seleccionando un rol de administrador y viendo los detalles del panel de funciones. Para administrar miembros de un rol de Azure AD, seleccione Administrar miembros en Azure AD. Esta opción le redirige al Portal de administración de Azure.

|Función|Descripción|
|:---|:----------|
|**Administrador global**|Acceso a todas las características administrativas en todos los servicios de Microsoft 365. Los administradores globales son los únicos que pueden asignar otros roles de administrador. Para más información, consulte [Administrador global / Administrador de empresa](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administrador de datos de cumplimiento**|Realizar un seguimiento de los datos de su organización a través de Microsoft 365, asegurarse de que están protegidos y obtener información sobre los problemas para ayudar a reducir los riesgos. Para obtener más información, consulte [Administrador de datos de cumplimiento](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Administrador de cumplimiento**|Ayudar a que su organización cumpla con los requisitos normativos, administrar casos de eDiscovery y mantener directivas de gobierno de datos en todas las ubicaciones, identidades y aplicaciones de Microsoft 365. Para obtener más información, consulte [Administrador de cumplimiento](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operador de seguridad**|Ver, investigar y responder a las amenazas activas a usuarios, dispositivos y contenido de Microsoft 365. Para obtener más información, vea [Operador de seguridad de seguridad](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Lector de seguridad**|Ver e investigar amenazas activas a usuarios, dispositivos y contenido de Microsoft 365, pero, a diferencia del operador de seguridad, no tienen permisos para responder realizando una acción. Para obtener más información, vea [Lector de seguridad](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Administrador de seguridad**|Controlar la seguridad global de la organización mediante la administración de directivas de seguridad, la revisión de análisis de seguridad y los informes en los productos de Microsoft 365, así como mantenerse al día con el panorama de amenazas. Para obtener más información, vea [Administrador de seguridad](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Lector global**|La versión de solo lectura del rol de **Administrador global**. Ver todas las configuraciones e información administrativa en Microsoft 365. Para más información, vea [Lector global](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Administrador de simulación de ataques**|Cree y administre todos los aspectos de la creación de simulación de ataque, el inicio/programación de una simulación y la revisión de los resultados de la simulación. Para obtener más información, vea [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Autor de carga de ataques**|Crea cargas de ataque pero no las inicias ni programas. Para obtener más información, vea [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

## <a name="add-users-to-a-compliance-role-group"></a>Agregar usuarios a un grupo de roles de cumplimiento

Siga estos pasos para agregar usuarios a un grupo de roles de cumplimiento:

1. Inicie sesión en el área de permisos del centro de [Microsoft 365 de cumplimiento](https://compliance.microsoft.com/permissions) con credenciales para una cuenta de administrador de su Microsoft 365 organización.
2. En el centro Microsoft 365 cumplimiento, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles de cumplimiento en Microsoft 365.
3. Expanda la **sección Centro de cumplimiento** y seleccione **Roles**.
4. En la **página Roles del Centro** de cumplimiento, seleccione un grupo de roles de cumplimiento al que desee agregar usuarios y, a continuación, seleccione Editar grupo **de** roles en el panel de detalles.
5. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.
6. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.
7. Seleccione **Agregar** y, después, **Listo**.
8. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="remove-users-from-a-compliance-role-group"></a>Quitar usuarios de un grupo de roles de cumplimiento

Siga estos pasos para quitar usuarios de un grupo de roles de cumplimiento:

1. Inicie sesión en el área de permisos del centro de [Microsoft 365 de cumplimiento](https://compliance.microsoft.com/permissions) con credenciales para una cuenta de administrador de su Microsoft 365 organización.
2. En el centro Microsoft 365 cumplimiento, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles de cumplimiento en Microsoft 365.
3. Expanda la sección Centro de cumplimiento y seleccione **Roles**.
4. En la **página Roles del centro** de cumplimiento, seleccione un grupo de roles de cumplimiento del que desea quitar usuarios y, a continuación, seleccione Editar grupo **de** roles en el panel de detalles.
5. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.
6. Seleccione **Quitar** y, a continuación, active la casilla para todos los usuarios que desee quitar del grupo de roles.
7. Seleccione **Quitar** y, a continuación, **Seleccione Listo**.
8. Seleccione **Guardar** para quitar los usuarios del grupo de roles. Seleccione **Cerrar** para completar los pasos.
