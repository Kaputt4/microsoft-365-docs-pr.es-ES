---
title: Criterios de salida de infraestructura de protección de información
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examine los criterios para la infraestructura y los servicios basados en la protección de información a fin de asegurarse de que su configuración cumple los requisitos de Microsoft 365 Enterprise.
ms.openlocfilehash: 9c74a3994a1a404583326f65f1cec579fccbe659
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400044"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="61efd-103">Criterios de salida de infraestructura de protección de información</span><span class="sxs-lookup"><span data-stu-id="61efd-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="61efd-104">Asegúrese de que su infraestructura de protección de información cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="61efd-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="61efd-105">Obligatorio: se han definido los niveles de protección de información y seguridad de su organización</span><span class="sxs-lookup"><span data-stu-id="61efd-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="61efd-p101">Ha planeado y determinado los niveles de seguridad que necesita su organización. Estos niveles definen un nivel mínimo de seguridad y niveles adicionales para la información cada vez más confidencial y su seguridad de datos necesaria.</span><span class="sxs-lookup"><span data-stu-id="61efd-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="61efd-108">Como mínimo, usa tres niveles de seguridad:</span><span class="sxs-lookup"><span data-stu-id="61efd-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="61efd-109">Línea base</span><span class="sxs-lookup"><span data-stu-id="61efd-109">Baseline</span></span>
- <span data-ttu-id="61efd-110">Confidencial</span><span class="sxs-lookup"><span data-stu-id="61efd-110">Sensitive</span></span>
- <span data-ttu-id="61efd-111">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="61efd-111">Highly regulated</span></span>

<span data-ttu-id="61efd-112">Si es necesario, el [Paso 1](infoprotect-define-sec-infoprotect-levels.md) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="61efd-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="61efd-113">Obligatorio: se ha configurado una mayor seguridad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61efd-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="61efd-114">Ha configurado los siguientes valores para [mayor seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="61efd-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="61efd-115">Directivas de administración de amenazas en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61efd-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="61efd-116">Configuración adicional de todo el espacio empresarial de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="61efd-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="61efd-117">Directivas de uso compartido aplicables a todo en el espacio empresarial en el centro de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="61efd-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="61efd-118">Configuración de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="61efd-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="61efd-119">También ha [habilitado la Protección contra amenazas avanzada (ATP) de Office 365 para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="61efd-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="61efd-120">Si es necesario, el [paso 3](infoprotect-configure-increased-security-office-365.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="61efd-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="61efd-121">Opcional: se ha configurado la clasificación en el entorno</span><span class="sxs-lookup"><span data-stu-id="61efd-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="61efd-122">Ha trabajado con sus equipos legales y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para el gobierno de datos y las directivas de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="61efd-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="61efd-123">Dichas directivas se corresponden con la configuración y la implementación de:</span><span class="sxs-lookup"><span data-stu-id="61efd-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="61efd-124">Tipos de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="61efd-124">Sensitive data types</span></span>
- <span data-ttu-id="61efd-125">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="61efd-125">Retention labels</span></span>
- <span data-ttu-id="61efd-126">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="61efd-126">Sensitivity labels</span></span>
- <span data-ttu-id="61efd-127">Etiquetas de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="61efd-127">Azure Information Protection labels</span></span>

<span data-ttu-id="61efd-128">Si es necesario, el [paso 2](infoprotect-configure-classification.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="61efd-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="61efd-129">Opcional: Windows Information Protection está implementado en su entorno</span><span class="sxs-lookup"><span data-stu-id="61efd-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="61efd-130">Los dispositivos Windows 10 Enterprise inscritos tienen una directiva de Intune implementada y aplicada que determina:</span><span class="sxs-lookup"><span data-stu-id="61efd-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="61efd-131">Qué aplicaciones proteger.</span><span class="sxs-lookup"><span data-stu-id="61efd-131">Which apps to protect.</span></span>
- <span data-ttu-id="61efd-132">El nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="61efd-132">The level of protection.</span></span>
- <span data-ttu-id="61efd-133">Dónde se extiende la protección.</span><span class="sxs-lookup"><span data-stu-id="61efd-133">Where the protection extends.</span></span>

<span data-ttu-id="61efd-134">Si es necesario, el [Paso 4](infoprotect-deploy-windows-information-protection.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="61efd-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="61efd-135">Opcional: Prevención de pérdida de datos (DLP) de Office 365 está implementada</span><span class="sxs-lookup"><span data-stu-id="61efd-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="61efd-136">Ha analizado, probado e implementado el conjunto de directivas DLP, con ubicaciones y reglas con condiciones y acciones, que su organización necesita para proteger los clientes y otros tipos de datos privados y ajustarse a normativas y requisitos regionales y del sector.</span><span class="sxs-lookup"><span data-stu-id="61efd-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="61efd-137">El personal de cumplimiento y seguridad de datos usa el panel de seguridad y cumplimiento de Office 365 para supervisar incidentes de DLP.</span><span class="sxs-lookup"><span data-stu-id="61efd-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="61efd-138">Si es necesario, el [Paso 5](infoprotect-data-loss-prevention.md) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="61efd-138">If needed, [Step 4](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="61efd-139">Opcional: se ha configurado la administración del acceso con privilegios para Office 365</span><span class="sxs-lookup"><span data-stu-id="61efd-139">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="61efd-140">Ha usado la información en el tema [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (Configuración de la administración del acceso con privilegios en Office 365) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en su organización.</span><span class="sxs-lookup"><span data-stu-id="61efd-140">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="61efd-141">Ha configurado estas directivas y el acceso Just-in-time está habilitado para el acceso a la información confidencial o el acceso a la configuración crítica.</span><span class="sxs-lookup"><span data-stu-id="61efd-141">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="61efd-142">Si es necesario, el [Paso 6](infoprotect-configure-privileged-access-management.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="61efd-142">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="61efd-143">Resultados y siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="61efd-143">Results and next steps</span></span>

<span data-ttu-id="61efd-144">Su infraestructura de protección de información para Microsoft 365 Enterprise utiliza niveles de seguridad definidos, seguridad ampliada de Office 365, clasificación con etiquetas y tipos de datos confidenciales, Windows Information Protection, Prevención de pérdida de datos y administración del acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="61efd-144">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="61efd-145">Si está siguiendo la implementación de punto a punto de Microsoft 365 Enterprise, ya puede hacer que las [cargas de trabajo y escenarios](deploy-workloads.md) aprovechen todas las características y configuración de la infraestructura de base.</span><span class="sxs-lookup"><span data-stu-id="61efd-145">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
