---
title: Administrar grupos de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar Microsoft 365 grupos.
ms.openlocfilehash: 72bc47bb699e32f849f21ea4c5470a95d6228b68
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356689"
---
# <a name="manage-microsoft-365-groups"></a>Administrar grupos de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede administrar los Microsoft 365 de varias maneras, según la configuración. Puede administrar cuentas de usuario en [Centro de administración de Microsoft 365](../admin/add-users/index.yml), PowerShell, en Servicios de dominio de Active Directory (AD DS) o en el Centro de administración de [Azure Active Directory (Azure AD).](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Planear dónde y cómo administrará los grupos

Dónde y cómo puede administrar sus cuentas de usuario depende del modelo de identidad que desee usar para su Microsoft 365. Los dos modelos generales son híbridos y solo en la nube.
  
### <a name="cloud-only"></a>Solo de nube

Puede crear y administrar grupos con:

- [Centro de administración de Microsoft 365](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Centro de administración de Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Híbrido

Los grupos de AD DS se sincronizan con Microsoft 365 de AD DS, por lo que debes usar las herramientas locales de AD DS para administrar estos grupos.

También puede crear y administrar grupos de Azure AD independientes de los grupos de AD DS, pero que pueden contener usuarios y grupos de AD DS. En este caso, puede usar:

- [Centro de administración de Microsoft 365](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Centro de administración de Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Permitir a los usuarios crear y administrar sus propios grupos

Azure AD permite grupos que pueden administrar los propietarios de grupos en lugar de los administradores de TI. Conocida como *administración autoservicio de grupos*, esta característica permite a los propietarios del grupo que no están asignados a un rol de administrador crear y administrar grupos de seguridad. 

Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.

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

Para usar la pertenencia dinámica, primero necesita determinar los conjuntos de grupos que tienen un conjunto común de atributos de cuenta de usuario. Por ejemplo, todos los miembros del departamento de ventas necesitan estar en el grupo de Azure AD “Ventas”, basándose en el atributo de cuenta de usuario “Departamento” establecido en “Ventas”.

Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Configurar las licencias automáticas

Puede configurar grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones a todos los miembros del grupo. Esto se conoce como *licencias basadas en grupos*. Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.

Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar la licencia apropiada de Microsoft 365 Enterprise.

Asegúrese de que tiene suficientes licencias para todos los miembros del grupo. Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.

>[!Note]
>No configure las licencias basadas en grupos para los grupos que contengan cuentas entre empresas (B2B) de Azure.
>

Para obtener más información, vea Conceptos básicos de licencias [basadas](/azure/active-directory/active-directory-licensing-whatis-azure-portal)en grupos en Azure AD .

Vea las [instrucciones para configurar las licencias basadas en grupos para un grupo de seguridad de Azure](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).