---
title: Administrar el acceso de invitado en grupos de Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Obtenga información sobre cómo agregar invitados a un grupo de Microsoft 365, ver invitados y usar PowerShell para controlar el acceso de invitado.
ms.openlocfilehash: 59ec932aea516107f08570f899987c4d619aa66b
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084221"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Administrar el acceso de invitado en grupos de Microsoft 365

De forma predeterminada, el acceso de invitado para grupos de Microsoft 365 está activado para su organización. Los administradores pueden controlar si se permite el acceso de invitado a grupos para toda su organización o para grupos individuales.

Cuando está activado, los miembros del grupo pueden invitar a invitados a un grupo de Microsoft 365 a través de Outlook on Web. Las invitaciones se envían al propietario del grupo para su aprobación.

Una vez aprobado, el invitado se agrega al directorio y al grupo.

> [!Note]
> Yammer Enterprise redes que están en modo nativo o la [geolocalía de la UE](/yammer/manage-security-and-compliance/manage-data-compliance) no admiten invitados de red.
> Los grupos de Yammer conectados de Microsoft 365 no admiten actualmente el acceso de invitado, pero puede crear grupos externos no conectados en la red de Yammer. Consulte [Creación y administración de grupos externos en Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) para obtener instrucciones.

El acceso de invitado en grupos se usa a menudo como parte de un escenario más amplio que incluye SharePoint o Teams. Estos servicios tienen su propia configuración de uso compartido de invitados. Para obtener instrucciones completas para configurar el uso compartido de invitados entre grupos, SharePoint y Teams, consulte:

- [Colaborar con invitados en un sitio](../../solutions/collaborate-in-site.md)
- [Colaborar con invitados en un equipo](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Administración del acceso de invitado de grupos

Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**grupos**</a>.

1. En el Centro de administración, vaya a **Mostrar toda** \> la **configuración Configuración** \> **Configuración De la organización** y, en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">pestaña **Servicios**</a>, seleccione **Grupos de Microsoft 365**.
  
2. En la página **Grupos de Microsoft 365**, elija si desea permitir que personas ajenas a su organización accedan a los recursos del grupo o permitir que los propietarios del grupo agreguen personas ajenas a la organización a grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Agregar invitados a un grupo de Microsoft 365 desde el Centro de administración

Si el invitado ya existe en el directorio, puede agregarlo a los grupos desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Centro de administración de Microsoft 365</a>. (Los grupos con pertenencia dinámica deben [administrarse en Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule)).
  
1. En el centro de administración, vaya a **Grupos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**.**</a>
  
2. Haga clic en el grupo al que desea agregar el invitado y seleccione **Ver todos los miembros y administrarlos** en la pestaña **Miembros** . 
  
4. Seleccione **Agregar miembros** y elija el nombre del invitado que desea agregar.
    
5. Seleccione **Guardar**.

Si desea agregar un invitado directamente al directorio, puede [agregar usuarios de colaboración B2B de Azure Active Directory en el Azure Portal](/azure/active-directory/b2b/add-users-administrator).

Si desea editar cualquiera de la información de un invitado, puede [agregar o actualizar la información de perfil de un usuario mediante Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>Contenido relacionado

[Bloquear invitados de un grupo específico](../../solutions/per-group-guest-access.md) (artículo)\
[Administrar la pertenencia a grupos en el Centro de administración de Microsoft 365](add-or-remove-members-from-groups.md) (artículo)\
[Revisiones de acceso de Azure Active Directory](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artículo)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artículo)
