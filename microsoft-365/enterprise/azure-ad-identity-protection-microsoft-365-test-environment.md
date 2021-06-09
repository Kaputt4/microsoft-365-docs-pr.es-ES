---
title: Azure AD Identity Protection para el entorno de prueba Microsoft 365 para empresas
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
description: Configure Azure AD Identity Protection y analice las cuentas actuales de su entorno de prueba Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905349"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d12bc-103">Azure AD Identity Protection para el entorno de prueba Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d12bc-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d12bc-104">*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*</span><span class="sxs-lookup"><span data-stu-id="d12bc-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d12bc-105">Puede usar Azure Active Directory (Azure AD) Identity Protection para detectar posibles vulnerabilidades que afecten a las identidades de su organización, configurar respuestas automatizadas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="d12bc-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="d12bc-106">En este artículo se describe cómo usar Azure AD Identity Protection para ver el análisis de las cuentas del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="d12bc-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="d12bc-107">La configuración de Azure AD Identity Protection en el entorno Microsoft 365 de prueba empresarial implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="d12bc-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="d12bc-108">Fase 1: Crear su Microsoft 365 entorno de prueba empresarial</span><span class="sxs-lookup"><span data-stu-id="d12bc-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d12bc-109">Fase 2: Usar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d12bc-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d12bc-111">Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d12bc-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d12bc-112">Fase 1: Crear su Microsoft 365 entorno de prueba empresarial</span><span class="sxs-lookup"><span data-stu-id="d12bc-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d12bc-113">Si solo desea probar Azure AD Identity Protection de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d12bc-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d12bc-114">Si desea probar Azure AD Identity Protection en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d12bc-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d12bc-115">Las pruebas de Azure AD Identity Protection no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="d12bc-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d12bc-116">Se proporciona aquí como una opción para que pueda probar Azure AD Identity Protection y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="d12bc-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="d12bc-117">Fase 2: Usar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d12bc-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="d12bc-118">Abra una instancia privada del explorador e inicie sesión en Azure Portal con la cuenta de administrador global de su entorno de [https://portal.azure.com](https://portal.azure.com) prueba Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="d12bc-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="d12bc-119">En Azure Portal, escriba **Identity Protection** en el cuadro de búsqueda y, a continuación, seleccione Azure AD **Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="d12bc-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="d12bc-120">En la **hoja Identity Protection - Overview,** seleccione cada informe para ver lo que está informando.</span><span class="sxs-lookup"><span data-stu-id="d12bc-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="d12bc-121">En **Notificar**, seleccione **Usuarios en riesgo alertas detectadas**.</span><span class="sxs-lookup"><span data-stu-id="d12bc-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="d12bc-122">En el panel **Usuarios en riesgo de alertas detectadas,** seleccione **Medio**.</span><span class="sxs-lookup"><span data-stu-id="d12bc-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="d12bc-123">Para **los correos electrónicos se envían a los siguientes usuarios,** seleccione **Incluido** y compruebe que su cuenta de administrador global esté en la lista de miembros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d12bc-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="d12bc-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d12bc-124">Select **Save**.</span></span>

<span data-ttu-id="d12bc-125">En **Proteger,** seleccione varias directivas para ver cómo configurarlas.</span><span class="sxs-lookup"><span data-stu-id="d12bc-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="d12bc-126">Si crea y activa una directiva, asegúrese de que no está bloqueando el acceso para todos los usuarios, o puede que no pueda iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="d12bc-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="d12bc-127">Para evitar esto, excluya cuentas de usuario específicas, como administradores globales.</span><span class="sxs-lookup"><span data-stu-id="d12bc-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="d12bc-128">Para más pruebas y experimentación, vea [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="d12bc-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="d12bc-129">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d12bc-129">Next step</span></span>

<span data-ttu-id="d12bc-130">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="d12bc-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d12bc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d12bc-131">See also</span></span>

[<span data-ttu-id="d12bc-132">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="d12bc-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="d12bc-133">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d12bc-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d12bc-134">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d12bc-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d12bc-135">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d12bc-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)