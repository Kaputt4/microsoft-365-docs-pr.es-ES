---
title: Asignar permisos de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Asigne los permisos necesarios para realizar tareas relacionadas con la exhibición de documentos electrónicos mediante el Centro de cumplimiento de Microsoft 365.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
ms.openlocfilehash: 426430f705fa85be440df39c6a40f8872d7024ad
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61422788"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365

Si desea que las personas [](ediscovery.md) usen cualquiera de las herramientas relacionadas con la exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365, debe asignarles los permisos adecuados. La forma más sencilla de hacerlo es agregar a la persona el grupo de roles adecuado en la página **Permisos** del centro de cumplimiento. En este tema se describen los permisos necesarios para realizar tareas de exhibición de documentos electrónicos.
  
El grupo de roles principal relacionado con la exhibición de documentos electrónicos en Centro de cumplimiento de Microsoft 365 se denomina **Administrador de exhibición de documentos electrónicos**. Hay dos subgrupos dentro de este grupo de roles.
  
- **Administrador de** exhibición de documentos electrónicos: un administrador de exhibición de documentos electrónicos puede usar herramientas de búsqueda de exhibición de documentos electrónicos para buscar ubicaciones de contenido en la organización y realizar varias acciones relacionadas con la búsqueda, como obtener una vista previa y exportar los resultados de la búsqueda. Los miembros también pueden crear y administrar casos en la exhibición de documentos electrónicos principales y Advanced eDiscovery, agregar y quitar miembros a un caso, crear retenciones de casos, ejecutar búsquedas asociadas a un caso y obtener acceso a datos de casos. Los supervisores de eDiscovery solo pueden acceder y supervisar los casos que crean. No pueden acceder ni supervisar los casos creados por otros supervisores de eDiscovery.
  
