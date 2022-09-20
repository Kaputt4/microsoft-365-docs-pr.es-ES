---
title: Asignar permisos de exhibición de documentos electrónicos en el portal de cumplimiento Microsoft Purview
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Asigne los permisos necesarios para realizar tareas relacionadas con eDiscovery mediante el portal de cumplimiento Microsoft Purview.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
ms.openlocfilehash: 4e1c1bdcda0f4912eefe65dc846338cceeae252f
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67823329"
---
# <a name="assign-ediscovery-permissions-in-the-compliance-portal"></a>Asignación de permisos de eDiscovery en el portal de cumplimiento

Si desea que los usuarios usen cualquiera de las [herramientas relacionadas con eDiscovery](ediscovery.md) en el portal de cumplimiento Microsoft Purview, debe asignarles los permisos adecuados. La manera más fácil de hacerlo es agregar a la persona el grupo de roles adecuado en la página **Permisos** del portal de cumplimiento. En este tema se describen los permisos necesarios para realizar tareas de exhibición de documentos electrónicos.

> [!TIP]
> Puede ver sus propios permisos en la página de información general de eDiscovery (Premium) en el portal de cumplimiento. Debe tener al menos un rol asignado para que se muestren los permisos.

El grupo de roles principal relacionado con eDiscovery en el portal de cumplimiento se denomina **Administrador de exhibición de documentos electrónicos**. Hay dos subgrupos dentro de este grupo de roles.
  
- **Administrador de exhibición de** documentos electrónicos: un Administrador de exhibición de documentos electrónicos puede usar herramientas de búsqueda de exhibición de documentos electrónicos para buscar ubicaciones de contenido en la organización y realizar diversas acciones relacionadas con la búsqueda, como la vista previa y la exportación de resultados de búsqueda. Los miembros también pueden crear y administrar casos en Microsoft Purview eDiscovery (Estándar) y Microsoft Purview eDiscovery (Premium), agregar y quitar miembros a un caso, crear retenciones de casos, ejecutar búsquedas asociadas a un caso y acceder a datos de casos. Los supervisores de eDiscovery solo pueden acceder y supervisar los casos que crean. No pueden acceder ni supervisar los casos creados por otros supervisores de eDiscovery.
  
