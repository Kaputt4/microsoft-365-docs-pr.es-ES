---
title: 'Paso 4: Agregar las cuentas de usuario'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Agregue cuentas de usuario y grupos directamente en la nube o a través de la sincronización con el directorio local.
ms.openlocfilehash: 324d4662f868a4a92693b43c6bc0f75c11f20519
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067386"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="32f84-103">Paso 4: Agregar las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="32f84-103">Step 4: Add your user accounts</span></span>

![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="32f84-105">Crear cuentas de usuario para identidades solo de nube</span><span class="sxs-lookup"><span data-stu-id="32f84-105">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="32f84-106">Para la identidad solo de nube, cree los usuarios y grupos en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="32f84-106">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="32f84-107">Puede utilizar:</span><span class="sxs-lookup"><span data-stu-id="32f84-107">You can use:</span></span>

- <span data-ttu-id="32f84-108">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32f84-108">The Microsoft 365 admin center</span></span>
- <span data-ttu-id="32f84-109">Microsoft Azure Portal</span><span class="sxs-lookup"><span data-stu-id="32f84-109">The Azure portal</span></span>
- <span data-ttu-id="32f84-110">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f84-110">Azure PowerShell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="32f84-111">Sincronizar identidades para identidades híbridas</span><span class="sxs-lookup"><span data-stu-id="32f84-111">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="32f84-112">*Este paso es obligatorio para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="32f84-112">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="32f84-113">En esta sección, sincronizará su instancia local de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD que usan sus suscripciones a Office 365, Microsoft Intune y otros servicios basados en la nube incluidos con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="32f84-113">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="32f84-114">Azure AD Connect es la herramienta compatible de Microsoft que le guiará durante el proceso de sincronizar solo las identidades que necesita desde entornos de AD DS de bosque único o bosques múltiples a su espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32f84-114">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="32f84-115">La siguiente figura muestra el proceso básico para la sincronización de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="32f84-115">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Cómo sincroniza Azure AD Connect su directorio local con Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="32f84-117">Azure AD Connect ejecutado en un servidor busca cambios en las cuentas, grupos y contactos de AD DS.</span><span class="sxs-lookup"><span data-stu-id="32f84-117">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="32f84-118">Azure AD Connect envía los cambios al espacio empresarial de Azure AD de su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32f84-118">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="32f84-p103">La primera decisión en su solución de identidad híbrida es el requisito de autenticación. Las siguientes opciones son:</span><span class="sxs-lookup"><span data-stu-id="32f84-p103">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="32f84-p104">Con la **autenticación administrada**, Azure AD controla el proceso de autenticación de inicio de sesión del usuario. Hay dos métodos de autenticación administrada:</span><span class="sxs-lookup"><span data-stu-id="32f84-p104">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="32f84-123">**Sincronización de hash de contraseña (PHS)** (recomendado y necesario para algunas características premium).</span><span class="sxs-lookup"><span data-stu-id="32f84-123">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="32f84-124">Esta es la forma más sencilla de habilitar la autenticación para los objetos del directorio local en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32f84-124">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="32f84-125">Azure AD Connect extrae la contraseña con hash de AD DS, realiza procesamientos de seguridad adicionales en el hash de contraseña y la sincroniza con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32f84-125">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password hash, and synchronizes it to Azure AD.</span></span> <span data-ttu-id="32f84-126">Para obtener más información, vea [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (Implementación de la sincronización de hash de contraseñas mediante la sincronización de Azure AD Connect).</span><span class="sxs-lookup"><span data-stu-id="32f84-126">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="32f84-127">La **autenticación de paso a través (PTA)** proporciona una sencilla solución de validación de contraseñas para servicios basados en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32f84-127">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="32f84-128">PTA usa un agente que se ejecuta en uno o más servidores locales para validar las autenticaciones de usuario directamente con AD DS local.</span><span class="sxs-lookup"><span data-stu-id="32f84-128">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="32f84-129">Para obtener más información, vea [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication) (Inicio de sesión de usuario con autenticación de paso a través de Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="32f84-129">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="32f84-p107">Con la **autenticación federada**, el proceso de autenticación se redirige a otro proveedor de identidades a través de un servidor de federación de identidades, como Servicios de federación de Active Directory (AD FS), para el inicio de sesión de un usuario. El proveedor de identidades puede proporcionar métodos de autenticación adicionales, como la autenticación basada en tarjeta inteligente. Para obtener más información, vea [Elegir el método de autenticación adecuado para la solución de identidad híbrida de Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="32f84-p107">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="32f84-133">Vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="32f84-133">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="32f84-134"><p> </p></span><span class="sxs-lookup"><span data-stu-id="32f84-134"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="32f84-135">Una vez que haya determinado la solución de identidad híbrida, descargue y ejecute la [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) (herramienta de corrección de errores de sincronización de directorios IdFix) para analizar los problemas de AD DS.</span><span class="sxs-lookup"><span data-stu-id="32f84-135">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="32f84-136">Después de resolver todos los problemas que haya identificado la herramienta IdFix, vea [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) (Implementación de sincronización de hash de contraseñas) para obtener instrucciones sobre cómo instalar la herramienta Azure AD Connect y configurar la sincronización de directorios entre la instancia local de AD DS y el espacio empresarial de Azure AD para sus suscripciones a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32f84-136">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="32f84-137">Después de que se inicie la sincronización, mantendrá sus cuentas de usuario y grupos con su proveedor de identidades local, como AD DS.</span><span class="sxs-lookup"><span data-stu-id="32f84-137">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="32f84-138">Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="32f84-138">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="32f84-139">Para ver los requisitos recomendados para entornos híbridos, consulte la columna **Active Directory con sincronización de contraseñas hash** en [requisitos previos](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="32f84-139">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="32f84-140">Para ver los requisitos recomendados para entornos de solo nube, consulte la columna **solo nube** en [requisitos previos](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="32f84-140">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="32f84-141">Una vez que existan usuarios y grupos locales en Azure AD, podrá empezar a asignar licencias y usar cargas de trabajo de productividad como OneDrive para la Empresa y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="32f84-141">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using productivity workloads such as OneDrive for Business and Exchange Online.</span></span>

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="32f84-143">Guía de laboratorio de pruebas: sincronización de hash de contraseñas</span><span class="sxs-lookup"><span data-stu-id="32f84-143">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="32f84-144">Guía de laboratorio de pruebas: autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="32f84-144">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="32f84-145">Como control provisional, puede ver [Fase 2: Criterios de salida de infraestructura de identidades](identity-exit-criteria.md#crit-identity-sync), que corresponde a esta sección.</span><span class="sxs-lookup"><span data-stu-id="32f84-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="32f84-146">Supervisión del estado de sincronización</span><span class="sxs-lookup"><span data-stu-id="32f84-146">Monitor synchronization health</span></span>

<span data-ttu-id="32f84-147">*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="32f84-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="32f84-148">En esta sección, deberá instalar a un agente de Azure AD Connect Health en cada uno de los controladores de dominio AD DS locales para supervisar su infraestructura de identidades y los servicios de sincronización proporcionados por Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="32f84-148">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="32f84-149">En el portal de Azure AD Connect Health podrá consultar la información de supervisión, y se pueden ver alertas, supervisión del rendimiento y análisis de uso, entre otros datos.</span><span class="sxs-lookup"><span data-stu-id="32f84-149">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Componentes de Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="32f84-151">La decisión de diseño clave sobre cómo usar Azure AD Connect Health se basa en la forma en que use Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="32f84-151">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="32f84-152">Si usa la opción de **autenticación administrada**, vea primero [Usar Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para comprender y configurar Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="32f84-152">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="32f84-153">Si solo sincroniza los nombres de las cuentas y los grupos mediante la **autenticación federada** con Servicios de federación de Active Directory (AD FS), empiece con [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para comprender y configurar Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="32f84-153">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="32f84-154">Cuando complete este paso, tendrá:</span><span class="sxs-lookup"><span data-stu-id="32f84-154">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="32f84-155">El agente de Azure AD Connect Health instalado en los servidores de proveedor de identidades locales.</span><span class="sxs-lookup"><span data-stu-id="32f84-155">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="32f84-156">En el portal de Azure AD Connect Health, se mostrará el estado actual de la infraestructura local y las actividades de sincronización con el espacio empresarial de Azure AD para su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32f84-156">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

<span data-ttu-id="32f84-157">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-sync-health) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="32f84-157">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="32f84-158">Simplificación de actualizaciones de contraseña</span><span class="sxs-lookup"><span data-stu-id="32f84-158">Simplify password updates</span></span>

<span data-ttu-id="32f84-159">*Esta función es opcional para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="32f84-159">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="32f84-160">En esta sección, permitirá a los usuarios restablecer sus contraseñas a través de Azure Active Directory (Azure AD), que se replicarán en el Active Directory Domain Services (AD DS) local.</span><span class="sxs-lookup"><span data-stu-id="32f84-160">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="32f84-161">Este proceso se conoce como reescritura de contraseña.</span><span class="sxs-lookup"><span data-stu-id="32f84-161">This process is known as password writeback.</span></span> <span data-ttu-id="32f84-162">Con la escritura diferida de contraseñas, los usuarios no necesitan actualizar las contraseñas mediante AD DS local donde se almacenan las cuentas de usuario y sus atributos.</span><span class="sxs-lookup"><span data-stu-id="32f84-162">With password writeback, users don’t need to update their passwords through the on-premises AD DS where user accounts and their attributes are stored.</span></span> <span data-ttu-id="32f84-163">Esto resulta útil para los usuarios móviles o remotos que no disponen de una conexión de acceso remoto a la red local.</span><span class="sxs-lookup"><span data-stu-id="32f84-163">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="32f84-164">La escritura diferida de contraseñas es necesaria para utilizar por completo las capacidades de Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.</span><span class="sxs-lookup"><span data-stu-id="32f84-164">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="32f84-165">Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).</span><span class="sxs-lookup"><span data-stu-id="32f84-165">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="32f84-p111">Actualice a la última versión de Azure AD Connect para garantizar que tiene la mejor experiencia posible y nuevas características cuando se publican. Para obtener más información, vea [Instalación personalizada de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="32f84-p111">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="32f84-169">Guía del entorno de pruebas: reescritura de contraseñas</span><span class="sxs-lookup"><span data-stu-id="32f84-169">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="32f84-170">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pw-writeback) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="32f84-170">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![Paso 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="32f84-172">Use grupos para administración</span><span class="sxs-lookup"><span data-stu-id="32f84-172">Use groups for management</span></span>](identity-use-group-management.md) |
