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
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487713"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="63640-103">Azure AD Identity Protection para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="63640-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="63640-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="63640-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="63640-105">Puede usar Azure Active Directory (Azure AD) Identity Protection para detectar posibles vulnerabilidades que afecten a las identidades de su organización, configurar respuestas automáticas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="63640-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="63640-106">En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="63640-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="63640-107">La configuración de Azure AD Identity Protection en el entorno de prueba de Microsoft 365 para empresas implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="63640-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="63640-108">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="63640-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="63640-109">Fase 2: usar la protección de identidad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="63640-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="63640-111">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="63640-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="63640-112">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="63640-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="63640-113">Si solo quiere probar la protección de identidad de Azure AD de manera ligera con los requisitos mínimos, siga las instrucciones de [configuración de base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="63640-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="63640-114">Si quiere probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="63640-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="63640-115">La prueba de la protección de identidad de Azure AD no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="63640-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="63640-116">Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con él en un entorno que represente una organización típica.</span><span class="sxs-lookup"><span data-stu-id="63640-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="63640-117">Fase 2: usar la protección de identidad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="63640-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="63640-118">Abra una instancia privada del explorador e inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con la cuenta de administrador global del entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="63640-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="63640-119">En Azure portal, escriba **protección de identidad** en el cuadro de búsqueda y, a continuación, seleccione **Azure ad Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="63640-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="63640-120">En la hoja de la **información general** de la identidad, seleccione cada uno de los informes para ver su información.</span><span class="sxs-lookup"><span data-stu-id="63640-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="63640-121">En **notificar**, seleccione **usuarios en alertas de riesgo detectado**.</span><span class="sxs-lookup"><span data-stu-id="63640-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="63640-122">En el panel de **alertas usuarios en riesgo detectados** , seleccione **medio**.</span><span class="sxs-lookup"><span data-stu-id="63640-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="63640-123">Para **los mensajes de correo electrónico se envían a los siguientes usuarios**, seleccione **incluido** y compruebe que la cuenta de administrador global está en la lista de miembros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="63640-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="63640-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="63640-124">Select **Save**.</span></span>

<span data-ttu-id="63640-125">En **proteger**, seleccione diversas directivas para ver cómo configurarlas.</span><span class="sxs-lookup"><span data-stu-id="63640-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="63640-126">Si crea y activa una directiva, asegúrese de que no esté bloqueando el acceso de todos los usuarios o de que no pueda iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="63640-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="63640-127">Para evitarlo, excluya las cuentas de usuario específicas, como los administradores globales.</span><span class="sxs-lookup"><span data-stu-id="63640-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="63640-128">Para obtener más pruebas y experimentación, vea [Simulate Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="63640-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="63640-129">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="63640-129">Next step</span></span>

<span data-ttu-id="63640-130">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="63640-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="63640-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="63640-131">See also</span></span>

[<span data-ttu-id="63640-132">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="63640-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="63640-133">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="63640-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="63640-134">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="63640-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="63640-135">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="63640-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
