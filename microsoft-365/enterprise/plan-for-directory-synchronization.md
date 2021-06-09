---
title: Identidad híbrida y sincronización de directorios para Microsoft 365
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
description: Describe la sincronización de directorios Microsoft 365, la limpieza de servicios de dominio de Active Directory y la herramienta Azure Active Directory Conectar directorio.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927549"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="4cc90-103">Identidad híbrida y sincronización de directorios para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4cc90-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="4cc90-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4cc90-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4cc90-105">Según las necesidades empresariales y los requisitos técnicos, el modelo de identidad híbrida y la sincronización de directorios es la opción más común para los clientes empresariales que adoptan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc90-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="4cc90-106">La sincronización de directorios permite administrar identidades en los Servicios de dominio de Active Directory (AD DS) y todas las actualizaciones de cuentas de usuario, grupos y contactos se sincronizan con el inquilino de Azure Active Directory (Azure AD) de su suscripción Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc90-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="4cc90-107">Cuando las cuentas de usuario de AD DS se sincronizan por primera vez, no se les asigna automáticamente una licencia de Microsoft 365 y no pueden acceder a Microsoft 365 servicios, como el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4cc90-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="4cc90-108">Primero debe asignarles una ubicación de uso.</span><span class="sxs-lookup"><span data-stu-id="4cc90-108">You must first assign them a usage location.</span></span> <span data-ttu-id="4cc90-109">A continuación, asigne una licencia a estas cuentas de usuario, ya sea de forma individual o dinámica a través de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="4cc90-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="4cc90-110">Autenticación para identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="4cc90-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="4cc90-111">Hay dos tipos de autenticación al usar el modelo de identidad híbrida:</span><span class="sxs-lookup"><span data-stu-id="4cc90-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="4cc90-112">Autenticación administrada</span><span class="sxs-lookup"><span data-stu-id="4cc90-112">Managed authentication</span></span>

  <span data-ttu-id="4cc90-113">Azure AD controla el proceso de autenticación mediante una versión hash almacenada localmente de la contraseña o envía las credenciales a un agente de software local para que ad DS local lo autentique.</span><span class="sxs-lookup"><span data-stu-id="4cc90-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="4cc90-114">Autenticación federada</span><span class="sxs-lookup"><span data-stu-id="4cc90-114">Federated authentication</span></span>

  <span data-ttu-id="4cc90-115">Azure AD redirige el equipo cliente que solicita autenticación a otro proveedor de identidades.</span><span class="sxs-lookup"><span data-stu-id="4cc90-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="4cc90-116">Autenticación administrada</span><span class="sxs-lookup"><span data-stu-id="4cc90-116">Managed authentication</span></span>

