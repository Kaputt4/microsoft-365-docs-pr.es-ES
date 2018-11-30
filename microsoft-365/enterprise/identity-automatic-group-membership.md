---
title: 'Paso 15: Configurar la pertenencia a grupos dinámicos'
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
description: Comprenda y configure la pertenencia a grupos automática basada en atributos de cuenta.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871675"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>Paso 15: Configurar la pertenencia a grupos dinámicos

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, creará una serie de reglas que agreguen o quiten automáticamente cuentas de usuario como miembros de un grupo de Azure AD. Esto se conoce como *pertenencia a grupos dinámicos*. La regla se basa en atributos de cuenta de usuario, como Departamento o País.

Las reglas se aplican de esta forma:

- Si la nueva cuenta de usuario coincide con todas las reglas del grupo, se convierte en un miembro.
- Si una cuenta de usuario no es miembro del grupo, pero sus atributos cambian para que coincidan con todas las reglas del grupo, se convierte en un miembro de ese grupo.
- Si una cuenta de usuario no coincide con todas las reglas del grupo, no se agregará al grupo.
- Si una cuenta de usuario es miembro del grupo, pero sus atributos cambian, por lo que ya no coinciden con todas las reglas del grupo, se quitará como miembro del grupo.

Para usar la pertenencia dinámica, primero necesita determinar los conjuntos de grupos que tienen un conjunto común de atributos de cuenta de usuario. Por ejemplo, todos los miembros del departamento de ventas necesitan estar en el grupo de Azure AD “Ventas”, basándose en el atributo de cuenta de usuario “Departamento” establecido en “Ventas”.

Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

Los resultados de este paso son:

- Un conjunto de grupos de Azure AD que se puede configurar para la pertenencia dinámica.
- Un conjunto de reglas para cada grupo dinámico.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-dyn-groups) de este paso.

## <a name="next-step"></a>Siguiente paso

[Criterios de salida de infraestructura de identidades](identity-exit-criteria.md)
