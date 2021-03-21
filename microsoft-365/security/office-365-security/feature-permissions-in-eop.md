---
title: Permisos de características en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Obtenga información sobre los permisos necesarios para las tareas en Exchange Online Protection independiente
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 212a109c792522270b7e5000747bec950b7f4fe2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926987"
---
# <a name="permissions-in-standalone-eop"></a>Permisos en EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](exchange-online-protection-overview.md)

La Protección independiente de Exchange Online (EOP) sin buzones de Exchange Online usa el modelo de permisos de control de acceso basado en roles (RBAC) para conceder fácilmente permisos a los administradores. Puede usar las características de permisos en EOP independiente para que la nueva organización se ejecute rápidamente.

Para conceder permisos a los usuarios, vea [Manage admin role groups in EOP](manage-admin-role-group-permissions-in-eop.md).

Para obtener más información acerca de los permisos en Microsoft 365, vea [About admin roles](../../admin/add-users/about-admin-roles.md).

## <a name="role-based-permissions"></a>Permisos basados en roles

Los permisos de administrador que concede a los usuarios se basan en roles de administración. Un rol de administración define los cmdlets que están disponibles para un conjunto de tareas determinadas. Dado que el Centro de administración de Exchange (EAC) y powerShell de EOP independiente usan cmdlets, la concesión de acceso a un cmdlet da al usuario permiso para realizar las tareas relacionadas en el EAC o en PowerShell de EOP independiente. Por ejemplo, el rol Destinatarios de correo define los cmdlets necesarios para modificar los usuarios de correo.

En EOP independiente, los roles administrativos son el único tipo de rol de administración que está disponible (no hay roles de usuario final ni directivas de asignación de roles).

## <a name="role-groups"></a>Grupos de funciones

Para facilitar la asignación de roles a los usuarios, EOP independiente usa grupos de roles. Los roles de administración se asignan a grupos de roles y los miembros del grupo de roles obtienen los permisos asociados a los roles. En otras palabras, los roles de administración no se asignan directamente a los usuarios; están asignados al grupo de roles. Este modelo permite asignar muchos roles a muchos miembros del grupo de roles a la vez. Los miembros del grupo de roles pueden ser usuarios de correo, grupos de seguridad habilitados para correo, usuarios del Centro de administración de Microsoft 365 y otros grupos de roles.

En la figura siguiente se ve la relación entre usuarios, grupos de roles y roles.

