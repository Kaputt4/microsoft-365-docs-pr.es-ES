---
title: Permisos en el Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
description: Obtenga información sobre la administración de permisos en el Centro de cumplimiento de Microsoft 365.
ms.collection: M365-security-compliance
ms.openlocfilehash: 8eed2bf7fb1bf2861fe3b138933ef5e2314d1325
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203080"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Permisos en el Centro de cumplimiento de Microsoft 365

El Centro de cumplimiento de Microsoft 365 se actualizó recientemente y ahora admite la administración directa de permisos para los usuarios que realizan tareas de cumplimiento en Microsoft 365. Esta actualización significa que Office 365 ya no tendrá que usar el Centro de seguridad & cumplimiento para administrar los permisos de las soluciones de cumplimiento. Con la  nueva página Permisos de la Centro de cumplimiento de Microsoft 365, puede administrar permisos a los usuarios para tareas de cumplimiento en características como administración de dispositivos, prevención de pérdida de datos, exhibición de documentos electrónicos, administración de riesgos insider, retención y muchas otras. Los usuarios solo pueden realizar las tareas de cumplimiento a las que se les conceda acceso explícitamente.

Para ver  la pestaña Permisos en el Centro de cumplimiento de Microsoft 365, los usuarios deben ser administradores globales o deben tener asignado el rol Administración de roles (un rol se asigna solo al grupo de roles Administración *de* la organización).  El *rol Administración de* roles permite a los usuarios ver, crear y modificar grupos de roles.

![Página permisos en Centro de cumplimiento de Microsoft 365.](../media/m365-compliance-center-permissions.png)

Los permisos de la Centro de cumplimiento de Microsoft 365 se basan en el modelo de permisos de control de acceso basado en roles (RBAC). RBAC es el mismo modelo de permisos que usa la mayoría de los servicios de Microsoft 365, por lo que si está familiarizado con la estructura de permisos de estos servicios, la concesión de permisos en el Centro de cumplimiento de Microsoft 365 será familiar. Es importante recordar que los permisos administrados en el Centro de cumplimiento de Microsoft 365 no cubren la administración de todos los permisos necesarios en cada servicio individual. Todavía tendrá que administrar ciertos permisos específicos del servicio en el Centro de administración para el servicio específico. Por ejemplo, si necesita asignar permisos para las directivas de archivado, auditoría y retención de MRM, deberá administrar estos permisos en el Centro de administración de Exchange administración.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relación de los miembros, los roles y los grupos de roles

Un rol concede permisos para realizar un conjunto de tareas; por ejemplo, el rol Administración de casos permite a los usuarios trabajar con casos de exhibición de documentos electrónicos.

Un grupo de roles es un conjunto de roles que permiten a los usuarios realizar su trabajo en las soluciones de cumplimiento del Centro de cumplimiento de Microsoft 365. Por ejemplo, al agregar usuarios al grupo de roles De administración de riesgos de *Insider,* los administradores, analistas, investigadores y auditores designados se configuran para los permisos de administración de riesgos insider necesarios en un solo grupo. El Centro de cumplimiento de Microsoft 365 incluye grupos de roles predeterminados para tareas y funciones para cada solución de cumplimiento a la que deberá asignar personas. Por lo general, se recomienda simplemente agregar usuarios individuales como miembros a los grupos de roles de cumplimiento predeterminados según sea necesario.

![Diagrama que muestra la relación de los grupos de roles con los roles y miembros.](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>Permisos necesarios para usar características en el Centro de cumplimiento de Microsoft 365

Para ver todos los grupos de roles predeterminados que están disponibles en el Centro de cumplimiento de Microsoft 365 y los roles [asignados](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)a los grupos de roles de forma predeterminada, vea permisos en el Centro de seguridad & cumplimiento .

La administración de permisos en el Centro de cumplimiento de Microsoft 365 solo proporciona a los usuarios acceso a las características de cumplimiento que están disponibles en el Centro de cumplimiento de Microsoft 365. Si desea conceder permisos a otras características que no están en el Centro de cumplimiento de Microsoft 365, como las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), deberá usar el Centro de administración de Exchange.

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Roles de Azure en el Centro de cumplimiento de Microsoft 365

