---
title: Identidad y dispositivo comunes, obtener acceso a directivas - Microsoft 365 Enterprise | Documentos de Microsoft
description: Explica las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de identidad y acceso a dispositivos.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871794"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="43267-103">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="43267-103">Common identity and device access policies</span></span>
<span data-ttu-id="43267-104">Este artículo describe la común recomendada directivas para proteger el acceso a los servicios, de la nube, con aplicaciones locales publicarán con Proxy de aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="43267-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="43267-p101">En estas instrucciones se explica cómo implementar las directivas recomendadas en un entorno recién aprovisionado. La configuración de estas directivas en un entorno de laboratorio independiente permite entender y evaluar las directivas recomendadas antes de su implementación en los entornos de preproducción y producción. El entorno recién aprovisionado puede ser solo en la nube o híbrido.</span><span class="sxs-lookup"><span data-stu-id="43267-p101">This guidance discusses how to deploy the recommended policies in a newly provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your pre-production and production environments. Your newly provisioned environment may be cloud-only or Hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="43267-108">Conjunto de directivas</span><span class="sxs-lookup"><span data-stu-id="43267-108">Policy set</span></span> 

<span data-ttu-id="43267-p102">El siguiente diagrama ilustra el conjunto de directivas recomendado. Muestra qué niveles de protecciones de cada directiva se aplica a y si las directivas se aplican a equipos, teléfonos y tabletas o ambas categorías de dispositivos. También indica donde se configuran estas directivas.</span><span class="sxs-lookup"><span data-stu-id="43267-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs, phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![Directivas comunes para configurar el acceso de identidad y dispositivos](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="43267-113">El resto de este artículo describe cómo configurar estas directivas.</span><span class="sxs-lookup"><span data-stu-id="43267-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="43267-p103">Se recomienda el uso de la autenticación multifactor antes de dispositivos que se inscriben en Intune para garantía de que el dispositivo está en posesión del usuario previsto. Y debe inscribirse dispositivos en Intune antes de aplicar las directivas de cumplimiento de normas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43267-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. And you must enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="43267-p104">Para dar tiempo para realizar estas tareas, se recomienda implementar las directivas de línea de base en el orden en que aparecen en esta tabla. Sin embargo, las directivas MFA para protección confidencial y altamente regulada pueden implementarse en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="43267-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="43267-118">Nivel de protección</span><span class="sxs-lookup"><span data-stu-id="43267-118">Protection level</span></span>|<span data-ttu-id="43267-119">Policies</span><span class="sxs-lookup"><span data-stu-id="43267-119">Policies</span></span>|<span data-ttu-id="43267-120">Más información</span><span class="sxs-lookup"><span data-stu-id="43267-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="43267-121">**Línea base**</span><span class="sxs-lookup"><span data-stu-id="43267-121">**Baseline**</span></span>|[<span data-ttu-id="43267-122">Requerir MFA al inicio de sesión de riesgo es *medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="43267-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="43267-123">Clientes de bloque que no admiten la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="43267-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="43267-124">Los clientes que no usan autenticación moderna pueden omitir las reglas de acceso condicional, por lo que es importante bloquear estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="43267-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these.</span></span>|
|        |[<span data-ttu-id="43267-125">Los usuarios de alto riesgo deben cambiar la contraseña</span><span class="sxs-lookup"><span data-stu-id="43267-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="43267-126">Fuerza a los usuarios cambiar su contraseña al iniciar la sesión si se detecta actividad de alto riesgo por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="43267-126">Forces users to change their password when signing in if high risk activity is detected for their account.</span></span>|
|        |[<span data-ttu-id="43267-127">Definir directivas de protección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="43267-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="43267-128">Una directiva por plataforma (iOS, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="43267-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="43267-129">Requieren aplicaciones aprobadas</span><span class="sxs-lookup"><span data-stu-id="43267-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="43267-130">Aplica la protección contra la aplicación móvil para teléfonos y tabletas</span><span class="sxs-lookup"><span data-stu-id="43267-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="43267-131">Definir directivas de cumplimiento de normas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="43267-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="43267-132">Una directiva para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="43267-132">One policy for each platform.</span></span>|
|        |[<span data-ttu-id="43267-133">Requerir PCs compatibles con</span><span class="sxs-lookup"><span data-stu-id="43267-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="43267-134">Aplica Intune administración de equipos</span><span class="sxs-lookup"><span data-stu-id="43267-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="43267-135">**Confidencial**</span><span class="sxs-lookup"><span data-stu-id="43267-135">**Sensitive**</span></span>|[<span data-ttu-id="43267-136">Requerir MFA al inicio de sesión de riesgo es *bajo*, *medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="43267-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="43267-137">Requerir compatible con PC *y* dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="43267-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="43267-138">Aplica la administración Intune para PC y teléfono/tabletas.</span><span class="sxs-lookup"><span data-stu-id="43267-138">Enforces Intune management for PCs and phone/tablets.</span></span>|
|<span data-ttu-id="43267-139">**Extremadamente regulado**</span><span class="sxs-lookup"><span data-stu-id="43267-139">**Highly regulated**</span></span>|[<span data-ttu-id="43267-140">*Siempre* requieren MFA</span><span class="sxs-lookup"><span data-stu-id="43267-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="43267-141">Asignación de directivas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="43267-141">Assigning policies to users</span></span>
<span data-ttu-id="43267-p105">Antes de configurar las directivas, identifique los grupos de Azure AD que utiliza para cada nivel de protección. Normalmente, la protección de línea de base se aplica a todas las personas de la organización. Un usuario que se incluye para la línea de base y protección confidencial tendrá todas las directivas de línea de base que se aplica además de las directivas confidenciales. Protección es acumulativa y se aplica la directiva más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="43267-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="43267-p106">Un procedimiento recomendado consiste en crear un grupo de Azure AD de exclusión de acceso condicional. Agregar este grupo a todas las reglas de acceso condicional en "Excluir". Esto le ofrece un método para proporcionar acceso a un usuario mientras solucionar problemas de acceso. Esto se recomienda como solución temporal. Supervise este grupo para que los cambios y asegúrese de que se está usando el grupo de exclusión sólo como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="43267-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="43267-151">En el siguiente diagrama se proporciona un ejemplo de asignación de usuario y las exclusiones.</span><span class="sxs-lookup"><span data-stu-id="43267-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![Asignación de usuario de ejemplo y exclusiones para las reglas de MFA](../images/identity-access-policies-assignment.png)

<span data-ttu-id="43267-p107">En la ilustración "equipo de proyecto secreto superior X" se asigna una directiva de acceso condicional que requiere MFA *siempre*. Ser razonable al aplicar mayores niveles de protección a los usuarios. Los miembros de este equipo de proyecto será necesario para proporcionar dos formas de autenticación cada vez que inicien sesión, incluso si no están viendo el contenido altamente regulado.</span><span class="sxs-lookup"><span data-stu-id="43267-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly regulated content.</span></span>  

 <span data-ttu-id="43267-p108">Todos los grupos de Azure AD creados como parte de estas recomendaciones deben crearse como grupos de Office 365. Esto es especialmente importante para la implementación de protección de información de Azure (AIP) cuando la protección de documentos en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="43267-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Captura de pantalla para la creación de grupos de Office 365](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="43267-159">Requerir MFA en función de inicio de sesión de riesgo</span><span class="sxs-lookup"><span data-stu-id="43267-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="43267-p109">Antes de solicitar MFA, utilice en primer lugar una directiva de registro de MFA de protección de identidad para registrar los usuarios de MFA. Después de que se registran los usuarios puede exigir MFA para el inicio de sesión. El [trabajo necesario como requisito previo](identity-access-prerequisites.md) se incluye el registro de todos los usuarios con MFA.</span><span class="sxs-lookup"><span data-stu-id="43267-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="43267-163">Para crear una directiva de acceso condicional, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43267-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="43267-p110">Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.</span><span class="sxs-lookup"><span data-stu-id="43267-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="43267-166">En el menú de la izquierda, seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="43267-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="43267-167">En la sección **Seguridad**, seleccione **Acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="43267-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="43267-168">Elija **nueva directiva** tal como se muestra en la captura de pantalla que aparece a continuación:</span><span class="sxs-lookup"><span data-stu-id="43267-168">Choose **New policy** as shown in the screenshot below:</span></span>

![Directiva de acceso condicional de base de referencia](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="43267-170">En las tablas siguientes se describe la configuración de directiva de acceso condicional para implementar para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="43267-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="43267-171">**Asignaciones**</span><span class="sxs-lookup"><span data-stu-id="43267-171">**Assignments**</span></span>

|<span data-ttu-id="43267-172">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-172">Type</span></span>|<span data-ttu-id="43267-173">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-173">Properties</span></span>|<span data-ttu-id="43267-174">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-174">Values</span></span>|<span data-ttu-id="43267-175">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-176">Usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="43267-176">Users and groups</span></span>|<span data-ttu-id="43267-177">Incluir</span><span class="sxs-lookup"><span data-stu-id="43267-177">Include</span></span>|<span data-ttu-id="43267-178">Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino</span><span class="sxs-lookup"><span data-stu-id="43267-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="43267-179">Comience con el grupo de seguridad que incluye usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="43267-179">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="43267-180">Excluir</span><span class="sxs-lookup"><span data-stu-id="43267-180">Exclude</span></span>|<span data-ttu-id="43267-181">Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)</span><span class="sxs-lookup"><span data-stu-id="43267-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="43267-182">Pertenencia modificada de forma temporal según necesidad</span><span class="sxs-lookup"><span data-stu-id="43267-182">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="43267-183">Aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="43267-183">Cloud apps</span></span>|<span data-ttu-id="43267-184">Incluir</span><span class="sxs-lookup"><span data-stu-id="43267-184">Include</span></span>|<span data-ttu-id="43267-p111">Seleccione las aplicaciones que desee aplicar a esta regla. Por ejemplo, seleccione Exchange en línea de Office 365</span><span class="sxs-lookup"><span data-stu-id="43267-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="43267-187">Condiciones</span><span class="sxs-lookup"><span data-stu-id="43267-187">Conditions</span></span>|<span data-ttu-id="43267-188">Configurado</span><span class="sxs-lookup"><span data-stu-id="43267-188">Configured</span></span>|<span data-ttu-id="43267-189">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-189">Yes</span></span>|<span data-ttu-id="43267-190">Configuración específica del entorno y las necesidades</span><span class="sxs-lookup"><span data-stu-id="43267-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="43267-191">Riesgo de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="43267-191">Sign-in risk</span></span>|<span data-ttu-id="43267-192">Nivel de riesgo</span><span class="sxs-lookup"><span data-stu-id="43267-192">Risk level</span></span>||<span data-ttu-id="43267-193">Vea las instrucciones en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="43267-193">See the guidance in the following table</span></span>|

<span data-ttu-id="43267-194">**Riesgo de inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="43267-194">**Sign-in risk**</span></span>

<span data-ttu-id="43267-195">Aplicar la configuración según el nivel de protección de destino.</span><span class="sxs-lookup"><span data-stu-id="43267-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="43267-196">Propiedad</span><span class="sxs-lookup"><span data-stu-id="43267-196">Property</span></span>|<span data-ttu-id="43267-197">Nivel de protección</span><span class="sxs-lookup"><span data-stu-id="43267-197">Level of protection</span></span>|<span data-ttu-id="43267-198">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-198">Values</span></span>|<span data-ttu-id="43267-199">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-200">Nivel de riesgo</span><span class="sxs-lookup"><span data-stu-id="43267-200">Risk level</span></span>|<span data-ttu-id="43267-201">Línea base</span><span class="sxs-lookup"><span data-stu-id="43267-201">Baseline</span></span>|<span data-ttu-id="43267-202">Alto, medio</span><span class="sxs-lookup"><span data-stu-id="43267-202">High, medium</span></span>|<span data-ttu-id="43267-203">Comprobar ambos</span><span class="sxs-lookup"><span data-stu-id="43267-203">Check both</span></span>|
| |<span data-ttu-id="43267-204">Confidencial</span><span class="sxs-lookup"><span data-stu-id="43267-204">Sensitive</span></span>|<span data-ttu-id="43267-205">Alta, Media, baja</span><span class="sxs-lookup"><span data-stu-id="43267-205">High, medium, low</span></span>|<span data-ttu-id="43267-206">Marcar los tres</span><span class="sxs-lookup"><span data-stu-id="43267-206">Check all three</span></span>|
| |<span data-ttu-id="43267-207">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="43267-207">Highly regulated</span></span>| |<span data-ttu-id="43267-208">Deje todas las opciones de verificación desactivada para aplicar siempre MFA</span><span class="sxs-lookup"><span data-stu-id="43267-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="43267-209">**Controles de acceso**</span><span class="sxs-lookup"><span data-stu-id="43267-209">**Access controls**</span></span>

|<span data-ttu-id="43267-210">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-210">Type</span></span>|<span data-ttu-id="43267-211">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-211">Properties</span></span>|<span data-ttu-id="43267-212">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-212">Values</span></span>|<span data-ttu-id="43267-213">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-214">Conceder</span><span class="sxs-lookup"><span data-stu-id="43267-214">Grant</span></span>|<span data-ttu-id="43267-215">Conceder acceso</span><span class="sxs-lookup"><span data-stu-id="43267-215">Grant access</span></span>|<span data-ttu-id="43267-216">True</span><span class="sxs-lookup"><span data-stu-id="43267-216">True</span></span>|<span data-ttu-id="43267-217">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="43267-217">Selected</span></span>|
||<span data-ttu-id="43267-218">Exigir MFA</span><span class="sxs-lookup"><span data-stu-id="43267-218">Require MFA</span></span>|<span data-ttu-id="43267-219">True</span><span class="sxs-lookup"><span data-stu-id="43267-219">True</span></span>|<span data-ttu-id="43267-220">Check</span><span class="sxs-lookup"><span data-stu-id="43267-220">Check</span></span>|
||<span data-ttu-id="43267-221">Requerir dispositivo para ser marcado como compatible</span><span class="sxs-lookup"><span data-stu-id="43267-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="43267-222">False</span><span class="sxs-lookup"><span data-stu-id="43267-222">False</span></span>||
||<span data-ttu-id="43267-223">Requerir dispositivo unida híbrida Azure AD</span><span class="sxs-lookup"><span data-stu-id="43267-223">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="43267-224">False</span><span class="sxs-lookup"><span data-stu-id="43267-224">False</span></span>||
||<span data-ttu-id="43267-225">Requiere aplicación cliente aprobado</span><span class="sxs-lookup"><span data-stu-id="43267-225">Require approved client app</span></span>|<span data-ttu-id="43267-226">False</span><span class="sxs-lookup"><span data-stu-id="43267-226">False</span></span>||
||<span data-ttu-id="43267-227">Exigir todos los controles seleccionados</span><span class="sxs-lookup"><span data-stu-id="43267-227">Require all the selected controls</span></span>|<span data-ttu-id="43267-228">True</span><span class="sxs-lookup"><span data-stu-id="43267-228">True</span></span>|<span data-ttu-id="43267-229">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="43267-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="43267-p112">Asegúrese de habilitar esta directiva, haciendo clic **en**. Tenga en cuenta también con la herramienta de [¿Qué ocurre si](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva</span><span class="sxs-lookup"><span data-stu-id="43267-p112">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="43267-232">Clientes de bloque que no admiten la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="43267-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="43267-p113">Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.</span><span class="sxs-lookup"><span data-stu-id="43267-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="43267-235">En el menú de la izquierda, seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="43267-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="43267-236">En la sección **Seguridad**, seleccione **Acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="43267-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="43267-237">Pulse **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="43267-237">Choose **New policy**.</span></span>

<span data-ttu-id="43267-238">En las tablas siguientes se describe la configuración de directiva de acceso condicional para implementar para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="43267-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="43267-239">**Asignaciones**</span><span class="sxs-lookup"><span data-stu-id="43267-239">**Assignments**</span></span>

|<span data-ttu-id="43267-240">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-240">Type</span></span>|<span data-ttu-id="43267-241">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-241">Properties</span></span>|<span data-ttu-id="43267-242">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-242">Values</span></span>|<span data-ttu-id="43267-243">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-244">Usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="43267-244">Users and groups</span></span>|<span data-ttu-id="43267-245">Incluir</span><span class="sxs-lookup"><span data-stu-id="43267-245">Include</span></span>|<span data-ttu-id="43267-246">Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino</span><span class="sxs-lookup"><span data-stu-id="43267-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="43267-247">Comience con el grupo de seguridad que incluye usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="43267-247">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="43267-248">Excluir</span><span class="sxs-lookup"><span data-stu-id="43267-248">Exclude</span></span>|<span data-ttu-id="43267-249">Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)</span><span class="sxs-lookup"><span data-stu-id="43267-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="43267-250">Pertenencia modificada de forma temporal según necesidad</span><span class="sxs-lookup"><span data-stu-id="43267-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="43267-251">Aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="43267-251">Cloud apps</span></span>|<span data-ttu-id="43267-252">Incluir</span><span class="sxs-lookup"><span data-stu-id="43267-252">Include</span></span>|<span data-ttu-id="43267-p114">Seleccione las aplicaciones que desee aplicar a esta regla. Por ejemplo, seleccione Exchange en línea de Office 365</span><span class="sxs-lookup"><span data-stu-id="43267-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="43267-255">Condiciones</span><span class="sxs-lookup"><span data-stu-id="43267-255">Conditions</span></span>|<span data-ttu-id="43267-256">Configurado</span><span class="sxs-lookup"><span data-stu-id="43267-256">Configured</span></span>|<span data-ttu-id="43267-257">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-257">Yes</span></span>|<span data-ttu-id="43267-258">Configurar aplicaciones de cliente</span><span class="sxs-lookup"><span data-stu-id="43267-258">Configure Client apps</span></span>|
|<span data-ttu-id="43267-259">Aplicaciones de cliente</span><span class="sxs-lookup"><span data-stu-id="43267-259">Client apps</span></span>|<span data-ttu-id="43267-260">Configurado</span><span class="sxs-lookup"><span data-stu-id="43267-260">Configured</span></span>|<span data-ttu-id="43267-261">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-261">Yes</span></span>|<span data-ttu-id="43267-262">Aplicaciones móviles y los clientes de escritorio, otros clientes (seleccione ambos)</span><span class="sxs-lookup"><span data-stu-id="43267-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="43267-263">**Controles de acceso**</span><span class="sxs-lookup"><span data-stu-id="43267-263">**Access controls**</span></span>

|<span data-ttu-id="43267-264">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-264">Type</span></span>|<span data-ttu-id="43267-265">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-265">Properties</span></span>|<span data-ttu-id="43267-266">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-266">Values</span></span>|<span data-ttu-id="43267-267">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-268">Conceder</span><span class="sxs-lookup"><span data-stu-id="43267-268">Grant</span></span>|<span data-ttu-id="43267-269">Bloquear acceso</span><span class="sxs-lookup"><span data-stu-id="43267-269">Block access</span></span>|<span data-ttu-id="43267-270">True</span><span class="sxs-lookup"><span data-stu-id="43267-270">True</span></span>|<span data-ttu-id="43267-271">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="43267-271">Selected</span></span>|
||<span data-ttu-id="43267-272">Exigir MFA</span><span class="sxs-lookup"><span data-stu-id="43267-272">Require MFA</span></span>|<span data-ttu-id="43267-273">False</span><span class="sxs-lookup"><span data-stu-id="43267-273">False</span></span>||
||<span data-ttu-id="43267-274">Requerir dispositivo para ser marcado como compatible</span><span class="sxs-lookup"><span data-stu-id="43267-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="43267-275">False</span><span class="sxs-lookup"><span data-stu-id="43267-275">False</span></span>||
||<span data-ttu-id="43267-276">Requerir dispositivo unida híbrida Azure AD</span><span class="sxs-lookup"><span data-stu-id="43267-276">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="43267-277">False</span><span class="sxs-lookup"><span data-stu-id="43267-277">False</span></span>||
||<span data-ttu-id="43267-278">Requiere aplicación cliente aprobado</span><span class="sxs-lookup"><span data-stu-id="43267-278">Require approved client app</span></span>|<span data-ttu-id="43267-279">False</span><span class="sxs-lookup"><span data-stu-id="43267-279">False</span></span>||
||<span data-ttu-id="43267-280">Exigir todos los controles seleccionados</span><span class="sxs-lookup"><span data-stu-id="43267-280">Require all the selected controls</span></span>|<span data-ttu-id="43267-281">True</span><span class="sxs-lookup"><span data-stu-id="43267-281">True</span></span>|<span data-ttu-id="43267-282">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="43267-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="43267-p115">Asegúrese de habilitar esta directiva, haciendo clic **en**. Tenga en cuenta también con la herramienta de [¿Qué ocurre si](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva</span><span class="sxs-lookup"><span data-stu-id="43267-p115">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="43267-285">Los usuarios de alto riesgo deben cambiar la contraseña</span><span class="sxs-lookup"><span data-stu-id="43267-285">High risk users must change password</span></span>
<span data-ttu-id="43267-286">Para asegurarse de que se obligue a todas las cuentas comprometidas de usuarios de alto riesgo a realizar un cambio de contraseña al iniciar sesión, se debe aplicar la directiva siguiente.</span><span class="sxs-lookup"><span data-stu-id="43267-286">To ensure that all high-risk users compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="43267-287">Inicie sesión en el [portal de Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) con sus credenciales de administrador y, a continuación, navegue hasta **Azure AD identidad protección > directiva de usuario de riesgo**.</span><span class="sxs-lookup"><span data-stu-id="43267-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="43267-288">**Asignaciones**</span><span class="sxs-lookup"><span data-stu-id="43267-288">**Assignments**</span></span>

|<span data-ttu-id="43267-289">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-289">Type</span></span>|<span data-ttu-id="43267-290">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-290">Properties</span></span>|<span data-ttu-id="43267-291">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-291">Values</span></span>|<span data-ttu-id="43267-292">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-293">Usuarios</span><span class="sxs-lookup"><span data-stu-id="43267-293">Users</span></span>|<span data-ttu-id="43267-294">Incluir</span><span class="sxs-lookup"><span data-stu-id="43267-294">Include</span></span>|<span data-ttu-id="43267-295">Todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="43267-295">All users</span></span>|<span data-ttu-id="43267-296">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="43267-296">Selected</span></span>|
||<span data-ttu-id="43267-297">Excluir</span><span class="sxs-lookup"><span data-stu-id="43267-297">Exclude</span></span>|<span data-ttu-id="43267-298">Ninguno</span><span class="sxs-lookup"><span data-stu-id="43267-298">None</span></span>||
|<span data-ttu-id="43267-299">Condiciones</span><span class="sxs-lookup"><span data-stu-id="43267-299">Conditions</span></span>|<span data-ttu-id="43267-300">Riesgo de usuario</span><span class="sxs-lookup"><span data-stu-id="43267-300">User risk</span></span>|<span data-ttu-id="43267-301">Alto</span><span class="sxs-lookup"><span data-stu-id="43267-301">High</span></span>|<span data-ttu-id="43267-302">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="43267-302">Selected</span></span>|

<span data-ttu-id="43267-303">**Controles**</span><span class="sxs-lookup"><span data-stu-id="43267-303">**Controls**</span></span>

| <span data-ttu-id="43267-304">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-304">Type</span></span> | <span data-ttu-id="43267-305">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-305">Properties</span></span> | <span data-ttu-id="43267-306">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-306">Values</span></span>                  | <span data-ttu-id="43267-307">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="43267-308">Acceso</span><span class="sxs-lookup"><span data-stu-id="43267-308">Access</span></span>     | <span data-ttu-id="43267-309">Permitir acceso</span><span class="sxs-lookup"><span data-stu-id="43267-309">Allow access</span></span>            | <span data-ttu-id="43267-310">True</span><span class="sxs-lookup"><span data-stu-id="43267-310">True</span></span>  |
|      | <span data-ttu-id="43267-311">Acceso</span><span class="sxs-lookup"><span data-stu-id="43267-311">Access</span></span>     | <span data-ttu-id="43267-312">Exigir cambio de contraseña</span><span class="sxs-lookup"><span data-stu-id="43267-312">Require password change</span></span> | <span data-ttu-id="43267-313">True</span><span class="sxs-lookup"><span data-stu-id="43267-313">True</span></span>  |

<span data-ttu-id="43267-314">**Revisión:** no es aplicable.</span><span class="sxs-lookup"><span data-stu-id="43267-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="43267-p116">Asegúrese de habilitar esta directiva, haciendo clic **en**. Tenga en cuenta también con la herramienta de [¿Qué ocurre si](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva</span><span class="sxs-lookup"><span data-stu-id="43267-p116">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="43267-317">Definir directivas de protección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="43267-317">Define app protection policies</span></span>
<span data-ttu-id="43267-p117">Directivas de protección de aplicaciones definición qué aplicaciones se permiten y las acciones pueden realizar con los datos de la organización. Crear aplicación Intune directivas de protección desde dentro del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="43267-p117">App protection policies define which apps are allowed and the actions they can take with your organization data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="43267-320">Crear una directiva para cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="43267-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="43267-321">iOS</span><span class="sxs-lookup"><span data-stu-id="43267-321">iOS</span></span>
- <span data-ttu-id="43267-322">Android</span><span class="sxs-lookup"><span data-stu-id="43267-322">Android</span></span>
- <span data-ttu-id="43267-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="43267-323">Windows 10</span></span>

<span data-ttu-id="43267-p118">Para crear una nueva directiva de protección de la aplicación, inicie sesión el portal de Microsoft Azure con sus credenciales de administrar y, a continuación, vaya a **aplicaciones móviles > directivas de protección de aplicaciones**. Haga clic en **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="43267-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Click **Add a policy**.</span></span>

<span data-ttu-id="43267-p119">Hay ligeras diferencias en la protección de la aplicación en las opciones de directiva entre iOS y Android. La por debajo de la directiva es específicamente para Android. Use esta opción como una guía para las otras directivas.</span><span class="sxs-lookup"><span data-stu-id="43267-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="43267-329">La lista de aplicaciones recomendada incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43267-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="43267-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="43267-330">PowerPoint</span></span>
- <span data-ttu-id="43267-331">Excel</span><span class="sxs-lookup"><span data-stu-id="43267-331">Excel</span></span>
- <span data-ttu-id="43267-332">Word</span><span class="sxs-lookup"><span data-stu-id="43267-332">Word</span></span>
- <span data-ttu-id="43267-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43267-333">Microsoft Teams</span></span>
- <span data-ttu-id="43267-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="43267-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="43267-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="43267-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="43267-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="43267-336">OneDrive</span></span>
- <span data-ttu-id="43267-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="43267-337">OneNote</span></span>
- <span data-ttu-id="43267-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="43267-338">Outlook</span></span>

<span data-ttu-id="43267-339">En las tablas siguientes se describen la configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="43267-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="43267-340">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-340">Type</span></span>|<span data-ttu-id="43267-341">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-341">Properties</span></span>|<span data-ttu-id="43267-342">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-342">Values</span></span>|<span data-ttu-id="43267-343">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-344">Reubicación de datos</span><span class="sxs-lookup"><span data-stu-id="43267-344">Data relocation</span></span>|<span data-ttu-id="43267-345">Impedir copias de seguridad de Android</span><span class="sxs-lookup"><span data-stu-id="43267-345">Prevent Android backup</span></span>|<span data-ttu-id="43267-346">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-346">Yes</span></span>|<span data-ttu-id="43267-347">En iOS esto específicamente llama a iTunes e iCloud</span><span class="sxs-lookup"><span data-stu-id="43267-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="43267-348">Permitir que la aplicación transfiera datos a otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="43267-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="43267-349">Aplicaciones administradas por directivas</span><span class="sxs-lookup"><span data-stu-id="43267-349">Policy managed apps</span></span>||
||<span data-ttu-id="43267-350">Permitir a la aplicación recibir datos de otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="43267-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="43267-351">Aplicaciones administradas por directivas</span><span class="sxs-lookup"><span data-stu-id="43267-351">Policy managed apps</span></span>||
||<span data-ttu-id="43267-352">Impedir "Guardar como"</span><span class="sxs-lookup"><span data-stu-id="43267-352">Prevent "Save As"</span></span>|<span data-ttu-id="43267-353">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-353">Yes</span></span>||
||<span data-ttu-id="43267-354">Seleccione qué datos corporativos de servicios de almacenamiento se pueden guardar en</span><span class="sxs-lookup"><span data-stu-id="43267-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="43267-355">OneDrive para la empresa, SharePoint</span><span class="sxs-lookup"><span data-stu-id="43267-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="43267-356">Restringir cortar, copiar y pegar con otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="43267-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="43267-357">Aplicaciones de la directiva administrada con pegar en</span><span class="sxs-lookup"><span data-stu-id="43267-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="43267-358">Restringir contenido web para mostrar en Managed Browser</span><span class="sxs-lookup"><span data-stu-id="43267-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="43267-359">No</span><span class="sxs-lookup"><span data-stu-id="43267-359">No</span></span>||
||<span data-ttu-id="43267-360">Cifrar datos de aplicación</span><span class="sxs-lookup"><span data-stu-id="43267-360">Encrypt app data</span></span>|<span data-ttu-id="43267-361">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-361">Yes</span></span>|<span data-ttu-id="43267-362">En iOS, seleccione la opción: Cuando el dispositivo está bloqueado</span><span class="sxs-lookup"><span data-stu-id="43267-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="43267-363">Deshabilitar el cifrado de la aplicación cuando está habilitado el dispositivo</span><span class="sxs-lookup"><span data-stu-id="43267-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="43267-364">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-364">Yes</span></span>|<span data-ttu-id="43267-365">Deshabilitar esta opción para evitar la doble cifrado</span><span class="sxs-lookup"><span data-stu-id="43267-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="43267-366">Deshabilitar la sincronización de contactos</span><span class="sxs-lookup"><span data-stu-id="43267-366">Disable contacts sync</span></span>|<span data-ttu-id="43267-367">No</span><span class="sxs-lookup"><span data-stu-id="43267-367">No</span></span>||
||<span data-ttu-id="43267-368">Deshabilitar la impresión</span><span class="sxs-lookup"><span data-stu-id="43267-368">Disable printing</span></span>|<span data-ttu-id="43267-369">No</span><span class="sxs-lookup"><span data-stu-id="43267-369">No</span></span>||
|<span data-ttu-id="43267-370">Acceso</span><span class="sxs-lookup"><span data-stu-id="43267-370">Access</span></span>|<span data-ttu-id="43267-371">Requerir PIN para acceder</span><span class="sxs-lookup"><span data-stu-id="43267-371">Require PIN for access</span></span>|<span data-ttu-id="43267-372">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-372">Yes</span></span>||
||<span data-ttu-id="43267-373">Seleccione el tipo de</span><span class="sxs-lookup"><span data-stu-id="43267-373">Select Type</span></span>|<span data-ttu-id="43267-374">Numérico</span><span class="sxs-lookup"><span data-stu-id="43267-374">Numeric</span></span>||
||<span data-ttu-id="43267-375">Permitir PIN sencillo</span><span class="sxs-lookup"><span data-stu-id="43267-375">Allow simple PIN</span></span>|<span data-ttu-id="43267-376">No</span><span class="sxs-lookup"><span data-stu-id="43267-376">No</span></span>||
||<span data-ttu-id="43267-377">Longitud del PIN</span><span class="sxs-lookup"><span data-stu-id="43267-377">PIN length</span></span>|<span data-ttu-id="43267-378">6 </span><span class="sxs-lookup"><span data-stu-id="43267-378">6</span></span>||
||<span data-ttu-id="43267-379">Permitir desbloqueo mediante huellas digitales en lugar de mediante PIN</span><span class="sxs-lookup"><span data-stu-id="43267-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="43267-380">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-380">Yes</span></span>||
||<span data-ttu-id="43267-381">Deshabilitar aplicación PIN cuando se administra el NIP del dispositivo</span><span class="sxs-lookup"><span data-stu-id="43267-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="43267-382">Sí</span><span class="sxs-lookup"><span data-stu-id="43267-382">Yes</span></span>||
||<span data-ttu-id="43267-383">Requerir credenciales corporativas para el acceso</span><span class="sxs-lookup"><span data-stu-id="43267-383">Require corporate credentials for access</span></span>|<span data-ttu-id="43267-384">No</span><span class="sxs-lookup"><span data-stu-id="43267-384">No</span></span>||
||<span data-ttu-id="43267-385">Volver a comprobar los requisitos de acceso después de (minutos)</span><span class="sxs-lookup"><span data-stu-id="43267-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="43267-386">30</span><span class="sxs-lookup"><span data-stu-id="43267-386">30</span></span>||
||<span data-ttu-id="43267-387">Bloquear captura de pantalla y asistente de Android</span><span class="sxs-lookup"><span data-stu-id="43267-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="43267-388">No</span><span class="sxs-lookup"><span data-stu-id="43267-388">No</span></span>|<span data-ttu-id="43267-389">En iOS esta opción no está disponible</span><span class="sxs-lookup"><span data-stu-id="43267-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="43267-390">Requisitos de seguridad de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="43267-390">Sign-in security requirements</span></span>|<span data-ttu-id="43267-391">Intentos de PIN de Max</span><span class="sxs-lookup"><span data-stu-id="43267-391">Max PIN attempts</span></span>|<span data-ttu-id="43267-392">5 </span><span class="sxs-lookup"><span data-stu-id="43267-392">5</span></span>|<span data-ttu-id="43267-393">Restablecer el Pin</span><span class="sxs-lookup"><span data-stu-id="43267-393">Reset Pin</span></span>|
||<span data-ttu-id="43267-394">Período de gracia sin conexión</span><span class="sxs-lookup"><span data-stu-id="43267-394">Offline grace period</span></span>|<span data-ttu-id="43267-395">720</span><span class="sxs-lookup"><span data-stu-id="43267-395">720</span></span>|<span data-ttu-id="43267-396">Bloquear acceso</span><span class="sxs-lookup"><span data-stu-id="43267-396">Block access</span></span>|
||<span data-ttu-id="43267-397">Intervalo sin conexión (días) antes de que se borren los datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="43267-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="43267-398">90</span><span class="sxs-lookup"><span data-stu-id="43267-398">90</span></span>|<span data-ttu-id="43267-399">Borrar datos</span><span class="sxs-lookup"><span data-stu-id="43267-399">Wipe data</span></span>|
||<span data-ttu-id="43267-400">Dispositivos Jailbroken/raíz</span><span class="sxs-lookup"><span data-stu-id="43267-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="43267-401">Borrar datos</span><span class="sxs-lookup"><span data-stu-id="43267-401">Wipe data</span></span>|

<span data-ttu-id="43267-p120">Cuando haya finalizado, recuerde hacer clic en "Crear". Repita los pasos anteriores y reemplace la plataforma seleccionada (desplegable) por iOS. Esto crea dos directivas de aplicación, por lo que una vez creada la directiva, asígnele grupos e impleméntela.</span><span class="sxs-lookup"><span data-stu-id="43267-p120">When complete, remember to click "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="43267-405">Para editar las directivas y asignar estas directivas a los usuarios, vea [cómo crear y asignar directivas de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="43267-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="43267-406">Requieren aplicaciones aprobadas</span><span class="sxs-lookup"><span data-stu-id="43267-406">Require approved apps</span></span>
<span data-ttu-id="43267-407">Para requerir aplicaciones aprobadas:</span><span class="sxs-lookup"><span data-stu-id="43267-407">To require approved apps:</span></span>

1. <span data-ttu-id="43267-p121">Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.</span><span class="sxs-lookup"><span data-stu-id="43267-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="43267-410">En el menú de la izquierda, seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="43267-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="43267-411">En la sección **Seguridad**, seleccione **Acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="43267-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="43267-412">Pulse **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="43267-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="43267-413">Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="43267-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="43267-414">Seleccione **Aplicaciones en la nube**.</span><span class="sxs-lookup"><span data-stu-id="43267-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="43267-p122">Elija **seleccionar aplicaciones**, seleccione las aplicaciones que desee en la lista de **aplicaciones en la nube** . Por ejemplo, seleccione Exchange en línea de Office 365. Haga clic en **Seleccionar** y **Listo**.</span><span class="sxs-lookup"><span data-stu-id="43267-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="43267-418">Pulse **Conceder** en la sección **Controles de acceso**.</span><span class="sxs-lookup"><span data-stu-id="43267-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="43267-p123">Elija **conceder acceso**, seleccione **Requerir aprobada por el cliente app**.  Para varios controles, seleccione **requerir los controles seleccionados**, a continuación, elija **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="43267-p123">Choose **Grant access**, select **Require approved client app**.  For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="43267-421">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="43267-421">Click **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="43267-422">Definir directivas de cumplimiento de normas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="43267-422">Define device compliance policies</span></span>

<span data-ttu-id="43267-p124">Directivas de cumplimiento de normas de dispositivo definición los requisitos que deben cumplir para que se marque como compatible con los dispositivos. Crear Intune dispositivo directivas de cumplimiento de normas desde dentro del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="43267-p124">Device compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="43267-425">Crear una directiva para cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="43267-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="43267-426">Android</span><span class="sxs-lookup"><span data-stu-id="43267-426">Android</span></span>
- <span data-ttu-id="43267-427">Enterprise Android</span><span class="sxs-lookup"><span data-stu-id="43267-427">Android enterprise</span></span>
- <span data-ttu-id="43267-428">iOS</span><span class="sxs-lookup"><span data-stu-id="43267-428">iOS</span></span>
- <span data-ttu-id="43267-429">Mac OS</span><span class="sxs-lookup"><span data-stu-id="43267-429">macOS</span></span>
- <span data-ttu-id="43267-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="43267-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="43267-431">Windows 8.1 y posterior</span><span class="sxs-lookup"><span data-stu-id="43267-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="43267-432">10 y versiones posteriores de Windows</span><span class="sxs-lookup"><span data-stu-id="43267-432">Windows 10 and later</span></span>

<span data-ttu-id="43267-p125">Para crear directivas de cumplimiento de dispositivo, inicie sesión el portal de Microsoft Azure con sus credenciales de administrar y, a continuación, vaya a **Intune > cumplimiento de dispositivo**. Haga clic en **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="43267-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Click **Create policy**.</span></span>

<span data-ttu-id="43267-435">La siguiente configuración se recomienda para 10 de Windows.</span><span class="sxs-lookup"><span data-stu-id="43267-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="43267-436">**Estado de dispositivo: las reglas de evaluación del servicio de certificación de mantenimiento de Windows**</span><span class="sxs-lookup"><span data-stu-id="43267-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="43267-437">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-437">Properties</span></span>|<span data-ttu-id="43267-438">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-438">Values</span></span>|<span data-ttu-id="43267-439">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="43267-440">Requerir BitLocker</span><span class="sxs-lookup"><span data-stu-id="43267-440">Require BitLocker</span></span>|<span data-ttu-id="43267-441">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-441">Require</span></span>||
|<span data-ttu-id="43267-442">Requerir inicio seguro a habilitarse en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="43267-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="43267-443">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-443">Require</span></span>||
|<span data-ttu-id="43267-444">Requerir la integridad del código</span><span class="sxs-lookup"><span data-stu-id="43267-444">Require code integrity</span></span>|<span data-ttu-id="43267-445">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-445">Require</span></span>||


<span data-ttu-id="43267-446">**Propiedades del dispositivo**</span><span class="sxs-lookup"><span data-stu-id="43267-446">**Device properties**</span></span>

|<span data-ttu-id="43267-447">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-447">Type</span></span>|<span data-ttu-id="43267-448">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-448">Properties</span></span>|<span data-ttu-id="43267-449">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-449">Values</span></span>|<span data-ttu-id="43267-450">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-451">Versión del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="43267-451">Operating system version</span></span>|<span data-ttu-id="43267-452">Todos</span><span class="sxs-lookup"><span data-stu-id="43267-452">All</span></span>|<span data-ttu-id="43267-453">No configurado</span><span class="sxs-lookup"><span data-stu-id="43267-453">Not configured</span></span>||

<span data-ttu-id="43267-p126">Para que todas las directivas anteriores se consideren implementadas, deben establecerse como destinos en los grupos de usuarios. Puede hacerlo al crear la directiva (al guardar) o después, al seleccionar Administrar la implementación en la sección Directiva (mismo nivel que Agregar).</span><span class="sxs-lookup"><span data-stu-id="43267-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting Manage Deployment in the Policy section (same level as Add).</span></span>

<span data-ttu-id="43267-456">**Seguridad del sistema**</span><span class="sxs-lookup"><span data-stu-id="43267-456">**System security**</span></span>

|<span data-ttu-id="43267-457">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-457">Type</span></span>|<span data-ttu-id="43267-458">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-458">Properties</span></span>|<span data-ttu-id="43267-459">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-459">Values</span></span>|<span data-ttu-id="43267-460">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-461">Contraseña</span><span class="sxs-lookup"><span data-stu-id="43267-461">Password</span></span>|<span data-ttu-id="43267-462">Requerir una contraseña para desbloquear los dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="43267-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="43267-463">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-463">Require</span></span>||
||<span data-ttu-id="43267-464">Contraseñas simples</span><span class="sxs-lookup"><span data-stu-id="43267-464">Simple passwords</span></span>|<span data-ttu-id="43267-465">Bloque</span><span class="sxs-lookup"><span data-stu-id="43267-465">Block</span></span>||
||<span data-ttu-id="43267-466">Tipo de contraseña</span><span class="sxs-lookup"><span data-stu-id="43267-466">Password type</span></span>|<span data-ttu-id="43267-467">Valor predeterminado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="43267-467">Device default</span></span>||
||<span data-ttu-id="43267-468">Longitud mínima de la contraseña</span><span class="sxs-lookup"><span data-stu-id="43267-468">Minimum password length</span></span>|<span data-ttu-id="43267-469">6 </span><span class="sxs-lookup"><span data-stu-id="43267-469">6</span></span>||
||<span data-ttu-id="43267-470">Número máximo de minutos de inactividad antes de que se requiere una contraseña</span><span class="sxs-lookup"><span data-stu-id="43267-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="43267-471">15 </span><span class="sxs-lookup"><span data-stu-id="43267-471">15</span></span>|<span data-ttu-id="43267-p127">Esta configuración se admite para Android versiones 4.0 y superior o KNOX 4.0 y anteriores. Para los dispositivos iOS, es compatible con para iOS 8.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="43267-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above.</span></span>|
||<span data-ttu-id="43267-474">Expiración de contraseña (días)</span><span class="sxs-lookup"><span data-stu-id="43267-474">Password expiration (days)</span></span>|<span data-ttu-id="43267-475">41</span><span class="sxs-lookup"><span data-stu-id="43267-475">41</span></span>||
||<span data-ttu-id="43267-476">Número de contraseñas anteriores para evitar que la reutilización</span><span class="sxs-lookup"><span data-stu-id="43267-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="43267-477">5 </span><span class="sxs-lookup"><span data-stu-id="43267-477">5</span></span>||
||<span data-ttu-id="43267-478">Requerir contraseña al dispositivo devuelve de estado inactivo (Mobile y Holographic)</span><span class="sxs-lookup"><span data-stu-id="43267-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="43267-479">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-479">Require</span></span>|<span data-ttu-id="43267-480">Disponible para Windows 10 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="43267-480">Available for Windows 10 and later.</span></span>|
|<span data-ttu-id="43267-481">Cifrado</span><span class="sxs-lookup"><span data-stu-id="43267-481">Encryption</span></span>|<span data-ttu-id="43267-482">Cifrado de almacenamiento de datos en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="43267-482">Encryption of data storage on device</span></span>|<span data-ttu-id="43267-483">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-483">Require</span></span>||
|<span data-ttu-id="43267-484">Seguridad de dispositivos</span><span class="sxs-lookup"><span data-stu-id="43267-484">Device Security</span></span>|<span data-ttu-id="43267-485">Firewall</span><span class="sxs-lookup"><span data-stu-id="43267-485">Firewall</span></span>|<span data-ttu-id="43267-486">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-486">Require</span></span>||
||<span data-ttu-id="43267-487">Antivirus</span><span class="sxs-lookup"><span data-stu-id="43267-487">Antivirus</span></span>|<span data-ttu-id="43267-488">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-488">Require</span></span>||
||<span data-ttu-id="43267-489">Anti spyware</span><span class="sxs-lookup"><span data-stu-id="43267-489">Antispyware</span></span>|<span data-ttu-id="43267-490">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-490">Require</span></span>|<span data-ttu-id="43267-491">Esta configuración requiere una solución de Anti-Spyware registrada con el centro de seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="43267-491">This setting requires an Anti-Spyware solution registered with Windows Security Center.</span></span>|
|<span data-ttu-id="43267-492">Defender</span><span class="sxs-lookup"><span data-stu-id="43267-492">Defender</span></span>|<span data-ttu-id="43267-493">Windows Defender Antimalware</span><span class="sxs-lookup"><span data-stu-id="43267-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="43267-494">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-494">Require</span></span>||
||<span data-ttu-id="43267-495">Versión mínima de Windows Defender Antimalware</span><span class="sxs-lookup"><span data-stu-id="43267-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="43267-p128">Solo se admite para el escritorio de Windows 10. Microsoft no recomienda más de cinco detrás de la versión más reciente de versiones.</span><span class="sxs-lookup"><span data-stu-id="43267-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version.</span></span>|
||<span data-ttu-id="43267-498">Firma de Windows Defender Antimalware actualizado</span><span class="sxs-lookup"><span data-stu-id="43267-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="43267-499">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-499">Require</span></span>||
||<span data-ttu-id="43267-500">Protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="43267-500">Real-time protection</span></span>|<span data-ttu-id="43267-501">Obligatoria</span><span class="sxs-lookup"><span data-stu-id="43267-501">Require</span></span>|<span data-ttu-id="43267-502">Solo se admite para el escritorio de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="43267-502">Only supported for Windows 10 desktop.</span></span>|

<span data-ttu-id="43267-503">**ATP de Windows Defender**</span><span class="sxs-lookup"><span data-stu-id="43267-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="43267-504">Tipo</span><span class="sxs-lookup"><span data-stu-id="43267-504">Type</span></span>|<span data-ttu-id="43267-505">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43267-505">Properties</span></span>|<span data-ttu-id="43267-506">Valores</span><span class="sxs-lookup"><span data-stu-id="43267-506">Values</span></span>|<span data-ttu-id="43267-507">Notas</span><span class="sxs-lookup"><span data-stu-id="43267-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="43267-508">Reglas de protección de amenaza avanzada de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="43267-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="43267-509">Requieren el dispositivo esté en o por debajo de la puntuación de riesgo de máquina</span><span class="sxs-lookup"><span data-stu-id="43267-509">Require the device to be at or under the machine risk score</span></span>|<span data-ttu-id="43267-510">Medio</span><span class="sxs-lookup"><span data-stu-id="43267-510">Medium</span></span>||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="43267-511">Requieren compatible con PCs (pero no compatible con teléfonos y tabletas)</span><span class="sxs-lookup"><span data-stu-id="43267-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="43267-p129">Antes de agregar una directiva para exigir PCs compatibles con, no olvide inscribirse dispositivos para la administración en Intune. Se recomienda el uso de la autenticación multifactor antes de dispositivos que se inscriben en Intune para garantía de que el dispositivo está en posesión del usuario previsto.</span><span class="sxs-lookup"><span data-stu-id="43267-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="43267-514">Para requerir PCs compatibles con:</span><span class="sxs-lookup"><span data-stu-id="43267-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="43267-p130">Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.</span><span class="sxs-lookup"><span data-stu-id="43267-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="43267-517">En el menú de la izquierda, seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="43267-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="43267-518">En la sección **Seguridad**, seleccione **Acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="43267-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="43267-519">Pulse **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="43267-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="43267-520">Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="43267-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="43267-521">Seleccione **Aplicaciones en la nube**.</span><span class="sxs-lookup"><span data-stu-id="43267-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="43267-p131">Elija **seleccionar aplicaciones**, seleccione las aplicaciones que desee en la lista de **aplicaciones en la nube** . Por ejemplo, seleccione Exchange en línea de Office 365. Haga clic en **Seleccionar** y **Listo**.</span><span class="sxs-lookup"><span data-stu-id="43267-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="43267-p132">Para requerir compatible con PC, pero no compatible con teléfonos y tabletas, elija **las condiciones** y **las plataformas de dispositivo**. Elija "plataformas de dispositivo seleccionado" y seleccione **Windows** y **Mac OS**.</span><span class="sxs-lookup"><span data-stu-id="43267-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose "Select device platforms" and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="43267-527">Pulse **Conceder** en la sección **Controles de acceso**.</span><span class="sxs-lookup"><span data-stu-id="43267-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="43267-p133">Elija **conceder acceso**, seleccione **requiere el dispositivo que se marcará como compatible con**.  Para varios controles, seleccione **requerir todos los controles seleccionados**, a continuación, elija **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="43267-p133">Choose **Grant access**, select **Require device to be marked as compliant**.  For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="43267-530">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="43267-530">Click **Create**.</span></span>

<span data-ttu-id="43267-p134">Si su objetivo es que requieren compatible con PC *y* dispositivos móviles, no seleccione plataformas. Esto exige compatible para todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="43267-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliant for all devices.</span></span> 




## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="43267-533">Requerir compatible con PC *y* dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="43267-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="43267-534">Para requerir el cumplimiento de normas para todos los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="43267-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="43267-p135">Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.</span><span class="sxs-lookup"><span data-stu-id="43267-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="43267-537">En el menú de la izquierda, seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="43267-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="43267-538">En la sección **Seguridad**, seleccione **Acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="43267-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="43267-539">Pulse **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="43267-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="43267-540">Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="43267-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="43267-541">Seleccione **Aplicaciones en la nube**.</span><span class="sxs-lookup"><span data-stu-id="43267-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="43267-p136">Elija **seleccionar aplicaciones**, seleccione las aplicaciones que desee en la lista de **aplicaciones en la nube** . Por ejemplo, seleccione Exchange en línea de Office 365. Haga clic en **Seleccionar** y **Listo**.</span><span class="sxs-lookup"><span data-stu-id="43267-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="43267-545">Pulse **Conceder** en la sección **Controles de acceso**.</span><span class="sxs-lookup"><span data-stu-id="43267-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="43267-p137">Elija **conceder acceso**, seleccione **requiere el dispositivo que se marcará como compatible con**. Para varios controles, seleccione **requerir todos los controles seleccionados**, a continuación, elija **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="43267-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="43267-548">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="43267-548">Click **Create**.</span></span>

<span data-ttu-id="43267-p138">Al crear esta directiva, no seleccione plataformas. Esto exige dispositivos compatibles con.</span><span class="sxs-lookup"><span data-stu-id="43267-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="43267-551">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="43267-551">Next steps</span></span>

[<span data-ttu-id="43267-552">Más información sobre recomendaciones de directivas para proteger el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="43267-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
