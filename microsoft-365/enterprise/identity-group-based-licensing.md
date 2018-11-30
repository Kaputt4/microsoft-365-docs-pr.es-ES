---
title: 'Paso 12: Configurar las licencias automáticas'
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
description: Comprenda y configure las licencias basadas en grupos para grupos de Azure AD.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871141"
---
# <a name="step-12-set-up-automatic-licensing"></a>Paso 12: Configurar las licencias automáticas

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, configurará los grupos de seguridad en Azure AD para que se asignen automáticamente licencias de un conjunto de suscripciones a todos los miembros del grupo. Esto se conoce como *licencias basadas en grupos*. Si se agrega o quita del grupo una cuenta de usuario, las licencias de las suscripciones del grupo se asignarán o quitarán automáticamente de la cuenta de usuario.

Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar estas dos licencias:

- Office 365 Enterprise E3 o E5
- Enterprise Mobility + Security (EMS) E3 o E5

Con los grupos que identificó en el paso 2, busque grupos que contengan una lista de cuentas donde todos los usuarios del grupo necesiten tener licencias de Office 365 y EMS. Asegúrese de tener licencias suficientes para todos los miembros del grupo. Si se queda sin licencias, no se asignarán licencias a los nuevos usuarios hasta que haya más licencias disponibles.

>[!Note]
>No configure las *licencias basadas en grupos* para los grupos que contengan cuentas entre empresas (B2B) de Azure.
>

Para obtener más información, vea [Conceptos básicos de las licencias basadas en grupos de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Vea los [pasos para configurar las licencias basadas en grupos para un grupo de seguridad de Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Los resultados de este paso son:

- Identificó los grupos de seguridad adecuados para las licencias basadas en grupos.
- Configuró estos grupos para las licencias basadas en grupos.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-group-license) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [Supervisar la actividad de inicio de sesión y del espacio empresarial](identity-azure-ad-access-usage-reporting.md) |