Los roles que aparecen en la sección **Roles de Azure AD** de la página Centro de cumplimiento de Microsoft 365 permisos  >   **son** Azure Active Directory roles. Estos roles están diseñados para alinearse con las funciones de trabajo en el grupo de TI de su organización, lo que facilita otorgar a una persona todos los permisos necesarios para realizar su trabajo. Puede ver los usuarios asignados actualmente a cada función seleccionando un rol de administrador y viendo los detalles del panel de funciones. Para administrar miembros de un rol de Azure AD, seleccione Administrar miembros en Azure AD. Esta opción le redirige al Portal de administración de Azure.

|Role|Descripción|
|:---|:----------|
|**Administrador global**|Acceso a todas las características administrativas en todos los servicios de Microsoft 365. Los administradores globales son los únicos que pueden asignar otros roles de administrador. Para más información, consulte [Administrador global / Administrador de empresa](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administrador de datos de cumplimiento**|Realizar un seguimiento de los datos de su organización a través de Microsoft 365, asegurarse de que están protegidos y obtener información sobre los problemas para ayudar a reducir los riesgos. Para obtener más información, consulte [Administrador de datos de cumplimiento](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Administrador de cumplimiento**|Ayudar a que su organización cumpla con los requisitos normativos, administrar casos de eDiscovery y mantener directivas de gobierno de datos en todas las ubicaciones, identidades y aplicaciones de Microsoft 365. Para obtener más información, consulte [Administrador de cumplimiento](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operador de seguridad**|Ver, investigar y responder a las amenazas activas a usuarios, dispositivos y contenido de Microsoft 365. Para obtener más información, vea [Operador de seguridad de seguridad](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Lector de seguridad**|Ver e investigar amenazas activas a usuarios, dispositivos y contenido de Microsoft 365, pero, a diferencia del operador de seguridad, no tienen permisos para responder realizando una acción. Para obtener más información, vea [Lector de seguridad](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Administrador de seguridad**|Controlar la seguridad global de la organización mediante la administración de directivas de seguridad, la revisión de análisis de seguridad y los informes en los productos de Microsoft 365, así como mantenerse al día con el panorama de amenazas. Para obtener más información, vea [Administrador de seguridad](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Lector global**|La versión de solo lectura del rol de **Administrador global**. Ver todas las configuraciones e información administrativa en Microsoft 365. Para más información, vea [Lector global](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Administrador de simulación de ataque**|Crea y administra todos los aspectos de la creación de simulación de ataques, el lanzamiento o la programación de la simulación y la revisión de los resultados de la misma. Para más información, consulte [Administrador de simulación de ataque](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Autor de carga de ataque**|Crea cargas de ataques pero no las inicia ni programa. Para más información, consulte [Autor de carga de ataques](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

## <a name="add-users-to-a-compliance-role-group"></a>Agregar usuarios a un grupo de roles de cumplimiento

Siga estos pasos para agregar usuarios a un grupo de roles de cumplimiento:

1. Inicie sesión en el área de permisos de [la Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/permissions) con credenciales para una cuenta de administrador en su Microsoft 365 organización.
2. En el Centro de cumplimiento de Microsoft 365, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles de cumplimiento en Microsoft 365.
3. Expanda la **sección Centro de cumplimiento** y seleccione **Roles**.
4. En la **página Roles del Centro** de cumplimiento, seleccione un grupo de roles de cumplimiento al que desee agregar usuarios y, a continuación, seleccione Editar grupo **de** roles en el panel de detalles.
5. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.
6. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.
7. Seleccione **Agregar** y, después, **Listo**.
8. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="remove-users-from-a-compliance-role-group"></a>Quitar usuarios de un grupo de roles de cumplimiento

Siga estos pasos para quitar usuarios de un grupo de roles de cumplimiento:

1. Inicie sesión en el área de permisos de [la Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/permissions) con credenciales para una cuenta de administrador en su Microsoft 365 organización.
2. En el Centro de cumplimiento de Microsoft 365, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles de cumplimiento en Microsoft 365.
3. Expanda la sección Centro de cumplimiento y seleccione **Roles**.
4. En la **página Roles del centro** de cumplimiento, seleccione un grupo de roles de cumplimiento del que desea quitar usuarios y, a continuación, seleccione Editar grupo **de** roles en el panel de detalles.
5. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.
6. Seleccione **Quitar** y, a continuación, active la casilla para todos los usuarios que desee quitar del grupo de roles.
7. Seleccione **Quitar** y, a continuación, **Seleccione Listo**.
8. Seleccione **Guardar** para quitar los usuarios del grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="create-a-custom-role-group"></a>Crear un grupo de roles personalizado

Siga estos pasos para crear un grupo de roles personalizado:

1. Inicie sesión [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.
2. En el Centro de cumplimiento de Microsoft 365, vaya a **Permisos**.
3. En la **página Permisos & roles,** seleccione **Centro de cumplimiento > Roles**.
4. En la **página Roles del centro de** cumplimiento, seleccione **Crear**.
5. En la **página Nombre del grupo de** roles, escriba un nombre para el grupo de roles personalizado en el **campo** Nombre. El nombre del grupo de funciones no se puede cambiar después de crear el grupo de funciones. Si es necesario, escriba una descripción para el grupo de roles personalizado en el **campo** Descripción. Seleccione **Siguiente** para continuar.
6. En la **página Elegir roles,** seleccione **Elegir roles**.
7. Seleccione **Agregar** y, a continuación, elija los roles que desea agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar el grupo de roles y, a continuación, seleccione **Listo**.
8. Seleccione **Siguiente** para continuar.
9. En la **página Elegir miembros,** seleccione **Elegir miembros**.
10. Seleccione **Agregar** y, a continuación, elija los miembros que desea agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar los miembros y, a continuación, **seleccione Listo**.
11. Seleccione **Siguiente** para continuar.
12. En la **página Revisar la configuración,** revise los detalles del grupo de roles personalizado. Si necesita editar la información, seleccione **Editar** en la sección correspondiente. Cuando todas las opciones de configuración sean correctas, seleccione  **Crear** grupo de roles para crear el grupo de roles personalizado o cancelar para descartar los cambios y no crear el grupo de funciones personalizado.

## <a name="update-a-custom-role-group"></a>Actualizar un grupo de roles personalizado

Siga estos pasos para actualizar un grupo de roles personalizado:

1. Inicie sesión [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.
2. En el Centro de cumplimiento de Microsoft 365, vaya a **Permisos**.
3. En la **página Permisos & roles,** seleccione **Centro de cumplimiento > Roles**.
4. En la **página Roles del Centro** de cumplimiento y seleccione el grupo de roles que desea actualizar.
5. En el panel de detalles del grupo de roles seleccionado, seleccione **Editar grupo de funciones**.
6. En la **página Editar nombre de grupo de** roles, actualice la descripción del grupo de roles personalizado en el **campo** Descripción. No se puede cambiar el nombre del grupo de roles personalizado.
7. En la **página Elegir roles,** seleccione **Editar** para actualizar los roles asignados a los grupos de roles.
8. Seleccione **Agregar** y, a continuación, elija los roles que desea agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar el grupo de roles y, a continuación, seleccione **Listo**.
9. En la **página Elegir miembros,** seleccione **Editar**.
10. Seleccione **Agregar** y, a continuación, elija los miembros que desea agregar al grupo de roles personalizado. Seleccione **Agregar** para agregar los miembros y, a continuación, **seleccione Listo**.
11. Seleccione **Guardar para** guardar los valores de *Descripción,* *Grupos de roles* y *Miembros* actualizados.
12. En el panel de detalles del grupo de roles seleccionado, seleccione **Cerrar**.

## <a name="delete-a-custom-role-group"></a>Eliminar un grupo de roles personalizado

Siga estos pasos para actualizar un grupo de roles personalizado:

1. Inicie sesión [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.
2. En el Centro de cumplimiento de Microsoft 365, vaya a **Permisos**.
3. En la **página Permisos & roles,** seleccione **Centro de cumplimiento > Roles**.
4. En la **página Roles del Centro** de cumplimiento y seleccione el grupo de roles que desea actualizar.
5. En el panel de detalles del grupo de roles seleccionado, seleccione **Eliminar grupo de roles**.
6. En el **cuadro de diálogo** Advertencia, seleccione **Sí** para eliminar el grupo de roles o **seleccione No** para cancelar el proceso de eliminación.
