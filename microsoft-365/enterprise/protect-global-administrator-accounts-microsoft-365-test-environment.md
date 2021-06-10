---
title: Proteger cuentas de administrador global en su Microsoft 365 entorno de prueba empresarial
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
description: Siga estos pasos para proteger las cuentas de administrador global en su Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918887"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="73176-103">Proteger cuentas de administrador global en su Microsoft 365 entorno de prueba empresarial</span><span class="sxs-lookup"><span data-stu-id="73176-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="73176-104">*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*</span><span class="sxs-lookup"><span data-stu-id="73176-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="73176-105">Puede evitar ataques digitales en su organización asegurándose de que sus cuentas de administrador sean lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="73176-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="73176-106">En este artículo se describe cómo usar directivas de acceso condicional Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="73176-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="73176-107">La protección de cuentas de administrador global en Microsoft 365 entorno de prueba de empresa implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="73176-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="73176-108">Fase 1: Crear su Microsoft 365 entorno de prueba empresarial</span><span class="sxs-lookup"><span data-stu-id="73176-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="73176-109">Fase 2: Configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="73176-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="73176-111">Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="73176-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="73176-112">Fase 1: Crear su Microsoft 365 entorno de prueba empresarial</span><span class="sxs-lookup"><span data-stu-id="73176-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="73176-113">Si desea probar la protección de cuentas de administrador global de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="73176-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="73176-114">Si desea probar la protección de cuentas de administrador global en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="73176-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="73176-115">Probar la protección de cuentas de administrador global no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="73176-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="73176-116">Se proporciona aquí como una opción para que pueda probar la protección de cuentas de administrador global y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="73176-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="73176-117">Fase 2: Configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="73176-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="73176-118">En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="73176-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="73176-119">En una pestaña independiente, abra el centro [Microsoft 365 de administración](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="73176-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="73176-120">Seleccione **Usuarios**  >  **Usuarios activos** y, a continuación, seleccione Agregar un **usuario**.</span><span class="sxs-lookup"><span data-stu-id="73176-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="73176-121">En el **panel Agregar usuario,** escriba **DedicatedAdmin** en los cuadros **Nombre,** **Nombre para** mostrar y **Nombre de** usuario.</span><span class="sxs-lookup"><span data-stu-id="73176-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="73176-122">Seleccione **Contraseña**, **seleccione Permitirme crear la contraseña** y, a continuación, escriba una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="73176-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="73176-123">Registre la contraseña de esta nueva cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="73176-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="73176-124">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="73176-124">Select **Next**.</span></span>
6. <span data-ttu-id="73176-125">En el **panel Asignar licencias de producto,** seleccione **Microsoft 365 E5** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="73176-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="73176-126">En el **panel Configuración opcional,** seleccione **Roles Admin** center  >  **access**  >  **Global admin**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="73176-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="73176-127">En el **panel Ya casi** terminado, seleccione Finalizar **adición** y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="73176-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="73176-128">A continuación, cree un nuevo grupo denominado GlobalAdmins y agréle la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="73176-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="73176-129">En la **Microsoft 365 centro de administración,** seleccione **Grupos** en la navegación izquierda y, a continuación, **seleccione Grupos**.</span><span class="sxs-lookup"><span data-stu-id="73176-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="73176-130">Seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="73176-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="73176-131">En el **panel Elegir un tipo de grupo,** seleccione **Seguridad** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="73176-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="73176-132">En el **panel Configurar los conceptos** básicos, seleccione **Crear grupo** y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="73176-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="73176-133">En el **panel Revisar y terminar de agregar grupo,** escriba **GlobalAdmins** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="73176-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="73176-134">En la lista de grupos, seleccione el **grupo GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="73176-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="73176-135">En el **panel GlobalAdmins,** seleccione **Miembros** y, a continuación, **seleccione Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="73176-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="73176-136">En el **panel GlobalAdmins,** seleccione **Agregar** miembros, seleccione la cuenta **DedicatedAdmin** y la cuenta de administrador global y, a continuación, **seleccione Guardar**  >  **cerrar**  >  **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="73176-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="73176-137">A continuación, cree directivas de acceso condicional para requerir autenticación multifactor para cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="73176-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="73176-138">Esta primera directiva requiere que todas las cuentas de administrador global usen MFA.</span><span class="sxs-lookup"><span data-stu-id="73176-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="73176-139">En una nueva pestaña del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="73176-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="73176-140">Haga **clic Azure Active Directory** acceso  >  **condicional** de  >  **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="73176-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="73176-141">En el **panel Acceso condicional: directivas,** seleccione **Directiva de línea base: Requerir MFA para administradores (versión preliminar).**</span><span class="sxs-lookup"><span data-stu-id="73176-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="73176-142">En el **panel Directiva de** línea base, seleccione Usar directiva inmediatamente > **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="73176-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="73176-143">Esta segunda directiva bloquea el acceso a la autenticación de cuentas de administrador global cuando el riesgo de inicio de sesión es medio o alto.</span><span class="sxs-lookup"><span data-stu-id="73176-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="73176-144">En el **panel Acceso condicional: directivas,** seleccione **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="73176-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="73176-145">En el **panel Nuevo,** escriba **Administradores globales** en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="73176-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="73176-146">En la **sección Asignaciones,** seleccione **Usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="73176-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="73176-147">En la **pestaña Incluir** del panel Usuarios **y grupos,** seleccione **Seleccionar usuarios y grupos** Usuarios  >  **y grupos**  >  **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="73176-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="73176-148">En el **panel Seleccionar,** seleccione el **grupo GlobalAdmins** y, a continuación, **seleccione Seleccionar**  >  **listo**.</span><span class="sxs-lookup"><span data-stu-id="73176-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="73176-149">En la **sección Asignaciones,** seleccione **Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="73176-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="73176-150">En el **panel Condiciones,** seleccione **Riesgo de** inicio de sesión, **Seleccione Sí** para **Configurar**, **Seleccione** Alto y Medio **y,** a continuación, **seleccione Seleccionar** y **Listo**.</span><span class="sxs-lookup"><span data-stu-id="73176-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="73176-151">En la **sección Controles de acceso** del panel **Nuevo,** seleccione **Conceder**.</span><span class="sxs-lookup"><span data-stu-id="73176-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="73176-152">En el **panel Conceder,** seleccione **Bloquear acceso** y, a continuación, **seleccione Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="73176-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="73176-153">En el **panel Nuevo,** seleccione **Activar para** **Habilitar directiva** y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="73176-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="73176-154">Cierre las **pestañas Azure Portal** **y Microsoft 365 centro de** administración.</span><span class="sxs-lookup"><span data-stu-id="73176-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="73176-155">Para probar la primera directiva, cerrar sesión e iniciar sesión con la cuenta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="73176-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="73176-156">Se le pedirá que configure MFA.</span><span class="sxs-lookup"><span data-stu-id="73176-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="73176-157">Esto demuestra que se está aplicando la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="73176-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="73176-158">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="73176-158">Next step</span></span>

<span data-ttu-id="73176-159">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="73176-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="73176-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="73176-160">See also</span></span>

[<span data-ttu-id="73176-161">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="73176-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="73176-162">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="73176-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="73176-163">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="73176-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="73176-164">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="73176-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)