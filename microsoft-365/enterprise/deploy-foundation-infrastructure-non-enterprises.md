---
title: Infraestructura básica de Microsoft 365 Enterprise para organizaciones que no son empresas
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Le mostramos las fases simplificadas de la infraestructura básica de Microsoft 365 Enterprise para organizaciones que no sean empresas.
ms.openlocfilehash: 8e2c254bf352baa14ff62dad500e5cdfa0af4563
ms.sourcegitcommit: 639607bbf02bdedd3fa5cd7b0984b422fe6c874e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "35624638"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="73a46-103">Infraestructura básica de Microsoft 365 Enterprise para organizaciones que no son empresas</span><span class="sxs-lookup"><span data-stu-id="73a46-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="73a46-104">Las organizaciones que no sean empresas también pueden implementar Microsoft 365 Enterprise y obtener el valor empresarial de una infraestructura integrada y segura que facilita el trabajo en equipo y fomenta la creatividad.</span><span class="sxs-lookup"><span data-stu-id="73a46-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="73a46-105">Por lo general, una organización que no es una empresa presenta estas características:</span><span class="sxs-lookup"><span data-stu-id="73a46-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="73a46-106">Una cantidad limitada de infraestructura de informática local, como correo electrónico y servidores de archivos, y, como mucho, un dominio de Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="73a46-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="73a46-107">Un equipo reducido de personal informático, la mayoría de cuyos miembros son generalistas, en lugar de especialistas en una tecnología o carga de trabajo específica, como redes o correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="73a46-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="73a46-108">Si su organización tiene un tamaño reducido y no es una empresa, Microsoft le ofrece [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span><span class="sxs-lookup"><span data-stu-id="73a46-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="73a46-109">Sin embargo, puede necesitar Microsoft 365 Enterprise, por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="73a46-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="73a46-110">Su organización necesita o necesitará más de 300 licencias de Microsoft 365, que es el límite máximo para Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="73a46-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="73a46-111">Su organización necesita servicios de productividad avanzada, voz, seguridad y analítica que no están disponibles en Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="73a46-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="73a46-112">Este artículo le mostrará una implementación simplificada de la infraestructura básica de Microsoft 365 Enterprise, ideal para su organización no empresarial.</span><span class="sxs-lookup"><span data-stu-id="73a46-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="73a46-113">Primero, configure la suscripción</span><span class="sxs-lookup"><span data-stu-id="73a46-113">First, set up your subscription</span></span>

