---
title: Asignar permisos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Asigne los permisos necesarios para realizar tareas relacionadas con la exhibición de documentos electrónicos mediante el centro de seguridad & cumplimiento.
ms.openlocfilehash: 4c39dc3cd0d3c5d13d33330eca930e07227c38d3
ms.sourcegitcommit: 17a45261926dde1a7cd24e0ac516cfc49e453806
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374409"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento

Si desea que los usuarios usen cualquiera de las [herramientas relacionadas con la exhibición](ediscovery.md) de documentos electrónicos en el centro de seguridad & cumplimiento en Office 365 o en el centro de cumplimiento de Microsoft 365, tiene que asignarles los permisos adecuados. La forma más sencilla de hacerlo es agregar la persona que tiene el grupo de roles apropiado en la página de **permisos** del centro de seguridad & cumplimiento. En este tema se describen los permisos necesarios para realizar tareas relacionadas con la búsqueda de exhibición de documentos electrónicos y contenido mediante el centro de seguridad & cumplimiento.
  
El grupo de roles principal relacionado con la exhibición de documentos electrónicos en el centro de seguridad & cumplimiento se llama **Administrador de exhibición**de documentos electrónicos. Hay dos subgrupos dentro de este grupo de roles. 
  
- **administradores** de exhibición de documentos electrónicos: un administrador de exhibición de documentos electrónicos puede usar la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar ubicaciones de contenido en la organización y realizar diversas acciones relacionadas con la búsqueda, como los resultados de la búsqueda de la vista previa y la exportación. Los miembros también pueden crear y administrar casos principales de eDiscovery y casos avanzados de eDiscovery, agregar y quitar miembros de un caso, crear casos, ejecutar búsquedas asociadas a un caso y obtener acceso a datos de caso. los administradores de eDiscovery solo pueden acceder y administrar los casos que crean. No pueden acceder ni administrar los casos creados por otros administradores de exhibición de documentos electrónicos.
  
