---
title: Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades.
ms.openlocfilehash: 7004a46873e32f39ace672bd955147e2f13ee05d
ms.sourcegitcommit: 2f7791159b715790463c6ce4835fbd9c0b48c047
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2019
ms.locfileid: "33243069"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365

[Configuraciones de acceso de dispositivos e identidades](microsoft-365-policies-configurations.md) es un conjunto de características y directivas de acceso condicional para proteger el acceso a todos los servicios que se integran con Azure Active Directory (Azure AD), incluyendo Office 365 y Enterprise Mobility + Security ( EMS) en Microsoft 365 Enterprise.

Para crear un entorno de prueba con estas directivas en su lugar:

1. Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:

  - [Basada sólo en nube](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronización de hash de contraseña (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticación de paso a través (PTA)](pta-prereqs-m365-test-environment.md)

2. Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protección de pruebas para dispositivos e identidades.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicional](m365-enterprise-test-lab-guides.md#identity)

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
