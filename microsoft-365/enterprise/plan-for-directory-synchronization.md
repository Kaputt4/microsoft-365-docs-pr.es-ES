---
title: Sincronización de directorios e identidades híbridas para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Describe la sincronización de directorios con Microsoft 365, la limpieza de Servicios de dominio de Active Directory y la herramienta Azure Active Directory Connect.
ms.openlocfilehash: 02b594f9db02df7e855a20dfc65b21ab2dbe91c0
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327384"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="dc6fe-103">Sincronización de directorios e identidades híbridas para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc6fe-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="dc6fe-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="dc6fe-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dc6fe-105">Según sus necesidades empresariales y requisitos técnicos, el modelo de identidad híbrido y la sincronización de directorios es la opción más común para los clientes empresariales que adoptan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="dc6fe-106">La sincronización de directorios le permite administrar identidades en los Servicios de dominio de Active Directory (AD DS) y todas las actualizaciones de cuentas de usuario, grupos y contactos se sincronizan con el inquilino de Azure Active Directory (Azure AD) de su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="dc6fe-107">Cuando las cuentas de usuario de AD DS se sincronizan por primera vez, no se les asigna automáticamente una licencia de Microsoft 365 y no pueden acceder a los servicios de Microsoft 365, como el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="dc6fe-108">Primero debe asignarles una ubicación de uso.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-108">You must first assign them a usage location.</span></span> <span data-ttu-id="dc6fe-109">A continuación, asigna una licencia a estas cuentas de usuario, ya sea de forma individual o dinámica a través de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="dc6fe-110">Autenticación para identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="dc6fe-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="dc6fe-111">Existen dos tipos de autenticación al usar el modelo de identidad híbrida:</span><span class="sxs-lookup"><span data-stu-id="dc6fe-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="dc6fe-112">Autenticación administrada</span><span class="sxs-lookup"><span data-stu-id="dc6fe-112">Managed authentication</span></span>

  <span data-ttu-id="dc6fe-113">Azure AD controla el proceso de autenticación mediante una versión hash almacenada localmente de la contraseña o envía las credenciales a un agente de software local para que ad DS local los autentique.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="dc6fe-114">Autenticación federada</span><span class="sxs-lookup"><span data-stu-id="dc6fe-114">Federated authentication</span></span>

  <span data-ttu-id="dc6fe-115">Azure AD redirige el equipo cliente que solicita la autenticación a otro proveedor de identidades.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="dc6fe-116">Autenticación administrada</span><span class="sxs-lookup"><span data-stu-id="dc6fe-116">Managed authentication</span></span>

