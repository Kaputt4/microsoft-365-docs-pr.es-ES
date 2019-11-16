---
title: Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure Azure AD Identity Protection y analice las cuentas actuales en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: bc98ebbdd45e06481e2d95687fb4eb8c986533a3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673246"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f5277-103">Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5277-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f5277-104">*Esta guía del entorno de pruebas solo puede usarse en entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f5277-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f5277-105">Azure AD Identity Protection le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automáticas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="f5277-105">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="f5277-106">En este artículo se describe cómo habilitar la protección de identidad de Azure AD y ver el análisis de las cuentas del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f5277-106">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="f5277-107">Hay dos fases para la configuración de Azure AD Identity Protection en su entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="f5277-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="f5277-108">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f5277-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="f5277-109">Habilite y use Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="f5277-109">Enable and use Azure AD Identity Protection.</span></span>

![Guías del entorno de pruebas para la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f5277-111">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f5277-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f5277-112">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5277-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f5277-113">Si solo quiere probar Azure AD Identity Protection de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f5277-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f5277-114">Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f5277-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f5277-115">La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f5277-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f5277-116">Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica.</span><span class="sxs-lookup"><span data-stu-id="f5277-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="f5277-117">Fase 2: habilitar y usar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f5277-117">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="f5277-118">Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global de su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f5277-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="f5277-119">En Azure portal, haga clic en **todos los servicios > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="f5277-119">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="f5277-120">Escriba **Azure ad Identity Protection** y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="f5277-120">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="f5277-121">En la hoja **Introducción** , haga clic **en incorporada** en **configuración**, haga clic en **anclar a panel**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="f5277-121">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="f5277-122">En Azure portal, haga clic en **Azure ad Identity Protection** en el panel.</span><span class="sxs-lookup"><span data-stu-id="f5277-122">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="f5277-123">Debe ver un blade **de Azure ad Identity Protection-Overview** con un panel.</span><span class="sxs-lookup"><span data-stu-id="f5277-123">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="f5277-124">En **vulnerabilidades**, observe que se ha determinado el número de cuentas de usuario sin registro de autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="f5277-124">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="f5277-125">Este número variará en función de las guías previas del laboratorio de pruebas de Microsoft 365 Enterprise que haya hecho.</span><span class="sxs-lookup"><span data-stu-id="f5277-125">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="f5277-126">Haga clic en las categorías para **investigar** para ver si hay algún usuario o evento que se haya detectado.</span><span class="sxs-lookup"><span data-stu-id="f5277-126">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="f5277-127">Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="f5277-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="f5277-128">Consulte el paso [proteger contra credenciales en peligro](identity-secure-user-sign-ins.md#identity-ident-prot) en la fase de identidad para obtener información y vínculos para implementar Azure ad Identity Protection en producción.</span><span class="sxs-lookup"><span data-stu-id="f5277-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5277-129">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f5277-129">Next step</span></span>

<span data-ttu-id="f5277-130">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="f5277-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5277-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5277-131">See also</span></span>

[<span data-ttu-id="f5277-132">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="f5277-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f5277-133">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5277-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f5277-134">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5277-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f5277-135">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5277-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
