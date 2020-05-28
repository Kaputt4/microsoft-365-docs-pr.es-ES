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
description: Obtenga información sobre cómo usar filtros para crear, editar o eliminar la vista de usuario personalizada en Microsoft 365.
ms.openlocfilehash: faea21f0e5142d197cc2b90d6ade99490f9f88e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387218"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a>Crear, editar o eliminar una vista de usuario personalizada en Office 365

Si es administrador global o de administración de usuarios de Office 365, puede crear vistas de usuario personalizadas para ver un subconjunto específico de usuarios. Estas vistas se agregan al conjunto estándar de vistas que se incluye con Office 365. Puede crear, editar o eliminar vistas de usuario personalizadas y las vistas personalizadas que cree estarán disponibles para todos los administradores.

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a>Vistas de usuario personalizadas en el centro de administración

::: moniker range="o365-worldwide"

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista de **filtros** que verán todos los administradores de la compañía cuando vayan a la página **usuarios** . Puede crear hasta 50 vistas personalizadas. 

::: moniker-end

::: moniker range="o365-germany"

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista **vistas** que verán todos los administradores de la compañía cuando vayan a la página **usuarios** . Puede crear hasta 50 vistas personalizadas. 

::: moniker-end

::: moniker range="o365-21vianet"

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se mostrarán en la lista **vistas** que verán todos los administradores de la compañía cuando vayan a la página **usuarios** . Puede crear hasta 50 vistas personalizadas. 

::: moniker-end

> [!TIP]
>  Las vistas de usuario estándar se muestran de forma predeterminada en la lista desplegable **filtros** . Los filtros estándar incluyen **todos los usuarios**, **los usuarios con licencia**, **los usuarios invitados**, el **Inicio de sesión permitido**, **el inicio de sesión bloqueado**, los usuarios sin licencia, **los usuarios con errores, los**administradores de **facturación**, los **administradores globales**, **los**administradores del **Departamento de soporte técnico**, los administradores de **servicios**y los administradores de **Administración de usuarios**. No puede editar ni eliminar vistas estándar. 

Algunos aspectos que se deben tener en cuenta sobre las vistas estándar: 

- Algunas vistas estándar muestran una lista sin ordenar si hay más de 2.000 usuarios en la lista. Para buscar usuarios específicos en esta lista, use el cuadro de búsqueda. 
- Si no ha adquirido Microsoft 365 de Microsoft, los **administradores de facturación** no aparecen en la lista de vistas estándar. Para más información, vea [Asignar roles de administrador](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Elegir los filtros para la vista de usuario personalizada

Puede crear y editar las vistas personalizadas en el panel de **filtros personalizado** . Si selecciona varias opciones de filtro, obtendrá resultados que contienen usuarios que cumplen todos los criterios seleccionados. En el ejemplo siguiente se muestra cómo crear una vista personalizada denominada "usuarios de Canadá" que muestra todos los usuarios de un dominio específico que se encuentran en Canadá. 

  
 **A-dominio** Si tiene varios dominios para su organización, puede elegir entre una lista desplegable de dominios que están disponibles. 
  
 **Estado de inicio de sesión B** Elija los usuarios que están permitidos o bloqueados. 
  
 **Ubicación C** Elija una ubicación en una lista desplegable de países. 
  
 **Licencia de producto asignada D** Elija entre una lista desplegable de licencias disponibles en su organización. Use este filtro para mostrar los usuarios que tienen asignada la licencia que ha seleccionado. Los usuarios también pueden tener licencias adicionales. 
  
También puede filtrar por los detalles de Perfil de usuario adicionales que se usan en su organización, como Departamento, ciudad, estado o provincia, país o región o puesto.
  
 **Otras condiciones:**
  
- **Solo usuarios sincronizados** Seleccione este cuadro para mostrar todos los usuarios que se han sincronizado con Active Directory local, independientemente de si los usuarios se han activado o no. 
    
- **Usuarios con errores** Seleccione este cuadro para mostrar los usuarios que pueden tener errores de aprovisionamiento. 
    
- **Usuarios sin licencia** Seleccione esta casilla para buscar todos los usuarios a los que no se ha asignado una licencia. Los resultados de esta vista también pueden incluir a los usuarios que tienen un buzón de Exchange pero que no tienen una licencia. Para realizar un seguimiento de esos usuarios específicamente, use el filtro **usuarios sin licencia con archivos o buzones de Exchange**. Los resultados de esta vista también pueden incluir usuarios que tienen un archivo de Exchange, pero que no tienen una licencia.
    
- **Usuarios sin licencia con archivos o buzones de Exchange** Seleccione este cuadro para mostrar las cuentas de usuario que se crearon en Exchange Online y que tienen un buzón de Exchange, pero no se les asignó una licencia de Microsoft 365. Los resultados de este filtro incluyen a los usuarios que tienen o están asignados a un archivo de Exchange. 

> [!NOTE]
> El filtro de **usuarios sin licencia con buzones de Exchange** funciona cuando:
1. El buzón se ha convertido recientemente de **compartido** a **usuario** y no tiene licencia.
2. El buzón de correo se migró recientemente a Microsoft 365, pero no se le ha asignado una licencia.
3. El buzón de correo se ha creado con PowerShell y no se ha asignado una licencia.
4. Se aprovisionará un nuevo buzón de correo que se haya creado de forma local con un cmdlet New-RemoteMailbox para el usuario.
    
> [!TIP]
> Si crea una vista personalizada que devuelve más de 2.000 usuarios, la lista de usuarios resultante no se ordenará. En este caso, use el cuadro de búsqueda para buscar usuarios o editar la vista personalizada para refinar la búsqueda. 
  
## <a name="create-a-custom-user-view"></a>Crear una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
    
2. En la página **usuarios activos** , seleccione **filtros** y seleccione **nuevo filtro**.
  
3. En la página **filtro personalizado** , escriba el nombre del filtro, elija las condiciones para el filtro personalizado y, a continuación, seleccione **Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.
    
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. En la página **usuarios activos** , seleccione **vistas** y seleccione **Agregar vista personalizada**.
  
3. En la página **vista personalizada** , escriba el nombre del filtro, elija las condiciones para el filtro personalizado y, a continuación, seleccione **Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.

::: moniker-end


::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. En la página **usuarios activos** , seleccione **vistas** y seleccione **Agregar vista personalizada**.
  
3. En la página **vista personalizada** , escriba el nombre del filtro, elija las condiciones para el filtro personalizado y, a continuación, seleccione **Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Editar o eliminar una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
    
2. En la página **usuarios activos** , seleccione **filtrar**, seleccione el filtro que desee cambiar y, a continuación, seleccione **Editar filtro**. 
    
    > [!TIP]
    > Solo se pueden editar vistas personalizadas. 
  
3. En la página **filtro personalizado** , modifique la información según sea necesario y, a continuación, seleccione **Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **eliminar**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. En la página **usuarios activos** , seleccione **vistas**, seleccione el filtro que desee cambiar y, a continuación, seleccione **editar esta vista**. 
    
    > [!TIP]
    > Solo se pueden editar vistas personalizadas. 
  
3. En la página **vista personalizada** , modifique la información según sea necesario y, a continuación, seleccione **Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **eliminar vista personalizada**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. En la página **usuarios activos** , seleccione **vistas**, seleccione el filtro que desee cambiar y, a continuación, seleccione **editar esta vista**. 
    
    > [!TIP]
    > Solo se pueden editar vistas personalizadas. 
  
3. En la página **vista personalizada** , modifique la información según sea necesario y, a continuación, seleccione **Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **eliminar vista personalizada**. 

::: moniker-end


     