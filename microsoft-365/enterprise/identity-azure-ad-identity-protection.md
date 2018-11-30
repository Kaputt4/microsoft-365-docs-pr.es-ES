---
title: 'Paso 6: Proteger contra credenciales en peligro'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871803"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="45402-103">Paso 6: Proteger contra credenciales en peligro</span><span class="sxs-lookup"><span data-stu-id="45402-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="45402-104">*Este paso es opcional y solo es válido para la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="45402-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="45402-p101">En este paso, obtendrá información sobre cómo configurar directivas para proteger contra credenciales en peligro, donde un atacante determina el nombre de la cuenta y la contraseña de un usuario para obtener acceso a los servicios y datos en la nube de una organización. Azure AD Identity Protection ofrece distintas formas de impedir que un atacante se mueva lateralmente por sus cuentas y grupos y, en consecuencia, impedir que obtenga acceso a los datos más valiosos.</span><span class="sxs-lookup"><span data-stu-id="45402-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="45402-107">Con Azure AD Identity Protection, puede:</span><span class="sxs-lookup"><span data-stu-id="45402-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="45402-108">Determinar y corregir posibles vulnerabilidades en las identidades de su organización</span><span class="sxs-lookup"><span data-stu-id="45402-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="45402-p102">Azure AD usa aprendizaje automático para detectar anomalías y actividades sospechosas, como inicios de sesión y actividades posteriores al inicio de sesión. Con estos datos, Identity Protection genera informes y alertas que le permiten evaluar los problemas y tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="45402-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="45402-111">Detectar acciones sospechosas relacionadas con las identidades de su organización y responder a ellas automáticamente</span><span class="sxs-lookup"><span data-stu-id="45402-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="45402-p103">Puede configurar directivas basadas en riesgos que responden automáticamente a los problemas encontrados cuando se alcanza un nivel de riesgo especificado. Estas directivas, además de otros controles de acceso condicional proporcionados por Azure Active Directory y Enterprise Mobility + Security (EMS), pueden automáticamente impedir el acceso o realizar acciones correctivas, como activar restablecimientos de contraseña y exigir la autenticación multifactor para los inicios de sesión posteriores.</span><span class="sxs-lookup"><span data-stu-id="45402-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="45402-114">Investigar incidentes sospechosos y solucionarlos con acciones administrativas</span><span class="sxs-lookup"><span data-stu-id="45402-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="45402-p104">Puede investigar eventos de riesgo con información sobre el incidente de seguridad. Hay disponibles flujos de trabajo básicos para realizar un seguimiento de las investigaciones e iniciar acciones de corrección, como restablecimientos de contraseña.</span><span class="sxs-lookup"><span data-stu-id="45402-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="45402-117">Vea [más información sobre Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="45402-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="45402-118">Vea los [pasos para habilitar Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="45402-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="45402-119">El resultado de este paso es que habilitó Azure AD Identity Protection y ahora lo usa para:</span><span class="sxs-lookup"><span data-stu-id="45402-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="45402-120">Solucionar posibles vulnerabilidades de identidad.</span><span class="sxs-lookup"><span data-stu-id="45402-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="45402-121">Detectar posibles intentos de uso ilícito de credenciales.</span><span class="sxs-lookup"><span data-stu-id="45402-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="45402-122">Investigar y solucionar incidentes de identidad sospechosos y continuados.</span><span class="sxs-lookup"><span data-stu-id="45402-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="45402-124">Guía de laboratorio de pruebas: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="45402-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="45402-125">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-ident-prot) de este paso.</span><span class="sxs-lookup"><span data-stu-id="45402-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="45402-126">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="45402-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="45402-127">Sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="45402-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