<span data-ttu-id="4cc90-117">Hay dos tipos de autenticación administrada:</span><span class="sxs-lookup"><span data-stu-id="4cc90-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="4cc90-118">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="4cc90-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="4cc90-119">Azure AD realiza la autenticación en sí.</span><span class="sxs-lookup"><span data-stu-id="4cc90-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="4cc90-120">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="4cc90-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="4cc90-121">Azure AD tiene AD DS para realizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="4cc90-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="4cc90-122">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="4cc90-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="4cc90-123">Con PHS, sincronizas tus cuentas de usuario de AD DS con Microsoft 365 y administras los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="4cc90-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="4cc90-124">Los hash de contraseñas de usuario se sincronizan desde AD DS a Azure AD para que los usuarios tengan la misma contraseña local y en la nube.</span><span class="sxs-lookup"><span data-stu-id="4cc90-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="4cc90-125">Esta es la forma más sencilla de habilitar la autenticación para identidades de AD DS en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4cc90-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Sincronización de hash de contraseña (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="4cc90-127">Cuando se cambian o restablecen las contraseñas locales, los nuevos hashes de contraseña se sincronizan con Azure AD para que los usuarios siempre puedan usar la misma contraseña para los recursos en la nube y los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="4cc90-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="4cc90-128">Las contraseñas de usuario nunca se envían a Azure AD ni se almacenan en Azure AD en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="4cc90-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="4cc90-129">Algunas características premium de Azure AD, como Identity Protection, requieren PHS independientemente del método de autenticación seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4cc90-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="4cc90-130">Consulta [elegir el método de autenticación correcto](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4cc90-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="4cc90-131">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="4cc90-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="4cc90-132">LA PTA proporciona una validación de contraseña sencilla para los servicios de autenticación de Azure AD mediante un agente de software que se ejecuta en uno o varios servidores locales para validar a los usuarios directamente con su AD DS.</span><span class="sxs-lookup"><span data-stu-id="4cc90-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="4cc90-133">Con la PTA, sincronizas las cuentas de usuario de AD DS Microsoft 365 y administras los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="4cc90-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Autenticación de paso a través (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="4cc90-135">LA PTA permite a los usuarios iniciar sesión en recursos y aplicaciones locales y Microsoft 365 con su cuenta y contraseña locales.</span><span class="sxs-lookup"><span data-stu-id="4cc90-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="4cc90-136">Esta configuración valida las contraseñas de los usuarios directamente en su AD DS local sin almacenar hashes de contraseña en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4cc90-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="4cc90-137">La PTA también está para que las organizaciones con un requisito de seguridad exijan inmediatamente los estados de cuenta de usuario local, las directivas de contraseña y las horas de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4cc90-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="4cc90-138">Consulta [elegir el método de autenticación correcto](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4cc90-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="4cc90-139">Autenticación federada</span><span class="sxs-lookup"><span data-stu-id="4cc90-139">Federated authentication</span></span>

<span data-ttu-id="4cc90-140">La autenticación federada es principalmente para organizaciones empresariales grandes con requisitos de autenticación más complejos.</span><span class="sxs-lookup"><span data-stu-id="4cc90-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="4cc90-141">Las identidades de AD DS se sincronizan con Microsoft 365 y las cuentas de usuarios se administran localmente.</span><span class="sxs-lookup"><span data-stu-id="4cc90-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="4cc90-142">Con la autenticación federada, los usuarios tienen la misma contraseña local y en la nube y no tienen que volver a iniciar sesión para usar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc90-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="4cc90-143">La autenticación federada puede admitir requisitos de autenticación adicionales, como la autenticación basada en tarjetas inteligentes o una autenticación multifactor de terceros, y normalmente es necesaria cuando las organizaciones tienen un requisito de autenticación que Azure AD no admite de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="4cc90-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="4cc90-144">Consulta [elegir el método de autenticación correcto](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4cc90-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="4cc90-145">Proveedores de identidades y autenticación de terceros</span><span class="sxs-lookup"><span data-stu-id="4cc90-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="4cc90-146">Los objetos de directorio locales pueden sincronizarse con Microsoft 365 y el acceso a recursos en la nube lo administra principalmente un proveedor de identidades (IdP) de terceros.</span><span class="sxs-lookup"><span data-stu-id="4cc90-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="4cc90-147">Si su organización usa una solución de federación de terceros, puede configurar el inicio de sesión con esa solución para Microsoft 365 siempre que la solución de federación de terceros sea compatible con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4cc90-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="4cc90-148">Consulta la lista [de compatibilidad de federación de Azure AD](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4cc90-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="4cc90-149">Preparación de AD DS</span><span class="sxs-lookup"><span data-stu-id="4cc90-149">AD DS Preparation</span></span>

<span data-ttu-id="4cc90-150">Para garantizar una transición sin problemas a Microsoft 365 mediante la sincronización, debe preparar el bosque de AD DS antes de comenzar la implementación Microsoft 365 sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="4cc90-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="4cc90-151">La preparación del directorio debe centrarse en las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="4cc90-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="4cc90-152">Quite los **atributos proxyAddress y** **userPrincipalName duplicados.**</span><span class="sxs-lookup"><span data-stu-id="4cc90-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="4cc90-153">Actualice los atributos **userPrincipalName** en blanco y no válidos con atributos **userPrincipalName** válidos.</span><span class="sxs-lookup"><span data-stu-id="4cc90-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="4cc90-154">Quite caracteres no válidos y cuestionables en los atributos **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** y **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="4cc90-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="4cc90-155">Para obtener más información acerca de la preparación de atributos, vea Lista de atributos [sincronizados por](https://go.microsoft.com/fwlink/p/?LinkId=396719)la Azure Active Directory sync tool .</span><span class="sxs-lookup"><span data-stu-id="4cc90-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4cc90-156">Estos son los mismos atributos que Azure AD Conectar sincroniza.</span><span class="sxs-lookup"><span data-stu-id="4cc90-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="4cc90-157">Consideraciones de implementación de varios bosques</span><span class="sxs-lookup"><span data-stu-id="4cc90-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="4cc90-158">Para varios bosques y opciones de SSO, use [una instalación personalizada de Azure AD Conectar](/azure/active-directory/hybrid/how-to-connect-install-custom).</span><span class="sxs-lookup"><span data-stu-id="4cc90-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="4cc90-159">Si su organización tiene varios bosques para la autenticación (bosques de inicio de sesión), se recomienda encarecidamente lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cc90-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="4cc90-160">**Considere la posibilidad de consolidar los bosques.**</span><span class="sxs-lookup"><span data-stu-id="4cc90-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="4cc90-161">En general, hay más sobrecarga necesaria para mantener varios bosques.</span><span class="sxs-lookup"><span data-stu-id="4cc90-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="4cc90-162">A menos que su organización tenga restricciones de seguridad que dicten la necesidad de bosques independientes, considere la posibilidad de simplificar el entorno local.</span><span class="sxs-lookup"><span data-stu-id="4cc90-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="4cc90-163">**Solo se usa en el bosque de inicio de sesión principal.**</span><span class="sxs-lookup"><span data-stu-id="4cc90-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="4cc90-164">Considere la posibilidad de Microsoft 365 solo en el bosque de inicio de sesión principal para el lanzamiento inicial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc90-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="4cc90-165">Si no puedes consolidar la implementación de AD DS de varios bosques o estás usando otros servicios de directorio para administrar identidades, es posible que puedas sincronizarlas con la ayuda de Microsoft o un partner.</span><span class="sxs-lookup"><span data-stu-id="4cc90-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="4cc90-166">Consulte [Topologías de Azure AD Conectar](/azure/active-directory/hybrid/plan-connect-topologies) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4cc90-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="4cc90-167">Características que dependen de la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="4cc90-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="4cc90-168">La sincronización de directorios es necesaria para las siguientes características y funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="4cc90-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="4cc90-169">Azure AD Seamless Single Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="4cc90-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="4cc90-170">Skype coexistencia</span><span class="sxs-lookup"><span data-stu-id="4cc90-170">Skype coexistence</span></span>
- <span data-ttu-id="4cc90-171">Exchange implementación híbrida, incluida:</span><span class="sxs-lookup"><span data-stu-id="4cc90-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="4cc90-172">Lista global de direcciones (GAL) totalmente compartida entre el entorno Exchange local y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc90-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="4cc90-173">Sincronización de información de GAL desde varios sistemas de correo.</span><span class="sxs-lookup"><span data-stu-id="4cc90-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="4cc90-174">La capacidad de agregar usuarios a y quitar usuarios de Microsoft 365 ofertas de servicio.</span><span class="sxs-lookup"><span data-stu-id="4cc90-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="4cc90-175">Esto requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cc90-175">This requires the following:</span></span>
  - <span data-ttu-id="4cc90-176">La sincronización bidireccional debe configurarse durante la instalación de sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="4cc90-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="4cc90-177">De forma predeterminada, las herramientas de sincronización de directorios escriben información de directorio solo en la nube.</span><span class="sxs-lookup"><span data-stu-id="4cc90-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="4cc90-178">Al configurar la sincronización bidireccional, se habilita la funcionalidad de reescribición para que un número limitado de atributos de objeto se copien de la nube y, a continuación, se vuelvan a escribir en su AD DS local.</span><span class="sxs-lookup"><span data-stu-id="4cc90-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="4cc90-179">La reescribición también se conoce como Exchange modo híbrido.</span><span class="sxs-lookup"><span data-stu-id="4cc90-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="4cc90-180">Una implementación híbrida Exchange local</span><span class="sxs-lookup"><span data-stu-id="4cc90-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="4cc90-181">La capacidad de mover algunos buzones de usuario a Microsoft 365 mientras se mantienen otros buzones de usuario locales.</span><span class="sxs-lookup"><span data-stu-id="4cc90-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="4cc90-182">Caja fuerte remitentes y remitentes bloqueados localmente se replican en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc90-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="4cc90-183">Función de delegación básica y envío en nombre de otra persona.</span><span class="sxs-lookup"><span data-stu-id="4cc90-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="4cc90-184">Tiene una tarjeta inteligente local integrada o una solución de autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="4cc90-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="4cc90-185">Sincronización de fotos, miniaturas, salas de conferencia y grupos de seguridad</span><span class="sxs-lookup"><span data-stu-id="4cc90-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="4cc90-186">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="4cc90-186">Next step</span></span>

<span data-ttu-id="4cc90-187">Cuando esté listo para implementar la identidad híbrida, vea [Prepare for directory synchronization](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="4cc90-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
