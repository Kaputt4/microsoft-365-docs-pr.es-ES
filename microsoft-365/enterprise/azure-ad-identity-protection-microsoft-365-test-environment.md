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
ms.openlocfilehash: d267bb9dff94acfec46fa1275887f9cade2a7285
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074090"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="de4e0-103">Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="de4e0-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="de4e0-104">Azure AD Identity Protection le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automáticas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="de4e0-104">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="de4e0-105">En este artículo se describe cómo habilitar la protección de identidad de Azure AD y ver el análisis de las cuentas del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="de4e0-105">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="de4e0-106">Hay dos fases para la configuración de Azure AD Identity Protection en su entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="de4e0-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="de4e0-107">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="de4e0-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="de4e0-108">Habilite y use Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="de4e0-108">Enable and use Azure AD Identity Protection.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="de4e0-110">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="de4e0-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="de4e0-111">Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="de4e0-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="de4e0-112">Si solo quiere probar Azure AD Identity Protection de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="de4e0-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="de4e0-113">Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="de4e0-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="de4e0-114">La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="de4e0-114">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="de4e0-115">Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica.</span><span class="sxs-lookup"><span data-stu-id="de4e0-115">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="de4e0-116">Fase 2: habilitar y usar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="de4e0-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="de4e0-117">Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global de su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="de4e0-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="de4e0-118">En Azure portal, haga clic en **todos los servicios > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="de4e0-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="de4e0-119">Escriba **Azure ad Identity Protection** y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="de4e0-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="de4e0-120">En la hoja **Introducción** , haga clic **en incorporada** en **configuración**, haga clic en **anclar a panel**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="de4e0-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="de4e0-121">En Azure portal, haga clic en **Azure ad Identity Protection** en el panel.</span><span class="sxs-lookup"><span data-stu-id="de4e0-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="de4e0-122">Debe ver un blade **de Azure ad Identity Protection-Overview** con un panel.</span><span class="sxs-lookup"><span data-stu-id="de4e0-122">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="de4e0-123">En **vulnerabilidades**, observe que se ha determinado el número de cuentas de usuario sin registro de autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="de4e0-123">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="de4e0-124">Este número variará en función de las guías previas del laboratorio de pruebas de Microsoft 365 Enterprise que haya hecho.</span><span class="sxs-lookup"><span data-stu-id="de4e0-124">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="de4e0-125">Haga clic en las categorías para **investigar** para ver si hay algún usuario o evento que se haya detectado.</span><span class="sxs-lookup"><span data-stu-id="de4e0-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="de4e0-126">Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="de4e0-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="de4e0-127">Consulte el paso [proteger contra credenciales en peligro](identity-multi-factor-authentication.md#identity-ident-prot) en la fase de identidad para obtener información y vínculos para implementar Azure ad Identity Protection en producción.</span><span class="sxs-lookup"><span data-stu-id="de4e0-127">See the [Protect against credential compromise](identity-multi-factor-authentication.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="de4e0-128">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="de4e0-128">Next step</span></span>

<span data-ttu-id="de4e0-129">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="de4e0-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="de4e0-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="de4e0-130">See also</span></span>

[<span data-ttu-id="de4e0-131">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="de4e0-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="de4e0-132">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="de4e0-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="de4e0-133">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="de4e0-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="de4e0-134">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="de4e0-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
