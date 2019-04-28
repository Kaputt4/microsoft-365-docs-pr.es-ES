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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="82027-103">Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82027-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="82027-104">[Configuraciones de acceso de dispositivos e identidades](microsoft-365-policies-configurations.md) es un conjunto de características y directivas de acceso condicional para proteger el acceso a todos los servicios que se integran con Azure Active Directory (Azure AD), incluyendo Office 365 y Enterprise Mobility + Security ( EMS) en Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="82027-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="82027-105">Para crear un entorno de prueba con estas directivas en su lugar:</span><span class="sxs-lookup"><span data-stu-id="82027-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="82027-106">Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:</span><span class="sxs-lookup"><span data-stu-id="82027-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="82027-107">Basada sólo en nube</span><span class="sxs-lookup"><span data-stu-id="82027-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="82027-108">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="82027-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="82027-109">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="82027-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="82027-110">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protección de pruebas para dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="82027-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="82027-111">Ver también</span><span class="sxs-lookup"><span data-stu-id="82027-111">See also</span></span>

[<span data-ttu-id="82027-112">Guías de laboratorio de pruebas de identidad adicional</span><span class="sxs-lookup"><span data-stu-id="82027-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="82027-113">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="82027-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="82027-114">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="82027-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="82027-115">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="82027-115">Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="82027-116">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="82027-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
