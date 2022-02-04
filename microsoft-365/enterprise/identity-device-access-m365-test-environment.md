---
title: Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365
author: kelleyvice-msft
f1.keywords:
  - NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
  - M365-subscription-management
  - Strat_O365_Enterprise
ms.custom: null
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades.
---

# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365

*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*

[Las configuraciones de acceso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) y identidades son un conjunto de configuraciones recomendadas y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).

Para crear un entorno de prueba que tenga las configuraciones comunes de acceso a dispositivos y identidades:

1. Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:

  - [Basada sólo en nube](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronización de hash de contraseña (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticación de paso a través (PTA)](pta-prereqs-m365-test-environment.md)

2. Use [Directivas comunes de acceso](../security/office-365-security/identity-access-policies.md) a dispositivos y identidades para configurar las directivas que se basen en los requisitos previos configurados para el entorno de prueba y explorar y comprobar la protección de identidades y dispositivos.

## <a name="see-also"></a>Ver también

[Guías de laboratorio de pruebas de identidad adicionales](m365-enterprise-test-lab-guides.md#identity)

[Implementar identidad](deploy-identity-solution-overview.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
