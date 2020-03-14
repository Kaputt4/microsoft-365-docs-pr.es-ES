---
title: 'Paso 7: Configurar Identity Governance'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure el gobierno de identidades para su cuenta empresarial de Azure AD.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633588"
---
# <a name="step-6-configure-identity-governance"></a>Paso 6: Configurar el gobierno de identidad

![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)

El gobierno de identidades consiste en proteger, supervisar y auditar el acceso a recursos críticos mientras se garantiza la productividad de los empleados. Por ejemplo, con la gobernanza de identidades puede asegurarse de que los usuarios adecuados tengan el acceso adecuado a los recursos adecuados y determinar si este acceso cambia a lo largo del tiempo.

Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para obtener más información sobre el gobierno de identidades de Azure Active Directory (Azure AD).


*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Revisiones de acceso de Azure AD

*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*

En este paso, configurará las revisiones de acceso de Azure AD, lo que le permitirá revisar el acceso de un usuario para asegurarse de que solo las personas adecuadas puedan seguir teniendo acceso. Por ejemplo:

- Cuando un nuevo empleado se une a la organización, usted debe asegurarse de que tiene un acceso adecuado para ser productivo.
- Cuando este empleado sea derivado a otros equipos, ubicaciones o departamentos, usted debe asegurarse de que su acceso a los equipos, ubicaciones o departamentos anteriores se elimine en función de las necesidades.
- Cuando ese empleado o un invitado deje la organización, usted debe asegurarse de que su acceso se elimine.

Esto es especialmente importante si su organización está sujeta a auditorías de seguridad para determinar si las cuentas de usuario tienen un acceso excesivo, lo que podría derivar en infracciones por incumplimiento de normativas del sector o de la región.

Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para obtener más información acerca de las revisiones de acceso de Azure AD.

Azure AD Privileged Identity Management (PIM) dispone de controles adicionales que están adaptados para proteger los derechos de acceso de los recursos en Azure AD, Azure y otros servicios en la nube de Microsoft. Azure AD PIM ofrece un conjunto completo de controles de gobierno para ayudar a proteger los recursos de la empresa, como directorio, Office 365 y roles de recursos de Azure. Al igual que con otras formas de acceso, las organizaciones pueden usar las revisiones de acceso para configurar nuevas certificaciones de acceso periódicas para todos los usuarios con roles de administrador. Azure AD PIM solo está disponible con la versión E5 de Microsoft 365 Enterprise.

Consulte estos artículos para configurar diferentes tipos de revisiones de acceso:

- [Grupos y aplicaciones](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Roles de Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Roles de recursos de Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-access-reviews) correspondientes a esta sección.

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de identidades](identity-exit-criteria.md)