<span data-ttu-id="dc6fe-117">Hay dos tipos de autenticación administrada:</span><span class="sxs-lookup"><span data-stu-id="dc6fe-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="dc6fe-118">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="dc6fe-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="dc6fe-119">Azure AD realiza la autenticación en sí.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="dc6fe-120">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="dc6fe-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="dc6fe-121">Azure AD hace que AD DS realice la autenticación.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="dc6fe-122">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="dc6fe-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="dc6fe-123">Con PHS, sincroniza las cuentas de usuario de AD DS con Microsoft 365 y administra los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="dc6fe-124">Los hash de las contraseñas de usuario se sincronizan desde AD DS a Azure AD para que los usuarios tengan la misma contraseña local y en la nube.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="dc6fe-125">Esta es la forma más sencilla de habilitar la autenticación para las identidades de AD DS en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Sincronización de hash de contraseña (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="dc6fe-127">Cuando las contraseñas se cambian o restablecen localmente, los nuevos hash de contraseña se sincronizan con Azure AD para que los usuarios siempre puedan usar la misma contraseña para los recursos en la nube y los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="dc6fe-128">Las contraseñas de usuario nunca se envían a Azure AD ni se almacenan en Azure AD como texto no definido.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="dc6fe-129">Algunas características premium de Azure AD, como Identity Protection, requieren PHS independientemente del método de autenticación seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="dc6fe-130">Vea [cómo elegir el método de autenticación correcto](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="dc6fe-131">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="dc6fe-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="dc6fe-132">LA PTA proporciona una validación de contraseña simple para los servicios de autenticación de Azure AD mediante un agente de software que se ejecuta en uno o más servidores locales para validar a los usuarios directamente con su AD DS.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="dc6fe-133">Con LA PTA, se sincronizan las cuentas de usuario de AD DS con Microsoft 365 y se administran los usuarios de forma local.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Autenticación de paso a través (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="dc6fe-135">LA PTA permite a los usuarios iniciar sesión en recursos y aplicaciones locales y de Microsoft 365 con su cuenta y contraseña locales.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="dc6fe-136">Esta configuración valida las contraseñas de los usuarios directamente en su AD DS local sin almacenar los hash de contraseña en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="dc6fe-137">LA PTA también es para las organizaciones que tienen un requisito de seguridad para aplicar inmediatamente los estados de cuenta de usuario local, las directivas de contraseña y las horas de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="dc6fe-138">Vea [cómo elegir el método de autenticación correcto](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="dc6fe-139">Autenticación federada</span><span class="sxs-lookup"><span data-stu-id="dc6fe-139">Federated authentication</span></span>

<span data-ttu-id="dc6fe-140">La autenticación federada es principalmente para grandes organizaciones empresariales con requisitos de autenticación más complejos.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="dc6fe-141">Las identidades de AD DS se sincronizan con Microsoft 365 y las cuentas de usuarios se administran localmente.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="dc6fe-142">Con la autenticación federada, los usuarios tienen la misma contraseña local y en la nube y no tienen que volver a iniciar sesión para usar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="dc6fe-143">La autenticación federada puede admitir requisitos de autenticación adicionales, como la autenticación basada en tarjeta inteligente o una autenticación multifactor de terceros y suele ser necesaria cuando las organizaciones tienen un requisito de autenticación que Azure AD no admite de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="dc6fe-144">Vea [cómo elegir el método de autenticación correcto](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="dc6fe-145">Proveedores de identidades y autenticación de terceros</span><span class="sxs-lookup"><span data-stu-id="dc6fe-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="dc6fe-146">Los objetos de directorio local se pueden sincronizar con Microsoft 365 y el acceso a recursos en la nube lo administra principalmente un proveedor de identidades (IdP) de terceros.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="dc6fe-147">Si su organización usa una solución de federación de terceros, puede configurar el inicio de sesión con esa solución para Microsoft 365 siempre que la solución de federación de terceros sea compatible con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="dc6fe-148">Consulta la lista [de compatibilidad de federación de Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="dc6fe-149">Preparación de AD DS</span><span class="sxs-lookup"><span data-stu-id="dc6fe-149">AD DS Preparation</span></span>

<span data-ttu-id="dc6fe-150">Para garantizar una transición sin problemas a Microsoft 365 mediante la sincronización, debe preparar el bosque de AD DS antes de comenzar la implementación de sincronización de directorios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="dc6fe-151">La preparación del directorio debe centrarse en las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="dc6fe-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="dc6fe-152">Quite los atributos **proxyAddress y** **userPrincipalName duplicados.**</span><span class="sxs-lookup"><span data-stu-id="dc6fe-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="dc6fe-153">Actualice los atributos **userPrincipalName en** blanco e no válidos con atributos **userPrincipalName válidos.**</span><span class="sxs-lookup"><span data-stu-id="dc6fe-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="dc6fe-154">Quite los caracteres no válidos y cuestionables de los atributos **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** y **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="dc6fe-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="dc6fe-155">Para obtener más información acerca de la preparación de atributos, vea la lista de atributos sincronizados por la Herramienta [de sincronización de Azure Active Directory.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="dc6fe-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc6fe-156">Estos son los mismos atributos que sincroniza Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="dc6fe-157">Consideraciones sobre la implementación de varios bosques</span><span class="sxs-lookup"><span data-stu-id="dc6fe-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="dc6fe-158">Para varios bosques y opciones de SSO, use [una instalación personalizada de Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span><span class="sxs-lookup"><span data-stu-id="dc6fe-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="dc6fe-159">Si su organización tiene varios bosques para la autenticación (bosques de inicio de sesión), se recomienda lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc6fe-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="dc6fe-160">**Considere la posibilidad de consolidar los bosques.**</span><span class="sxs-lookup"><span data-stu-id="dc6fe-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="dc6fe-161">En general, hay más sobrecarga necesaria para mantener varios bosques.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="dc6fe-162">A menos que su organización tenga restricciones de seguridad que dicten la necesidad de bosques independientes, considere la posibilidad de simplificar el entorno local.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="dc6fe-163">**Usar solo en el bosque de inicio de sesión principal.**</span><span class="sxs-lookup"><span data-stu-id="dc6fe-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="dc6fe-164">Considere la posibilidad de implementar Microsoft 365 solo en el bosque de inicio de sesión principal para la implementación inicial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="dc6fe-165">Si no puede consolidar la implementación de AD DS de varios bosques o usa otros servicios de directorio para administrar identidades, puede sincronizarlas con la ayuda de Microsoft o de un partner.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="dc6fe-166">Para obtener más información, vea Topologías [de Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)</span><span class="sxs-lookup"><span data-stu-id="dc6fe-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="dc6fe-167">Características que dependen de la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="dc6fe-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="dc6fe-168">La sincronización de directorios es necesaria para las siguientes características y funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="dc6fe-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="dc6fe-169">Inicio de sesión único (SSO) Sign-On conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc6fe-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="dc6fe-170">Coexistencia de Skype</span><span class="sxs-lookup"><span data-stu-id="dc6fe-170">Skype coexistence</span></span>
- <span data-ttu-id="dc6fe-171">Implementación híbrida de Exchange, que incluye:</span><span class="sxs-lookup"><span data-stu-id="dc6fe-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="dc6fe-172">Lista global de direcciones (GAL) totalmente compartida entre su entorno de Exchange local y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="dc6fe-173">Sincronización de información de GAL desde varios sistemas de correo.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="dc6fe-174">La capacidad de agregar usuarios y quitarlos de las ofertas de servicio de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="dc6fe-175">Esto requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc6fe-175">This requires the following:</span></span>
  - <span data-ttu-id="dc6fe-176">La sincronización bidireccional debe configurarse durante la configuración de la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="dc6fe-177">De forma predeterminada, las herramientas de sincronización de directorios escriben información de directorio solo en la nube.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="dc6fe-178">Al configurar la sincronización bidireccional, habilita la funcionalidad de reescribición para que se copie un número limitado de atributos de objeto de la nube y, a continuación, vuelva a escribirlos en su AD DS local.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="dc6fe-179">La reescribición también se conoce como modo híbrido de Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="dc6fe-180">Una implementación híbrida de Exchange local</span><span class="sxs-lookup"><span data-stu-id="dc6fe-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="dc6fe-181">La capacidad de mover algunos buzones de usuario a Microsoft 365 a la vez que se mantienen los buzones de otros usuarios de forma local.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="dc6fe-182">Los remitentes seguros y los remitentes bloqueados localmente se replican en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="dc6fe-183">Función de delegación básica y envío en nombre de otra persona.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="dc6fe-184">Tiene una solución integrada de autenticación multifactor o tarjeta inteligente local.</span><span class="sxs-lookup"><span data-stu-id="dc6fe-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="dc6fe-185">Sincronización de fotos, miniaturas, salas de conferencias y grupos de seguridad</span><span class="sxs-lookup"><span data-stu-id="dc6fe-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="dc6fe-186">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="dc6fe-186">Next step</span></span>

<span data-ttu-id="dc6fe-187">Cuando esté listo para implementar la identidad híbrida, consulte [Preparar la sincronización de directorios.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="dc6fe-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
  
