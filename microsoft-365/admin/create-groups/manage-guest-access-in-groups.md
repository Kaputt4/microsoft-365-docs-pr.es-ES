---
title: Administrar el acceso de invitado en grupos de 365 de Microsoft
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
description: Obtenga información sobre cómo agregar invitados a un grupo de 365 de Microsoft, ver los usuarios invitados y usar PowerShell para controlar el acceso de invitados.
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753282"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Administrar el acceso de invitado en grupos de 365 de Microsoft

De forma predeterminada, el acceso de invitado para los grupos de Microsoft 365 está activado para su organización. Los administradores pueden controlar si se permite el acceso de invitado a grupos para toda la organización o para grupos individuales.

Cuando está activada, los miembros del grupo pueden invitar a los usuarios invitados a un grupo de Microsoft 365 a través de Outlook en la Web. Las invitaciones se envían al propietario del grupo para su aprobación.

Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.

> [!Note]
> Las redes de Yammer Enterprise que están en modo nativo o el geográfico de la [UE](https://go.microsoft.com/fwlink/?linkid=2107357) no admiten invitados de red.
> Los grupos de Yammer conectados a Microsoft 365 no son compatibles actualmente con el acceso de invitado, pero puede crear grupos externos no conectados en su red de Yammer. Consulte [crear y administrar grupos externos en Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) para obtener instrucciones.

El acceso de invitado en grupos suele usarse como parte de un escenario más amplio que incluye SharePoint o Teams. Estos servicios tienen su propia configuración de uso compartido de invitado. Para obtener instrucciones completas sobre cómo configurar el uso compartido de invitado en grupos, SharePoint y Teams, vea:

- [Colaborar con invitados en un sitio](../../solutions/collaborate-in-site.md)
- [Colaborar con invitados en un equipo](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Administrar grupos acceso de invitado

Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el centro de administración de 365 de Microsoft.

1. En el centro de administración, vaya a **Mostrar todas las** opciones de configuración de \> **Settings** \> la **organización** y, en la pestaña **servicios** , seleccione **Microsoft 365 Groups**.
  
2. En la página **Microsoft 365 Groups** , elija si desea permitir que los usuarios ajenos a la organización obtengan acceso a los recursos del grupo o que los propietarios del grupo agreguen personas fuera de la organización a los grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Agregar invitados a un grupo de Microsoft 365 desde el centro de administración

Si el invitado ya existe en su directorio, puede agregarlo a los grupos desde el centro de administración de Microsoft 365.
  
1. En el centro de administración, vaya a **la**página grupos de grupos  >  **Groups** .
  
2. Haga clic en el grupo al que desea agregar el invitado y seleccione **Ver todos y administrar miembros** en la pestaña **miembros** . 
  
4. Seleccione **Agregar miembros**y, a continuación, elija el nombre del invitado que quiera agregar.
    
5. Seleccione **Guardar**.

Si desea agregar un invitado directamente al directorio, puede [Agregar usuarios de colaboración B2B de Azure Active Directory en Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Si desea editar la información de algún invitado, puede [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="see-also"></a>Recursos adicionales

[Bloquear a usuarios invitados de un grupo específico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Administrar la pertenencia a grupos en el centro de administración de Microsoft 365](add-or-remove-members-from-groups.md)
  
[Revisiones de acceso de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
