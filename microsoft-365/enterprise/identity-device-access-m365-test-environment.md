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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7b210-103">Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b210-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7b210-104">*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*</span><span class="sxs-lookup"><span data-stu-id="7b210-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7b210-105">[Las configuraciones de](../security/office-365-security/microsoft-365-policies-configurations.md) acceso a dispositivos e identidades son un conjunto de configuraciones recomendadas y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7b210-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="7b210-106">Para crear un entorno de prueba que tenga las configuraciones comunes de acceso a dispositivos e identidades:</span><span class="sxs-lookup"><span data-stu-id="7b210-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="7b210-107">Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:</span><span class="sxs-lookup"><span data-stu-id="7b210-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="7b210-108">Basada sólo en nube</span><span class="sxs-lookup"><span data-stu-id="7b210-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="7b210-109">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="7b210-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="7b210-110">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="7b210-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="7b210-111">Use [directivas comunes de acceso](identity-access-policies.md) a dispositivos e identidades para configurar las directivas que se basen en los requisitos previos configurados para su entorno de prueba y explorar y comprobar la protección de identidades y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7b210-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b210-112">Ver también</span><span class="sxs-lookup"><span data-stu-id="7b210-112">See also</span></span>

[<span data-ttu-id="7b210-113">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="7b210-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="7b210-114">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="7b210-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7b210-115">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7b210-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7b210-116">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b210-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7b210-117">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b210-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
