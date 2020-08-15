---
title: Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure Azure AD Identity Protection y analice las cuentas actuales en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694995"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="190e5-103">Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="190e5-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="190e5-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="190e5-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="190e5-105">La protección de identidad de Azure Active Directory (Azure AD) le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automáticas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="190e5-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="190e5-106">En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="190e5-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="190e5-107">Hay dos fases para la configuración de Azure AD Identity Protection en el entorno de prueba de Microsoft 365 para empresas:</span><span class="sxs-lookup"><span data-stu-id="190e5-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="190e5-108">Cree el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="190e5-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="190e5-109">Use Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="190e5-109">Use Azure AD Identity Protection.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="190e5-111">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="190e5-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="190e5-112">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="190e5-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="190e5-113">Si solo quiere probar Azure AD Identity Protection de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="190e5-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="190e5-114">Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="190e5-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="190e5-115">La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="190e5-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="190e5-116">Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica.</span><span class="sxs-lookup"><span data-stu-id="190e5-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="190e5-117">Fase 2: usar la protección de identidad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="190e5-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="190e5-118">Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global del entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="190e5-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="190e5-119">En Azure portal, escriba **protección de identidad** en el cuadro de búsqueda y, a continuación, haga clic en **Azure ad Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="190e5-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="190e5-120">En la hoja **protección de identidad: información general** , haga clic en cada uno de los informes para ver qué son los informes.</span><span class="sxs-lookup"><span data-stu-id="190e5-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="190e5-121">En **notificar**, haga clic en **alertas de usuarios en riesgo detectado**.</span><span class="sxs-lookup"><span data-stu-id="190e5-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="190e5-122">En el panel de **alertas usuarios en riesgo detectados** , seleccione **medio**.</span><span class="sxs-lookup"><span data-stu-id="190e5-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="190e5-123">Para **los mensajes de correo electrónico se envían a los siguientes usuarios**, haga clic en **incluido** y compruebe que la cuenta de administrador global está en la lista de miembros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="190e5-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="190e5-124">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="190e5-124">Click **Save**.</span></span>

<span data-ttu-id="190e5-125">Haga clic en las diferentes directivas en **proteger** para ver cómo configurarlas.</span><span class="sxs-lookup"><span data-stu-id="190e5-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="190e5-126">Si crea y activa una directiva, asegúrese de que no bloquee el acceso por un ámbito de condiciones demasiado amplio o de que no pueda iniciar sesión, ni siquiera como administrador global.</span><span class="sxs-lookup"><span data-stu-id="190e5-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="190e5-127">Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="190e5-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="190e5-128">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="190e5-128">Next step</span></span>

<span data-ttu-id="190e5-129">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="190e5-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="190e5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="190e5-130">See also</span></span>

[<span data-ttu-id="190e5-131">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="190e5-131">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="190e5-132">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="190e5-132">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="190e5-133">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="190e5-133">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="190e5-134">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="190e5-134">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
