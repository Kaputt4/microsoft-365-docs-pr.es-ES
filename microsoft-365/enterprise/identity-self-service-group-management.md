---
title: 'Paso 14: Permitir a los usuarios crear y administrar sus propios grupos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la administración de grupos de autoservicio de Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871488"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>Paso 14: Permitir a los usuarios crear y administrar sus propios grupos

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, identificará grupos de Azure Active Directory (AD) que pueden administrar los propietarios del grupo en lugar de los administradores de TI. Esta característica, que se conoce como *administración de grupos de autoservicio*, permite que los propietarios del grupo que no tienen asignado un rol administrativo creen y administren grupos de seguridad. 

Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.

>[!Note]
>La administración de grupos de autoservicio solo está disponible para la seguridad de Azure AD y los grupos de Office 365. No está disponible para los grupos habilitados para correo, las listas de distribución ni ningún grupo que se haya sincronizado desde la instancia local de Windows Server Active Directory (AD).
>

Para obtener más información, vea las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Como control interno, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-self-service-groups) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [Configurar la pertenencia a grupos dinámica](identity-automatic-group-membership.md) |
