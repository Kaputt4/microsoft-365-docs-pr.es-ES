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
ms.openlocfilehash: b8e91a58bb6e1c00013b963c77151080a419b836
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398812"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="2ec66-103">Acceso de dispositivos e identidades en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ec66-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="2ec66-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="2ec66-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="2ec66-105">Las [configuraciones de identidad y acceso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) son un conjunto de características y directivas de acceso condicional para proteger el acceso a todos los servicios que se integran con Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="2ec66-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="2ec66-106">Para crear un entorno de prueba que tenga las configuraciones comunes de identidad y acceso a dispositivos en su ubicación:</span><span class="sxs-lookup"><span data-stu-id="2ec66-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="2ec66-107">Configurar el entorno de prueba con las características de seguridad y la identidad de requisitos previos en función de la elección del método de autenticación y el modelo de identidad:</span><span class="sxs-lookup"><span data-stu-id="2ec66-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="2ec66-108">Basada sólo en nube</span><span class="sxs-lookup"><span data-stu-id="2ec66-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2ec66-109">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="2ec66-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2ec66-110">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="2ec66-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="2ec66-111">Use [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos configurados para el entorno de prueba y para explorar y comprobar la protección de las identidades y los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2ec66-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ec66-112">Ver también</span><span class="sxs-lookup"><span data-stu-id="2ec66-112">See also</span></span>

[<span data-ttu-id="2ec66-113">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="2ec66-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="2ec66-114">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="2ec66-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2ec66-115">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2ec66-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2ec66-116">Información general de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2ec66-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2ec66-117">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2ec66-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