![Rol, relación de los miembros y grupo de roles](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

Los grupos de roles disponibles en EOP independiente se describen en la tabla siguiente.

****

|Grupo de funciones|Descripción|Roles predeterminados asignados|
|---|---|---|
|ComplianceManagement|Configure y administre la configuración de cumplimiento dentro de la organización, incluida la prevención de pérdida de datos (DLP) si su suscripción tiene capacidades dlp. <p> Los miembros del [rol Administrador de cumplimiento](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) en Azure AD obtienen automáticamente los permisos de este grupo de roles.|Registros de auditoría <p> Administración de cumplimiento <p> Information Rights Management <p> Administración de retención <p> View-Only de auditoría <p> Configuración con permiso de vista <p> Destinatarios con permiso de vista|
|ContentExplorerContentViewer|No se usa.|Visor de contenido de clasificación de datos|
|ContentExplorerListViewer|No se usa.|Visor de listas de clasificación de datos|
|HelpDesk|Ver y administrar usuarios de correo.|Restablecer contraseña <p> Opciones de usuario <p> Destinatarios con permiso de vista|
|HygieneManagement|Administrar características de protección (correo no deseado, antimalware, etc.).|Higiene del transporte <p> Configuración con permiso de vista <p> Destinatarios con permiso de vista|
|MailFlowAdministrator|Ver y administrar los dominios y conectores aceptados|Dominios remotos y aceptados <p> Destinatarios con permiso de vista|
|OrganizationManagement|Acceso de administrador a toda la organización y capacidad para realizar casi cualquier tarea. <p> Los miembros del rol [Administrador global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) en Azure AD obtienen automáticamente los permisos de este grupo de roles. <p> **Importante:** Dado que el grupo de roles OrganizationManagement es un rol eficaz, solo los usuarios que realizan tareas administrativas de nivel organizativo deben ser miembros de este grupo de roles.|AntiMalware <p> AntiSpam <p> Registros de auditoría <p> Administrador de cumplimiento <p> Grupos de distribución dinámicos <p> Information Rights Management <p> Creación de destinatario de correo <p> Destinatarios de correo <p> Seguimiento de mensajes <p> Migración <p> Acceso de cliente de la organización <p> Configuración de la organización <p> Configuración de transporte de la organización <p> Cuarentena <p> Directivas de destinatarios <p> Dominios remotos y aceptados <p> Restablecer contraseña <p> Administración de retención <p> Administración de roles <p> Administrador de seguridad <p> Creación y pertenencia a grupos de seguridad <p> Lector de seguridad <p> Administrador de etiquetas de confidencialidad <p> Supervisión <p> Higiene del transporte <p> Reglas de transporte <p> Opciones de usuario <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only de auditoría <p> Configuración con permiso de vista <p> View-Only cuarentena <p> Destinatarios con permiso de vista <p> View-Only de amenazas|
|QuarantineAdministrator|Administrar mensajes en cuarentena para todos los destinatarios.|Cuarentena|
|RecipientManagement|Cree, administre y quite objetos de destinatario en la organización.|Grupos de distribución dinámicos <p> Creación de destinatario de correo <p> Destinatarios de correo <p> Seguimiento de mensajes <p> Migración <p> Directivas de destinatarios <p> Restablecer contraseña|
|RecordsManagement|Configure características de cumplimiento, como etiquetas de directiva de retención, clasificaciones de mensajes y reglas de flujo de correo (también conocidas como reglas de transporte).|Seguimiento de mensajes <p> Administración de retención <p> Reglas de transporte|
|SecurityAdministrator|Configure todos los aspectos de protección de la organización (antispam, antimalware, anti suplantación, cuarentena, etc.). <p> Los miembros del [rol Administrador de](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) seguridad en Azure AD obtienen automáticamente los permisos de este grupo de roles.|AntiMalware <p> AntiSpam <p> Registros de auditoría <p> Cuarentena <p> Administrador de seguridad <p> Administrador de etiquetas de confidencialidad <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only de auditoría <p> View-Only cuarentena <p> View-Only de amenazas|
|SecurityReader|Acceso de solo vista a todos los aspectos de la protección de la organización (antispam, antimalware, anti suplantación, cuarentena, etc.). <p> Los miembros del [rol Lector de](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) seguridad en Azure AD obtienen automáticamente los permisos de este grupo de roles.|Lector de seguridad <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only cuarentena <p> View-Only de amenazas|
|TenantAdmins|La pertenencia a este grupo de roles se sincroniza en todos los servicios y se administra de forma centralizada. De forma predeterminada, este grupo de roles no tiene asignado ningún rol. Sin embargo, será miembro del grupo de roles Administración de la organización y heredará esos permisos.|none|
|ViewOnlyOrganizationManagement|Ver objetos de destinatario, protección y configuración y sus propiedades en la organización.|Administrador de cumplimiento <p> Administrador de seguridad <p> Lector de seguridad <p> Administrador de etiquetas de confidencialidad <p> Configuración con permiso de vista <p> Destinatarios con permiso de vista|
|

Si trabaja en una organización pequeña que solo tiene unos pocos administradores, es posible que deba agregar esos usuarios solo al grupo de roles Administración de la organización y es posible que nunca necesite usar los otros grupos de roles. Si trabaja en una organización más grande, es posible que tenga administradores que realicen tareas específicas, como la configuración de destinatarios. En esos casos, puede agregar un administrador al grupo de roles Administración de destinatarios y otro administrador al grupo de roles Administración de la organización. A continuación, estos administradores pueden administrar sus áreas específicas, pero no tendrán permisos para administrar áreas de las que no son responsables.

Si los grupos de roles integrados de Exchange Online no coinciden con la función de trabajo de los administradores, puede crear grupos y agregarles roles. Para obtener más información, vea [Manage role groups in standalone EOP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Funciones

Los roles integrados que están disponibles en EOP independiente se describen en la tabla siguiente.

****

|Rol**|Descripción|Asignaciones predeterminadas de grupos de roles|
|---|---|---|
|AntiMalware|Ver y modificar la configuración y los informes de las características antimalware.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|Ver y modificar la configuración y los informes de las características contra correo no deseado.|OrganizationManagement <p> SecurityAdministrator|
|Registros de auditoría|Busque en el registro de auditoría de administrador y vea los resultados.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Administrador de cumplimiento<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|Visor de contenido de clasificación de datos<sup>\*</sup>||ContentExplorerContentViewer|
|Visor de listas de clasificación de datos<sup>\*</sup>||
|Grupos de distribución dinámicos|Cree y administre todos los grupos de distribución, grupos de seguridad habilitados para correo y miembros.|OrganizationManagement <p> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|Creación de destinatario de correo|Crear y quitar usuarios de correo.|OrganizationManagement <p> RecipientManagement|
|Destinatarios de correo|Modificar usuarios de correo existentes.|OrganizationManagement <p> RecipientManagement|
|Seguimiento de mensajes<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> Records Management|
|Migración<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|Permite a los usuarios ver sus propios mensajes en cuarentena. <p> Este rol se asigna automáticamente a los usuarios y no se puede asignar manualmente.|none|
|Acceso de cliente de la organización<sup>\*</sup>||OrganizationManagement|
|Configuración de la organización|Ver informes.|OrganizationManagement|
|Configuración de transporte de la organización<sup>\*</sup>||OrganizationManagement|
|Cuarentena|Administrar todos los tipos de mensaje en cuarentena para todos los destinatarios.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|Directivas de destinatarios<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|Dominios remotos y aceptados|Administrar dominios remotos, dominios aceptados y conectores.|MailFlowAdministrator <p> OrganizationManagement|
|Restablecer contraseña<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|Administración de retención<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|Administración de roles|Crear y administrar grupos de roles.|OrganizationManagement|
|Administrador de seguridad|Administrar la configuración y los informes de todas las características de seguridad y protección.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Creación y pertenencia a grupos de seguridad|Crear y administrar grupos de seguridad habilitados para correo.|OrganizationManagement|
|Lector de seguridad|Vea la configuración y los informes de las características de seguridad y protección.|Administración de la organización <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Administrador de etiquetas de confidencialidad<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Supervisión<sup>\*</sup>||OrganizationManagement|
|Higiene del transporte|Administrar características contra malware, contra correo no deseado y contra la suplantación de dominio.|HygieneManagement <p> OrganizationManagement|
|Reglas de transporte|Crear y administrar reglas de flujo de correo (también conocidas como reglas de transporte).|OrganizationManagement <p> RecordsManagement|
|Opciones de usuario|Modificar usuarios de correo existentes.|HelpDesk <p> OrganizationManagement|
|View-Only AntiMalware|Ver la configuración y los informes de las características antimalware.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|Vea la configuración y los informes de las características contra correo no deseado.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only de auditoría|Busque en el registro de auditoría de administrador y vea los resultados.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Configuración con permiso de vista|Ver todas las opciones de organización y flujo de correo (no destinatario) de la organización.|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only cuarentena|Ver todos los mensajes en cuarentena para todos los destinatarios.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|Destinatarios con permiso de vista|Ver las propiedades del destinatario y ejecutar el seguimiento de mensajes.|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only de amenazas<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Aunque este rol está disponible, básicamente no hace nada útil en EOP independiente.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Permisos de Microsoft 365 en EOP independiente

Al crear un usuario en el Centro de administración de Microsoft 365, puede elegir si desea asignar varios roles administrativos, como administrador global, administrador de servicio, administrador de contraseñas, entre otros, al usuario. Algunos roles de Microsoft 365, pero no todos, conceden al usuario permisos administrativos en EOP.

> [!NOTE]
> La cuenta que usó para crear la organización independiente de EOP se asigna automáticamente al rol de administrador global.

En la tabla siguiente se enumeran los roles de Microsoft 365 y los grupos de roles de EOP independientes a los que corresponden. Para obtener más información acerca de estos roles, vea [About admin roles](../../admin/add-users/about-admin-roles.md).

****

|Rol de Microsoft 365|Grupo de roles de EOP|
|---|---|
|Administrador de Exchange|OrganizationManagement|
|Administrador global|OrganizationManagement <p> **Nota:** El rol de administrador global y el grupo de roles OrganizationManagement están unidos mediante un grupo de roles de administrador de empresa especial. El grupo de roles Administrador de empresa se administra internamente y no se puede modificar directamente.|
|Administrador de contraseñas|HelpDesk|
|Lector global|ViewOnlyOrganizationManagement|
|Administrador de seguridad|SecurityAdministrator|
|Lector de seguridad|SecurityReader|
|

Otros roles de Microsoft 365 no tienen un grupo de roles EOP correspondiente y no concederán permisos administrativos en EOP. Para obtener más información acerca de cómo asignar un rol de Microsoft 365 a un usuario, vea [Asignar roles de administrador.](../../admin/add-users/assign-admin-roles.md)

Los usuarios pueden obtener derechos administrativos en EOP sin agregarlos a roles de Microsoft 365. Para ello, agregue al usuario como miembro de un grupo de roles de EOP. El usuario recibirá permisos en EOP, pero no recibirá permisos en otras cargas de trabajo de Microsoft 365.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha copiado correctamente un grupo de roles, siga uno de estos pasos:

- En el EAC, vaya a **Permisos** Roles de administrador y compruebe que el grupo de roles \> aparece (o no aparece). Seleccione el grupo de roles y compruebe la configuración en el panel Detalles o haga clic **en Editar** icono Editar para comprobar ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.

- En Exchange Online PowerShell, reemplace por el nombre del grupo de funciones y ejecute el siguiente comando para comprobar que el grupo de funciones existe (o no existe) y compruebe la \<Role Group Name\> configuración:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```