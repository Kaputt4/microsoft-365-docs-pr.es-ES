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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="2182a-103">Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2182a-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="2182a-104">*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*</span><span class="sxs-lookup"><span data-stu-id="2182a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="2182a-105">[Las configuraciones de acceso](../security/office-365-security/microsoft-365-policies-configurations.md) a dispositivos y identidades son un conjunto de configuraciones recomendadas y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2182a-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="2182a-106">Para crear un entorno de prueba que tenga las configuraciones comunes de acceso a dispositivos y identidades:</span><span class="sxs-lookup"><span data-stu-id="2182a-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="2182a-107">Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:</span><span class="sxs-lookup"><span data-stu-id="2182a-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="2182a-108">Basada sólo en nube</span><span class="sxs-lookup"><span data-stu-id="2182a-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2182a-109">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="2182a-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2182a-110">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="2182a-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="2182a-111">Use [Directivas comunes de acceso](../security/office-365-security/identity-access-policies.md) a dispositivos y identidades para configurar las directivas que se basen en los requisitos previos configurados para el entorno de prueba y explorar y comprobar la protección de identidades y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2182a-111">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="2182a-112">Ver también</span><span class="sxs-lookup"><span data-stu-id="2182a-112">See also</span></span>

[<span data-ttu-id="2182a-113">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="2182a-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="2182a-114">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="2182a-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2182a-115">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2182a-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2182a-116">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2182a-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2182a-117">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2182a-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)