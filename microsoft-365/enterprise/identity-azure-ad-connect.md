---
title: 'Paso 7: Sincronizar las identidades'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda las opciones de identidad y configure Azure AD Connect para sincronizar la instancia local de Windows Server AD con Azure AD.
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871233"
---
# <a name="step-7-synchronize-identities"></a><span data-ttu-id="42913-103">Paso 7: Sincronizar las identidades</span><span class="sxs-lookup"><span data-stu-id="42913-103">Step 7: Synchronize identities</span></span>

<span data-ttu-id="42913-104">*Este paso es obligatorio para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="42913-104">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="42913-105">En este paso, sincronizará su instancia local de Windows Server Active Directory (AD) con el espacio empresarial de Azure Active Directory (AD) que usan sus suscripciones a Office 365 y Enterprise Mobility + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="42913-105">In this step, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="42913-106">Azure AD Connect es la herramienta compatible de Microsoft que le guiará por el proceso de sincronizar solo las identidades que necesita desde entornos de Windows Server AD de bosque único o bosques múltiples a su espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42913-106">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span>

![Cómo sincroniza Azure AD Connect su directorio local con Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

<span data-ttu-id="42913-108">*Cómo sincroniza Azure AD Connect su directorio local con Azure AD*</span><span class="sxs-lookup"><span data-stu-id="42913-108">*How Azure AD Connect synchronizes your on-premises directory with Azure AD*</span></span>

<span data-ttu-id="42913-p101">La primera decisión en su solución de identidad híbrida es el requisito de autenticación. Las siguientes opciones son:</span><span class="sxs-lookup"><span data-stu-id="42913-p101">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="42913-p102">Con la **autenticación administrada**, Azure AD controla el proceso de autenticación de inicio de sesión del usuario. Hay dos métodos de autenticación administrada:</span><span class="sxs-lookup"><span data-stu-id="42913-p102">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="42913-p103">**Sincronización de hash de contraseñas (PHS)** [recomendado y obligatorio para algunas características premium]. Esta es la forma más sencilla de habilitar la autenticación para objetos del directorio local en Azure AD. Azure AD Connect extrae la contraseña con hash de Windows Server AD, aplica un procesamiento de seguridad adicional en la contraseña y la guarda en Azure AD. Para obtener más información, vea [Implementación de la sincronización de hash de contraseñas con la sincronización de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span><span class="sxs-lookup"><span data-stu-id="42913-p103">**Password Hash Sync (PHS)** [Recommended and required for some premium features]. This is the simplest way to enable authentication for on-premises directory objects in Azure AD. Azure AD Connect extracts the hashed password from Windows Server AD, does extra security processing on the password, and saves it in Azure AD. For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="42913-p104">La **autenticación de paso a través (PTA)** proporciona una solución de validación de contraseña simple para los servicios basados en Azure AD. PTA usa un agente que se ejecuta en uno o varios servidores locales para validar las autenticaciones de los usuarios directamente con su instancia local de Windows Server AD. Para obtener más información, vea [Inicio de sesión del usuario con la autenticación de paso a través de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="42913-p104">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services. PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises Windows Server AD. For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="42913-p105">Con la **autenticación federada**, el proceso de autenticación se redirige a otro proveedor de identidades a través de un servidor de federación de identidades, como Servicios de federación de Active Directory (AD FS), para el inicio de sesión de un usuario. El proveedor de identidades puede proporcionar métodos de autenticación adicionales, como la autenticación basada en tarjeta inteligente. Para obtener más información, vea [Elegir el método de autenticación adecuado para la solución de identidad híbrida de Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="42913-p105">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="42913-123">Una vez que haya determinado la solución de identidad híbrida, descargue y ejecute la [herramienta de corrección de errores de DirSync IdFix](https://www.microsoft.com/download/details.aspx?id=36832) para analizar los problemas de Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="42913-123">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="42913-p106">Después de resolver todos los problemas que haya identificado la herramienta IdFix, vea [Implementar la sincronización de hash de contraseñas](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) para obtener instrucciones sobre cómo instalar la herramienta Azure AD Connect y configurar la sincronización de directorios entre la instancia local de Windows Server AD y el espacio empresarial de Azure AD para sus suscripciones a Office 365 y EMS. Después de que se inicie la sincronización, mantendrá sus cuentas de usuario y grupos con su proveedor de identidades local, como Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="42913-p106">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span>

<span data-ttu-id="42913-126">Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="42913-126">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 
- <span data-ttu-id="42913-127">Para ver los requisitos recomendados para entornos híbridos, consulte la columna **Active Directory con sincronización de contraseñas hash** en [requisitos previos](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="42913-127">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="42913-128">Para ver los requisitos recomendados para entornos de solo nube, consulte la columna **solo nube** en [requisitos previos](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="42913-128">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="42913-130">Guía de laboratorio de pruebas: sincronización de hash de contraseñas</span><span class="sxs-lookup"><span data-stu-id="42913-130">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="42913-131">Guía de laboratorio de pruebas: autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="42913-131">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="42913-132">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-sync) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="42913-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="42913-133">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="42913-133">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="42913-134">Supervisar el estado de sincronización</span><span class="sxs-lookup"><span data-stu-id="42913-134">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |

