---
title: Asignar permisos de exhibición de documentos electrónicos en el Centro de & cumplimiento
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Asigne los permisos necesarios para realizar tareas relacionadas con la exhibición de documentos electrónicos mediante el Centro de & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d4be264791c4f3d37d7a88cb3d12d1023b3c347
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759894"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en el Centro de & cumplimiento

Si desea que los usuarios [](ediscovery.md) usen cualquiera de las herramientas relacionadas con la exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & en Office 365 o en el Centro de cumplimiento de Microsoft 365, debe asignarles los permisos adecuados. La forma más sencilla de hacerlo es agregar a  la persona el grupo de roles adecuado en la página Permisos del Centro de seguridad & cumplimiento. En este tema se describen los permisos necesarios para realizar tareas relacionadas con la exhibición de documentos electrónicos y la búsqueda de contenido mediante el Centro de & cumplimiento.
  
El grupo de roles principal relacionado con la exhibición de documentos electrónicos en el Centro de & cumplimiento se denomina **Administrador de exhibición de documentos electrónicos.** Hay dos subgrupos dentro de este grupo de roles.
  
- Administradores de exhibición de documentos **electrónicos:** un administrador de exhibición de documentos electrónicos puede usar la herramienta de búsqueda de contenido en el Centro de seguridad y cumplimiento de & para buscar ubicaciones de contenido en la organización y realizar diversas acciones relacionadas con la búsqueda, como obtener una vista previa y exportar los resultados de la búsqueda. Los miembros también pueden crear y administrar casos en eDiscovery principal y eDiscovery avanzado, agregar y quitar miembros a un caso, crear retenciones de casos, ejecutar búsquedas asociadas a un caso y acceder a datos de casos. Los administradores de exhibición de documentos electrónicos solo pueden acceder y administrar los casos que crean. No pueden acceder ni administrar casos creados por otros administradores de exhibición de documentos electrónicos.
  
