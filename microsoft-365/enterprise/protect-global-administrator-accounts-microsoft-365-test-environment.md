---
title: Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise
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
description: Siga estos pasos para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871182"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e7f79-103">Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7f79-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e7f79-p101">Para evitar los ataques digitales en su organización, asegurarse de que las cuentas de administrador sean tan seguras como sea posible. En este artículo se describe cómo usar las directivas de acceso condicional de seguridad de la aplicación de nube de Office 365 y Azure AD para proteger las cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e7f79-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="e7f79-106">Existen dos fases a proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="e7f79-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="e7f79-107">Crear el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e7f79-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="e7f79-108">Proteger la cuenta de administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="e7f79-108">Protect your dedicated global administrator account.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e7f79-110">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e7f79-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e7f79-111">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7f79-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e7f79-112">Si desea probar la protección de la cuenta de administrador global de una manera ligera con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e7f79-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e7f79-113">Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e7f79-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7f79-p102">Comprobación de la cuenta de administrador global protección no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectado a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="e7f79-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="e7f79-116">Fase 2: Configuración de seguridad de la aplicación en la nube y las directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="e7f79-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="e7f79-117">En primer lugar, cree una directiva de seguridad de la aplicación de Office 365 en la nube para supervisar la actividad de la cuenta de administrador global y enviar alertas a la dirección de correo electrónico de su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e7f79-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="e7f79-118">Inicie sesión el portal de Office 365 en [http://portal.office.com](http://portal.office.com) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e7f79-118">Sign in to the Office 365 portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="e7f79-p103">Haga clic en el icono de **administración** . En la ficha del **Centro de administración de Office** , haga clic en **centros de administración > seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="e7f79-121">En el panel de navegación izquierdo, haga clic en **alertas > Administrar avanzada alertas**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="e7f79-122">En la página **Administrar alertas de avanzada** , haga clic en **activar la seguridad de la aplicación de nube de Office 365**y, a continuación, haga clic en **Ir a la seguridad de la aplicación de nube de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="e7f79-123">En la ficha nuevo del **panel** , haga clic en **Control > directivas**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="e7f79-124">En la página **Directiva** , haga clic en **Crear directiva**y, a continuación, haga clic en **Directiva de actividad**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="e7f79-125">En **nombre de directiva**, escriba **actividad administrativa**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="e7f79-126">En **Gravedad de directiva**, haga clic en **Alto**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="e7f79-127">En **categoría**, haga clic en **cuentas con privilegios**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="e7f79-128">**Crear filtros para la directiva**, en **las actividades que coincidan con todos los elementos siguientes**, haga clic en **actividades administrativas**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="e7f79-p104">En **Alertas**, haga clic en **Enviar alerta como mensaje de correo electrónico**. En **Para**, escriba la dirección de correo electrónico de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e7f79-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="e7f79-131">En la parte inferior de la página, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="e7f79-132">Cierre la ficha de **panel** .</span><span class="sxs-lookup"><span data-stu-id="e7f79-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="e7f79-133">A continuación, cree una nueva cuenta de usuario como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="e7f79-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="e7f79-134">En la ficha del **Centro de administración de Office** , en **usuarios activos**, haga clic en **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="e7f79-135">En la página **nuevo usuario** , escriba **DedicatedAdmin** en el **nombre**, el **nombre para mostrar**y el **nombre de usuario**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="e7f79-p105">Haga clic en **contraseña**, haga clic en **Permitir la creación de la contraseña**y, a continuación, escriba una contraseña segura. Registre la contraseña para esta cuenta nueva en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="e7f79-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="e7f79-138">Desactive **hacer que este usuario cambiar su contraseña cuando inician sesión por primera vez en**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="e7f79-139">Haga clic en **funciones**y, a continuación, haga clic en **Administrador Global**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="e7f79-140">Haga clic en **licencias de producto**y, a continuación, activar la **movilidad de la empresa + E5 de seguridad** y **licencias de Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="e7f79-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="e7f79-141">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-141">Click **Add**.</span></span>
8. <span data-ttu-id="e7f79-142">En la **página se agregó el usuario**, desactive **Enviar contraseña en correo electrónico**y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="e7f79-143">A continuación, cree un nuevo grupo denominado GlobalAdmins y agregue la cuenta DedicatedAdmin a ella.</span><span class="sxs-lookup"><span data-stu-id="e7f79-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="e7f79-144">En la ficha del **Centro de administración de Office** , haga clic en el icono de grupos en el panel de navegación izquierdo y, a continuación, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="e7f79-145">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="e7f79-146">En la página **Nuevo grupo** , escriba **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="e7f79-147">Haga clic en **Seleccionar propietario de** la cuenta de administrador global y, a continuación, haga clic en **Agregar > Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="e7f79-148">En la lista de grupos, haga clic en el grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="e7f79-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="e7f79-149">En la página **GlobalAdmins** , haga clic en **Editar para el miembro**y, a continuación, haga clic en **Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="e7f79-150">En la lista, haga clic en la cuenta de **DedicatedAdmin** y, a continuación, haga clic en **Guardar > Close > Close > Centro de administración de**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="e7f79-151">A continuación, cree las directivas de acceso condicional requerir la autenticación con varios factores para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="e7f79-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="e7f79-152">Esta primera directiva requiere que todas las cuentas de administrador global usar MFA.</span><span class="sxs-lookup"><span data-stu-id="e7f79-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="e7f79-153">En una nueva ficha del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="e7f79-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="e7f79-154">Haga clic en **Azure Active Directory > acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="e7f79-155">En el servidor blade de **acceso condicional – las directivas** , haga clic en **Directiva de línea de base: requieren MFA para los administradores (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="e7f79-p106">En el servidor blade de **las directivas de línea de base...** , haga clic en **usar inmediatamente la directiva > Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="e7f79-158">Esta segunda directiva bloquea el acceso a la autenticación de cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="e7f79-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="e7f79-159">En el servidor blade de **acceso condicional – las directivas** , haga clic en **nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="e7f79-160">En el servidor blade de **nuevo** , escriba **los administradores globales** en **nombre**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="e7f79-161">En la sección **asignaciones** , haga clic en **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="e7f79-162">En la ficha **incluir** de blade de **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="e7f79-163">En el servidor blade **Seleccione** , haga clic en el **GlobalAdmins > seleccione > realiza**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="e7f79-164">En la sección **asignaciones** , haga clic en **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="e7f79-165">En el servidor blade de **condiciones** , haga clic en **Inicio de sesión de riesgo**, haga clic en **Sí** para **Configurar**y, a continuación, haga clic en **alto** y **medio**y, a continuación, haga clic en **Seleccionar** y **Listo**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="e7f79-166">En la sección de **controles de acceso** del módulo **nuevo** , haga clic en **conceder**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="e7f79-167">En el servidor blade **Grant** , haga clic en **bloquear el acceso**y, a continuación, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="e7f79-168">En el servidor blade de **nuevo** , haga clic **en** para **Habilitar la directiva**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="e7f79-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="e7f79-169">Cierre las fichas de **Centro de administración de Office** y **portal de Azure** .</span><span class="sxs-lookup"><span data-stu-id="e7f79-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="e7f79-p107">Para probar la primera directiva, cierre la sesión e inicie sesión con la cuenta DedicatedAdmin. Debe pedir para configurar MFA en la cuenta de usuario. Esto demuestra que se aplica la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="e7f79-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="e7f79-173">Consulte el paso de [las cuentas de administrador global de Protect](identity-designate-protect-admin-accounts.md) en la fase de identidad para obtener información y vínculos para proteger las cuentas de administrador global en producción.</span><span class="sxs-lookup"><span data-stu-id="e7f79-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="e7f79-174">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e7f79-174">Next step</span></span>

<span data-ttu-id="e7f79-175">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="e7f79-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7f79-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7f79-176">See also</span></span>

[<span data-ttu-id="e7f79-177">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="e7f79-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="e7f79-178">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7f79-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e7f79-179">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7f79-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e7f79-180">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7f79-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
