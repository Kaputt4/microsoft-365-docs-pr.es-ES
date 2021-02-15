---
title: Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades.
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233733"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365

*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*

[Las configuraciones de](../security/office-365-security/microsoft-365-policies-configurations.md) acceso a dispositivos e identidades son un conjunto de configuraciones recomendadas y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).

Para crear un entorno de prueba que tenga las configuraciones comunes de acceso a dispositivos e identidades:

1. Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:

  - [Basada sólo en nube](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronización de hash de contraseña (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticación de paso a través (PTA)](pta-prereqs-m365-test-environment.md)

2. Use [directivas comunes de acceso](identity-access-policies.md) a dispositivos e identidades para configurar las directivas que se basen en los requisitos previos configurados para su entorno de prueba y explorar y comprobar la protección de identidades y dispositivos.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicionales](m365-enterprise-test-lab-guides.md#identity)

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
