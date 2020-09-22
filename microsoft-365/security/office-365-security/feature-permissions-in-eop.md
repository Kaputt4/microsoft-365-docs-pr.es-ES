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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Obtenga información sobre el permiso necesario para las tareas de la protección independiente de Exchange Online
ms.openlocfilehash: ae43dc2223b17d3b73f9b76fa6bde8fb9cb95e77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202872"
---
# <a name="permissions-in-standalone-eop"></a>Permisos en EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Independiente de Exchange Online Protection (EOP) sin buzones de correo de Exchange online usa el modelo de permisos de control de acceso basado en roles (RBAC) para conceder permisos fácilmente a los administradores. Puede usar las características de permisos en EOP independiente para poner en marcha rápidamente su nueva organización.

Para conceder permisos a los usuarios, vea [administrar grupos de roles de administración en EOP](manage-admin-role-group-permissions-in-eop.md).

Para obtener más información acerca de los permisos en Microsoft 365, consulte [acerca de los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="role-based-permissions"></a>Permisos basados en roles

Los permisos de administrador que se conceden a los usuarios se basan en roles de administración. Un rol de administración define los cmdlets que están disponibles para un conjunto de tareas determinadas. Como el centro de administración de Exchange (EAC) y PowerShell independiente de EOP usan los cmdlets, conceder acceso a un cmdlet concede al usuario permiso para realizar las tareas relacionadas en el EAC o en PowerShell independiente de EOP. Por ejemplo, la función destinatarios de correo define los cmdlets necesarios para modificar usuarios de correo.

En EOP independiente, los roles administrativos son el único tipo de rol de administración que está disponible (no hay roles de usuario final ni directivas de asignación de roles).

## <a name="role-groups"></a>Grupos de funciones

Para que sea más fácil asignar roles a los usuarios, EOP independiente usa grupos de roles. Los roles de administración se asignan a grupos de roles y los miembros del grupo de roles obtienen los permisos asociados con los roles. Es decir, los roles de administración no se asignan directamente a los usuarios; están asignados al grupo de roles. Este modelo le permite asignar muchas funciones a varios miembros del grupo de roles a la vez. Los miembros del grupo de roles pueden ser usuarios de correo, grupos de seguridad habilitados para correo, usuarios del centro de administración de Microsoft 365 y otros grupos de roles.

En la figura siguiente se ve la relación entre usuarios, grupos de roles y roles.

![Rol, relación de los miembros y grupo de roles](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

En la tabla siguiente se describen los grupos de funciones disponibles en EOP independiente.

****

|Grupo de funciones|Descripción|Roles predeterminados asignados|
|---|---|---|
|ComplianceManagement|Configure y administre la configuración de cumplimiento dentro de la organización, incluida la prevención de pérdida de datos (DLP) si la suscripción tiene capacidades de DLP. <br/><br/> Los miembros del rol de [Administrador de cumplimiento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) en Azure ad obtienen automáticamente los permisos de este grupo de roles.|Registros de auditoría <br/><br/> Administración de cumplimiento <br/><br/> Information Rights Management <br/><br/> Administración de retención <br/><br/> Registros de auditoría de solo vista <br/><br/> Configuración con permiso de vista <br/><br/> Destinatarios con permiso de vista|
|ContentExplorerContentViewer|No se usa.|Visor de contenido de clasificación de datos|
|ContentExplorerListViewer|No se usa.|Visor de lista de clasificación de datos|
|Escritorio|Ver y administrar usuarios de correo.|Restablecer contraseña <br/><br/> Opciones de usuario <br/><br/> Destinatarios con permiso de vista|
|HygieneManagement|Administrar las características de protección (contra correo no deseado, anti-malware, etc.).|Higiene del transporte <br/><br/> Configuración con permiso de vista <br/><br/> Destinatarios con permiso de vista|
|MailFlowAdministrator|Ver y administrar los dominios y conectores aceptados|Dominios remotos y aceptados <br/><br/> Destinatarios con permiso de vista|
|OrganizationManagement|Acceso de administrador a toda la organización y la capacidad de realizar casi cualquier tarea. <br/><br/> Los miembros del rol de [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) de Azure ad obtienen automáticamente los permisos de este grupo de roles. <br/><br/> **Importante**: dado que el grupo de roles OrganizationManagement es un rol eficaz, solo los usuarios que realicen tareas administrativas de nivel organizativa deben ser miembros de este grupo de roles.|AntiMalware <br/><br/> Anti <br/><br/> Registros de auditoría <br/><br/> Administrador de cumplimiento <br/><br/> Grupos de distribución dinámicos <br/><br/> Information Rights Management <br/><br/> Creación de destinatario de correo <br/><br/> Destinatarios de correo <br/><br/> Seguimiento de mensajes <br/><br/> Migración <br/><br/> Acceso de clientes de la organización <br/><br/> Configuración de la organización <br/><br/> Configuración de transporte de la organización <br/><br/> Quarantine <br/><br/> Directivas de destinatarios <br/><br/> Dominios remotos y aceptados <br/><br/> Restablecer contraseña <br/><br/> Administración de retención <br/><br/> Administración de funciones <br/><br/> Administrador de seguridad <br/><br/> Creación y pertenencia a grupos de seguridad <br/><br/> Lector de seguridad <br/><br/> Administrador de la etiqueta de confidencialidad <br/><br/> Supervisión <br/><br/> Higiene del transporte <br/><br/> Reglas de transporte <br/><br/> Opciones de usuario <br/><br/> Antimalware solo de vista <br/><br/> Correo no deseado de solo vista <br/><br/> Registros de auditoría de solo vista <br/><br/> Configuración con permiso de vista <br/><br/> Cuarentena de solo vista <br/><br/> Destinatarios con permiso de vista <br/><br/> Inteligencia sobre amenazas de solo vista|
|QuarantineAdministrator|Administrar los mensajes en cuarentena para todos los destinatarios.|Quarantine|
|RecipientManagement|Crear, administrar y quitar objetos de destinatarios en la organización.|Grupos de distribución dinámicos <br/><br/> Creación de destinatario de correo <br/><br/> Destinatarios de correo <br/><br/> Seguimiento de mensajes <br/><br/> Migración <br/><br/> Directivas de destinatarios <br/><br/> Restablecer contraseña|
|RecordsManagement|Configure las características de cumplimiento, como las etiquetas de directiva de retención, las clasificaciones de mensajes y las reglas de flujo de correo (también conocidas como reglas de transporte).|Seguimiento de mensajes <br/><br/> Administración de retención <br/><br/> Reglas de transporte|
|SecurityAdministrator|Configure todos los aspectos de la protección de la organización (contra correo electrónico no deseado, antimalware, contra la suplantación de identidad, cuarentena, etc.). <br/><br/> Los miembros del rol de [Administrador de seguridad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) en Azure ad obtienen automáticamente los permisos de este grupo de roles.|AntiMalware <br/><br/> Anti <br/><br/> Registros de auditoría <br/><br/> Quarantine <br/><br/> Administrador de seguridad <br/><br/> Administrador de la etiqueta de confidencialidad <br/><br/> Antimalware solo de vista <br/><br/> Correo no deseado de solo vista <br/><br/> Registros de auditoría de solo vista <br/><br/> Cuarentena de solo vista <br/><br/> Inteligencia sobre amenazas de solo vista|
|SecurityReader|Acceso de solo lectura a todos los aspectos de la protección de la organización (contra correo electrónico no deseado, antimalware, contra la suplantación de identidad, cuarentena, etc.). <br/><br/> Los miembros del rol de [lector de seguridad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) en Azure ad obtienen automáticamente los permisos de este grupo de roles.|Lector de seguridad <br/><br/> Antimalware solo de vista <br/><br/> Correo no deseado de solo vista <br/><br/> Cuarentena de solo vista <br/><br/> Inteligencia sobre amenazas de solo vista|
|TenantAdmins|La pertenencia a este grupo de roles se sincroniza entre los servicios y se administra de forma centralizada. De forma predeterminada, este grupo de roles no tiene asignado ningún rol. Sin embargo, será miembro del grupo de roles de administración de la organización y heredará dichos permisos.|ninguno|
|ViewOnlyOrganizationManagement|Ver los objetos de destinatarios, de protección y de configuración, así como sus propiedades en la organización.|Administrador de cumplimiento <br/><br/> Administrador de seguridad <br/><br/> Lector de seguridad <br/><br/> Administrador de la etiqueta de confidencialidad <br/><br/> Configuración con permiso de vista <br/><br/> Destinatarios con permiso de vista|
|

Si trabaja en una organización pequeña que tiene solo unos pocos administradores, es posible que necesite agregar esos usuarios al grupo de roles de administración de la organización únicamente y que nunca necesite usar los otros grupos de roles. Si trabaja en una organización de mayor tamaño, es posible que tenga administradores que realicen tareas específicas, como la configuración de destinatarios. En esos casos, puede Agregar un administrador al grupo de roles de administración de destinatarios y otro administrador al grupo de roles de administración de la organización. A continuación, estos administradores pueden administrar áreas específicas, pero no tienen permisos para administrar áreas de las que no son responsables.

Si los grupos de roles integrados de Exchange Online no coinciden con la función de trabajo de los administradores, puede crear grupos y agregarles roles. Para obtener más información, consulte [administrar grupos de roles en EOP independiente](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Roles

En la tabla siguiente se describen los roles integrados que están disponibles en EOP independiente.

****

|Función * *|Descripción|Asignaciones de grupo de roles predeterminadas|
|---|---|---|
|AntiMalware|Permite ver y modificar la configuración y los informes de las características antimalware.|OrganizationManagement <br/><br/> SecurityAdministrator|
|Anti|Permite ver y modificar la configuración y los informes de las características contra correo no deseado.|OrganizationManagement <br/><br/> SecurityAdministrator|
|Registros de auditoría|Busque en el registro de auditoría de administrador y vea los resultados.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|Administrador de cumplimiento<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Visor de contenido de clasificación de datos<sup>\*</sup>||ContentExplorerContentViewer|
|Visor de lista de clasificación de datos<sup>\*</sup>||
|Grupos de distribución dinámicos|Cree y administre todos los grupos de distribución, los grupos de seguridad habilitados para correo y los miembros.|OrganizationManagement <br/><br/> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement|
|Creación de destinatario de correo|Crear y quitar usuarios de correo.|OrganizationManagement <br/><br/> RecipientManagement|
|Destinatarios de correo|Modificar usuarios de correo existentes.|OrganizationManagement <br/><br/> RecipientManagement|
|Seguimiento de mensajes<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement <br/><br/> Records Management|
|Migraciones<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|MyBaseOptions|Permite a los usuarios ver sus propios mensajes en cuarentena. <br/><br/> Este rol se asigna automáticamente a los usuarios y no se puede asignar manualmente.|ninguno|
|Acceso de clientes de la organización<sup>\*</sup>||OrganizationManagement|
|Configuración de la organización|Ver informes.|OrganizationManagement|
|Configuración de transporte de la organización<sup>\*</sup>||OrganizationManagement|
|Quarantine|Administrar todos los tipos de mensajes en cuarentena para todos los destinatarios.|OrganizationManagement <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|Directivas de destinatarios<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|Dominios remotos y aceptados|Administrar dominios remotos, dominios aceptados y conectores.|MailFlowAdministrator <br/><br/> OrganizationManagement|
|Restablecer contraseña<sup>\*</sup>||Escritorio <br/><br/> OrganizationManagement <br/><br/> RecipientManagement|
|Administración de retención<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> RecordsManagement|
|Administración de funciones|Crear y administrar grupos de roles.|OrganizationManagement|
|Administrador de seguridad|Administre la configuración y los informes de todas las características de seguridad y protección.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Creación y pertenencia a grupos de seguridad|Crear y administrar grupos de seguridad habilitados para correo.|OrganizationManagement|
|Lector de seguridad|Vea la configuración y los informes de las características de seguridad y protección.|Administración de la organización <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|Administrador de la etiqueta de confidencialidad<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Supervisión<sup>\*</sup>||OrganizationManagement|
|Higiene del transporte|Administrar las características antimalware, contra correo no deseado y contra la suplantación de identidad (phishing).|HygieneManagement <br/><br/> OrganizationManagement|
|Reglas de transporte|Crear y administrar reglas de flujo de correo (también conocidas como reglas de transporte).|OrganizationManagement <br/><br/> RecordsManagement|
|Opciones de usuario|Modificar usuarios de correo existentes.|Escritorio <br/><br/> OrganizationManagement|
|Antimalware solo de vista|Ver la configuración y los informes de las características antimalware.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Correo no deseado de solo vista|Ver la configuración y los informes de las características contra correo no deseado.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Registros de auditoría de solo vista|Busque en el registro de auditoría de administrador y vea los resultados.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|Configuración con permiso de vista|Ver todas las opciones de configuración de la organización y el flujo de correo (no destinatario) de la organización.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Cuarentena de solo vista|Ver todos los mensajes en cuarentena para todos los destinatarios.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Destinatarios con permiso de vista|Ver las propiedades de los destinatarios y ejecutar el seguimiento de mensajes.|ComplianceManagement <br/><br/> Escritorio <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Inteligencia sobre amenazas de solo vista<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> Aunque esta función está disponible, básicamente no hace nada útil en EOP independiente.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Permisos de Microsoft 365 en EOP independiente

Al crear un usuario en el centro de administración de 365 de Microsoft, puede elegir si desea asignar al usuario varios roles administrativos, como el administrador global, el administrador de servicios, el administrador de contraseñas, etc. Algunos roles de Microsoft 365, pero no todos, conceden al usuario permisos administrativos en EOP.

> [!NOTE]
> La cuenta que usó para crear la organización de EOP independiente se asigna automáticamente al rol de administrador global.

En la siguiente tabla se enumeran los roles de Microsoft 365 y los grupos de roles de EOP independientes a los que corresponden. Para obtener más información acerca de estos roles, consulte [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

****

|Rol de Microsoft 365|Grupo de roles de EOP|
|---|---|
|Administrador de Exchange|OrganizationManagement|
|Administrador global|OrganizationManagement <br/><br/> **Nota**: el rol de administrador global y el grupo de roles OrganizationManagement están ligados a la vez que usan un grupo de roles de administrador de empresa especial. El grupo de roles de administrador de la compañía se administra internamente y no se puede modificar directamente.|
|Administrador de contraseñas|Escritorio|
|Lector global|ViewOnlyOrganizationManagement|
|Administrador de seguridad|SecurityAdministrator|
|Lector de seguridad|SecurityReader|
|

Otros roles de Microsoft 365 no tienen un grupo de roles de EOP correspondiente y no concederán permisos administrativos en EOP. Para obtener más información acerca de la asignación de un rol de Microsoft 365 a un usuario, vea [asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).

A los usuarios se les pueden conceder derechos administrativos en EOP sin agregarlos a los roles de 365 de Microsoft. Para hacerlo, agregue el usuario como miembro de un grupo de roles de EOP. El usuario obtendrá permisos en EOP, pero no obtendrá permisos en otras cargas de trabajo de Microsoft 365.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que el grupo de roles se copió correctamente, siga uno de estos pasos:

- En el EAC, vaya a **Permissions** \> **roles de administrador**de permisos y compruebe que el grupo de roles aparece (o no aparece en la lista). Seleccione el grupo de roles y Compruebe la configuración en el panel de detalles o haga clic en el icono **Editar** ![ Edición ](../../media/ITPro-EAC-EditIcon.png) para comprobar la configuración.

- En Exchange Online PowerShell, reemplace \<Role Group Name\> por el nombre del grupo de roles y ejecute el siguiente comando para comprobar que el grupo de roles existe (o no existe) y Compruebe la configuración:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
