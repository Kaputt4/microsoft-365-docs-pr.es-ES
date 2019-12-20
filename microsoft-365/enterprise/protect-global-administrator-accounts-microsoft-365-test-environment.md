---
title: Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise
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
description: Siga estos pasos para proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 32e5983532c89c6ada106ed32d8ef3eabd5dc569
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801395"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="27a89-103">Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="27a89-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="27a89-104">*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="27a89-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="27a89-105">Puede evitar ataques digitales en su organización asegurándose de que las cuentas de administrador son lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="27a89-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="27a89-106">En este artículo se describe cómo usar las directivas de acceso condicional de Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="27a89-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="27a89-107">Existen dos fases para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="27a89-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="27a89-108">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="27a89-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="27a89-109">Proteja su cuenta de administrador global dedicada.</span><span class="sxs-lookup"><span data-stu-id="27a89-109">Protect your dedicated global administrator account.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="27a89-111">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="27a89-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="27a89-112">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="27a89-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="27a89-113">Si solo quiere probar la protección de la cuenta de administrador global de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="27a89-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="27a89-114">Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="27a89-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="27a89-115">La comprobación de la protección de la cuenta de administrador global no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="27a89-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="27a89-116">Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="27a89-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="27a89-117">Fase 2: configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="27a89-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="27a89-118">En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="27a89-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="27a89-119">En una pestaña independiente, abra el [centro de administración de Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="27a89-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="27a89-120">Haga clic en **usuarios > usuarios activos**y, a continuación, haga clic en **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="27a89-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="27a89-121">En el panel **Agregar usuario** , escriba **DedicatedAdmin** en **nombre**, **nombre para mostrar**y nombre de **usuario**.</span><span class="sxs-lookup"><span data-stu-id="27a89-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="27a89-122">Haga clic en **contraseña**, en **deseo crear la contraseña**y, a continuación, escriba una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="27a89-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="27a89-123">Registre la contraseña de esta nueva cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="27a89-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="27a89-124">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="27a89-124">Click **Next**.</span></span>
6. <span data-ttu-id="27a89-125">En el panel **asignar licencias de producto** , seleccione **Microsoft 365 e5** u **Office 365 E5**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="27a89-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="27a89-126">En el panel **configuración opcional** , haga clic en **roles**y, a continuación, seleccione **acceso al centro de administración** y **administrador global**. Haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="27a89-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="27a89-127">En el panel **está casi terminado** , haga clic en **Finalizar adición**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="27a89-128">A continuación, cree un nuevo grupo denominado GlobalAdmins y agréguele la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="27a89-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="27a89-129">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en **grupos** en el panel de navegación izquierdo y, después, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="27a89-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="27a89-130">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="27a89-131">En el panel **elegir un tipo de grupo** , seleccione **seguridad**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="27a89-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="27a89-132">En el panel **configurar conceptos básicos** , haga clic en **Crear grupo**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="27a89-133">En el panel **revisar y finalizar agregar grupo** , escriba **GlobalAdmins**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="27a89-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="27a89-134">En la lista de grupos, haga clic en el grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="27a89-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="27a89-135">En el panel **GlobalAdmins** , haga clic en **miembros**y, a continuación, haga clic en **Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="27a89-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="27a89-136">En el panel **GlobalAdmins** , haga clic en **Agregar miembros**, seleccione la cuenta **DedicatedAdmin** y la cuenta de administrador global y, a continuación, haga clic en **Guardar > cerrar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="27a89-137">A continuación, cree directivas de acceso condicional para requerir la autenticación multifactor para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="27a89-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="27a89-138">Esta primera Directiva requiere que todas las cuentas de administrador global usen MFA.</span><span class="sxs-lookup"><span data-stu-id="27a89-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="27a89-139">En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="27a89-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="27a89-140">Haga clic en **Azure active directory > Security > el acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="27a89-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="27a89-141">En el panel **acceso condicional-directivas** , haga clic en **Directiva de línea de base: requerir MFA para administradores (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="27a89-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="27a89-142">En el panel **Directiva de línea de base** , haga clic en usar la **Directiva inmediatamente > guardar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="27a89-143">Esta segunda Directiva bloquea el acceso a la autenticación de la cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="27a89-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="27a89-144">En el panel **acceso condicional-directivas** , haga clic en **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="27a89-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="27a89-145">En el panel **nuevo** , escriba **administradores globales** en **nombre**.</span><span class="sxs-lookup"><span data-stu-id="27a89-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="27a89-146">En la sección **asignaciones** , haga clic en **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="27a89-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="27a89-147">En la ficha **incluir** del panel **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.</span><span class="sxs-lookup"><span data-stu-id="27a89-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="27a89-148">En el panel de **selección** , haga clic en el grupo **GlobalAdmins** y, a continuación, haga clic en **seleccionar > listo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="27a89-149">En la sección **asignaciones** , haga clic en **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="27a89-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="27a89-150">En el panel de **condiciones** , haga clic en **riesgo de inicio de sesión**, haga clic en **sí** para **configurar**, haga clic en **alta** y **media**y, a continuación, haga clic en **seleccionar** y **listo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="27a89-151">En la sección **controles de acceso** del panel **nuevo** , haga clic en **conceder**.</span><span class="sxs-lookup"><span data-stu-id="27a89-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="27a89-152">En el panel **conceder** , haga clic en **Bloquear acceso**y, a continuación, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="27a89-153">En el panel **nuevo** , haga clic **en** **Habilitar Directiva**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="27a89-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="27a89-154">Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="27a89-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="27a89-155">Para probar la primera Directiva, cierre e inicie sesión con la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="27a89-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="27a89-156">Se le pedirá que configure la MFA.</span><span class="sxs-lookup"><span data-stu-id="27a89-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="27a89-157">Esto demuestra que se está aplicando la primera Directiva.</span><span class="sxs-lookup"><span data-stu-id="27a89-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="27a89-158">Consulte el paso [proteger las cuentas de administrador global](identity-create-protect-global-admins.md#identity-global-admin) en la fase de identidad para obtener información y vínculos para proteger las cuentas de administrador global en producción.</span><span class="sxs-lookup"><span data-stu-id="27a89-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="27a89-159">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="27a89-159">Next step</span></span>

<span data-ttu-id="27a89-160">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="27a89-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="27a89-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="27a89-161">See also</span></span>

[<span data-ttu-id="27a89-162">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="27a89-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="27a89-163">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="27a89-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="27a89-164">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="27a89-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="27a89-165">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="27a89-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