<span data-ttu-id="73a46-114">Debe configurar los dominios del Sistema de Nombres de Dominio (DNS) de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="73a46-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="73a46-115">Si ya tiene una suscripción a Office 365, este paso ya debería de estar realizado.</span><span class="sxs-lookup"><span data-stu-id="73a46-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="73a46-116">Si no lo está, siga las instrucciones para [Agregar un dominio a Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="73a46-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="73a46-117">El siguiente paso es la configuración de seguridad adicional de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73a46-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="73a46-118">Siga las instrucciones en [Configuración para una mayor seguridad](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="73a46-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="73a46-119">Fase 1: Redes</span><span class="sxs-lookup"><span data-stu-id="73a46-119">Phase 1: Networking</span></span>

<span data-ttu-id="73a46-120">Las organizaciones no empresariales suelen tener conexiones a Internet locales en cada oficina y no usan servidores proxy, firewalls ni dispositivos de inspección de paquetes.</span><span class="sxs-lookup"><span data-stu-id="73a46-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="73a46-121">El proveedor de acceso a Internet (ISP) de cada oficina tiene un servidor DNS regionalmente local, de modo que el tráfico se dirige a la ubicación de red de Microsoft 365 más cercana a las oficinas y a sus usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="73a46-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="73a46-122">Por lo tanto, solo tiene que comprobar con su ISP que la conexión de cada una de las ubicaciones de la oficina:</span><span class="sxs-lookup"><span data-stu-id="73a46-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="73a46-123">Usa un servidor DNS regionalmente local.</span><span class="sxs-lookup"><span data-stu-id="73a46-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="73a46-124">Es adecuada para las necesidades actuales y futuras, a medida que los usuarios usen más servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73a46-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="73a46-125">Si usa servidores proxy, firewalls o dispositivos de inspección de paquetes, vea [infraestructura de red de Microsoft 365 Enterprise](networking-infrastructure.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73a46-125">If you do use proxy servers, firewalls, or packet inspection devices, see [Networking infrastructure for Microsoft 365 Enterprise](networking-infrastructure.md) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="73a46-126">Su configuración hasta ahora</span><span class="sxs-lookup"><span data-stu-id="73a46-126">Your configuration so far</span></span>

<span data-ttu-id="73a46-127">Este es un resumen visual en el que hemos resaltado el elemento de la Fase 1.</span><span class="sxs-lookup"><span data-stu-id="73a46-127">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="73a46-128">**Su organización** puede contener varias oficinas y cada una de ellas tener una conexión a Internet local con un ISP que use un servidor DNS regionalmente local.</span><span class="sxs-lookup"><span data-stu-id="73a46-128">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="73a46-129">Mediante el ISP, los usuarios de cada oficina pueden acceder a la ubicación de red de Microsoft 365 más cercana y a los recursos de la suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73a46-129">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="73a46-130">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="73a46-130">Phase 2: Identity</span></span>

<span data-ttu-id="73a46-131">Cada uno de los empleados de su organización debe poder iniciar sesión, lo que requiere una cuenta de usuario en el espacio empresarial de Azure Active Directory (Azure AD) de la suscripción a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73a46-131">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="73a46-132">Los grupos se usan para contener cuentas de usuario y otros grupos para comunicarse u obtener acceso a recursos con permisos, como un sitio de SharePoint Online o un equipo.</span><span class="sxs-lookup"><span data-stu-id="73a46-132">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="73a46-133">Cuentas de administrador</span><span class="sxs-lookup"><span data-stu-id="73a46-133">Administrator accounts</span></span>

<span data-ttu-id="73a46-134">Proteja sus cuentas de usuario de administrador global exigiendo el uso de contraseñas muy seguras y de la autenticación multifactor (MFA).</span><span class="sxs-lookup"><span data-stu-id="73a46-134">Protect your global administrator user accounts by requiring very strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="73a46-135">Más información en: [Proteger las cuentas de administrador global](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="73a46-135">See [Protect your Office 365 global administrator accounts](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="73a46-136">Si su organización necesita un alto nivel de seguridad y dispone de Microsoft 365 Enterprise E5, utilice la Azure AD Privileged Identity Management para permitir el acceso de administrador de forma puntual.</span><span class="sxs-lookup"><span data-stu-id="73a46-136">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="73a46-137">Más información en: [Configurar los administradores globales a petición](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators)</span><span class="sxs-lookup"><span data-stu-id="73a46-137">See [Set up on-demand global administrators](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="73a46-138">Recomendaciones para grupos</span><span class="sxs-lookup"><span data-stu-id="73a46-138">Recommendations for groups</span></span>

<span data-ttu-id="73a46-139">Si tiene un dominio de AD DS local, siga usando estos grupos de Microsoft 365 Enterprise como grupos en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a46-139">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="73a46-140">Si no tiene un dominio de AD DS local, cree grupos de seguridad en Azure AD con estos niveles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73a46-140">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="73a46-141">Nivel de seguridad</span><span class="sxs-lookup"><span data-stu-id="73a46-141">Security level</span></span> | <span data-ttu-id="73a46-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="73a46-142">Description</span></span> | <span data-ttu-id="73a46-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="73a46-143">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="73a46-144">Línea base</span><span class="sxs-lookup"><span data-stu-id="73a46-144">Baseline</span></span> | <span data-ttu-id="73a46-145">Este es un estándar mínimo y predeterminado para proteger los datos, así como las identidades y los dispositivos que acceden a los datos.</span><span class="sxs-lookup"><span data-stu-id="73a46-145">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="73a46-146">Normalmente, se trata de la mayoría de los datos de la organización gestionados por la mayoría de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="73a46-146">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="73a46-147">Grupos para los trabajadores de primera línea, como ventas, marketing, asistencia al cliente, administración y fabricación.</span><span class="sxs-lookup"><span data-stu-id="73a46-147">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="73a46-148">Confidencial</span><span class="sxs-lookup"><span data-stu-id="73a46-148">Sensitive</span></span> | <span data-ttu-id="73a46-149">Esta es una protección adicional para un subconjunto de los datos que se deban proteger más allá del nivel básico.</span><span class="sxs-lookup"><span data-stu-id="73a46-149">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="73a46-150">Estos grupos contienen usuarios que usan y crean datos confidenciales específicos de departamentos y proyectos que no se han diseñado para que estén disponibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="73a46-150">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="73a46-151">Equipos de producto o de marketing que desarrollan futuros productos</span><span class="sxs-lookup"><span data-stu-id="73a46-151">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="73a46-152">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="73a46-152">Highly regulated</span></span> | <span data-ttu-id="73a46-153">Este es el nivel más alto de protección de una cantidad de datos habitualmente pequeña y altamente confidencial, que se consideran como secretos comerciales o propiedad intelectual, o datos que deben cumplir normas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73a46-153">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="73a46-154">Los equipos de investigación, de seguridad y de finanzas, o bien equipos que almacenan o usan los datos de clientes o socios.</span><span class="sxs-lookup"><span data-stu-id="73a46-154">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="73a46-155">Identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="73a46-155">Hybrid identity</span></span>

<span data-ttu-id="73a46-156">Si tiene un dominio de AD DS local, debe sincronizar el conjunto de cuentas de usuario, grupos y contactos de su dominio con el espacio empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73a46-156">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="73a46-157">Para su organización no empresarial, configure Azure AD Connect en un servidor con sincronización de hash de contraseña (PHS).</span><span class="sxs-lookup"><span data-stu-id="73a46-157">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="73a46-158">Vea [Sincronizar identidades](identity-azure-ad-connect.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73a46-158">See [Synchronize identities](identity-azure-ad-connect.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="73a46-159">Directivas de acceso condicional para un acceso de usuario más seguro</span><span class="sxs-lookup"><span data-stu-id="73a46-159">More secure user access with conditional access policies</span></span>

<span data-ttu-id="73a46-160">Azure AD evalúa las condiciones de inicio de sesión de usuario y puede usar directivas de acceso condicionales para conceder o denegar un acceso e imponer otras acciones para completar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="73a46-160">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="73a46-161">Por ejemplo, si Azure AD determina que el inicio de sesión se está realizando en condiciones de riesgo medio o alto, puede requerir la implementación de MFA para que el usuario complete el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="73a46-161">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="73a46-162">Aplique directivas de acceso condicional a las cuentas o grupos de usuario.</span><span class="sxs-lookup"><span data-stu-id="73a46-162">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="73a46-163">Para facilitar una asignación más fácil de directivas de acceso condicional, cree estos grupos de seguridad de Azure AD en la organización:</span><span class="sxs-lookup"><span data-stu-id="73a46-163">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="73a46-164">LÍNEA BASE</span><span class="sxs-lookup"><span data-stu-id="73a46-164">Baseline</span></span>

  <span data-ttu-id="73a46-165">Contiene los grupos o cuentas de usuario para aquellos usuarios con acceso a los datos de línea base.</span><span class="sxs-lookup"><span data-stu-id="73a46-165">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="73a46-166">CONFIDENCIAL</span><span class="sxs-lookup"><span data-stu-id="73a46-166">Sensitive</span></span>

  <span data-ttu-id="73a46-167">Contiene los grupos o cuentas de usuario para aquellos usuarios con acceso a los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="73a46-167">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="73a46-168">EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-168">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="73a46-169">Contiene los grupos o cuentas de usuario para aquellos usuarios con acceso a datos extremadamente regulados.</span><span class="sxs-lookup"><span data-stu-id="73a46-169">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="73a46-170">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="73a46-170">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="73a46-171">Grupo vacío que puede usar para excluir temporalmente a un usuario de las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="73a46-171">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="73a46-172">Esta es una lista de las directivas de acceso condicional de Azure AD que se habilitan o se crean.</span><span class="sxs-lookup"><span data-stu-id="73a46-172">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="73a46-173">Directivas de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="73a46-173">Azure AD conditional access policy</span></span> | <span data-ttu-id="73a46-174">Grupos a los que se aplica</span><span class="sxs-lookup"><span data-stu-id="73a46-174">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="73a46-175">Directiva de línea base: requerir MFA para los administradores</span><span class="sxs-lookup"><span data-stu-id="73a46-175">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="73a46-176">Esta directiva se aplica a roles de administrador, por lo que no es necesario especificar grupos.</span><span class="sxs-lookup"><span data-stu-id="73a46-176">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="73a46-177">El único paso que debe dar es habilitar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="73a46-177">This policy just needs to be enabled.</span></span> <span data-ttu-id="73a46-178">Todas las directivas futuras se deben crear y, luego, habilitar.</span><span class="sxs-lookup"><span data-stu-id="73a46-178">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="73a46-179">Bloquear a los clientes que no sean compatibles con la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="73a46-179">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="73a46-180">Seleccione "Todos los usuarios" en la configuración de la directiva.</span><span class="sxs-lookup"><span data-stu-id="73a46-180">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="73a46-181">Requerir MFA cuando el riesgo de inicio de sesión sea medio o alto (se necesita Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="73a46-181">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="73a46-182">LÍNEA BASE</span><span class="sxs-lookup"><span data-stu-id="73a46-182">Baseline</span></span> |
| <span data-ttu-id="73a46-183">Requerir MFA cuando el riesgo de inicio de sesión sea bajo, medio o alto (se necesita Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="73a46-183">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="73a46-184">CONFIDENCIAL</span><span class="sxs-lookup"><span data-stu-id="73a46-184">Sensitive</span></span> |
| <span data-ttu-id="73a46-185">*Siempre* exigir MFA</span><span class="sxs-lookup"><span data-stu-id="73a46-185">Always require MFA</span></span> | <span data-ttu-id="73a46-186">EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-186">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-187">Requerir aplicaciones aprobadas en dispositivos iOS y Android</span><span class="sxs-lookup"><span data-stu-id="73a46-187">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="73a46-188">LÍNEAS BASE, CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-189">Exigir equipos PC compatibles</span><span class="sxs-lookup"><span data-stu-id="73a46-189">Require compliant PCs</span></span> | <span data-ttu-id="73a46-190">LÍNEA BASE</span><span class="sxs-lookup"><span data-stu-id="73a46-190">Baseline</span></span> |
| <span data-ttu-id="73a46-191">Requerir PC, y dispositivos iOS y Android compatibles</span><span class="sxs-lookup"><span data-stu-id="73a46-191">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="73a46-192">CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-192">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="73a46-193">Esta es la Directiva de riesgo de usuario de Azure AD Identity Protection para crear y habilitar (requiere Microsoft 365 Enterprise E5).</span><span class="sxs-lookup"><span data-stu-id="73a46-193">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="73a46-194">Directiva de riesgo de usuarios de Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="73a46-194">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="73a46-195">Grupos a los que se aplica</span><span class="sxs-lookup"><span data-stu-id="73a46-195">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="73a46-196">Los usuarios de riesgo alto tienen que cambiar las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="73a46-196">High risk users must change passwords</span></span> | <span data-ttu-id="73a46-197">Seleccione "Todos los usuarios" en la configuración de la directiva.</span><span class="sxs-lookup"><span data-stu-id="73a46-197">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="73a46-198">Puede encontrar las instrucciones en [Implementar directivas comunes de acceso a dispositivos e identidad](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="73a46-198">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="73a46-199">Grupos para facilitar la administración</span><span class="sxs-lookup"><span data-stu-id="73a46-199">Groups for easier management</span></span>

<span data-ttu-id="73a46-200">Estas son algunas características que pueden facilitar la administración de licencias y grupos.</span><span class="sxs-lookup"><span data-stu-id="73a46-200">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="73a46-201">Característica</span><span class="sxs-lookup"><span data-stu-id="73a46-201">Feature</span></span> | <span data-ttu-id="73a46-202">Utilice</span><span class="sxs-lookup"><span data-stu-id="73a46-202">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="73a46-203">Administración de grupos de autoservicio</span><span class="sxs-lookup"><span data-stu-id="73a46-203">Self-service group management</span></span> | <span data-ttu-id="73a46-204">Permitir que sean los propietarios de los grupos de Azure AD, y no el personal de informática, quienes gestionen dichos grupos.</span><span class="sxs-lookup"><span data-stu-id="73a46-204">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="73a46-205">Consulte [Administración de grupos de autoservicio](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) para más información.</span><span class="sxs-lookup"><span data-stu-id="73a46-205">See [Self-service group management](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="73a46-206">Pertenencia a grupo dinámico</span><span class="sxs-lookup"><span data-stu-id="73a46-206">Dynamic group membership</span></span> | <span data-ttu-id="73a46-207">Configure la incorporación o eliminación automática de cuentas de usuario de grupos de Azure AD en función de los atributos de la cuenta, como departamento o país.</span><span class="sxs-lookup"><span data-stu-id="73a46-207">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="73a46-208">Para obtener más información, consulte [Pertenencia a grupos dinámicos](identity-self-service-group-management.md#set-up-dynamic-group-membership).</span><span class="sxs-lookup"><span data-stu-id="73a46-208">See [Dynamic group membership](identity-self-service-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="73a46-209">Licencias basadas en grupos</span><span class="sxs-lookup"><span data-stu-id="73a46-209">Group-based licensing</span></span> | <span data-ttu-id="73a46-210">Use la pertenencia a grupos para asignar o retirar licencias a cuentas de usuario automáticamente.</span><span class="sxs-lookup"><span data-stu-id="73a46-210">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="73a46-211">Vea [Licencias basadas en grupo](identity-self-service-group-management.md#set-up-automatic-licensing) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73a46-211">See [Group-based licensing](identity-self-service-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="73a46-212">Si va a usar una licencia basada en grupos, cree un grupo denominado LICENCIADO para que contenga los nombres de las cuentas de usuario asignadas a una licencia de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73a46-212">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="73a46-213">Seguir el acceso del usuario</span><span class="sxs-lookup"><span data-stu-id="73a46-213">Monitor user access</span></span>

<span data-ttu-id="73a46-214">Si tiene Microsoft 365 Enterprise E5, puede usar Azure AD Identity Protection para supervisar y analizar los inicios de sesión de los usuarios para comprobar si las credenciales se ven comprometidas.</span><span class="sxs-lookup"><span data-stu-id="73a46-214">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="73a46-215">Para obtener más información, consulte [Protegerse en caso de que las credenciales se vean comprometidas](identity-multi-factor-authentication.md#protect-against-credential-compromise).</span><span class="sxs-lookup"><span data-stu-id="73a46-215">See [Protect against credential compromise](identity-multi-factor-authentication.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="73a46-216">Su configuración hasta ahora</span><span class="sxs-lookup"><span data-stu-id="73a46-216">Your configuration so far</span></span>

<span data-ttu-id="73a46-217">Este es un resumen visual de la fase de identidad de la identidad híbrida, con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="73a46-217">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="73a46-218">Los elementos de identidad híbrida nuevos y resaltados incluyen:</span><span class="sxs-lookup"><span data-stu-id="73a46-218">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="73a46-219">Un dominio de AD DS local con grupos y cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="73a46-219">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="73a46-220">Servidor basado en Windows que ejecuta Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="73a46-220">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="73a46-221">El conjunto sincronizado de cuentas y grupos de AD DS en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a46-221">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="73a46-222">Opciones de configuración de Azure AD para autenticarse, proteger cuentas globales y facilitar la administración de grupos y licencias.</span><span class="sxs-lookup"><span data-stu-id="73a46-222">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="73a46-223">Directivas de acceso condicional de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a46-223">Azure AD conditional access policies.</span></span> |
|||

<span data-ttu-id="73a46-224">Este es un resumen visual de la fase de identidad de la identidad solo de nube, con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="73a46-224">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="73a46-225">Los elementos de identidad solo de nube nuevos y resaltados incluyen:</span><span class="sxs-lookup"><span data-stu-id="73a46-225">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="73a46-226">Opciones de configuración de Azure AD para autenticarse, proteger cuentas globales y facilitar la administración de grupos y licencias.</span><span class="sxs-lookup"><span data-stu-id="73a46-226">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="73a46-227">Directivas de acceso condicional de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a46-227">Azure AD conditional access policies.</span></span> |
|||



## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="73a46-228">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="73a46-228">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="73a46-229">Tiene las siguientes opciones para asegurarse de que los dispositivos de Windows 10 Enterprise se integren en la infraestructura de identidad y seguridad de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="73a46-229">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="73a46-230">Híbrido (tiene un dominio local de AD DS)</span><span class="sxs-lookup"><span data-stu-id="73a46-230">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="73a46-231">Vincule al espacio empresarial de Azure AD cada dispositivo existente de Windows 10 Enterprise que ya esté vinculado al dominio de AD DS.</span><span class="sxs-lookup"><span data-stu-id="73a46-231">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="73a46-232">Para descubrir cómo hacerlo, consulte [Configuración de dispositivos híbridos unidos a Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="73a46-232">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="73a46-233">Vincule cada dispositivo nuevo de Windows 10 Enterprise, primero, al dominio de AD DS, y luego al espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a46-233">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="73a46-234">Inscriba todos los dispositivos con Windows 10 Enterprise en la administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="73a46-234">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="73a46-235">Vea las instrucciones en [Inscripción de un dispositivo con Windows 10 con Intune mediante una directiva de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871).</span><span class="sxs-lookup"><span data-stu-id="73a46-235">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="73a46-236">Solo de nube (no tiene un dominio local de AD DS)</span><span class="sxs-lookup"><span data-stu-id="73a46-236">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="73a46-237">Vincule cada dispositivo de Windows 10 Enterprise al espacio empresarial de Azure AD de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="73a46-237">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="73a46-238">Para obtener más información, vea [Unir el dispositivo de trabajo a la red de su organización](https://docs.microsoft.com/es-ES/azure/active-directory/user-help/user-help-join-device-on-network).</span><span class="sxs-lookup"><span data-stu-id="73a46-238">See [Join your work device to your organization's network](https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="73a46-239">Tras su instalación y vinculación, cada dispositivo con Windows 10 Enterprise instalará automáticamente las actualizaciones desde el servicio en la nube de Windows Update para empresas.</span><span class="sxs-lookup"><span data-stu-id="73a46-239">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="73a46-240">Por lo general, no es necesario que una organización no empresarial configure una infraestructura para distribuir e instalar actualizaciones de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73a46-240">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="73a46-241">Su configuración hasta ahora</span><span class="sxs-lookup"><span data-stu-id="73a46-241">Your configuration so far</span></span>

<span data-ttu-id="73a46-242">Este es un resumen visual de la fase de Windows 10 Enterprise, con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="73a46-242">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="73a46-243">Los elementos nuevos y resaltados de Windows 10 Enterprise incluyen:</span><span class="sxs-lookup"><span data-stu-id="73a46-243">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="73a46-244">Windows 10 Enterprise instalado en dispositivos Windows, con el portátil local como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="73a46-244">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="73a46-245">El Centro de servicios de licencias por volumen, que proporciona imágenes para nuevas instalaciones de Windows 10 Enterprise, y el servicio de Windows Update para empresas, que ofrece las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="73a46-245">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="73a46-246">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="73a46-246">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="73a46-247">Microsoft 365 Enterprise incluye Office 365 ProPlus, la versión de suscripción de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="73a46-247">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="73a46-248">Office 365 ProPlus, igual que Office 2016 u Office 2019, está instalado directamente en los dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="73a46-248">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="73a46-249">Pero Office 365 ProPlus recibe actualizaciones que incluyen las nuevas características de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="73a46-249">However, Office 365 ProPlus receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="73a46-250">Para más información, vea [Información sobre Office 365 ProPlus en un entorno empresarial](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="73a46-250">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="73a46-251">En el caso de una organización no empresarial, instale manualmente Office 365 ProPlus en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73a46-251">For your non-enterprise organization, you manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="73a46-252">Esto puede hacerse como parte de la preparación para usar un nuevo dispositivo o lo puede realizar el usuario como parte de su proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="73a46-252">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="73a46-253">En ambos casos, el administrador o el usuario deben iniciar sesión en el portal de Office 365 en https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="73a46-253">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="73a46-254">En la pestaña **Página principal de Microsoft Office** haga clic en **Instalar Office** y siga los pasos del proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="73a46-254">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="73a46-255">En cada equipo en el que se instale Office 365 ProPlus se descargarán mensualmente las actualizaciones de características.</span><span class="sxs-lookup"><span data-stu-id="73a46-255">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="73a46-256">Por lo general, no es necesario que una organización no empresarial configure una infraestructura para distribuir actualizaciones de Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="73a46-256">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="73a46-257">Su configuración hasta ahora</span><span class="sxs-lookup"><span data-stu-id="73a46-257">Your configuration so far</span></span>

<span data-ttu-id="73a46-258">Este es un resumen visual de la fase de Office 365 ProPlus, con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="73a46-258">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="73a46-259">Los elementos de Office 365 ProPlus nuevos y resaltados incluyen:</span><span class="sxs-lookup"><span data-stu-id="73a46-259">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="73a46-260">Office 365 ProPlus instalado en dispositivos, con el portátil local como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="73a46-260">Office 365 ProPlus installed on devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="73a46-261">La Red de entrega de contenido (CDN) de Office para Office 365 ProPlus, donde los dispositivos obtienen acceso a las actualizaciones de Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="73a46-261">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="73a46-262">Fase 5: Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="73a46-262">Phase 5: Mobile device management</span></span>

<span data-ttu-id="73a46-263">Microsoft 365 Enterprise incluye Microsoft Intune para la administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="73a46-263">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="73a46-264">Con Intune, puede administrar dispositivos iOS, Android, macOS y Windows para proteger el acceso a los recursos de su organización, incluidos los datos.</span><span class="sxs-lookup"><span data-stu-id="73a46-264">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="73a46-265">Intune usa las cuentas de usuario, grupo y equipo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a46-265">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="73a46-266">Intune ofrece dos tipos de administración de dispositivos móviles:</span><span class="sxs-lookup"><span data-stu-id="73a46-266">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="73a46-267">La Administración de Dispositivos Móviles (MDM) se utiliza cuando se inscriben dispositivos en Intune.</span><span class="sxs-lookup"><span data-stu-id="73a46-267">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="73a46-268">Una vez que se hayan inscrito, se consideran dispositivos administrados y pueden recibir las directivas, las reglas y la configuración que use su organización.</span><span class="sxs-lookup"><span data-stu-id="73a46-268">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="73a46-269">Por lo general, estos tipos de dispositivos son propiedad de su organización y se entregan a sus empleados.</span><span class="sxs-lookup"><span data-stu-id="73a46-269">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="73a46-270">Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o no quieran que sus dispositivos sean administrados con las directivas y configuraciones de usted.</span><span class="sxs-lookup"><span data-stu-id="73a46-270">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="73a46-271">Pero todavía debe proteger los datos y recursos de su organización.</span><span class="sxs-lookup"><span data-stu-id="73a46-271">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="73a46-272">Si esto ocurre, puede proteger las aplicaciones con la administración de aplicaciones móviles (MAM).</span><span class="sxs-lookup"><span data-stu-id="73a46-272">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="73a46-273">Las directivas de Intune pueden exigir el cumplimiento de dispositivos y la protección de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="73a46-273">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="73a46-274">Esta es la lista de directivas de Intune que debe crear.</span><span class="sxs-lookup"><span data-stu-id="73a46-274">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="73a46-275">Directivas de Intune</span><span class="sxs-lookup"><span data-stu-id="73a46-275">Intune policies</span></span> | <span data-ttu-id="73a46-276">Grupos a los que se aplica</span><span class="sxs-lookup"><span data-stu-id="73a46-276">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="73a46-277">Directivas de cumplimiento de dispositivos para Windows</span><span class="sxs-lookup"><span data-stu-id="73a46-277">Device compliance policy for Windows</span></span> | <span data-ttu-id="73a46-278">LÍNEAS BASE, CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-279">Directivas de cumplimiento de dispositivos para iOS</span><span class="sxs-lookup"><span data-stu-id="73a46-279">Device compliance policy for iOS</span></span> | <span data-ttu-id="73a46-280">CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-281">Cumplimiento de dispositivos para macOS</span><span class="sxs-lookup"><span data-stu-id="73a46-281">Device compliance for macOS</span></span> | <span data-ttu-id="73a46-282">CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-282">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-283">Directiva de cumplimiento de dispositivos para Android y Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="73a46-283">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="73a46-284">CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-284">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-285">Directiva de protección de aplicaciones para iOS</span><span class="sxs-lookup"><span data-stu-id="73a46-285">App protection policy for iOS</span></span> | <span data-ttu-id="73a46-286">LÍNEAS BASE, CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-287">Directiva de protección de aplicaciones para macOS</span><span class="sxs-lookup"><span data-stu-id="73a46-287">App protection policy for macOS</span></span> | <span data-ttu-id="73a46-288">LÍNEAS BASE, CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="73a46-289">Directiva de protección de apps para Android y Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="73a46-289">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="73a46-290">LÍNEAS BASE, CONFIDENCIAL, EXTREMADAMENTE REGULADO</span><span class="sxs-lookup"><span data-stu-id="73a46-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="73a46-291">Puede encontrar las instrucciones en [Implementar directivas comunes de acceso a dispositivos e identidad](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="73a46-291">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="73a46-292">Su configuración hasta ahora</span><span class="sxs-lookup"><span data-stu-id="73a46-292">Your configuration so far</span></span>

<span data-ttu-id="73a46-293">Este es un resumen visual de la fase de la Administración de dispositivos móviles, con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="73a46-293">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="73a46-294">Entre los elementos nuevos y resaltados de la administración de dispositivos móviles se incluyen:</span><span class="sxs-lookup"><span data-stu-id="73a46-294">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="73a46-295">Dispositivos que se inscriben en Intune que muestran como ejemplo el portátil local que ejecuta Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73a46-295">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="73a46-296">Directivas de Intune para el cumplimiento de dispositivos y la protección de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="73a46-296">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="73a46-297">Fase 6: Protección de la información</span><span class="sxs-lookup"><span data-stu-id="73a46-297">Phase 6: Information protection</span></span>

<span data-ttu-id="73a46-298">Microsoft 365 Enterprise ofrece una gran variedad de opciones para proteger su información. Estas le permiten realizar distintas clasificaciones de datos y aplicar varios niveles de control, seguridad y protección.</span><span class="sxs-lookup"><span data-stu-id="73a46-298">Microsoft 365 Enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="73a46-299">Por ejemplo, se requiere un nivel básico de protección para la correspondencia normal entre la mayoría de los empleados y los documentos con los que trabajan.</span><span class="sxs-lookup"><span data-stu-id="73a46-299">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="73a46-300">Pero se requiere un nivel de protección más alto para los registros financieros, los datos de los clientes y su propiedad intelectual.</span><span class="sxs-lookup"><span data-stu-id="73a46-300">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="73a46-301">El primer paso en una estrategia de protección de datos es determinar los distintos niveles de protección.</span><span class="sxs-lookup"><span data-stu-id="73a46-301">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="73a46-302">Muchas organizaciones usan estos niveles, ya empleados en directivas de acceso condicional:</span><span class="sxs-lookup"><span data-stu-id="73a46-302">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="73a46-303">Línea base</span><span class="sxs-lookup"><span data-stu-id="73a46-303">Baseline</span></span>

  <span data-ttu-id="73a46-304">Algunos ejemplos son las comunicaciones empresariales normales (correo electrónico) y los archivos de empleados administrativos, de ventas y de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="73a46-304">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="73a46-305">Confidencial</span><span class="sxs-lookup"><span data-stu-id="73a46-305">Sensitive</span></span>

  <span data-ttu-id="73a46-306">Algunos ejemplos son la información jurídica y financiera, y los datos de investigación y desarrollo de productos o servicios nuevos.</span><span class="sxs-lookup"><span data-stu-id="73a46-306">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="73a46-307">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="73a46-307">Highly regulated</span></span>

  <span data-ttu-id="73a46-308">Algunos ejemplos incluyen la información de identificación personal de clientes y socios, y la propiedad intelectual o la información financiera de su organización.</span><span class="sxs-lookup"><span data-stu-id="73a46-308">Examples include customer and partner personally identifiable information and your organization’s financial information or intellectual property.</span></span>

<span data-ttu-id="73a46-309">En función de estos niveles de seguridad de datos, el siguiente paso es identificar e implementar:</span><span class="sxs-lookup"><span data-stu-id="73a46-309">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="73a46-310">Tipos de información confidencial personalizada</span><span class="sxs-lookup"><span data-stu-id="73a46-310">Custom sensitive information types</span></span>

  <span data-ttu-id="73a46-311">Microsoft 365 proporciona una amplia variedad de tipos de información confidencial, como el servicio de mantenimiento y los números de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="73a46-311">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="73a46-312">Si no encuentra el que necesita en la lista proporcionada, puede crear su propia lista.</span><span class="sxs-lookup"><span data-stu-id="73a46-312">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="73a46-313">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="73a46-313">Retention labels</span></span>

  <span data-ttu-id="73a46-314">Para cumplir con las directivas de la organización y la reglamentación regional, puede que deba especificar cuánto tiempo deben conservarse determinados tipos de documentos o documentos con contenidos específicos.</span><span class="sxs-lookup"><span data-stu-id="73a46-314">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="73a46-315">Puede implementarlo para correos electrónicos y documentos con etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="73a46-315">You can implement this for email and documents using retention labels.</span></span>

- <span data-ttu-id="73a46-316">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="73a46-316">Sensitivity labels</span></span>

  <span data-ttu-id="73a46-317">Puede asignar una etiqueta de confidencialidad con nombre a mensajes de correo electrónico o documentos para que se puedan aplicar niveles de seguridad adicionales.</span><span class="sxs-lookup"><span data-stu-id="73a46-317">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="73a46-318">Algunos ejemplos son las marcas de agua, el cifrado y los permisos, que especifican a quién se le permite obtener acceso al correo electrónico o documento y qué se les permite hacer.</span><span class="sxs-lookup"><span data-stu-id="73a46-318">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="73a46-319">Para obtener más información, consulte [Tipos de clasificación de Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types).</span><span class="sxs-lookup"><span data-stu-id="73a46-319">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="73a46-320">Si usa etiquetas de confidencialidad con permisos, es posible que tenga que crear grupos de seguridad de Azure AD adicionales para definir qué se le permite hacer a cada persona con el correo electrónico y los documentos.</span><span class="sxs-lookup"><span data-stu-id="73a46-320">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="73a46-321">Pongamos el supuesto de que necesita crear una etiqueta de confidencialidad de INVESTIGACIÓN para proteger el correo electrónico y los documentos de su equipo de investigación.</span><span class="sxs-lookup"><span data-stu-id="73a46-321">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="73a46-322">Usted determina que:</span><span class="sxs-lookup"><span data-stu-id="73a46-322">You determine that:</span></span>

- <span data-ttu-id="73a46-323">Los investigadores deben tener la capacidad de cambiar los documentos marcados con la etiqueta de confidencialidad de INVESTIGACIÓN.</span><span class="sxs-lookup"><span data-stu-id="73a46-323">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="73a46-324">Los empleados ajenos a la investigación solo deben tener la capacidad de ver los documentos marcados con la etiqueta de confidencialidad de INVESTIGACIÓN.</span><span class="sxs-lookup"><span data-stu-id="73a46-324">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="73a46-325">Esto quiere decir que debe crear y administrar dos grupos adicionales:</span><span class="sxs-lookup"><span data-stu-id="73a46-325">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="73a46-326">INVESTIGACIÓN-TODO</span><span class="sxs-lookup"><span data-stu-id="73a46-326">RESEARCH-ALL</span></span>
- <span data-ttu-id="73a46-327">INVESTIGACIÓN-VISTA</span><span class="sxs-lookup"><span data-stu-id="73a46-327">RESEARCH-VIEW</span></span>

<span data-ttu-id="73a46-328">Estos grupos y sus permisos forman parte de la configuración de la etiqueta de confidencialidad INVESTIGACIÓN.</span><span class="sxs-lookup"><span data-stu-id="73a46-328">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="73a46-329">Para las etiquetas de confidencialidad configuradas con permisos basados en grupos, debe administrar la pertenencia a estos grupos.</span><span class="sxs-lookup"><span data-stu-id="73a46-329">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="73a46-330">Su configuración hasta ahora</span><span class="sxs-lookup"><span data-stu-id="73a46-330">Your configuration so far</span></span>

<span data-ttu-id="73a46-331">Este es un resumen visual de la fase de protección de información, con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="73a46-331">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="73a46-332">Entre los elementos de protección de la información nuevos y resaltados se incluyen:</span><span class="sxs-lookup"><span data-stu-id="73a46-332">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="73a46-333">Etiquetas de confidencialidad para los tres niveles de seguridad que los usuarios pueden aplicar a los documentos.</span><span class="sxs-lookup"><span data-stu-id="73a46-333">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="73a46-334">No se muestran las etiquetas de retención ni los tipos de información personalizados.</span><span class="sxs-lookup"><span data-stu-id="73a46-334">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="73a46-335">Incorporación</span><span class="sxs-lookup"><span data-stu-id="73a46-335">Onboarding</span></span>

<span data-ttu-id="73a46-336">Con la infraestructura de Microsoft 365 Enterprise, podrá incorporar fácilmente a sus empleados.</span><span class="sxs-lookup"><span data-stu-id="73a46-336">With your Microsoft 365 Enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="73a46-337">Un nuevo dispositivo con Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="73a46-337">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="73a46-338">Antes de dar a un empleado un nuevo dispositivo con Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="73a46-338">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="73a46-339">Para identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="73a46-339">For hybrid identity</span></span>

  <span data-ttu-id="73a46-340">Vincule el dispositivo a su dominio de AD DS, luego vincule el dispositivo a su espacio empresarial de Azure AD y, después, inscriba el dispositivo en Intune.</span><span class="sxs-lookup"><span data-stu-id="73a46-340">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="73a46-341">Para una identidad solo de nube</span><span class="sxs-lookup"><span data-stu-id="73a46-341">For cloud-only identity</span></span>

  <span data-ttu-id="73a46-342">Vincule el dispositivo al espacio empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73a46-342">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="73a46-343">Empleado existente con una cuenta de usuario de AD DS</span><span class="sxs-lookup"><span data-stu-id="73a46-343">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="73a46-344">Cuando utilice la identidad híbrida, y como parte de la incorporación inicial de su organización, agregue la cuenta de usuario de AD DS a estos grupos de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="73a46-344">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="73a46-345">CON LICENCIA</span><span class="sxs-lookup"><span data-stu-id="73a46-345">Licensed</span></span>
- <span data-ttu-id="73a46-346">Los grupos de seguridad de AD DS o Azure AD adecuados que son miembros de los grupos de Azure AD LÍNEA BASE, CONFIDENCIAL y EXTREMADAMENTE REGULADO.</span><span class="sxs-lookup"><span data-stu-id="73a46-346">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="73a46-347">Grupos de etiquetas de confidencialidad (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="73a46-347">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="73a46-348">El empleado existente ya debe haber sido agregado a los grupos correspondientes de departamento, grupo de trabajo y grupos regionales de AD DS.</span><span class="sxs-lookup"><span data-stu-id="73a46-348">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="73a46-349">Puede agregar una cuenta de usuario a varios grupos de Azure AD en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73a46-349">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="73a46-350">En las propiedades de la cuenta de usuario, haga clic en **Administrar grupos > Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="73a46-350">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="73a46-351">Si quiere usar PowerShell, vea este [libro de Excel descargable](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), donde se generan los comandos de PowerShell basándose en una cuenta de usuario específica y en nombres de grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="73a46-351">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="73a46-352">Nuevo empleado con una cuenta de usuario solo de nube</span><span class="sxs-lookup"><span data-stu-id="73a46-352">New employee with a cloud-only user account</span></span>

<span data-ttu-id="73a46-353">Cuando utilice la identidad solo de nube como parte de la incorporación inicial de su organización, agregue la nueva cuenta de usuario a estos grupos:</span><span class="sxs-lookup"><span data-stu-id="73a46-353">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="73a46-354">CON LICENCIA</span><span class="sxs-lookup"><span data-stu-id="73a46-354">Licensed</span></span>
- <span data-ttu-id="73a46-355">Los grupos de seguridad de Azure AD adecuados que son miembros de los grupos de Azure AD LÍNEA BASE, CONFIDENCIAL y EXTREMADAMENTE REGULADO.</span><span class="sxs-lookup"><span data-stu-id="73a46-355">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="73a46-356">Grupos de trabajo, de departamento y regionales</span><span class="sxs-lookup"><span data-stu-id="73a46-356">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="73a46-357">Grupos de etiquetas de confidencialidad (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="73a46-357">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="73a46-358">Primer inicio de sesión en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73a46-358">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="73a46-359">La primera vez que los empleados inicien sesión en Microsoft 365, indíqueles que:</span><span class="sxs-lookup"><span data-stu-id="73a46-359">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="73a46-360">Deben iniciar sesión en sus dispositivos con las credenciales de su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="73a46-360">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="73a46-361">Con un explorador, deben iniciar sesión en el portal de Office 365 en https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="73a46-361">Using a browser on your local computer, sign in to the https://portal.office.com using your global administrator account.</span></span>
3. <span data-ttu-id="73a46-362">Desde la pestaña **Página principal de Office 365**, deben hacer clic en **Instalar Office** para instalar Office 365 ProPlus en su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73a46-362">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="73a46-363">Resultados finales</span><span class="sxs-lookup"><span data-stu-id="73a46-363">End results</span></span>

<span data-ttu-id="73a46-364">Estos son los resultados de la configuración de la infraestructura básica de Microsoft 365 Enterprise para una organización no empresarial.</span><span class="sxs-lookup"><span data-stu-id="73a46-364">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="73a46-365">Resultados de la infraestructura</span><span class="sxs-lookup"><span data-stu-id="73a46-365">Infrastructure results</span></span>

<span data-ttu-id="73a46-366">Después de la creación y de la configuración de su infraestructura empresarial de Microsoft 365 Enterprise, debe tener:</span><span class="sxs-lookup"><span data-stu-id="73a46-366">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="73a46-367">Una conexión a Internet local para cada una de las oficinas, con suficiente ancho de banda proporcionado por un proveedor de Internet que utilice un servidor DNS regionalmente local.</span><span class="sxs-lookup"><span data-stu-id="73a46-367">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="73a46-368">En el caso de las identidades híbridas, Azure AD Connect se ejecuta en un servidor que sincroniza el dominio de AD DS local con su espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a46-368">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="73a46-369">Estos grupos:</span><span class="sxs-lookup"><span data-stu-id="73a46-369">These groups:</span></span>
  - <span data-ttu-id="73a46-370">CON LICENCIA</span><span class="sxs-lookup"><span data-stu-id="73a46-370">Licensed</span></span>
  - <span data-ttu-id="73a46-371">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="73a46-371">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="73a46-372">Los grupos de seguridad de AD DS o Azure AD adecuados que también son miembros de los grupos de Azure AD LÍNEA BASE, CONFIDENCIAL y EXTREMADAMENTE REGULADO.</span><span class="sxs-lookup"><span data-stu-id="73a46-372">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="73a46-373">Grupos de trabajo, de departamento y regionales</span><span class="sxs-lookup"><span data-stu-id="73a46-373">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="73a46-374">Grupos de etiquetas de confidencialidad (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="73a46-374">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="73a46-375">Directivas de acceso condicional de inicio de sesión de Azure AD que usan los grupos de Azure AD LÍNEA BASE, CONFIDENCIAL, EXTREMADAMENTE REGULADO y COND-ACCESS-EXCLUDE.</span><span class="sxs-lookup"><span data-stu-id="73a46-375">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="73a46-376">Directivas de cumplimiento normativo de aplicaciones y dispositivos Intune.</span><span class="sxs-lookup"><span data-stu-id="73a46-376">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="73a46-377">Tipos de información confidencial personalizada (si se necesitan)</span><span class="sxs-lookup"><span data-stu-id="73a46-377">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="73a46-378">Etiquetas de retención (si se necesitan)</span><span class="sxs-lookup"><span data-stu-id="73a46-378">Retention labels (as needed).</span></span>
- <span data-ttu-id="73a46-379">Etiquetas de confidencialidad (si se necesitan)</span><span class="sxs-lookup"><span data-stu-id="73a46-379">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="73a46-380">Aquí se muestra un resumen visual de la infraestructura en caso de que su organización use una identidad híbrida. Incluye el dominio de AD DS, un servidor de Azure AD Connect y usuarios y grupos de AD DS sincronizados.</span><span class="sxs-lookup"><span data-stu-id="73a46-380">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="73a46-381">Este es un resumen visual de la infraestructura en caso de que su organización use una identidad solo de nube.</span><span class="sxs-lookup"><span data-stu-id="73a46-381">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="73a46-382">Resultados de empleados</span><span class="sxs-lookup"><span data-stu-id="73a46-382">Employee results</span></span>

<span data-ttu-id="73a46-383">Después de ser incorporado, cada empleado debe tener:</span><span class="sxs-lookup"><span data-stu-id="73a46-383">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="73a46-384">Una ruta de acceso de red local de altas prestaciones desde su dispositivo hasta los servicios en la nube de Microsoft 365 en su región.</span><span class="sxs-lookup"><span data-stu-id="73a46-384">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="73a46-385">Una cuenta de usuario con estas pertenencias de grupo:</span><span class="sxs-lookup"><span data-stu-id="73a46-385">A user account with these group memberships:</span></span>
   - <span data-ttu-id="73a46-386">CON LICENCIA</span><span class="sxs-lookup"><span data-stu-id="73a46-386">Licensed</span></span>
   - <span data-ttu-id="73a46-387">Los grupos de seguridad de AD DS o Azure AD adecuados que también son miembros de los grupos de Azure AD LÍNEA BASE, CONFIDENCIAL y EXTREMADAMENTE REGULADO para directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="73a46-387">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="73a46-388">Grupos de trabajo, de departamento y regionales adecuados</span><span class="sxs-lookup"><span data-stu-id="73a46-388">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="73a46-389">Grupos de etiquetas de confidencialidad (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="73a46-389">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="73a46-390">Un nuevo dispositivo con Windows 10 Enterprise que:</span><span class="sxs-lookup"><span data-stu-id="73a46-390">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="73a46-391">se ha unido al espacio empresarial de Azure AD (solo en la nube) o tanto al espacio empresarial de Azure AD como al dominio de AD DS (híbrido).</span><span class="sxs-lookup"><span data-stu-id="73a46-391">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="73a46-392">se actualiza automáticamente con las mejoras más recientes de producto y mejoras de seguridad de Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73a46-392">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="73a46-393">tiene Office 365 ProPlus instalado y este se actualiza automáticamente con las mejoras de producto más recientes de Office y mejoras de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73a46-393">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="73a46-394">se ha inscrito en Intune y está sujeto a las directivas de cumplimiento de dispositivos y a las directivas de protección de aplicaciones de Intune.</span><span class="sxs-lookup"><span data-stu-id="73a46-394">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="73a46-395">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="73a46-395">Next step</span></span>

<span data-ttu-id="73a46-396">Implemente las [cargas de trabajo y los escenarios](deploy-workloads.md) para aprovechar las características y la configuración de su infraestructura de base de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73a46-396">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
