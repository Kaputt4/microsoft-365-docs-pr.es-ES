---
title: Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Siga estos pasos para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487641"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8e961-103">Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8e961-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8e961-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="8e961-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="8e961-105">Puede evitar ataques digitales en su organización asegurándose de que las cuentas de administrador son lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="8e961-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="8e961-106">En este artículo se describe cómo usar las directivas de acceso condicional de Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="8e961-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="8e961-107">La protección de las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="8e961-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="8e961-108">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8e961-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="8e961-109">Fase 2: configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="8e961-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8e961-111">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="8e961-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8e961-112">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8e961-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8e961-113">Si desea probar la protección de la cuenta de administrador global de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8e961-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8e961-114">Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8e961-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e961-115">La comprobación de la protección de la cuenta de administrador global no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="8e961-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="8e961-116">Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="8e961-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="8e961-117">Fase 2: configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="8e961-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="8e961-118">En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="8e961-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="8e961-119">En una pestaña independiente, abra el [centro de administración de Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8e961-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="8e961-120">Seleccione **usuarios**  >  **activos**y, a continuación, seleccione **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="8e961-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="8e961-121">En el panel **Agregar usuario** , escriba **DedicatedAdmin** en los cuadros **nombre**, **nombre para mostrar**y nombre de **usuario** .</span><span class="sxs-lookup"><span data-stu-id="8e961-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="8e961-122">Seleccione **contraseña**, seleccione **me permite crear la contraseña**y, a continuación, escriba una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="8e961-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="8e961-123">Registre la contraseña de esta nueva cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="8e961-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="8e961-124">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8e961-124">Select **Next**.</span></span>
6. <span data-ttu-id="8e961-125">En el panel **asignar licencias de producto** , seleccione **Microsoft 365 E5**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8e961-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="8e961-126">En el panel **configuración opcional** , seleccione **roles**de administrador global de  >  **acceso al centro de administración**  >  **Global admin**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="8e961-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="8e961-127">En el panel **está casi listo** , seleccione **terminar de agregar**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8e961-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="8e961-128">A continuación, cree un nuevo grupo denominado GlobalAdmins y agréguele la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="8e961-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="8e961-129">En la pestaña **centro de administración de 365 de Microsoft** , seleccione **grupos** en el panel de navegación izquierdo y, a continuación, seleccione **grupos**.</span><span class="sxs-lookup"><span data-stu-id="8e961-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="8e961-130">Seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="8e961-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="8e961-131">En el panel **elegir un tipo de grupo** , seleccione **seguridad**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8e961-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="8e961-132">En el panel **configurar conceptos básicos** , seleccione **Crear grupo**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8e961-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="8e961-133">En el panel **revisar y finalizar agregar grupo** , escriba **GlobalAdmins**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8e961-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="8e961-134">En la lista de grupos, seleccione el grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="8e961-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="8e961-135">En el panel **GlobalAdmins** , seleccione **miembros**y, a continuación, seleccione **Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="8e961-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="8e961-136">En el panel **GlobalAdmins** , seleccione **Agregar miembros**, seleccione la cuenta **DedicatedAdmin** y la cuenta de administrador global y, a continuación, seleccione **Guardar**  >  **cerrar**  >  **Close**.</span><span class="sxs-lookup"><span data-stu-id="8e961-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="8e961-137">A continuación, cree directivas de acceso condicional para requerir multi-factor Authentication para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="8e961-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="8e961-138">Esta primera Directiva requiere que todas las cuentas de administrador global usen MFA.</span><span class="sxs-lookup"><span data-stu-id="8e961-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="8e961-139">En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="8e961-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="8e961-140">Haga **Azure Active Directory**clic en  >  **Security**  >  **acceso condicional**de seguridad de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8e961-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="8e961-141">En el panel **acceso condicional-directivas** , seleccione **Directiva de línea de base: solicitar MFA para administradores (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="8e961-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="8e961-142">En el panel **Directiva de línea de base** , seleccione usar la **Directiva inmediatamente > guardar**.</span><span class="sxs-lookup"><span data-stu-id="8e961-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="8e961-143">Esta segunda Directiva bloquea el acceso a la autenticación de la cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="8e961-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="8e961-144">En el panel **acceso condicional-directivas** , seleccione **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="8e961-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="8e961-145">En el panel **nuevo** , escriba **administradores globales** en **nombre**.</span><span class="sxs-lookup"><span data-stu-id="8e961-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="8e961-146">En la sección **asignaciones** , seleccione **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="8e961-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="8e961-147">En la ficha **incluir** del panel **usuarios y grupos** , seleccione **Seleccionar usuarios y**grupos, seleccione usuarios y  >  **grupos**  >  **Select**.</span><span class="sxs-lookup"><span data-stu-id="8e961-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="8e961-148">En el panel de **selección** , seleccione el grupo **GlobalAdmins** y, a continuación, seleccione **seleccionar**  >  **listo**.</span><span class="sxs-lookup"><span data-stu-id="8e961-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="8e961-149">En la sección **asignaciones** , seleccione **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="8e961-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="8e961-150">En el panel de **condiciones** , seleccione **riesgo de inicio de sesión**, seleccione **sí** para **configurar**, seleccione **alta** y **media**y, a continuación, seleccione **seleccionar** y **listo**.</span><span class="sxs-lookup"><span data-stu-id="8e961-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="8e961-151">En la sección **controles de acceso** del panel **nuevo** , seleccione **conceder**.</span><span class="sxs-lookup"><span data-stu-id="8e961-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="8e961-152">En el panel **conceder** , seleccione **Bloquear acceso**y, a continuación, seleccione **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="8e961-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="8e961-153">En el panel **nuevo** , seleccione **activado** para **Habilitar Directiva**y, a continuación, seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="8e961-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="8e961-154">Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="8e961-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="8e961-155">Para probar la primera Directiva, cierre e inicie sesión con la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="8e961-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="8e961-156">Se le pedirá que configure la MFA.</span><span class="sxs-lookup"><span data-stu-id="8e961-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="8e961-157">Esto demuestra que se está aplicando la primera Directiva.</span><span class="sxs-lookup"><span data-stu-id="8e961-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="8e961-158">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="8e961-158">Next step</span></span>

<span data-ttu-id="8e961-159">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="8e961-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e961-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e961-160">See also</span></span>

[<span data-ttu-id="8e961-161">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="8e961-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="8e961-162">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8e961-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8e961-163">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8e961-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8e961-164">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8e961-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
