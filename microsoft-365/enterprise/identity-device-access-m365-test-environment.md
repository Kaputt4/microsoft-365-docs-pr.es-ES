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
ms.openlocfilehash: 427b0589da0347008cca0e2004bc23f494bebb29
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907473"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365

*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

[Las configuraciones de acceso](../security/office-365-security/microsoft-365-policies-configurations.md) a dispositivos y identidades son un conjunto de configuraciones recomendadas y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).

Para crear un entorno de prueba que tenga las configuraciones comunes de acceso a dispositivos y identidades:

1. Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:

  - [Basada sólo en nube](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronización de hash de contraseña (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticación de paso a través (PTA)](pta-prereqs-m365-test-environment.md)

2. Use [Directivas comunes de acceso](../security/office-365-security/identity-access-policies.md) a dispositivos y identidades para configurar las directivas que se basen en los requisitos previos configurados para el entorno de prueba y explorar y comprobar la protección de identidades y dispositivos.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicionales](m365-enterprise-test-lab-guides.md#identity)

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)