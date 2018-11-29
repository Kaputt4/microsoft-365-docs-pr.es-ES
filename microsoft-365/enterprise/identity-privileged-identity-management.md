---
title: 'Paso 3: Configurar los administradores globales a petición'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure Azure AD Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871350"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>Paso 3: Configurar los administradores globales a petición

*Este paso es opcional y solo es válido para la versión E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, configurará Azure AD Privileged Identity Management (PIM) para reducir el tiempo durante el que sus cuentas de administrador global son vulnerables ante ataques de usuarios malintencionados. PIM proporciona una asignación a petición y Just-In-Time del rol de administrador global cuando sea necesaria.  

En lugar de convertir sus cuentas de administrador global en un administrador permanente, se convierten en administradores válidos. El rol de administrador global está inactivo hasta que alguien lo necesita. Después, deberá completar un proceso de activación para agregar el rol de administrador global a la cuenta de administrador global durante un período de tiempo concreto. Cuando expira el tiempo, PIM quita el rol de administrador global de la cuenta de administrador global.

PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 Enterprise E5. También puede comprar licencias individuales de Azure Active Directory Premium P2 para sus cuentas de administrador global.

Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador global, vea los [pasos para configurar PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-pim) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Simplificar los restablecimientos de contraseña](identity-password-reset.md) |

