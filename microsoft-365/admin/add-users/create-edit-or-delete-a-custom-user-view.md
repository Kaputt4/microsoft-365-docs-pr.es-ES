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
ms.openlocfilehash: b4177a561d13d76f6d5a0a1077fe8037d469ee48
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683228"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Crear, editar o eliminar una vista de usuario personalizada

Si es administrador global o de administración de usuarios de una suscripción Microsoft 365 para empresas, puede crear vistas de usuario personalizadas para ver un subconjunto específico de usuarios. Estas vistas son además del conjunto estándar de vistas. Puede crear, editar o eliminar vistas de usuario personalizadas y las vistas personalizadas que cree estarán disponibles para todos los administradores.
  
## <a name="custom-user-views-in-the-admin-center"></a>Vistas de usuario personalizadas en el Centro de administración

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista de filtros que verán todos los administradores de su **empresa** cuando vayan a la página Usuarios.  Puede crear hasta 50 vistas personalizadas. 

> [!TIP]
>  Las vistas de usuario estándar se muestran de forma predeterminada en la **lista** desplegable Filtros. Los filtros estándar incluyen **Todos** los usuarios **,** Usuarios con **licencia,** Usuarios **invitados,** Inicio de sesión **permitido,** Inicio de sesión bloqueado **,** **Usuarios** sin **licencia,** Usuarios con **errores,** Administradores de facturación **,** Administradores globales, Administradores del departamento de soporte técnico, Administradores de **servicio** y Administradores de administración de **usuarios.** No puede editar ni eliminar vistas estándar. 

Algunas cosas que debe tener en cuenta acerca de las vistas estándar: 

- Algunas vistas estándar muestran una lista sin selección si hay más de 2.000 usuarios en la lista. Para buscar usuarios específicos en esta lista, use el cuadro de búsqueda. 
- Si no compraste Microsoft 365 **microsoft,** los administradores de facturación no aparecerán en la lista de vistas estándar. Para más información, vea [Asignar roles de administrador](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Elegir los filtros para la vista de usuario personalizada

Puede crear y editar las vistas personalizadas en el **panel Filtro** personalizado. Si selecciona varias opciones de filtro, obtiene resultados que contienen usuarios que coinciden con todos los criterios seleccionados. En el ejemplo siguiente se muestra cómo crear una vista personalizada denominada "Usuarios canadienses" que muestre todos los usuarios de un dominio específico que se encuentran en Canadá. 

  
 **A - Dominio** Si tiene varios dominios para su organización, puede elegir entre una lista desplegable de dominios que están disponibles. 
  
 **B: estado de inicio de sesión** Elija los usuarios que están permitidos o bloqueados. 
  
 **C - Ubicación** Elija una ubicación de una lista desplegable de países. 
  
 **D: licencia de producto asignada** Elija entre una lista desplegable de licencias que están disponibles en su organización. Use este filtro para mostrar a los usuarios que tienen asignada la licencia que seleccionó. Los usuarios también pueden tener licencias adicionales. 
  
También puede filtrar por detalles de perfil de usuario adicionales usados en su organización, como departamento, ciudad, estado o provincia, país o región, o puesto de trabajo.
  
 **Otras condiciones:**
  
- **Solo usuarios sincronizados** Seleccione este cuadro para mostrar todos los usuarios que se han sincronizado con Active Directory local, independientemente de si los usuarios se han activado o no. 
    
- **Usuarios con errores** Seleccione este cuadro para mostrar a los usuarios que pueden tener errores de aprovisionamiento. 
    
- **Usuarios sin licencia** Seleccione este cuadro para buscar todos los usuarios a los que no se les ha asignado una licencia. Los resultados de esta vista también pueden incluir usuarios que tienen un buzón Exchange pero no tienen una licencia. Para realizar un seguimiento específico de esos usuarios, use el filtro Usuarios sin licencia con Exchange **buzones o archivos**. Los resultados de esta vista también pueden incluir usuarios que tienen un archivo Exchange, pero que no tienen una licencia.
    
- **Usuarios sin licencia con Exchange buzones o archivos** Seleccione este cuadro para mostrar las cuentas de usuario que se crearon en Exchange Online y tienen un buzón Exchange, pero no se les asignó una licencia Microsoft 365 usuario. Los resultados de este filtro incluyen usuarios que tienen o a los que se les asignó un Exchange archivo. 

> [!NOTE]
> Los **usuarios sin licencia con Exchange de buzones** de correo funciona cuando:
1. El buzón se ha convertido recientemente de **compartido** a **usuario** y no tiene licencia.
2. El buzón se ha migrado recientemente a Microsoft 365 pero no se ha asignado una licencia.
3. El buzón se ha creado con PowerShell y no se ha asignado una licencia.
4. Un nuevo buzón que se ha creado localmente con un cmdlet New-RemoteMailbox se aprovisiona para el usuario.
    
> [!TIP]
> Si crea una vista personalizada que devuelve más de 2.000 usuarios, la lista de usuarios resultante no se ordenará. En este caso, use el cuadro de búsqueda para buscar usuarios o editar la vista personalizada para refinar la búsqueda. 
  
## <a name="create-a-custom-user-view"></a>Crear una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el Centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuarios activos.</a>
  
::: moniker-end

::: moniker range="o365-germany"

1. En el Centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">usuarios activos.</a> 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el Centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">usuarios activos.</a>  

::: moniker-end
    
2. En la **página Usuarios activos,** seleccione **Filtros** y **nuevo filtro.**
  
3. En la **página Filtro** personalizado, escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, **seleccione Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.

## <a name="edit-or-delete-a-custom-user-view"></a>Editar o eliminar una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el Centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuarios activos.</a>

::: moniker-end

::: moniker range="o365-germany"

1. En el Centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">usuarios activos.</a> 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el Centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">usuarios activos.</a> 

::: moniker-end 
    
2. En la **página Usuarios activos,** seleccione **Filtrar**, seleccione el filtro que desea cambiar y, a continuación, seleccione **Editar filtro**. 
    
    > [!TIP]
    > Solo puede editar vistas personalizadas. 
  
3. En la **página Filtro** personalizado, edite la información según sea necesario y, a continuación, **seleccione Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página seleccione **Eliminar**. 

## <a name="related-content"></a>Contenido relacionado

[Información general sobre el Microsoft 365 de administración](../../business-video/admin-center-overview.md) (vídeo)\
[Acerca de los roles de administrador](../add-users/about-admin-roles.md) (vídeo)\
[Personalizar el Microsoft 365 de la organización](../setup/customize-your-organization-theme.md) (artículo)


     