- Administradores de exhibición de documentos electrónicos: un administrador de exhibición de documentos electrónicos es miembro del grupo de roles administrador de exhibición de documentos electrónicos y puede realizar las mismas tareas relacionadas con la búsqueda de contenido y la administración de **casos** que un administrador de exhibición de documentos electrónicos. Además, un administrador de exhibición de documentos electrónicos puede:
  
  - Obtenga acceso a todos los casos que aparecen en las páginas **eDiscovery** y **eDiscovery** avanzado en el Centro de & cumplimiento.

  - Obtener acceso a los datos de casos en eDiscovery avanzado para cualquier caso de la organización.
  
  - Administrar cualquier caso de exhibición de documentos electrónicos después de agregarse a sí mismos como miembro del caso.
  
  For reasons why you might want eDiscovery Administrators in your organization, see [More information](#more-information).

> [!NOTE]
> Para analizar los datos de un usuario mediante eDiscovery avanzado, el usuario (el administrador de los datos) debe tener asignada una licencia de Office 365 E5 o Microsoft 365 E5. Como alternativa, a los usuarios con una licencia de Office 365 E1 o Office 365 o Microsoft 365 E3 se les puede asignar una licencia de cumplimiento de Microsoft 365 E5 o una licencia de complemento de exhibición de documentos electrónicos y auditoría de Microsoft 365. Los administradores, responsables de cumplimiento normativo o personal legal asignados a casos como miembros y usan eDiscovery avanzado para recopilar, ver y analizar datos no necesitan una licencia E5. Para obtener más información acerca de las licencias de eDiscovery avanzado, vea [Introducción a eDiscovery avanzado.](get-started-with-advanced-ediscovery.md)
  
## <a name="confirm-your-roles"></a>Confirmar los roles

- Debe ser miembro del grupo de roles Administración de la organización o tener asignado el rol Administración de roles para asignar permisos de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento.

- Puede usar el cmdlet [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) en PowerShell del Centro de seguridad & Cumplimiento para agregar un grupo de seguridad habilitado para correo como miembro del subgrupo Administradores de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos. Sin embargo, no puede agregar un grupo de seguridad habilitado para correo al subgrupo administradores de exhibición de documentos electrónicos. Para obtener más información, [vea Más información.](#more-information) 
  
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en el Centro de & cumplimiento

1. Vaya a [https://protection.office.com](https://protection.office.com).
  
2. Inicie sesión con su cuenta profesional o educativa.
  
3. En el panel izquierdo del Centro de seguridad y cumplimiento, seleccione Permisos y, a continuación, active la casilla junto al Administrador de **exhibición de documentos electrónicos.**
  
4. En la página desplegable del **Administrador** de exhibición de documentos electrónicos, realice una de las siguientes acciones en función de los permisos de exhibición de documentos electrónicos que desee asignar.
  
    **Para que un usuario sea un administrador de exhibición de documentos electrónicos:** Junto al **Administrador de exhibición de documentos electrónicos,** **seleccione Editar**. En la **sección Elegir administrador de** exhibición de documentos electrónicos, seleccione el hipervínculo Elegir administrador de **exhibición** de documentos electrónicos y, a continuación, ![ seleccione Agregar icono ](../media/ITPro-EAC-AddIcon.gif) **agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, **seleccione Agregar**. Cuando haya terminado de agregar usuarios, seleccione **Listo.** A continuación, en la página desplegable **Elegir** administrador de exhibición de documentos electrónicos de edición, seleccione Guardar para guardar los cambios en la pertenencia al Administrador de exhibición de documentos electrónicos. 
  
    **Para convertir a un usuario en administrador de exhibición de documentos electrónicos:** Junto al **Administrador de exhibición de documentos electrónicos,** **seleccione Editar**. En la **sección Elegir** administrador de exhibición de documentos electrónicos, en Administradores de **exhibición** de documentos electrónicos, seleccione Elegir administrador de **exhibición** de documentos electrónicos, editar **y,** a continuación, seleccione Agregar icono ![ ](../media/ITPro-EAC-AddIcon.gif) **agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de **exhibición** de documentos electrónicos y, a continuación,  **agregue**. Cuando haya terminado de agregar usuarios, seleccione **Listo.** A continuación, en la página desplegable Elegir  administrador de **exhibición** de documentos electrónicos de edición, seleccione Guardar para guardar los cambios en la pertenencia del administrador de exhibición de documentos electrónicos.
  
> [!NOTE]
> También puede usar el cmdlet **Add-eDiscoveryCaseAdmin** para convertir a un usuario en administrador de exhibición de documentos electrónicos. Sin embargo, el usuario debe tener asignado el rol de administración de casos antes de poder usar este cmdlet para que sea administrador de exhibición de documentos electrónicos. Para obtener más información, [vea Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
En  la página Permisos del Centro de seguridad y cumplimiento de &, también puede asignar a los usuarios permisos relacionados con la exhibición de documentos electrónicos agregándolos a los grupos de roles Administrador de cumplimiento, Administración de la organización y Revisor. Para obtener una descripción de los roles RBAC relacionados con la exhibición de documentos electrónicos asignados a cada uno de estos grupos de roles, vea los roles RBAC relacionados [con la exhibición de documentos electrónicos.](#rbac-roles-related-to-ediscovery)

## <a name="rbac-roles-related-to-ediscovery"></a>Roles RBAC relacionados con la exhibición de documentos electrónicos

En la siguiente tabla se enumeran los roles RBAC relacionados con la exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento e indica los grupos de roles integrados a los que se asigna cada rol de forma predeterminada.
  
| Función | Administrador de cumplimiento | Administrador de eDiscovery & administrador | Administración de la organización | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Administración de casos <br/> |![Marca de verificación](../media/checkmark.png) <br/> |![Marca de verificación](../media/checkmark.png) <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> |
|Comunicación <br/> | <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> | <br/> |
|Búsqueda de cumplimiento <br/> |![Marca de verificación](../media/checkmark.png) <br/> |![Marca de verificación](../media/checkmark.png) <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> | <br/> |
|Exportar <br/> | <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Marca de verificación](../media/checkmark.png) <br/> |![Marca de verificación](../media/checkmark.png) <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> |
|Preview <br/>  | <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> | <br/> |
|Revisar <br/>  | <br/> |![Marca de verificación](../media/checkmark.png) <br/> | <br/> |![Marca de verificación](../media/checkmark.png) <br/> |
|Descifrado de RMS <br/>  ||![Marca de verificación](../media/checkmark.png) <br/> |||
|Buscar y purgar <br/> | <br/> | <br/> |![Marca de verificación](../media/checkmark.png)           <br/> | <br/> |
||||
  
En las secciones siguientes se describe cada uno de los roles RBAC relacionados con la exhibición de documentos electrónicos enumerados en la tabla anterior.

### <a name="case-management"></a>Administración de casos

Este rol permite a los usuarios crear, editar, eliminar y controlar el acceso a los casos principales de eDiscovery y eDiscovery avanzado en el Centro de & cumplimiento. Como se ha explicado anteriormente, un usuario debe tener asignado el rol de administración de casos antes de poder usar el cmdlet **Add-eDiscoveryCaseAdmin** para que sea un administrador de exhibición de documentos electrónicos.

Para obtener más información, vea:

- [Introducción a Core eDiscovery](get-started-core-ediscovery.md)

- [Introducción a eDiscovery avanzado](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicación

Este rol permite a los usuarios administrar todas las comunicaciones con los administradores identificados en un caso de eDiscovery avanzado. Esto incluye la creación de notificaciones de retención, avisos de retención y escalaciones a la administración. El usuario también puede realizar un seguimiento de las notificaciones de retención y administrar el acceso al portal de administrador que usa cada administrador para realizar un seguimiento de las comunicaciones de los casos en los que se identificaron como administradores.

Para obtener más información, vea [Trabajar con comunicaciones en eDiscovery avanzado.](managing-custodian-communications.md)

### <a name="compliance-search"></a>Búsqueda de cumplimiento

Este rol permite a los usuarios ejecutar la herramienta de búsqueda de contenido en el Centro de seguridad y cumplimiento de & para buscar buzones y carpetas públicas, sitios de SharePoint Online, sitios de OneDrive para la Empresa, conversaciones de Skype Empresarial, grupos de Microsoft 365 y Grupos de Microsoft Teams y Yammer. Este rol permite al usuario obtener una estimación de los resultados de la búsqueda y crear informes de exportación, pero se necesitan roles adicionales para iniciar acciones de búsqueda de contenido como la vista previa, exportación o eliminación de resultados de búsqueda.

Los usuarios que tienen asignado el rol Búsqueda de cumplimiento pero que no tienen el rol Vista previa pueden obtener una vista previa de los resultados de una búsqueda en la que la acción de vista previa ha sido iniciada por un usuario que tiene asignado el rol Vista previa. El usuario sin el rol Vista previa puede obtener una vista previa de los resultados hasta dos semanas después de crear la acción de vista previa inicial.

De forma similar, los usuarios que tienen asignado el rol Búsqueda de cumplimiento pero que no tienen el rol Exportar pueden descargar los resultados de una búsqueda en la que un usuario al que se le asignó el rol Exportar inició la acción de exportación. El usuario sin el rol Exportar puede descargar los resultados de una búsqueda hasta dos semanas después de que se creó la acción de exportación inicial. Después, no podrán descargar los resultados a menos que alguien con el rol Exportar reinicie la exportación.

Para obtener más información, vea [Búsqueda de contenido en Office 365.](content-search.md)

### <a name="custodian"></a>Custodian

Este rol permite a los usuarios identificar y administrar administradores para casos de eDiscovery avanzado y usar la información de Azure Active Directory y otros orígenes para buscar orígenes de datos asociados con administradores. El usuario puede asociar otros orígenes de datos como buzones de correo, sitios de SharePoint y Teams con administradores en un caso. El usuario también puede colocar una retención legal en los orígenes de datos asociados con los administradores para conservar el contenido en el contexto de un caso.

Para obtener más información, [vea Trabajar con administradores en eDiscovery avanzado.](managing-custodians.md)

### <a name="export"></a>Exportar

El rol permite a los usuarios exportar los resultados de una búsqueda de contenido a un equipo local. También les permite preparar los resultados de búsqueda para su análisis en eDiscovery avanzado.

Para obtener más información acerca de la exportación de resultados de búsqueda, vea Exportar resultados de búsqueda desde el Centro [de & cumplimiento.](export-search-results.md)

### <a name="hold"></a>Hold

Este rol permite a los usuarios poner contenido en espera en buzones, carpetas públicas, sitios, conversaciones de Skype Empresarial y grupos de Microsoft 365. Cuando el contenido está en retención, los propietarios de contenido aún pueden modificar o eliminar el contenido original, pero el contenido se conservará hasta que se quite la retención o hasta que expire la duración de la retención.

Para obtener más información acerca de las retenciones, vea:

- [Crear una retención en eDiscovery principal](create-ediscovery-holds.md) 

- [Crear una retención en eDiscovery avanzado](add-custodians-to-case.md)

### <a name="preview"></a>Preview

Este rol permite a los usuarios ver una lista de elementos que se devolvieron de una búsqueda de contenido. También pueden abrir y ver cada elemento de la lista para ver su contenido.

### <a name="review"></a>Revisar

Este rol permite a los usuarios tener acceso a conjuntos de revisión en [eDiscovery avanzado.](overview-ediscovery-20.md) Los usuarios que tienen asignado este rol pueden ver y abrir la lista de casos en la página **eDiscovery >** Advanced en el Centro de cumplimiento de Microsoft 365 del que son miembros. Una vez que el usuario tiene acceso a un caso de eDiscovery avanzado, puede seleccionar conjuntos de **revisión** para obtener acceso a los datos de casos. Este rol no permite al usuario obtener una vista previa de los resultados de una búsqueda de colección asociada al caso o realizar otras tareas de administración de casos o búsqueda. Los usuarios con este rol solo pueden acceder a los datos de un conjunto de revisión.

### <a name="rms-decrypt"></a>Descifrado de RMS

Este rol permite a los usuarios ver mensajes de correo electrónico protegidos por derechos al obtener una vista previa de los resultados de la búsqueda y exportar mensajes de correo electrónico descifrados protegidos por derechos. Este rol también permite a los usuarios ver (y exportar) un archivo cifrado con una tecnología de cifrado de [Microsoft](encryption.md) cuando el archivo cifrado se adjunta a un mensaje de correo electrónico que se incluye en los resultados de una búsqueda de exhibición de documentos electrónicos. Además, este rol permite a los usuarios revisar y consultar datos adjuntos cifrados de correo electrónico que se agregan a un conjunto de revisión en eDiscovery avanzado. Para obtener más información acerca del descifrado en la exhibición de documentos electrónicos, vea Descifrado en las herramientas de exhibición de documentos electrónicos [de Microsoft 365](ediscovery-decryption.md).

### <a name="search-and-purge"></a>Buscar y purgar

Este rol permite a los usuarios realizar la eliminación masiva de datos que coinciden con los criterios de una búsqueda de contenido. Para obtener más información, vea Buscar y eliminar mensajes de correo electrónico [en su organización.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Más información

- **¿Por qué debería crear un administrador de exhibición de documentos electrónicos?** Tal como se explicó anteriormente, un administrador de exhibición de documentos electrónicos es miembro del Grupo de roles de administrador de exhibición de documentos electrónicos, que puede ver y tener acceso a todos los casos de exhibición de documentos electrónicos de la organización. Esta capacidad para tener acceso a todos los casos de exhibición de documentos electrónicos tiene dos fines importantes:

  - Si un usuario es el único miembro de un caso de exhibición de documentos electrónicos y abandona la organización, ningún usuario (ni siquiera los miembros del grupo de roles Administración de la organización ni otro miembro del grupo de roles Administrador de exhibición de documentos electrónicos) puede tener acceso a ese caso de exhibición de documentos electrónicos, ya que no es miembro del caso. En esta situación, no habría ninguna manera de tener acceso a los datos del caso. Pero como un administrador de exhibición de documentos electrónicos puede tener acceso a todos los casos de exhibición de documentos electrónicos de la organización, puede ver el caso y agregarse a sí mismo u otro administrador de exhibición de documentos electrónicos como miembro del caso.

  - Dado que un administrador de exhibición de documentos electrónicos puede ver y obtener acceso a todos los casos principales de eDiscovery y eDiscovery avanzado, pueden auditar y supervisar todos los casos y búsquedas de cumplimiento asociadas. Esto puede ayudar a evitar el uso incorrecto de búsquedas de cumplimiento o casos de exhibición de documentos electrónicos. Y como los administradores de exhibición de documentos electrónicos pueden acceder a información potencialmente confidencial en los resultados de una búsqueda de cumplimiento, debe limitar el número de personas que son administradores de exhibición de documentos electrónicos.

- **¿Puedo agregar un grupo como miembro del grupo de roles administrador de exhibición de documentos electrónicos?** Como se ha explicado anteriormente, puede agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos mediante el cmdlet **Add-RoleGroupMember** en PowerShell del Centro de seguridad & cumplimiento. Por ejemplo, puede ejecutar el siguiente comando para agregar un grupo de seguridad habilitado para correo al grupo de roles administrador de exhibición de documentos electrónicos. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Los grupos de distribución de Exchange y los Grupos de Microsoft 365 no son compatibles. Debe usar un grupo de seguridad habilitado para correo, que puede crear en Exchange Online PowerShell ejecutando `New-DistributionGroup -Type Security` . También puede crear un grupo de seguridad habilitado para correo (y agregar miembros) en el Centro de administración de Exchange o en el Centro de administración de Microsoft 365. Puede tardar hasta 60 minutos después de crearla para que una nueva seguridad habilitada para correo esté disponible para agregarla al grupo de roles administradores de exhibición de documentos electrónicos. 

    Además, como se ha indicado anteriormente, no puede hacer que un grupo de seguridad habilitado para correo sea un administrador de exhibición de documentos electrónicos mediante el cmdlet **Add-eDiscoveryCaseAdmin** en PowerShell del Centro de seguridad & cumplimiento. Solo puede agregar usuarios individuales como administradores de exhibición de documentos electrónicos.

    Tampoco puede agregar un grupo de seguridad habilitado para correo como miembro de un caso.
