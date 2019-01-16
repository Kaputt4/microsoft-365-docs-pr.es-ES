---
title: Entorno de prueba de Azure protección de identidad de AD para su empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurar la protección de identidad de Azure AD y analizar las cuentas actuales en el entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871243"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="805d5-103">Entorno de prueba de Azure protección de identidad de AD para su empresa de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="805d5-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="805d5-p101">Protección de identidad de AD Azure permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar las respuestas automáticas e investigar incidentes. En este artículo se describe cómo habilitar la protección de la identidad de Azure AD y ver el análisis de las cuentas del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="805d5-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="805d5-106">Hay dos fases para configurar la protección de la identidad de AD de Azure en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="805d5-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="805d5-107">Crear el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="805d5-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="805d5-108">Habilitar y usar la protección de la identidad de AD de Azure.</span><span class="sxs-lookup"><span data-stu-id="805d5-108">Enable and use Azure AD Identity Protection.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="805d5-110">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="805d5-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="805d5-111">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="805d5-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="805d5-112">Si desea probar la protección de la identidad de AD de Azure en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="805d5-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="805d5-113">Si desea probar la protección de la identidad de AD de Azure en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="805d5-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="805d5-p102">Prueba de protección de identidad de Azure AD no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar la protección de la identidad de Azure AD y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="805d5-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="805d5-116">Fase 2: Habilitar y usar la protección de la identidad de AD de Azure</span><span class="sxs-lookup"><span data-stu-id="805d5-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="805d5-117">Abra una instancia privada de su explorador e inicie sesión el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global de su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="805d5-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="805d5-118">En el portal de Azure, haga clic en **todos los servicios > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="805d5-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="805d5-119">Escriba la **protección de la identidad de Azure AD** y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="805d5-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="805d5-120">En el servidor blade **De introducción** , haga clic en **incorporado** en **configuración**, haga clic en **Anclar a panel**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="805d5-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="805d5-121">En el portal de Azure, haga clic en **protección de la identidad de AD de Azure** en el panel.</span><span class="sxs-lookup"><span data-stu-id="805d5-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="805d5-p103">Debería ver un blade de **Azure AD protección-Introducción Identity** con un panel. En **las vulnerabilidades**, tenga en cuenta que determina el número de cuentas de usuario sin registro autenticación multifactor. Este número variará en función de anterior Microsoft 365 Enterprise prueba guías de laboratorio de que ha llevado a cabo.</span><span class="sxs-lookup"><span data-stu-id="805d5-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="805d5-125">Haga clic en a través de las categorías para **investigar** ver si hay eventos que se han detectado o los usuarios.</span><span class="sxs-lookup"><span data-stu-id="805d5-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="805d5-126">Para realizar más pruebas y experimentación, consulte [eventos de riesgo Simulating](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="805d5-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="805d5-127">Vea el paso de [protección contra credenciales ponen en peligro](identity-azure-ad-identity-protection.md) en la fase de identidad para obtener información y vínculos para implementar la protección de la identidad de AD de Azure en producción.</span><span class="sxs-lookup"><span data-stu-id="805d5-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="805d5-128">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="805d5-128">Next step</span></span>

<span data-ttu-id="805d5-129">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="805d5-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="805d5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="805d5-130">See also</span></span>

[<span data-ttu-id="805d5-131">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="805d5-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="805d5-132">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="805d5-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="805d5-133">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="805d5-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="805d5-134">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="805d5-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
