---
title: Administrar el acceso de invitado en Microsoft 365 grupos
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Obtenga información sobre cómo agregar invitados a un grupo Microsoft 365, ver usuarios invitados y usar PowerShell para controlar el acceso de invitados.
ms.openlocfilehash: dd29775aebc9b5a6434e7ce5bdbd46b6a874d548b6a82f61f2e525f51b638c27
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53826494"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Administrar el acceso de invitado en Microsoft 365 grupos

De forma predeterminada, el acceso de invitado para Microsoft 365 grupos está activado para su organización. Los administradores pueden controlar si se permite el acceso de invitados a grupos para toda la organización o para grupos individuales.

Cuando está activado, los miembros del grupo pueden invitar a los usuarios invitados a un grupo Microsoft 365 a través Outlook web. Las invitaciones se envían al propietario del grupo para su aprobación.

Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.

> [!Note]
> Yammer Enterprise las redes que están en modo nativo o en la [GEO](/yammer/manage-security-and-compliance/manage-data-compliance) de la UE no admiten invitados de red.
> Microsoft 365 Los Yammer conectados no admiten actualmente el acceso de invitado, pero puede crear grupos externos no conectados en su red Yammer invitado. Consulte [Crear y administrar grupos externos en Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) para obtener instrucciones.

El acceso de invitado en grupos suele usarse como parte de un escenario más amplio que incluye SharePoint o Teams. Estos servicios tienen su propia configuración de uso compartido de invitados. Para obtener instrucciones completas para configurar el uso compartido de invitados entre grupos, SharePoint y Teams, vea:

- [Colaborar con invitados en un sitio](../../solutions/collaborate-in-site.md)
- [Colaborar con invitados en un equipo](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Administrar el acceso de invitado de grupos

Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el Centro de administración de Microsoft 365.

1. En el Centro de administración, vaya a **Mostrar** toda la configuración Configuración org y, en la pestaña \>  \>  Servicios, seleccione **Microsoft 365 grupos**  .
  
2. En la **página Microsoft 365 grupos,** elija si desea permitir que los usuarios externos a la organización accedan a los recursos de grupo o permitir que los propietarios de grupos agreguen personas fuera de la organización a los grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Agregar invitados a un grupo Microsoft 365 desde el Centro de administración

Si el invitado ya existe en el directorio, puede agregarlos a los grupos desde el Centro de administración de Microsoft 365. (Los grupos con pertenencia dinámica deben [administrarse Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. En el Centro de administración, vaya a la **página Grupos.**  >  
  
2. Haga clic en el grupo al que desea agregar el invitado y seleccione Ver todos y **administrar miembros** en la **pestaña** Miembros. 
  
4. Seleccione **Agregar miembros** y elija el nombre del invitado que desea agregar.
    
5. Seleccione **Guardar**.

Si desea agregar un invitado al directorio directamente, puede agregar Azure Active Directory usuarios de colaboración [B2B en Azure Portal](/azure/active-directory/b2b/add-users-administrator).

Si desea editar cualquiera de la información de un invitado, puede agregar o actualizar la información de perfil de un usuario [mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>Contenido relacionado

[Bloquear usuarios invitados de un grupo](../../solutions/per-group-guest-access.md) específico (artículo)\
[Administrar la pertenencia a grupos en el Centro de administración de Microsoft 365](add-or-remove-members-from-groups.md) (artículo)\
[Azure Active Directory de acceso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artículo)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artículo)