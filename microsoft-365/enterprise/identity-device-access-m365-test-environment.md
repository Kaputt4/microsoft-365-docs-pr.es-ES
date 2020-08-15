---
title: Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades.
ms.openlocfilehash: c5bc0fbbb3ae3839cb7aa71e8c840784ae4a4cad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685859"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6e7fd-103">Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e7fd-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6e7fd-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="6e7fd-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6e7fd-105">Las [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md) son un conjunto de características y directivas de acceso condicional para proteger el acceso a todos los servicios que se integran con Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="6e7fd-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="6e7fd-106">Para crear un entorno de prueba con estas directivas en su lugar:</span><span class="sxs-lookup"><span data-stu-id="6e7fd-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="6e7fd-107">Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:</span><span class="sxs-lookup"><span data-stu-id="6e7fd-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="6e7fd-108">Basada sólo en nube</span><span class="sxs-lookup"><span data-stu-id="6e7fd-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="6e7fd-109">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="6e7fd-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="6e7fd-110">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="6e7fd-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="6e7fd-111">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protección de pruebas para dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="6e7fd-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e7fd-112">Ver también</span><span class="sxs-lookup"><span data-stu-id="6e7fd-112">See also</span></span>

[<span data-ttu-id="6e7fd-113">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="6e7fd-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="6e7fd-114">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="6e7fd-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="6e7fd-115">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6e7fd-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6e7fd-116">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e7fd-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6e7fd-117">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6e7fd-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