- **Administrador de exhibición de** documentos electrónicos: un administrador de exhibición de documentos electrónicos es miembro del grupo de roles administrador de exhibición de documentos electrónicos y puede realizar las mismas tareas relacionadas con la búsqueda de contenido y la administración de casos que un Administrador de exhibición de documentos electrónicos puede realizar. Además, un administrador de exhibición de documentos electrónicos puede:
  
  - Acceda a todos los casos que aparecen en las páginas **eDiscovery (Estándar)** y **eDiscovery (Premium)** del portal de cumplimiento.

  - Acceder a los datos de los casos en eDiscovery (Premium) para cualquier caso en la organización.
  
  - Administrar cualquier caso de eDiscovery después de agregarse como miembro del caso.
  
  - Quitar miembros de un caso de eDiscovery. Solo un administrador de eDiscovery puede quitar miembros de un caso. Los usuarios que son miembros del subgrupo administrador de exhibición de documentos electrónicos no pueden quitar miembros de un caso, incluso si el usuario creó el caso.
  
  Para conocer las razones por las que podría querer administradores de exhibición de documentos electrónicos en su organización, consulte [Más información](#more-information).

> [!NOTE]
> Para analizar los datos de un usuario mediante eDiscovery (Premium), al usuario (el custodio de los datos) se le debe asignar una licencia de Office 365 E5 o Microsoft 365 E5. Como alternativa, a los usuarios con una licencia de Office 365 E1 o de Office 365 o Microsoft 365 E3 se les puede asignar una licencia de complemento de Cumplimiento de Microsoft 365 E5 o microsoft 365 eDiscovery y auditoría. Los administradores, los responsables de cumplimiento o el personal legal que están asignados a casos como miembros y usan eDiscovery (Premium) para recopilar, ver y analizar datos no necesitan una licencia E5. Para obtener más información sobre las licencias de eDiscovery (Premium[), vea Suscripciones y licencias en eDiscovery (Premium).](overview-ediscovery-20.md#subscriptions-and-licensing)
  
## <a name="before-you-assign-permissions"></a>Antes de asignar permisos

- Debe ser miembro del grupo de roles Administración de la organización o tener asignado el rol Administración de roles para asignar permisos de exhibición de documentos electrónicos en el portal de cumplimiento.

- Puede usar el cmdlet [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) en Security & Compliance PowerShell para agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de eDiscovery en el grupo de roles administrador de eDiscovery. Sin embargo, no puede agregar un grupo de seguridad habilitado para correo al subgrupo administradores de exhibición de documentos electrónicos. Para obtener más información, consulte [Más información](#more-information).
  
## <a name="assign-ediscovery-permissions"></a>Asignar permisos de eDiscovery

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento</a> e inicie sesión con una cuenta que pueda asignar permisos.
  
2. En el panel izquierdo, seleccione **Permisos**.

3. En la página **Permisos & roles** , en **Soluciones de Microsoft Purview**, haga clic en **Roles**.

   Para ir directamente a esta página, use <https://compliance.microsoft.com/compliancecenterpermissions>.

4. En la página **Grupos de roles para soluciones de Microsoft Purview** , seleccione **Administrador de exhibición de documentos electrónicos**.
  
5. En la página de control flotante **del Administrador de exhibición de** documentos electrónicos, realice una de las siguientes acciones en función de los permisos de exhibición de documentos electrónicos que quiera asignar.
  
    **Para convertir a un usuario en administrador de exhibición de documentos electrónicos:** Junto al **Administrador de exhibición de documentos electrónicos**, seleccione **Editar**. En la página **Elegir administrador de exhibición de documentos electrónicos** , haga clic en ![Agregar icono.](../media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, seleccione **Agregar**. Cuando haya terminado de agregar usuarios, seleccione **Listo**. A continuación, en la página **Editar elegir administrador de exhibición de documentos electrónicos** , seleccione **Guardar** para guardar los cambios en la pertenencia al Administrador de exhibición de documentos electrónicos.
  
    **Para convertir a un usuario en administrador de eDiscovery:** Junto a **Administrador de eDiscovery**, seleccione **Editar**. En la página **Elegir administrador de exhibición de documentos electrónicos** , haga clic en ![Agregar icono.](../media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como **administrador de exhibición de documentos electrónicos** y, a continuación,  **Agregar**. Cuando haya terminado de agregar usuarios, seleccione **Listo**. A continuación, en la página **Editar elegir administrador de exhibición de documentos electrónicos** , seleccione **Guardar** para guardar los cambios en la pertenencia al administrador de eDiscovery.
  
> [!NOTE]
> También puede usar el cmdlet **Add-eDiscoveryCaseAdmin** para convertir a un usuario en administrador de eDiscovery. Sin embargo, se debe asignar al usuario el rol Administración de casos para poder usar este cmdlet para convertirlo en administrador de exhibición de documentos electrónicos. Para obtener más información, vea [Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin).
  
En la página **Permisos** del portal de cumplimiento, también puede asignar a los usuarios permisos relacionados con eDiscovery agregándolos a los grupos de roles Administrador de cumplimiento, Administración de la organización y Revisor. Para obtener una descripción de los roles de RBAC relacionados con eDiscovery asignados a cada uno de estos grupos de roles, vea [Roles de RBAC relacionados con eDiscovery](#rbac-roles-related-to-ediscovery).

## <a name="rbac-roles-related-to-ediscovery"></a>Roles de RBAC relacionados con eDiscovery

En la tabla siguiente se enumeran los roles RBAC relacionados con eDiscovery en el portal de cumplimiento e indican los grupos de roles integrados a los que se asigna cada rol de forma predeterminada.
  
| Rol | Administrador de cumplimiento | Administrador de eDiscovery & Administrador | Administración de la organización | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Administración de casos|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)||
|Comunicación||![Marca de verificación.](../media/checkmark.png)|||
|Búsqueda de cumplimiento|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)||
|Custodio||![Marca de verificación.](../media/checkmark.png)|||
|Export||![Marca de verificación.](../media/checkmark.png)|||
|Hold|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)||
|Preview||![Marca de verificación.](../media/checkmark.png)|||
|Revisar||![Marca de verificación.](../media/checkmark.png)||![Marca de verificación](../media/checkmark.png)|
|Descifrado de RMS||![Marca de verificación](../media/checkmark.png)|||
|Buscar y purgar|||![Marca de verificación](../media/checkmark.png)||
  
En las secciones siguientes se describen cada uno de los roles de RBAC relacionados con eDiscovery enumerados en la tabla anterior.

### <a name="case-management"></a>Administración de casos

Este rol permite a los usuarios crear, editar, eliminar y controlar el acceso a casos de exhibición de documentos electrónicos (estándar) y exhibición de documentos electrónicos (Premium) en el portal de cumplimiento. Como se explicó anteriormente, se debe asignar a un usuario el rol Administración de casos para poder usar el cmdlet **Add-eDiscoveryCaseAdmin** para convertirlo en administrador de eDiscovery.

Para obtener más información, consulte:

- [Introducción a eDiscovery (Estándar)](get-started-core-ediscovery.md)

- [Introducción a eDiscovery (Premium)](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicación

Este rol permite a los usuarios administrar todas las comunicaciones con los custodios identificados en un caso de exhibición de documentos electrónicos (Premium). Esto incluye la creación de notificaciones de suspensión, recordatorios de suspensión y escalaciones a la administración. El usuario también puede realizar un seguimiento de la confirmación del custodio de las notificaciones de suspensión y administrar el acceso al portal de custodios que usa cada custodio para realizar un seguimiento de las comunicaciones de los casos en los que se identificaron como custodios.

Para obtener más información, vea [Trabajar con comunicaciones en eDiscovery (Premium).](managing-custodian-communications.md)

### <a name="compliance-search"></a>Búsqueda de cumplimiento

Este rol permite a los usuarios ejecutar la herramienta Búsqueda de contenido en el portal de cumplimiento para buscar buzones y carpetas públicas, sitios de SharePoint Online, sitios OneDrive para la Empresa, conversaciones Skype Empresarial, grupos de Microsoft 365 y grupos de Microsoft Teams y Yammer. Este rol permite a un usuario obtener una estimación de los resultados de búsqueda y crear informes de exportación, pero se necesitan otros roles para iniciar acciones de búsqueda de contenido, como la vista previa, la exportación o la eliminación de resultados de búsqueda.

En Búsqueda de contenido y exhibición de documentos electrónicos (estándar), los usuarios a los que se les asigna el rol Búsqueda de cumplimiento pero no tienen el rol Vista previa pueden obtener una vista previa de los resultados de una búsqueda en la que un usuario al que se le ha asignado el rol Vista previa ha iniciado la acción de vista previa. El usuario sin el rol Vista previa puede obtener una vista previa de los resultados hasta dos semanas después de crear la acción de vista previa inicial.

De forma similar, los usuarios de búsqueda de contenido y exhibición de documentos electrónicos (estándar) a los que se les asigna el rol Búsqueda de cumplimiento pero no tienen el rol Exportar pueden descargar los resultados de una búsqueda en la que un usuario al que se le ha asignado el rol Exportar inició la acción de exportación. El usuario sin el rol Exportar puede descargar los resultados de una búsqueda hasta dos semanas después de crear la acción de exportación inicial. Después de eso, no pueden descargar los resultados a menos que alguien con el rol Exportar reinicie la exportación.

El período de gracia de dos semanas para obtener una vista previa y exportar los resultados de búsqueda (sin los roles de búsqueda y exportación correspondientes) no se aplica a eDiscovery (Premium). A los usuarios se les deben asignar los roles Vista previa y Exportar para obtener una vista previa y exportar contenido en eDiscovery (Premium).

### <a name="custodian"></a>Custodio

Este rol permite a los usuarios identificar y administrar custodios para casos de exhibición de documentos electrónicos (Premium) y usar la información de Azure Active Directory y otros orígenes para buscar orígenes de datos asociados a los custodios. El usuario puede asociar otros orígenes de datos, como buzones de correo, sitios de SharePoint y Teams, con custodios en un caso. El usuario también puede colocar una suspensión legal en los orígenes de datos asociados a los custodios para conservar el contenido en el contexto de un caso.

Para obtener más información, vea [Trabajar con custodios en eDiscovery (Premium).](managing-custodians.md)

### <a name="export"></a>Export

El rol permite a los usuarios exportar los resultados de una búsqueda de contenido a un equipo local. También les permite preparar los resultados de búsqueda para su análisis en eDiscovery (Premium).

Para obtener más información sobre la exportación de resultados de búsqueda, consulte [Exportación de resultados de búsqueda desde portal de cumplimiento Microsoft Purview](export-search-results.md).

### <a name="hold"></a>Hold

Este rol permite a los usuarios colocar contenido en espera en buzones, carpetas públicas, sitios, conversaciones Skype Empresarial y grupos de Microsoft 365. Cuando el contenido está suspendido, los propietarios del contenido pueden seguir modificando o eliminando el contenido original, pero este se conservará hasta que se elimine la suspensión o hasta que expire la duración de la suspensión.

Para obtener más información sobre las retenciones, consulte:

- [Creación de una suspensión en eDiscovery (estándar)](create-ediscovery-holds.md) 

- [Creación de una suspensión en eDiscovery (Premium)](add-custodians-to-case.md)

### <a name="preview"></a>Preview

Este rol permite a los usuarios ver una lista de elementos devueltos desde una búsqueda de contenido. También pueden abrir y ver cada elemento de la lista para ver su contenido.

### <a name="review"></a>Revisar

Este rol permite a los usuarios acceder a conjuntos de revisión en [eDiscovery (Premium).](overview-ediscovery-20.md) Los usuarios a los que se les asigna este rol pueden ver y abrir la lista de casos en la página **eDiscovery > Advanced** del portal de cumplimiento del que son miembros. Una vez que el usuario accede a un caso de exhibición de documentos electrónicos (Premium), puede seleccionar **Revisar conjuntos** para acceder a los datos del caso. Este rol no permite al usuario obtener una vista previa de los resultados de una búsqueda de recopilación asociada al caso ni realizar otras tareas de búsqueda o administración de casos. Los usuarios con este rol solo pueden acceder a los datos de un conjunto de revisión.

### <a name="rms-decrypt"></a>Descifrado de RMS

Este rol permite a los usuarios ver mensajes de correo electrónico protegidos por derechos al obtener una vista previa de los resultados de búsqueda y exportar mensajes de correo electrónico descifrados protegidos por derechos. Este rol también permite a los usuarios ver (y exportar) un archivo cifrado con una [tecnología de cifrado de Microsoft](encryption.md) cuando el archivo cifrado se adjunta a un mensaje de correo electrónico que se incluye en los resultados de una búsqueda de exhibición de documentos electrónicos. Además, este rol permite a los usuarios revisar y consultar datos adjuntos de correo electrónico cifrados que se agregan a un conjunto de revisión en eDiscovery (Premium). Para obtener más información sobre el descifrado en eDiscovery, vea [Descifrado en herramientas de eDiscovery de Microsoft 365](ediscovery-decryption.md).

### <a name="search-and-purge"></a>Buscar y purgar

Este rol permite a los usuarios realizar la eliminación masiva de datos que coinciden con los criterios de una búsqueda de contenido. Para obtener más información, consulte [Búsqueda y eliminación de mensajes de correo electrónico en su organización](search-for-and-delete-messages-in-your-organization.md).

## <a name="adding-role-groups-as-members-of-ediscovery-cases"></a>Adición de grupos de roles como miembros de casos de eDiscovery

Puede agregar grupos de roles como miembros de casos de eDiscovery (Estándar) y eDiscovery (Premium) para que los miembros de los grupos de roles puedan acceder a las tareas y realizarlas en los casos asignados. Los roles asignados al grupo de roles definen lo que pueden hacer los miembros del grupo de roles. A continuación, agregar un grupo de roles como miembro del caso permite a los miembros acceder a esas tareas y realizarlas en un caso específico. Para obtener más información sobre cómo agregar grupos de roles como miembros de casos, consulte:

- [Introducción a eDiscovery (Estándar)](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-ediscovery-standard-case)

- [Agregar o quitar miembros de un caso de exhibición de documentos electrónicos (Premium)](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

Teniendo esto en cuenta, es importante saber que, si se agrega o quita un rol de un grupo de roles, ese grupo de roles se quitará automáticamente como miembro de cualquier caso del que el grupo de roles sea miembro. El motivo es proteger su organización frente a proporcionar permisos adicionales involuntariamente a los miembros de un caso. De forma similar, si se elimina un grupo de roles, se quitará de todos los casos de los que era miembro.

Antes de agregar o quitar roles a un grupo de roles que pueda ser miembro de un caso de exhibición de documentos electrónicos, puede ejecutar los siguientes comandos en [PowerShell de seguridad & cumplimiento](/powershell/exchange/connect-to-scc-powershell) para obtener una lista de casos de los que el grupo de roles es miembro. Después de actualizar el grupo de roles, vuelva a agregar el grupo de roles como miembro de esos casos.

### <a name="get-a-list-of-ediscovery-standard-cases-a-role-group-is-assigned-to"></a>Obtener una lista de casos de exhibición de documentos electrónicos (estándar) a los que se asigna un grupo de roles

```powershell
Get-ComplianceCase -RoleGroup "Name of role group"
```

### <a name="get-a-list-of-ediscovery-premium-cases-a-role-group-is-assigned-to"></a>Obtener una lista de casos de exhibición de documentos electrónicos (Premium) a los que se asigna un grupo de roles

```powershell
Get-ComplianceCase -RoleGroup "Name of role group" -CaseType AdvancedEdiscovery
```

## <a name="more-information"></a>Más información

- **¿Por qué debería crear un administrador de exhibición de documentos electrónicos?** Tal como se explicó anteriormente, un administrador de exhibición de documentos electrónicos es miembro del Grupo de roles de administrador de exhibición de documentos electrónicos, que puede ver y tener acceso a todos los casos de exhibición de documentos electrónicos de la organización. Esta capacidad para tener acceso a todos los casos de exhibición de documentos electrónicos tiene dos fines importantes:

  - Si un usuario es el único miembro de un caso de exhibición de documentos electrónicos y abandona la organización, ningún usuario (ni siquiera los miembros del grupo de roles Administración de la organización ni otro miembro del grupo de roles Administrador de exhibición de documentos electrónicos) puede tener acceso a ese caso de exhibición de documentos electrónicos, ya que no es miembro del caso. En esta situación, no habría ninguna manera de tener acceso a los datos del caso. Pero como un administrador de eDiscovery puede acceder a todos los casos de eDiscovery de la organización, puede ver el caso y agregarse a sí mismo u otro administrador de exhibición de documentos electrónicos como miembro del caso.

  - Dado que un administrador de eDiscovery puede ver y acceder a todos los casos de eDiscovery (Estándar) y eDiscovery (Premium), puede auditar y supervisar todos los casos y las búsquedas de cumplimiento asociadas. Esto puede ayudar a evitar cualquier uso indebido de búsquedas de cumplimiento o casos de exhibición de documentos electrónicos. Y dado que los administradores de eDiscovery pueden acceder a información potencialmente confidencial en los resultados de una búsqueda de cumplimiento, debe limitar el número de personas que son administradores de eDiscovery.

- **¿Puedo agregar un grupo como miembro del grupo de roles del Administrador de exhibición de documentos electrónicos?** Como se explicó anteriormente, puede agregar un grupo de seguridad habilitado para correo como miembro del subgrupo Administradores de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos mediante el cmdlet **Add-RoleGroupMember** en PowerShell de cumplimiento de & seguridad. Por ejemplo, puede ejecutar el siguiente comando para agregar un grupo de seguridad habilitado para correo al grupo de roles del Administrador de exhibición de documentos electrónicos. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    No se admiten los grupos de distribución y Grupos de Microsoft 365 de Exchange. Debe usar un grupo de seguridad habilitado para correo, que puede crear en Exchange Online PowerShell mediante la ejecución de `New-DistributionGroup -Type Security`. También puede crear un grupo de seguridad habilitado para correo (y agregar miembros) en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> o en el [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). Puede tardar hasta 60 minutos después de crearlo para que un nuevo grupo de seguridad habilitado para correo esté disponible para agregarlo al grupo de roles administradores de exhibición de documentos electrónicos.

    Además, como se indicó anteriormente, no puede convertir un grupo de seguridad habilitado para correo en un administrador de exhibición de documentos electrónicos mediante el cmdlet **Add-eDiscoveryCaseAdmin** en PowerShell de cumplimiento de & seguridad. Solo puede agregar usuarios individuales como administradores de eDiscovery.

    Tampoco puede agregar un grupo de seguridad habilitado para correo como miembro de un caso.
