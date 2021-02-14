---
title: Crear, editar o eliminar una vista de usuario personalizada
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Aprenda a usar filtros para crear, editar o eliminar la vista de usuario personalizada en Microsoft 365.
ms.openlocfilehash: 598a167b9845f763ddab57d3c5ba36e431aa751c
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664579"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Crear, editar o eliminar una vista de usuario personalizada

Si es administrador global o de administración de usuarios de una suscripción a Microsoft 365 para empresas, puede crear vistas de usuario personalizadas para ver un subconjunto específico de usuarios. Estas vistas se sume al conjunto estándar de vistas. Puede crear, editar o eliminar vistas de usuario personalizadas y las vistas personalizadas que cree estarán disponibles para todos los administradores.
  
## <a name="custom-user-views-in-the-admin-center"></a>Vistas de usuario personalizadas en el centro de administración

::: moniker range="o365-worldwide"

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista de filtros que verán todos los administradores de su empresa cuando vayan a la página **Usuarios.**  Puede crear hasta 50 vistas personalizadas. 

::: moniker-end

::: moniker range="o365-germany"

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista Vistas que verán todos los administradores de su empresa cuando vayan a la página **Usuarios.**  Puede crear hasta 50 vistas personalizadas. 

::: moniker-end

::: moniker range="o365-21vianet"

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista Vistas que verán todos los administradores de su empresa cuando vayan a la página **Usuarios.**  Puede crear hasta 50 vistas personalizadas. 

::: moniker-end

> [!TIP]
>  Las vistas de usuario estándar se muestran de forma predeterminada en **la** lista desplegable Filtros. Los filtros estándar incluyen **Todos** los **usuarios,** Usuarios con **licencia,** Usuarios **invitados,** Inicio de sesión **permitido,** Inicio de sesión bloqueado **,** Usuarios sin **licencia,** Usuarios con **errores,** Administradores de facturación, Administradores **globales,** Administradores del departamento de soporte técnico, Administradores de servicio y Administradores de administración de **usuarios.**  No puede editar ni eliminar vistas estándar. 

Algunos aspectos a tener en cuenta sobre las vistas estándar: 

- Algunas vistas estándar muestran una lista desordenada si hay más de 2.000 usuarios en la lista. Para buscar usuarios específicos en esta lista, use el cuadro de búsqueda. 
- Si no compró Microsoft 365 a **Microsoft,** los administradores de facturación no aparecerán en la lista de vistas estándar. Para más información, vea [Asignar roles de administrador](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Elegir los filtros para la vista de usuario personalizada

Puede crear y editar las vistas personalizadas en el **panel filtro** personalizado. Si selecciona varias opciones de filtro, obtiene resultados que contienen usuarios que coinciden con todos los criterios seleccionados. En el siguiente ejemplo se muestra cómo crear una vista personalizada denominada "Usuarios canadienses" que muestre todos los usuarios de un dominio específico que están en Canadá. 

  
 **A: dominio** Si tiene varios dominios para su organización, puede elegir entre una lista desplegable de dominios que están disponibles. 
  
 **B: estado de inicio de sesión** Elija los usuarios que están permitidos o bloqueados. 
  
 **C: ubicación** Elija una ubicación de una lista desplegable de países. 
  
 **D: licencia de producto asignada** Elija una lista desplegable de licencias disponibles en su organización. Use este filtro para mostrar los usuarios que tienen asignada la licencia que seleccionó. Los usuarios también pueden tener licencias adicionales. 
  
También puede filtrar por detalles de perfil de usuario adicionales usados en su organización, como departamento, ciudad, estado o provincia, país o región, o puesto.
  
 **Otras condiciones:**
  
- **Solo usuarios sincronizados** Seleccione este cuadro para mostrar todos los usuarios que se han sincronizado con active Directory local, independientemente de si los usuarios se han activado o no. 
    
- **Usuarios con errores** Seleccione esta casilla para mostrar los usuarios que pueden tener errores de aprovisionamiento. 
    
- **Usuarios sin licencia** Seleccione esta casilla para buscar todos los usuarios a los que no se ha asignado una licencia. Los resultados de esta vista también pueden incluir usuarios que tienen un buzón de Exchange pero no tienen una licencia. Para realizar un seguimiento específico de esos usuarios, use el filtro usuarios sin licencia con **buzones o archivos de Exchange.** Los resultados de esta vista también pueden incluir usuarios que tienen un archivo de Exchange, pero no tienen una licencia.
    
- **Usuarios sin licencia con buzones o archivos de Exchange** Seleccione esta casilla para mostrar las cuentas de usuario que se crearon en Exchange Online y que tienen un buzón de Exchange, pero que no se asignaron a una licencia de Microsoft 365. Los resultados de este filtro incluyen usuarios que tienen o a los que se les asignó un archivo de Exchange. 

> [!NOTE]
> El **filtro de usuarios sin licencia con buzones de Exchange** funciona cuando:
1. El buzón se ha convertido recientemente de **compartido** a **usuario** y no tiene licencia.
2. El buzón se ha migrado recientemente a Microsoft 365, pero no se ha asignado una licencia.
3. El buzón se ha creado con PowerShell y no se ha asignado una licencia.
4. Se aprovisiona un nuevo buzón que se ha creado localmente con New-RemoteMailbox cmdlet para el usuario.
    
> [!TIP]
> Si crea una vista personalizada que devuelve más de 2.000 usuarios, la lista de usuarios resultante no se ordena. En este caso, use el cuadro de búsqueda para buscar usuarios o editar la vista personalizada para refinar la búsqueda. 
  
## <a name="create-a-custom-user-view"></a>Crear una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos.</a>
    
2. En la **página Usuarios activos,** seleccione **Filtros** y **nuevo filtro.**
  
3. En la **página Filtro** personalizado, escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, **seleccione Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.
    
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">activos.</a>  

2. En la **página Usuarios activos,** seleccione **Vistas** y agregar **vista personalizada.**
  
3. En la **página Vista** personalizada, escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, **seleccione Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.

::: moniker-end


::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">activos.</a> 

2. En la **página Usuarios activos,** seleccione **Vistas** y agregar **vista personalizada.**
  
3. En la **página Vista** personalizada, escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, **seleccione Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Editar o eliminar una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos.</a>
    
2. En la **página Usuarios activos,** seleccione **Filtro**, seleccione el filtro que desea cambiar y, a continuación, seleccione **Editar filtro.** 
    
    > [!TIP]
    > Solo puede editar vistas personalizadas. 
  
3. En la **página Filtro** personalizado, edite la información según sea necesario y, a continuación, **seleccione Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página seleccione **Eliminar**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">activos.</a>  

2. En la **página Usuarios activos,** seleccione **Vistas**, seleccione el filtro que desea cambiar y, a continuación, seleccione Editar **esta vista.** 
    
    > [!TIP]
    > Solo puede editar vistas personalizadas. 
  
3. En la **página Vista personalizada,** edite la información según sea necesario y, a continuación, **seleccione Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **Eliminar vista personalizada.** 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">activos.</a> 

2. En la **página Usuarios activos,** seleccione **Vistas**, seleccione el filtro que desea cambiar y, a continuación, seleccione Editar **esta vista.** 
    
    > [!TIP]
    > Solo puede editar vistas personalizadas. 
  
3. En la **página Vista personalizada,** edite la información según sea necesario y, a continuación, **seleccione Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **Eliminar vista personalizada.** 

::: moniker-end


     