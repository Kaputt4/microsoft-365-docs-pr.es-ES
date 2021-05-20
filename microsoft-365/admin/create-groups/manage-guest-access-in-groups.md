---
title: Administrar el acceso de los huéspedes en grupos de Microsoft 365
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
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571942"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Administrar el acceso de los huéspedes en grupos de Microsoft 365

De forma predeterminada, el acceso de invitados para grupos de Microsoft 365 está activado para su organización. Los administradores pueden controlar si permiten el acceso de los invitados a grupos para toda su organización o para grupos individuales.

Cuando está activado, los miembros del grupo pueden invitar a los usuarios invitados a un grupo de Microsoft 365 a través de Outlook en la Web. Las invitaciones se envían al propietario del grupo para su aprobación.

Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.

> [!Note]
> Yammer Enterprise redes que se encuentran en modo nativo o en la [geo de la UE](/yammer/manage-security-and-compliance/manage-data-compliance) no admiten invitados de red.
> Microsoft 365 Los grupos de Yammer conectados actualmente no admiten el acceso de invitados, pero puede crear grupos externos no conectados en la red Yammer. Consulte [Crear y administrar grupos externos en Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) para obtener instrucciones.

El acceso de invitados en grupos se utiliza a menudo como parte de un escenario más amplio que incluye SharePoint o Teams. Estos servicios tienen su propia configuración de uso compartido de invitados. Para obtener instrucciones completas sobre cómo configurar el uso compartido de invitados entre grupos, SharePoint y Teams, consulte:

- [Colaborar con invitados en un sitio](../../solutions/collaborate-in-site.md)
- [Colaborar con invitados en un equipo](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Administrar el acceso de los invitados a los grupos

Si desea habilitar o deshabilitar el acceso de invitados en grupos, puede hacerlo en el Centro de administración de Microsoft 365.

1. En el Centro de administración, vaya a **Mostrar toda** la configuración \> **de Configuración** \> **organización** y, en la pestaña **Servicios,** seleccione **grupos de Microsoft 365.**
  
2. En la página **Grupos de Microsoft 365,** elija si desea permitir que personas ajenas a la organización accedan a recursos del grupo o permita que los propietarios de grupos agreguen personas fuera de la organización a grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Agregue invitados a un grupo de Microsoft 365 desde el centro de administración

Si el invitado ya existe en el directorio, puede agregarlos a los grupos desde el Centro de administración de Microsoft 365. (Los grupos con pertenencia dinámica deben [administrarse en Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. En el Centro de administración, vaya a la página  >  **Grupos de grupos.**
  
2. Haga clic en el grupo al que desea agregar el invitado y seleccione **Ver todos y administrar miembros** en la pestaña **Miembros.** 
  
4. Seleccione **Agregar miembros** y elija el nombre del invitado que desea agregar.
    
5. Seleccione **Guardar**.

Si desea agregar un invitado directamente al directorio, puede [agregar Azure Active Directory usuarios de colaboración B2B en Azure Portal](/azure/active-directory/b2b/add-users-administrator).

Si desea editar cualquiera de la información de un invitado, puede [agregar o actualizar la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>Contenido relacionado

[Bloquear usuarios invitados de un grupo específico](../../solutions/per-group-guest-access.md) (artículo)

[Administrar la pertenencia a grupos en el centro de administración de Microsoft 365](add-or-remove-members-from-groups.md) (artículo)
  
[Azure Active Directory opiniones de acceso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artículo)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artículo)