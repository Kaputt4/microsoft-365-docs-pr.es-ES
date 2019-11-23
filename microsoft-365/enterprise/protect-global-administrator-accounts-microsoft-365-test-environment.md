---
title: Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Siga estos pasos para proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 5447177c6581b69d48272ceef7718552ea84dc9d
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202231"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a8b13-103">Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8b13-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a8b13-104">*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a8b13-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a8b13-105">Puede evitar ataques digitales en su organización asegurándose de que las cuentas de administrador son lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="a8b13-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="a8b13-106">En este artículo se describe cómo usar las directivas de acceso condicional de Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a8b13-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="a8b13-107">Existen dos fases para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="a8b13-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="a8b13-108">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a8b13-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="a8b13-109">Proteja su cuenta de administrador global dedicada.</span><span class="sxs-lookup"><span data-stu-id="a8b13-109">Protect your dedicated global administrator account.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a8b13-111">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a8b13-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a8b13-112">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8b13-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a8b13-113">Si solo quiere probar la protección de la cuenta de administrador global de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a8b13-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a8b13-114">Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a8b13-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="a8b13-115">La comprobación de la protección de la cuenta de administrador global no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a8b13-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="a8b13-116">Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="a8b13-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="a8b13-117">Fase 2: configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="a8b13-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="a8b13-118">En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="a8b13-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="a8b13-119">En una pestaña independiente, abra el [centro de administración de Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a8b13-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="a8b13-120">En **usuarios activos**, haga clic en **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="a8b13-121">En la página **nuevo usuario** , escriba **DedicatedAdmin** en **nombre**, **nombre para mostrar**y nombre de **usuario**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="a8b13-122">Haga clic en **contraseña**, en **deseo crear la contraseña**y, a continuación, escriba una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="a8b13-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="a8b13-123">Registre la contraseña de esta nueva cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="a8b13-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="a8b13-124">Desactive **la casilla hacer que este usuario cambie su contraseña la primera vez que inicie sesión**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="a8b13-125">Haga clic en **roles**y, a continuación, en **administrador global**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="a8b13-126">Haga clic en **licencias de producto**y, a continuación, active la licencia de **Microsoft 365 E5** .</span><span class="sxs-lookup"><span data-stu-id="a8b13-126">Click **Product licenses**, and then turn the **Microsoft 365 E5** license on.</span></span>
8. <span data-ttu-id="a8b13-127">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-127">Click **Add**.</span></span>
9. <span data-ttu-id="a8b13-128">En la **página se ha agregado el usuario**, desactive **Enviar contraseña en correo electrónico**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="a8b13-129">A continuación, cree un nuevo grupo denominado GlobalAdmins y agréguele la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="a8b13-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="a8b13-130">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en el icono grupos en el panel de navegación izquierdo y, a continuación, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="a8b13-131">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="a8b13-132">En la página **nuevo grupo** , escriba **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="a8b13-133">Haga clic en **seleccionar propietario, seleccione** su cuenta de administrador global y, a continuación, haga clic en **Agregar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="a8b13-134">En la lista de grupos, haga clic en el grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="a8b13-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="a8b13-135">En la página **GlobalAdmins** , haga clic en **Editar para miembro**y, a continuación, haga clic en **Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="a8b13-136">En la lista, haga clic en la cuenta **DedicatedAdmin** y, a continuación, haga clic en **guardar > cerrar > cerrar > centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="a8b13-137">A continuación, cree directivas de acceso condicional para requerir la autenticación multifactor para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="a8b13-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="a8b13-138">Esta primera Directiva requiere que todas las cuentas de administrador global usen MFA.</span><span class="sxs-lookup"><span data-stu-id="a8b13-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="a8b13-139">En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a8b13-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a8b13-140">Haga clic en **Azure active directory > acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="a8b13-141">En la hoja de **acceso condicional-directivas** , haga clic en **Directiva de línea de base: requerir MFA para administradores (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="a8b13-142">En las **directivas de línea base...**</span><span class="sxs-lookup"><span data-stu-id="a8b13-142">On the **Baseline policies…**</span></span> <span data-ttu-id="a8b13-143">Haga clic en **usar Directiva inmediatamente > guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="a8b13-144">Esta segunda Directiva bloquea el acceso a la autenticación de la cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="a8b13-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="a8b13-145">En la hoja de **acceso condicional-directivas** , haga clic en **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="a8b13-146">En la hoja **nueva** , escriba **administradores globales** en **nombre**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="a8b13-147">En la sección **asignaciones** , haga clic en **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="a8b13-148">En la ficha **incluir** de la hoja **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="a8b13-149">En la hoja **seleccionar** , haga clic en el **GlobalAdmins > seleccione > listo**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="a8b13-150">En la sección **asignaciones** , haga clic en **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="a8b13-151">En la **hoja condiciones** , haga clic en **riesgo de inicio de sesión**, haga clic en **sí** para **configurar**, haga clic en **alta** y **media**y, a continuación, haga clic en **seleccionar** y **listo**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="a8b13-152">En la sección **controles de acceso** de la **nueva** hoja, haga clic en **conceder**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="a8b13-153">En la hoja **conceder** , haga clic en **Bloquear acceso**y, a continuación, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="a8b13-154">En la hoja **nueva** , haga clic en **Habilitar Directiva**y, a continuación, haga **clic en** **crear**.</span><span class="sxs-lookup"><span data-stu-id="a8b13-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="a8b13-155">Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="a8b13-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="a8b13-156">Para probar la primera Directiva, cierre e inicie sesión con la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="a8b13-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="a8b13-157">Se le pedirá que configure la MFA en la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="a8b13-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="a8b13-158">Esto demuestra que se está aplicando la primera Directiva.</span><span class="sxs-lookup"><span data-stu-id="a8b13-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="a8b13-159">Consulte el paso [proteger las cuentas de administrador global](identity-create-protect-global-admins.md#identity-global-admin) en la fase de identidad para obtener información y vínculos para proteger las cuentas de administrador global en producción.</span><span class="sxs-lookup"><span data-stu-id="a8b13-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a8b13-160">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="a8b13-160">Next step</span></span>

<span data-ttu-id="a8b13-161">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="a8b13-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8b13-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8b13-162">See also</span></span>

[<span data-ttu-id="a8b13-163">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="a8b13-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a8b13-164">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8b13-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a8b13-165">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8b13-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a8b13-166">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8b13-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