- **administradores de exhibición** de documentos electrónicos: un administrador de exhibición de documentos electrónicos es miembro del grupo de roles eDiscovery Manager y puede realizar las mismas tareas relacionadas con la búsqueda de contenido y la administración de casos que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de exhibición de documentos electrónicos puede:
  
  - Obtenga acceso a todos los casos que se enumeran en las páginas **eDiscovery** y **eDiscovery avanzado** del centro de seguridad & cumplimiento.

  - Obtenga acceso a los datos de caso en eDiscovery avanzado para cualquier caso de la organización.
  
  - Administrar cualquier caso de exhibición de documentos electrónicos después de que se agreguen como miembro del caso.
  
  Consulte la sección [More Information](#more-information) para ver los motivos por los que puede desear que los administradores de eDiscovery de su organización.

> [!NOTE]
> Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5 o Microsoft E5. Como alternativa, a los usuarios con una licencia E1 o E3 se les puede asignar una licencia de complemento E5. Los administradores, los responsables de cumplimiento normativo o el personal jurídico asignado a los casos como miembros y usan la exhibición avanzada de documentos electrónicos para recopilar, ver y analizar datos no necesitan una licencia E5. Para obtener más información acerca de las licencias, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://aka.ms/complianceSD).
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe ser miembro del grupo de roles de administración de la organización o tener asignado el rol de administración de roles para asignar permisos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento.
    
- Puede usar el cmdlet [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) en seguridad & PowerShell del centro de cumplimiento para agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de eDiscovery en el grupo de roles eDiscovery Manager. Sin embargo, no puede Agregar un grupo de seguridad habilitado para correo al subgrupo administradores de eDiscovery. Para obtener información detallada, consulte la sección [más información](#more-information) . 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión con su cuenta profesional o educativa.
    
3. En el panel izquierdo del centro de seguridad y cumplimiento, seleccione **permisos**y, después, active la casilla situada junto a **Administrador de exhibición**de documentos electrónicos.
    
4. En la página flotante del **Administrador de exhibición** de documentos electrónicos, realice una de las siguientes acciones en función de los permisos de exhibición de documentos electrónicos que desee asignar. 
  
    **Para convertir un usuario en Administrador de exhibición** de documentos electrónicos: Junto a **Administrador de exhibición**de documentos electrónicos, seleccione **Editar**. En la sección **elegir administrador de exhibición** de documentos electrónicos, seleccione el hipervínculo **elegir eDiscovery Manager** y, a continuación, seleccione ![ Agregar icono ](../media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, seleccione **Agregar**. Cuando haya terminado de agregar usuarios, seleccione **listo**. A continuación, en la página de **edición elegir administrador de exhibición** de documentos electrónicos, seleccione **Guardar** para guardar los cambios en la pertenencia al administrador de exhibición de documentos electrónicos.
  
    **Para convertir un usuario en Administrador de exhibición** de documentos electrónicos: Junto a **Administrador de exhibición**de documentos electrónicos, seleccione **Editar**. En la **sección elegir administrador de eDiscovery** , en **administradores de exhibición**de documentos electrónicos, seleccione **elegir administrador de exhibición**de documentos electrónicos, seleccione **Editar**y, a continuación, seleccione ![ Agregar icono ](../media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de **exhibición**de documentos electrónicos y, a continuación, **Agregar**. Cuando haya terminado de agregar usuarios, seleccione **listo**. A continuación, en la página de **edición de elegir administrador de exhibición** de documentos electrónicos, seleccione **Guardar** para guardar los cambios en la pertenencia del administrador de exhibición de documentos electrónicos.
      
> [!NOTE]
> También puede usar el cmdlet **Add-eDiscoveryCaseAdmin** para que un usuario sea administrador de exhibición de documentos electrónicos. Sin embargo, al usuario se le debe asignar el rol de administración de casos antes de que pueda usar este cmdlet para convertirlo en Administrador de exhibición de documentos electrónicos. Para obtener más información, vea [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
En la página **permisos** del centro de seguridad & cumplimiento, también puede asignar permisos relacionados con la exhibición de documentos electrónicos agregándolos a los grupos de roles administrador de cumplimiento, administración de la organización y revisor. Para obtener una descripción de los roles RBAC relacionados con la exhibición de documentos electrónicos asignados a cada uno de estos grupos de roles, consulte la sección [roles de RBAC relacionados con la exhibición](#rbac-roles-related-to-ediscovery) de documentos electrónicos. 

## <a name="rbac-roles-related-to-ediscovery"></a>Roles RBAC relacionados con la exhibición de documentos electrónicos

En la siguiente tabla se enumeran los roles RBAC relacionados con la exhibición de documentos electrónicos en el centro de seguridad & cumplimiento e indica los grupos de roles integrados a los que se asigna cada rol de forma predeterminada. 
    
|**Rol**|**Administrador de cumplimiento**|**Administrador de exhibición de documentos electrónicos & administrador**|**Administración de organizaciones**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Administración de casos <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Comunicación <br/> | <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Búsqueda de cumplimiento <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Exportar <br/> | <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Preview <br/>  | <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Revisar <br/>  | <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|Descifrado de RMS <br/>  ||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Búsqueda y depuración <br/> | <br/> | <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
En las secciones siguientes se describe cada uno de los roles RBAC relacionados con la exhibición de documentos electrónicos que aparecen en la tabla anterior.

### <a name="case-management"></a>Administración de casos

Este rol permite a los usuarios crear, editar, eliminar y controlar el acceso a los casos principales de eDiscovery y de eDiscovery avanzado en el centro de seguridad & cumplimiento. Como se ha explicado anteriormente, a un usuario se le debe asignar el rol de administración de casos antes de poder usar el cmdlet **Add-eDiscoveryCaseAdmin** para convertirlo en Administrador de exhibición de documentos electrónicos.

Para más información, consulte lo siguiente:

- [Introducción a Core eDiscovery](get-started-core-ediscovery.md)

- [Introducción a eDiscovery avanzado](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicación

Este rol permite a los usuarios administrar todas las comunicaciones con los custodios identificados en un caso de exhibición avanzada de documentos electrónicos. Esto incluye la creación de notificaciones de retención, recordatorios de retenciones y escalaciones a la administración. El usuario también puede realizar un seguimiento de la confirmación del custodio de las notificaciones de retención y administrar el acceso al portal de custodios que usa cada custodio para realizar un seguimiento de las comunicaciones para los casos en los que se identificaron como custodio.

Para obtener más información, consulte [trabajar con comunicaciones en la exhibición avanzada de](managing-custodian-communications.md)documentos electrónicos.

### <a name="compliance-search"></a>Búsqueda de cumplimiento

Este rol permite a los usuarios ejecutar la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar en buzones de correo y carpetas públicas, sitios de SharePoint Online, sitios de OneDrive para la empresa, conversaciones de Skype empresarial, grupos de 365 de Microsoft Teams y grupos de Yammer. Este rol permite al usuario obtener una estimación de los resultados de la búsqueda y crear informes de exportación, pero se necesitan roles adicionales para iniciar acciones de búsqueda de contenido, como la vista previa, la exportación o la eliminación de los resultados de la búsqueda.

Los usuarios que tienen asignado el rol de búsqueda de cumplimiento pero que no tienen el rol de vista previa pueden obtener una vista previa de los resultados de una búsqueda en la que un usuario que tenga asignada la función de vista previa haya iniciado la acción de vista previa. El usuario sin el rol vista previa puede obtener una vista previa de los resultados de hasta dos semanas después de que se haya creado la acción de vista previa inicial.

De forma similar, los usuarios a los que se les ha asignado el rol de búsqueda de cumplimiento pero que no tienen la función exportar pueden descargar los resultados de una búsqueda en la que la acción de exportación ha sido iniciada por un usuario que tiene asignada la función exportar. El usuario sin el rol exportar puede descargar los resultados de una búsqueda durante un máximo de dos semanas después de que se haya creado la acción de exportación inicial. Después de eso, no pueden descargar los resultados a menos que un usuario con el rol exportar reinicie la exportación.

Para obtener más información, consulte [búsqueda de contenido en Office 365](content-search.md).

### <a name="custodian"></a>Custodian

Este rol permite a los usuarios identificar y administrar custodios para casos de eDiscovery avanzados y usar la información de Azure Active Directory y otros orígenes para buscar orígenes de datos asociados con los custodios. El usuario puede asociar otros orígenes de datos como buzones de correo, sitios de SharePoint y equipos con custodios en un caso. El usuario también puede realizar una retención legal en los orígenes de datos asociados con los custodios para conservar el contenido en el contexto de un caso.

Para obtener más información, consulte [work with custodios in Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Exportar

El rol permite a los usuarios exportar los resultados de una búsqueda de contenido a un equipo local. También les permite preparar los resultados de búsqueda para el análisis en eDiscovery avanzado. 

Para obtener más información acerca de cómo exportar resultados de búsqueda, vea [exportar resultados de búsqueda del centro de seguridad & cumplimiento](export-search-results.md).

### <a name="hold"></a>Hold

Este rol permite a los usuarios poner contenido en retención en buzones de correo, carpetas públicas, sitios, conversaciones de Skype empresarial y grupos de 365 de Microsoft. Cuando el contenido está en espera, los propietarios de contenido pueden modificar o eliminar el contenido original, pero el contenido se conservará hasta que se quite la retención o hasta que expire la duración de retención. 

Para obtener más información acerca de las suspensiones, consulte:

- [Crear una suspensión en la exhibición de documentos electrónicos principal](create-ediscovery-holds.md) 

- [Crear una retención en eDiscovery avanzado](add-custodians-to-case.md#step-4-place-custodians-on-hold)

### <a name="preview"></a>Preview

Este rol permite a los usuarios ver una lista de elementos devueltos de una búsqueda de contenido. También pueden abrir y ver cada elemento de la lista para ver su contenido.

### <a name="review"></a>Revisar

Esta función permite a los usuarios acceder a datos de casos en [eDiscovery avanzado (Classic)](office-365-advanced-ediscovery.md) (también conocido como *eDiscovery avanzado v1*). El objetivo principal de este rol es proporcionar a los usuarios acceso a la exhibición de documentos electrónicos (Classic) avanzada. Los usuarios que tienen asignado este rol pueden ver y abrir la lista de casos en la página de **exhibición** de documentos electrónicos en el centro de seguridad & cumplimiento del que son miembros. Una vez que el usuario tiene acceso a un caso en el centro de seguridad & cumplimiento, puede seleccionar **cambiar a eDiscovery avanzado** para acceder y analizar los datos del caso en la exhibición avanzada de documentos electrónicos (Classic). Este rol no permite al usuario obtener una vista previa de los resultados de una búsqueda de contenido asociada con el caso o realizar otras tareas de búsqueda de contenido o de administración de casos.

> [!NOTE]
> En este momento, los usuarios a los que se les asigna la función Review (o que es miembro del grupo de roles Reviewer) no pueden acceder a datos en [eDiscovery avanzado en Microsoft 365](overview-ediscovery-20.md) (también conocido como *eDiscovery avanzado V2*). Para agregar miembros a un caso en eDiscovery avanzado v2 para que puedan revisar los datos de caso, un usuario debe ser miembro del grupo de roles eDiscovery Manager.

### <a name="rms-decrypt"></a>Descifrado de RMS

Este rol permite a los usuarios descifrar mensajes de correo electrónico protegidos por derechos al exportar los resultados de la búsqueda o preparar los resultados de búsqueda para analizarlos en eDiscovery avanzado. Para obtener más información acerca del descifrado de los resultados de búsqueda durante la exportación, consulte [exportar resultados de búsqueda de contenido](export-search-results.md).

### <a name="search-and-purge"></a>Búsqueda y depuración

Este rol permite a los usuarios realizar la eliminación masiva de datos que coinciden con los criterios de una búsqueda de contenido. Para obtener más información, vea [Buscar y eliminar mensajes de correo electrónico de la organización](search-for-and-delete-messages-in-your-organization.md). 

## <a name="more-information"></a>Más información

- **¿Por qué debería crear un administrador de exhibición de documentos electrónicos? ** Tal como se explicó anteriormente, un administrador de exhibición de documentos electrónicos es miembro del Grupo de roles de administrador de exhibición de documentos electrónicos, que puede ver y tener acceso a todos los casos de exhibición de documentos electrónicos de la organización. Esta capacidad para tener acceso a todos los casos de exhibición de documentos electrónicos tiene dos fines importantes: 

  - Si un usuario es el único miembro de un caso de exhibición de documentos electrónicos y abandona la organización, ningún usuario (ni siquiera los miembros del grupo de roles Administración de la organización ni otro miembro del grupo de roles Administrador de exhibición de documentos electrónicos) puede tener acceso a ese caso de exhibición de documentos electrónicos, ya que no es miembro del caso. En esta situación, no habría ninguna manera de tener acceso a los datos del caso. Pero como un administrador de eDiscovery puede acceder a todos los casos de eDiscovery de la organización, pueden ver el caso y agregarse a sí mismos o a otro administrador de eDiscovery como miembro del caso.

  - Dado que un administrador de eDiscovery puede ver y tener acceso a todos los casos principales de eDiscovery y eDiscovery, puede auditar y supervisar todos los casos y las búsquedas de cumplimiento asociadas. Esto puede ayudar a evitar cualquier uso incorrecto de las búsquedas de cumplimiento o los casos de exhibición de documentos electrónicos. Y, dado que los administradores de eDiscovery pueden tener acceso a información potencialmente confidencial en los resultados de una búsqueda de cumplimiento, debe limitar el número de usuarios que son administradores de eDiscovery.

- **¿Puedo agregar un grupo como miembro del grupo de roles eDiscovery Manager?** Como se ha explicado anteriormente, puede Agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de eDiscovery en el grupo de roles administrador de eDiscovery mediante el cmdlet **Add-RoleGroupMember** en el PowerShell del centro de cumplimiento de & de seguridad. Por ejemplo, puede ejecutar el siguiente comando para agregar un grupo de seguridad habilitado para correo al grupo de roles eDiscovery Manager. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Los grupos de distribución de Exchange y los grupos de Microsoft 365 no son compatibles. Debe usar un grupo de seguridad habilitado para correo, que puede crear en Exchange Online PowerShell con el `New-DistributionGroup -Type Security` comando. También puede crear un grupo de seguridad habilitado para correo (y agregar miembros) en el centro de administración de Exchange o en el centro de administración de Microsoft 365. Puede tardar hasta 60 minutos después de crear una nueva seguridad habilitada para correo que esté disponible para agregarla al grupo de roles eDiscovery Managers. 

    Además, como se mencionó anteriormente, no puede hacer que un grupo de seguridad habilitado para correo sea un administrador de eDiscovery usando el cmdlet **Add-eDiscoveryCaseAdmin** en el PowerShell del centro de cumplimiento de & de seguridad. Solo puede Agregar usuarios individuales como administradores de exhibición de documentos electrónicos.

    Tampoco puede Agregar un grupo de seguridad habilitado para correo como miembro de un caso.
