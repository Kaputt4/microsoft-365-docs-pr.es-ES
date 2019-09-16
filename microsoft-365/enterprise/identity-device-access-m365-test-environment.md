---
title: Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades.
ms.openlocfilehash: c8d7aed1422f9d0c5891157e6fb7d3d30d976c4a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981901"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e0ba5-103">Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0ba5-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e0ba5-104">[Configuración de acceso de dispositivos e identidades](microsoft-365-policies-configurations.md) es un conjunto de características y directivas de acceso condicional para proteger el acceso a todos los servicios que se integran con Azure Active Directory (Azure AD), incluidos Office 365 y Microsoft Intune en Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e0ba5-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="e0ba5-105">Para crear un entorno de prueba con estas directivas en su lugar:</span><span class="sxs-lookup"><span data-stu-id="e0ba5-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="e0ba5-106">Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:</span><span class="sxs-lookup"><span data-stu-id="e0ba5-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="e0ba5-107">Basada sólo en nube</span><span class="sxs-lookup"><span data-stu-id="e0ba5-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="e0ba5-108">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="e0ba5-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="e0ba5-109">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="e0ba5-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="e0ba5-110">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protección de pruebas para dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="e0ba5-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0ba5-111">Ver también</span><span class="sxs-lookup"><span data-stu-id="e0ba5-111">See also</span></span>

[<span data-ttu-id="e0ba5-112">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="e0ba5-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="e0ba5-113">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="e0ba5-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="e0ba5-114">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e0ba5-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e0ba5-115">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e0ba5-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e0ba5-116">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e0ba5-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
