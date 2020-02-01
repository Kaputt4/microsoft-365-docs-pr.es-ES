---
title: Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise
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
description: Configure Azure AD Identity Protection y analice las cuentas actuales en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 376fc838191314e93ae37accb7fc5066456499fb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597167"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="75531-103">Azure AD Identity Protection para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="75531-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="75531-104">*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="75531-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="75531-105">La protección de identidad de Azure Active Directory (Azure AD) le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización, configurar respuestas automáticas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="75531-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="75531-106">En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="75531-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="75531-107">Hay dos fases para la configuración de Azure AD Identity Protection en su entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="75531-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="75531-108">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="75531-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="75531-109">Use Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="75531-109">Use Azure AD Identity Protection.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="75531-111">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="75531-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="75531-112">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="75531-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="75531-113">Si solo quiere probar Azure AD Identity Protection de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="75531-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="75531-114">Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="75531-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="75531-115">La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="75531-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="75531-116">Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica.</span><span class="sxs-lookup"><span data-stu-id="75531-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="75531-117">Fase 2: usar la protección de identidad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="75531-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="75531-118">Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global de su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="75531-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="75531-119">En Azure portal, escriba **protección de identidad** en el cuadro de búsqueda y, a continuación, haga clic en **Azure ad Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="75531-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="75531-120">En la hoja **protección de identidad: información general** , haga clic en cada uno de los informes para ver qué son los informes.</span><span class="sxs-lookup"><span data-stu-id="75531-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="75531-121">En **notificar**, haga clic en **alertas de usuarios en riesgo detectado**.</span><span class="sxs-lookup"><span data-stu-id="75531-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="75531-122">En el panel de **alertas usuarios en riesgo detectados** , seleccione **medio**.</span><span class="sxs-lookup"><span data-stu-id="75531-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="75531-123">Para **los mensajes de correo electrónico se envían a los siguientes usuarios**, haga clic en **incluido** y compruebe que la cuenta de administrador global está en la lista de miembros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="75531-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="75531-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="75531-124">Click **Save**.</span></span>

<span data-ttu-id="75531-125">Haga clic en las diferentes directivas en **proteger** para ver cómo configurarlas.</span><span class="sxs-lookup"><span data-stu-id="75531-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="75531-126">Si crea y activa una directiva, asegúrese de que no bloquee el acceso por un ámbito de condiciones demasiado amplio o de que no pueda iniciar sesión, ni siquiera como administrador global.</span><span class="sxs-lookup"><span data-stu-id="75531-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="75531-127">Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="75531-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="75531-128">Consulte el paso [proteger contra credenciales en peligro](identity-secure-user-sign-ins.md#identity-ident-prot) en la fase de identidad para obtener información y vínculos para implementar Azure ad Identity Protection en producción.</span><span class="sxs-lookup"><span data-stu-id="75531-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="75531-129">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="75531-129">Next step</span></span>

<span data-ttu-id="75531-130">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="75531-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="75531-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="75531-131">See also</span></span>

[<span data-ttu-id="75531-132">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="75531-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="75531-133">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="75531-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="75531-134">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="75531-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="75531-135">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="75531-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
