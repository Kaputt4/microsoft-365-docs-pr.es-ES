---
title: Administrar el acceso de invitado en grupos de Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Obtenga información sobre cómo agregar invitados a un grupo de Microsoft 365, ver usuarios invitados y usar PowerShell para controlar el acceso de invitados.
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753282"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Administrar el acceso de invitado en grupos de Microsoft 365

De forma predeterminada, el acceso de invitado para grupos de Microsoft 365 está activado para su organización. Los administradores pueden controlar si se va a permitir el acceso de invitado a grupos para toda la organización o para grupos individuales.

Cuando está activado, los miembros del grupo pueden invitar a usuarios invitados a un grupo de Microsoft 365 a través de Outlook en la Web. Las invitaciones se envían al propietario del grupo para su aprobación.

Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.

> [!Note]
> Las redes de Yammer Enterprise que están en modo nativo o [ENE Geo](https://go.microsoft.com/fwlink/?linkid=2107357) no admiten invitados de red.
> Los grupos de Yammer conectados a Microsoft 365 actualmente no admiten el acceso de invitado, pero puede crear grupos externos no conectados en la red de Yammer. Vea [Crear y administrar grupos externos en Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) para obtener instrucciones.

El acceso de invitado en grupos se suele usar como parte de un escenario más amplio que incluye SharePoint o Teams. Estos servicios tienen su propia configuración de uso compartido de invitados. Para obtener instrucciones completas para configurar el uso compartido de invitados entre grupos, SharePoint y Teams, vea:

- [Colaborar con invitados en un sitio](../../solutions/collaborate-in-site.md)
- [Colaborar con invitados en un equipo](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Administrar el acceso de invitado de grupos

Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el Centro de administración de Microsoft 365.

1. En el centro de administración, vaya **a Mostrar** toda la configuración de la organización de configuración y, en la pestaña \>  \>  Servicios, seleccione Grupos de **Microsoft 365.** 
  
2. En la página Grupos de **Microsoft 365,** elija si desea permitir que los usuarios externos a su organización accedan a los recursos del grupo o permitir que los propietarios de grupos agreguen a grupos a personas fuera de su organización.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Agregar invitados a un grupo de Microsoft 365 desde el Centro de administración

Si el invitado ya existe en el directorio, puede agregarlos a los grupos desde el Centro de administración de Microsoft 365.
  
1. En el centro de administración, vaya a la **página**  >  **Grupos.**
  
2. Haga clic en el grupo al que desea agregar el invitado y seleccione Ver todos y **administrar miembros** en la **pestaña** Miembros. 
  
4. Seleccione **Agregar miembros** y elija el nombre del invitado que desea agregar.
    
5. Seleccione **Guardar**.

Si desea agregar un invitado al directorio directamente, puede agregar usuarios de colaboración [B2B](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)de Azure Active Directory en Azure Portal.

Si desea editar cualquiera de la información de un invitado, puede agregar o actualizar la información de perfil de un usuario [con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>Vea también

[Bloquear usuarios invitados de un grupo específico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Administrar la pertenencia a grupos en el Centro de administración de Microsoft 365](add-or-remove-members-from-groups.md)
  
[Revisiones de acceso de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
