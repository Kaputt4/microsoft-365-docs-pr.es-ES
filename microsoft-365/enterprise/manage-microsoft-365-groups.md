---
title: Administrar grupos de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- scotvorg
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar grupos de Microsoft 365.
ms.openlocfilehash: 28af0d9581753e1852c0274feb92123ec70b23fd
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185477"
---
# <a name="manage-microsoft-365-groups"></a>Administrar grupos de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede administrar grupos de Microsoft 365 de varias maneras diferentes, en función de la configuración. Puede administrar cuentas de usuario en el [Centro de administración de Microsoft 365](/admin), PowerShell, en Servicios de dominio de Active Directory (AD DS) o en el Centro de administración de [Azure Active Directory (Azure AD).](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Planear dónde y cómo administrará los grupos

Dónde y cómo puede administrar las cuentas de usuario depende del modelo de identidad que quiera usar para Microsoft 365. Los dos modelos generales son solo en la nube e híbridos.
  
### <a name="cloud-only"></a>Solo de nube

Cree y administre grupos con:

- [El Centro de administración de Microsoft 365](/admin)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Centro de administración de Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Híbrido

Los grupos de AD DS se sincronizan con Microsoft 365 desde AD DS, por lo que debe usar herramientas de AD DS locales para administrar estos grupos.

También puede crear y administrar grupos de Azure AD independientes de los grupos de AD DS, pero que pueden contener usuarios y grupos de AD DS. En este caso, puede usar:

- [El Centro de administración de Microsoft 365](/admin)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Centro de administración de Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Permitir a los usuarios crear y administrar sus propios grupos

Azure AD permite grupos que pueden administrar los propietarios de grupos en lugar de los administradores de TI. Conocida como *administración autoservicio de grupos*, esta característica permite a los propietarios del grupo que no están asignados a un rol de administrador crear y administrar grupos de seguridad. 

Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.

>[!Note]
>La administración de grupos de autoservicio está disponible solo para grupos de seguridad de Azure AD y Microsoft 365. No está disponible para grupos habilitados para correo, listas de distribución ni ningún grupo que se haya sincronizado desde AD DS.
>

Para obtener más información, consulte las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

## <a name="set-up-dynamic-group-membership"></a>Configurar la pertenencia a grupo dinámico

Azure AD admite la configuración de una serie de reglas que agregan o quitan automáticamente cuentas de usuario como miembros de un grupo de Azure AD. Esto se conoce como *pertenencia a grupo dinámico*. Las reglas se basan en atributos de cuenta de usuario, como el país o el departamento.

Las reglas se aplican de esta forma:

- Si la nueva cuenta de usuario coincide con todas las reglas del grupo, se convierte en un miembro.
- Si una cuenta de usuario no es miembro del grupo, pero sus atributos cambian para que coincidan con todas las reglas del grupo, se convierte en un miembro de ese grupo.
- Si una cuenta de usuario no coincide con todas las reglas del grupo, no se agregará al grupo.
- Si una cuenta de usuario es miembro del grupo, pero sus atributos cambian, por lo que ya no coinciden con todas las reglas del grupo, se quitará como miembro del grupo.

To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".

Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Configurar las licencias automáticas

Puede configurar grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones a todos los miembros del grupo. Esto se conoce como *licencias basadas en grupos*. Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.

Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar la licencia apropiada de Microsoft 365 Enterprise.

Asegúrese de que tiene suficientes licencias para todos los miembros del grupo. Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.

>[!Note]
>No configure las licencias basadas en grupos para los grupos que contengan cuentas entre empresas (B2B) de Azure.
>

Para obtener más información, consulte [Conceptos básicos de licencias basadas en grupos en Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Consulte las [instrucciones para configurar licencias basadas en grupos para un grupo de seguridad de Azure](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).