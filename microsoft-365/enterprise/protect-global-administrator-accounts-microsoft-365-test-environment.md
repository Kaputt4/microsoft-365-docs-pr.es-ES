---
title: Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Siga estos pasos para proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 457ac33aa2242dc4b25cd662bf233bb1599a6fec
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071559"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ec6e7-103">Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec6e7-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ec6e7-104">Puede evitar ataques digitales en su organización asegurándose de que las cuentas de administrador son lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="ec6e7-105">En este artículo se describe cómo usar las directivas de acceso condicional de Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-105">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="ec6e7-106">Existen dos fases para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="ec6e7-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="ec6e7-107">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="ec6e7-108">Proteja su cuenta de administrador global dedicada.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-108">Protect your dedicated global administrator account.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ec6e7-110">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ec6e7-111">Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec6e7-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ec6e7-112">Si solo quiere probar la protección de la cuenta de administrador global de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ec6e7-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ec6e7-113">Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ec6e7-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="ec6e7-114">La comprobación de la protección de la cuenta de administrador global no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="ec6e7-114">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="ec6e7-115">Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-115">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="ec6e7-116">Fase 2: configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="ec6e7-116">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="ec6e7-117">En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-117">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="ec6e7-118">En una pestaña independiente, abra el [centro de administración de Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ec6e7-118">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="ec6e7-119">En **usuarios activos**, haga clic en **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-119">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="ec6e7-120">En la página **nuevo usuario** , escriba **DedicatedAdmin** en **nombre**, **nombre para mostrar**y nombre de **usuario**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-120">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="ec6e7-121">Haga clic en **contraseña**, en **deseo crear la contraseña**y, a continuación, escriba una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-121">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="ec6e7-122">Registre la contraseña de esta nueva cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-122">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="ec6e7-123">Desactive **la casilla hacer que este usuario cambie su contraseña la primera vez que inicie sesión**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-123">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="ec6e7-124">Haga clic en **roles**y, a continuación, en **administrador global**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-124">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="ec6e7-125">Haga clic en **licencias de producto**y, a continuación, active las licencias de **Enterprise Mobility + Security e5** y **Office 365 Enterprise E5** en.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-125">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="ec6e7-126">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-126">Click **Add**.</span></span>
9. <span data-ttu-id="ec6e7-127">En la **página se ha agregado el usuario**, desactive **Enviar contraseña en correo electrónico**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-127">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="ec6e7-128">A continuación, cree un nuevo grupo denominado GlobalAdmins y agréguele la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="ec6e7-129">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en el icono grupos en el panel de navegación izquierdo y, a continuación, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-129">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="ec6e7-130">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="ec6e7-131">En la página **nuevo grupo** , escriba **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-131">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="ec6e7-132">Haga clic en **seleccionar propietario, seleccione** su cuenta de administrador global y, a continuación, haga clic en **Agregar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-132">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="ec6e7-133">En la lista de grupos, haga clic en el grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="ec6e7-133">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="ec6e7-134">En la página **GlobalAdmins** , haga clic en **Editar para miembro**y, a continuación, haga clic en **Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-134">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="ec6e7-135">En la lista, haga clic en la cuenta **DedicatedAdmin** y, a continuación, haga clic en **guardar > cerrar > cerrar > centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-135">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="ec6e7-136">A continuación, cree directivas de acceso condicional para requerir la autenticación multifactor para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-136">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="ec6e7-137">Esta primera Directiva requiere que todas las cuentas de administrador global usen MFA.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-137">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="ec6e7-138">En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="ec6e7-138">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ec6e7-139">Haga clic en **Azure active directory > acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-139">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="ec6e7-140">En la hoja de **acceso condicional-directivas** , haga clic en **Directiva de línea de base: requerir MFA para administradores (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-140">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="ec6e7-141">En las **directivas de línea base...**</span><span class="sxs-lookup"><span data-stu-id="ec6e7-141">On the **Baseline policies…**</span></span> <span data-ttu-id="ec6e7-142">Haga clic en **usar Directiva inmediatamente > guardar**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-142">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="ec6e7-143">Esta segunda Directiva bloquea el acceso a la autenticación de la cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="ec6e7-144">En la hoja de **acceso condicional-directivas** , haga clic en **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-144">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="ec6e7-145">En la hoja **nueva** , escriba **administradores globales** en **nombre**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-145">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="ec6e7-146">En la sección **asignaciones** , haga clic en **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="ec6e7-147">En la ficha **incluir** de la hoja **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-147">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="ec6e7-148">En la hoja **seleccionar** , haga clic en el **GlobalAdmins > seleccione > listo**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-148">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="ec6e7-149">En la sección **asignaciones** , haga clic en **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="ec6e7-150">En la **hoja condiciones** , haga clic en **riesgo de inicio de sesión**, haga clic en **sí** para **configurar**, haga clic en **alta** y **media**y, a continuación, haga clic en **seleccionar** y **listo**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-150">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="ec6e7-151">En la sección **controles de acceso** de la **nueva** hoja, haga clic en **conceder**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-151">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="ec6e7-152">En la hoja **conceder** , haga clic en **Bloquear acceso**y, a continuación, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-152">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="ec6e7-153">En la hoja **nueva** , haga clic en **Habilitar Directiva**y, a continuación, haga **clic en** **crear**.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-153">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="ec6e7-154">Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="ec6e7-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="ec6e7-155">Para probar la primera Directiva, cierre e inicie sesión con la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="ec6e7-156">Se le pedirá que configure la MFA en la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-156">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="ec6e7-157">Esto demuestra que se está aplicando la primera Directiva.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="ec6e7-158">Consulte el paso [proteger las cuentas de administrador global](identity-create-protect-global-admins.md#identity-global-admin) en la fase de identidad para obtener información y vínculos para proteger las cuentas de administrador global en producción.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="ec6e7-159">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="ec6e7-159">Next step</span></span>

<span data-ttu-id="ec6e7-160">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="ec6e7-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec6e7-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec6e7-161">See also</span></span>

[<span data-ttu-id="ec6e7-162">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="ec6e7-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="ec6e7-163">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec6e7-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ec6e7-164">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec6e7-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ec6e7-165">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec6e7-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