- **Administrador de** exhibición de documentos electrónicos: un administrador de exhibición de documentos electrónicos es miembro del grupo de roles administrador de exhibición de documentos electrónicos y puede realizar las mismas tareas relacionadas con la administración de casos y búsqueda de contenido que un administrador de exhibición de documentos electrónicos. Además, un administrador de eDiscovery puede:
  
  - Obtenga acceso a todos los casos enumerados en **la** exhibición de documentos electrónicos principal **y** Advanced eDiscovery páginas de la Centro de cumplimiento de Microsoft 365.

  - Acceder a los datos de los casos en eDiscovery avanzado para cualquier caso en la organización.
  
  - Administrar cualquier caso de eDiscovery después de agregarse como miembro del caso.
  
  - Quite miembros de un caso de exhibición de documentos electrónicos. Solo un administrador de exhibición de documentos electrónicos puede quitar miembros de un caso. Los usuarios que son miembros del subgrupo administrador de exhibición de documentos electrónicos no pueden quitar miembros de un caso, incluso si el usuario creó el caso.
  
  Por motivos por los que es posible que desee administradores de exhibición de documentos electrónicos en su organización, vea [Más información](#more-information).

> [!NOTE]
> Para analizar los datos de un usuario mediante Advanced eDiscovery, al usuario (el administrador de los datos) se le debe asignar una Office 365 E5 o Microsoft 365 E5 licencia. Como alternativa, a los usuarios con una Office 365 E1 o una licencia Office 365 o Microsoft 365 E3 se les puede asignar una licencia de complemento Cumplimiento de Microsoft 365 E5 o Microsoft 365 eDiscovery and Audit. Los administradores, los responsables de cumplimiento o el personal legal que están asignados a casos como miembros y usan Advanced eDiscovery para recopilar, ver y analizar datos no necesitan una licencia E5. Para obtener más información sobre Advanced eDiscovery licencias, vea [Suscripciones y licencias en Advanced eDiscovery](overview-ediscovery-20.md#subscriptions-and-licensing).
  
## <a name="before-you-assign-permissions"></a>Antes de asignar permisos

- Debe ser miembro del grupo de roles Administración de la organización o tener asignado el rol Administración de roles para asignar permisos de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365.

- Puede usar el cmdlet [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) en PowerShell del Centro de seguridad & para agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos. Sin embargo, no puede agregar un grupo de seguridad habilitado para correo al subgrupo administradores de exhibición de documentos electrónicos. Para obtener más información, [vea More information](#more-information).
  
## <a name="assign-ediscovery-permissions"></a>Asignar permisos de eDiscovery

1. Vaya a <https://compliance.microsoft.com> e inicie sesión con una cuenta que pueda asignar permisos.
  
2. En el panel izquierdo, seleccione **Permisos**.

3. En la **página Permisos & roles,** en **Centro de cumplimiento**, haga clic en **Roles**.

4. En la **página Roles del centro de** cumplimiento, seleccione Administrador de **exhibición de documentos electrónicos**.
  
5. En la página desplegable **del Administrador** de exhibición de documentos electrónicos, realice una de las siguientes acciones en función de los permisos de exhibición de documentos electrónicos que desee asignar.
  
    **Para convertir a un usuario en administrador de exhibición de documentos electrónicos:** Junto al **Administrador de exhibición de documentos electrónicos,** seleccione **Editar**. En la página **Elegir asistente del Administrador de exhibición de** documentos electrónicos, haga clic en Agregar ![ icono.](../media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, **seleccione Agregar**. Cuando haya terminado de agregar usuarios, seleccione **Listo**. A continuación, en la página **Asistente**  para editar Elegir administrador de exhibición de documentos electrónicos, seleccione Guardar para guardar los cambios en la pertenencia al Administrador de exhibición de documentos electrónicos.
  
    **Para convertir a un usuario en administrador de exhibición de documentos electrónicos:** Junto a **Administrador de exhibición de documentos electrónicos,** seleccione **Editar**. En la página **Elegir administrador de exhibición de** documentos electrónicos, haga clic en Agregar ![ icono.](../media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de **exhibición** de documentos electrónicos y, a continuación,  **Agregue**. Cuando haya terminado de agregar usuarios, seleccione **Listo**. A continuación, en la página Asistente  para editar **elegir** administrador de exhibición de documentos electrónicos, seleccione Guardar para guardar los cambios en la pertenencia al administrador de exhibición de documentos electrónicos.
  
> [!NOTE]
> También puede usar el cmdlet **Add-eDiscoveryCaseAdmin** para convertir a un usuario en administrador de exhibición de documentos electrónicos. Sin embargo, el usuario debe tener asignado el rol de administración de casos antes de poder usar este cmdlet para que sea un administrador de exhibición de documentos electrónicos. Para obtener más información, [vea Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin). 
  
En **la** página Permisos de la Centro de cumplimiento de Microsoft 365, también puede asignar a los usuarios permisos relacionados con la exhibición de documentos electrónicos agregándolos a los grupos de roles Administrador de cumplimiento, Administración de la organización y Revisor. Para obtener una descripción de los roles RBAC relacionados con la exhibición de documentos electrónicos asignados a cada uno de estos grupos de roles, vea [RBAC roles related to eDiscovery](#rbac-roles-related-to-ediscovery).

## <a name="rbac-roles-related-to-ediscovery"></a>Roles RBAC relacionados con eDiscovery

En la tabla siguiente se enumeran los roles RBAC relacionados con la exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365 e indica los grupos de roles integrados a los que se asigna cada función de forma predeterminada.
  
| Role | Administrador de cumplimiento | Administrador de eDiscovery & administrador | Administración de la organización | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Administración de casos <br/> |![Marca de verificación.](../media/checkmark.png) <br/> |![Marca de verificación.](../media/checkmark.png) <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> |
|Comunicación <br/> | <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> | <br/> |
|Búsqueda de cumplimiento <br/> |![Marca de verificación.](../media/checkmark.png) <br/> |![Marca de verificación.](../media/checkmark.png) <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> |
|Custodio <br/> | <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> | <br/> |
|Export <br/> | <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Marca de verificación.](../media/checkmark.png) <br/> |![Marca de verificación.](../media/checkmark.png) <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> |
|Preview <br/>  | <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> | <br/> |
|Revisar <br/>  | <br/> |![Marca de verificación.](../media/checkmark.png) <br/> | <br/> |![Marca de verificación](../media/checkmark.png) <br/> |
|Descifrado de RMS <br/>  ||![Marca de verificación](../media/checkmark.png) <br/> |||
|Buscar y purgar <br/> | <br/> | <br/> |![Marca de verificación](../media/checkmark.png)           <br/> | <br/> |
||||
  
En las secciones siguientes se describe cada uno de los roles RBAC relacionados con la exhibición de documentos electrónicos enumerados en la tabla anterior.

### <a name="case-management"></a>Administración de casos

Este rol permite a los usuarios crear, editar, eliminar y controlar el acceso a la exhibición de documentos electrónicos principales y Advanced eDiscovery casos en el Centro de cumplimiento de Microsoft 365. Como se explicó anteriormente, se debe asignar a un usuario el rol de administración de casos para poder usar el cmdlet **Add-eDiscoveryCaseAdmin** para que sea un administrador de exhibición de documentos electrónicos.

Para más información, vea:

- [Introducción a Core eDiscovery](get-started-core-ediscovery.md)

- [Introducción a eDiscovery avanzado](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicación

Este rol permite a los usuarios administrar todas las comunicaciones con los custodios identificados en un Advanced eDiscovery caso. Esto incluye la creación de notificaciones de retención, avisos de retención y escalaciones a la administración. El usuario también puede realizar un seguimiento de la confirmación de custodia de las notificaciones de retención y administrar el acceso al portal de custodia que usa cada custodio para realizar un seguimiento de las comunicaciones de los casos en los que se identificaron como custodios.

Para obtener más información, [vea Trabajar con comunicaciones en Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Búsqueda de cumplimiento

Este rol permite a los usuarios ejecutar la herramienta búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 para buscar buzones y carpetas públicas, sitios de SharePoint Online, sitios OneDrive para la Empresa, conversaciones Skype Empresarial, Microsoft 365, y Microsoft Teams y Yammer grupos. Este rol permite al usuario obtener una estimación de los resultados de la búsqueda y crear informes de exportación, pero se necesitan otros roles para iniciar acciones de búsqueda de contenido como la vista previa, la exportación o la eliminación de resultados de búsqueda.

En la búsqueda de contenido y la exhibición de documentos electrónicos principales, los usuarios a los que se les asigna el rol Búsqueda de cumplimiento pero no tienen el rol Vista previa pueden obtener una vista previa de los resultados de una búsqueda en la que la acción de vista previa ha sido iniciada por un usuario al que se ha asignado el rol Vista previa. El usuario sin el rol Vista previa puede obtener una vista previa de los resultados hasta dos semanas después de crear la acción de vista previa inicial.

Del mismo modo, los usuarios de búsqueda de contenido y exhibición de documentos electrónicos principales a los que se les asigna el rol Búsqueda de cumplimiento pero que no tienen el rol Exportar pueden descargar los resultados de una búsqueda en la que la acción de exportación la inició un usuario al que se le asignó el rol Exportar. El usuario sin el rol Exportar puede descargar los resultados de una búsqueda hasta dos semanas después de que se creó la acción de exportación inicial. Después de eso, no pueden descargar los resultados a menos que alguien con el rol Exportar reinicie la exportación.

El período de gracia de dos semanas para obtener una vista previa y exportar los resultados de búsqueda (sin los roles de búsqueda y exportación correspondientes) no se aplica a Advanced eDiscovery. Los usuarios deben tener asignados los roles Vista previa y Exportar para obtener una vista previa y exportar contenido en Advanced eDiscovery.

### <a name="custodian"></a>Custodio

Este rol permite a los usuarios identificar y administrar custodios para casos Advanced eDiscovery y usar la información de Azure Active Directory y otros orígenes para buscar orígenes de datos asociados con custodios. El usuario puede asociar otros orígenes de datos, como buzones de correo, sitios SharePoint y Teams con los custodios en un caso. El usuario también puede colocar una retención legal en los orígenes de datos asociados con los custodios para conservar el contenido en el contexto de un caso.

Para obtener más información, [vea Trabajar con custodios en Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Export

El rol permite a los usuarios exportar los resultados de una búsqueda de contenido a un equipo local. También les permite preparar los resultados de búsqueda para el análisis en Advanced eDiscovery.

Para obtener más información acerca de la exportación de resultados de búsqueda, vea [Export search results from Centro de cumplimiento de Microsoft 365](export-search-results.md).

### <a name="hold"></a>Hold

Este rol permite a los usuarios poner contenido en espera en buzones, carpetas públicas, sitios, Skype Empresarial conversaciones y Microsoft 365 grupos. Cuando el contenido está suspendido, los propietarios del contenido pueden seguir modificando o eliminando el contenido original, pero este se conservará hasta que se elimine la suspensión o hasta que expire la duración de la suspensión.

Para obtener más información acerca de las retenciones, vea:

- [Crear una retención en eDiscovery principal](create-ediscovery-holds.md) 

- [Crear una retención en Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Preview

Este rol permite a los usuarios ver una lista de elementos devueltos desde una búsqueda de contenido. También pueden abrir y ver cada elemento de la lista para ver su contenido.

### <a name="review"></a>Revisar

Este rol permite a los usuarios acceder a conjuntos de [revisión en Advanced eDiscovery](overview-ediscovery-20.md). Los usuarios a los que se asigna este rol pueden ver y abrir la lista de casos en la página > **eDiscovery advanced** en la Centro de cumplimiento de Microsoft 365 de la que son miembros. Después de que el usuario obtenga acceso a Advanced eDiscovery caso, puede seleccionar **Revisar conjuntos para** obtener acceso a los datos de caso. Este rol no permite al usuario obtener una vista previa de los resultados de una búsqueda de colección asociada al caso o realizar otras tareas de administración de casos o búsqueda. Los usuarios con este rol solo pueden tener acceso a los datos de un conjunto de revisión.

### <a name="rms-decrypt"></a>Descifrado de RMS

Este rol permite a los usuarios ver mensajes de correo electrónico protegidos por derechos al obtener una vista previa de los resultados de búsqueda y exportar mensajes de correo electrónico con derechos descifrados protegidos. Este rol también permite a los usuarios ver (y exportar) un archivo cifrado con una tecnología de cifrado de [Microsoft](encryption.md) cuando el archivo cifrado se adjunta a un mensaje de correo electrónico que se incluye en los resultados de una búsqueda de exhibición de documentos electrónicos. Además, este rol permite a los usuarios revisar y consultar datos adjuntos cifrados de correo electrónico que se agregan a un conjunto de revisión en Advanced eDiscovery. Para obtener más información sobre el descifrado en eDiscovery, vea [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

### <a name="search-and-purge"></a>Buscar y purgar

Este rol permite a los usuarios realizar la eliminación masiva de datos que coincidan con los criterios de una búsqueda de contenido. Para obtener más información, vea [Buscar y eliminar mensajes de correo electrónico en la organización.](search-for-and-delete-messages-in-your-organization.md)

## <a name="adding-role-groups-as-members-of-ediscovery-cases"></a>Agregar grupos de roles como miembros de casos de exhibición de documentos electrónicos

Puede agregar grupos de roles como miembros de la exhibición de documentos electrónicos principales y Advanced eDiscovery para que los miembros de los grupos de roles puedan tener acceso y realizar tareas en los casos asignados. Los roles asignados al grupo de roles definen lo que pueden hacer los miembros del grupo de roles. A continuación, agregar un grupo de roles como miembro del caso permite a los miembros tener acceso a esas tareas y realizar estas tareas en un caso específico. Para obtener más información acerca de cómo agregar grupos de roles como miembros de casos, vea:

- [Introducción a Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

- [Agregar o quitar miembros de un Advanced eDiscovery caso](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

Con esto en mente, es importante saber que si se agrega o quita un rol de un grupo de roles, ese grupo de funciones se quitará automáticamente como miembro de cualquier caso del grupo de roles. El motivo es proteger la organización de proporcionar permisos adicionales a los miembros de un caso de forma involuntaria. Del mismo modo, si se elimina un grupo de roles, se quitará de todos los casos de los que era miembro.

Antes de agregar o quitar roles a un grupo de roles que puede ser miembro de un caso de exhibición de documentos electrónicos, puede ejecutar los siguientes comandos en [PowerShell](/powershell/exchange/connect-to-scc-powershell) de seguridad & cumplimiento para obtener una lista de casos de los que el grupo de roles es miembro. Después de actualizar el grupo de roles, se vuelve a agregar el grupo de roles como miembro de esos casos.

### <a name="get-a-list-of-core-ediscovery-cases-a-role-group-is-assigned-to"></a>Obtener una lista de casos principales de exhibición de documentos electrónicos a los que se asigna un grupo de roles

```powershell
Get-ComplianceCase -RoleGroup "Name of role group"
```

### <a name="get-a-list-of-advanced-ediscovery-cases-a-role-group-is-assigned-to"></a>Obtener una lista de Advanced eDiscovery casos a los que se asigna un grupo de roles

```powershell
Get-ComplianceCase -RoleGroup "Name of role group" -CaseType AdvancedEdiscovery
```

## <a name="more-information"></a>Más información

- **¿Por qué debería crear un administrador de exhibición de documentos electrónicos?** Tal como se explicó anteriormente, un administrador de exhibición de documentos electrónicos es miembro del Grupo de roles de administrador de exhibición de documentos electrónicos, que puede ver y tener acceso a todos los casos de exhibición de documentos electrónicos de la organización. Esta capacidad para tener acceso a todos los casos de exhibición de documentos electrónicos tiene dos fines importantes:

  - Si un usuario es el único miembro de un caso de exhibición de documentos electrónicos y abandona la organización, ningún usuario (ni siquiera los miembros del grupo de roles Administración de la organización ni otro miembro del grupo de roles Administrador de exhibición de documentos electrónicos) puede tener acceso a ese caso de exhibición de documentos electrónicos, ya que no es miembro del caso. En esta situación, no habría ninguna manera de tener acceso a los datos del caso. Pero como un administrador de exhibición de documentos electrónicos puede tener acceso a todos los casos de exhibición de documentos electrónicos de la organización, pueden ver el caso y agregarse a sí mismos u otro administrador de exhibición de documentos electrónicos como miembro del caso.

  - Dado que un administrador de exhibición de documentos electrónicos puede ver y obtener acceso a todos los casos principales de exhibición de documentos electrónicos Advanced eDiscovery, pueden auditar y supervisar todos los casos y las búsquedas de cumplimiento asociadas. Esto puede ayudar a evitar cualquier uso incorrecto de búsquedas de cumplimiento o casos de exhibición de documentos electrónicos. Y como los administradores de exhibición de documentos electrónicos pueden tener acceso a información potencialmente confidencial en los resultados de una búsqueda de cumplimiento, debe limitar el número de personas que son administradores de exhibición de documentos electrónicos.

- **¿Puedo agregar un grupo como miembro del grupo de roles administrador de exhibición de documentos electrónicos?** Como se explicó anteriormente, puede agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos mediante el cmdlet **Add-RoleGroupMember** en PowerShell del Centro de seguridad & cumplimiento. Por ejemplo, puede ejecutar el siguiente comando para agregar un grupo de seguridad habilitado para correo al grupo de roles administrador de exhibición de documentos electrónicos. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange no se admiten Microsoft 365 de distribución y grupos de distribución. Debe usar un grupo de seguridad habilitado para correo, que puede crear en Exchange Online PowerShell ejecutando `New-DistributionGroup -Type Security` . También puede crear un grupo de seguridad habilitado para <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank"></a> correo (y agregar miembros) en el centro de administración de Exchange o en el [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). Puede tardar hasta 60 minutos después de crearlo para que un nuevo grupo de seguridad habilitado para correo esté disponible para agregarlo al grupo de roles Administradores de exhibición de documentos electrónicos.

    También como se ha indicado anteriormente, no puede convertir un grupo de seguridad habilitado para correo como administrador de exhibición de documentos electrónicos mediante el cmdlet **Add-eDiscoveryCaseAdmin** en PowerShell del Centro de seguridad & cumplimiento. Solo puede agregar usuarios individuales como administradores de exhibición de documentos electrónicos.

    Tampoco puede agregar un grupo de seguridad habilitado para correo como miembro de un caso.
