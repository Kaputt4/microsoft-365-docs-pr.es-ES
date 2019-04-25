---
title: Criterios de salida de infraestructura de protección de información
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examine los criterios para la infraestructura y los servicios basados en la protección de información a fin de asegurarse de que su configuración cumple los requisitos de Microsoft 365 Enterprise.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283706"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="724f4-103">Criterios de salida de infraestructura de protección de información</span><span class="sxs-lookup"><span data-stu-id="724f4-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="724f4-104">Asegúrese de que su infraestructura de protección de información cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="724f4-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="724f4-105">Obligatorio: se han definido los niveles de protección de información y seguridad de su organización</span><span class="sxs-lookup"><span data-stu-id="724f4-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="724f4-p101">Ha planeado y determinado los niveles de seguridad que necesita su organización. Estos niveles definen un nivel mínimo de seguridad y niveles adicionales para la información cada vez más confidencial y su seguridad de datos necesaria.</span><span class="sxs-lookup"><span data-stu-id="724f4-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="724f4-108">Como mínimo, usa tres niveles de seguridad:</span><span class="sxs-lookup"><span data-stu-id="724f4-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="724f4-109">Línea base</span><span class="sxs-lookup"><span data-stu-id="724f4-109">Baseline</span></span>
- <span data-ttu-id="724f4-110">Confidencial</span><span class="sxs-lookup"><span data-stu-id="724f4-110">Sensitive</span></span>
- <span data-ttu-id="724f4-111">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="724f4-111">Highly regulated</span></span>

<span data-ttu-id="724f4-112">Si es necesario, el [Paso 1](infoprotect-define-sec-infoprotect-levels.md) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="724f4-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="724f4-113">Obligatorio: se ha configurado una mayor seguridad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="724f4-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="724f4-114">Ha configurado los siguientes valores para [mayor seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="724f4-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="724f4-115">Directivas de administración de amenazas en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="724f4-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="724f4-116">Configuración adicional de todo el espacio empresarial de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="724f4-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="724f4-117">Directivas de uso compartidas de todo el espacio empresarial en el Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="724f4-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="724f4-118">Configuración de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="724f4-118">CORS support in Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="724f4-119">También ha [habilitado la Protección contra amenazas avanzada (ATP) de Office 365 para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/es-ES/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="724f4-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/es-ES/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="724f4-120">Si es necesario, el [paso 3](infoprotect-configure-increased-security-office-365.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="724f4-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="724f4-121">Opcional: se ha configurado la clasificación en el entorno</span><span class="sxs-lookup"><span data-stu-id="724f4-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="724f4-122">Ha trabajado con sus equipos legales y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para el gobierno de datos y las directivas de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="724f4-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span> 

<span data-ttu-id="724f4-123">Dichas directivas se corresponden con la configuración y la implementación de:</span><span class="sxs-lookup"><span data-stu-id="724f4-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="724f4-124">Tipos de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="724f4-124">Sensitive data types</span></span>
- <span data-ttu-id="724f4-125">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="724f4-125">Retention labels</span></span>
- <span data-ttu-id="724f4-126">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="724f4-126">Sensitivity labels</span></span>
- <span data-ttu-id="724f4-127">Etiquetas de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="724f4-127">Azure Information Protection labels</span></span>

<span data-ttu-id="724f4-128">Si es necesario, el [paso 2](infoprotect-configure-classification.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="724f4-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="724f4-129">Opcional: se ha configurado la administración del acceso con privilegios para Office 365</span><span class="sxs-lookup"><span data-stu-id="724f4-129">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="724f4-130">Ha usado la información en el tema [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (Configuración de la administración del acceso con privilegios en Office 365) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en su organización.</span><span class="sxs-lookup"><span data-stu-id="724f4-130">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="724f4-131">Ha configurado estas directivas y el acceso Just-in-time está habilitado para el acceso a la información confidencial o el acceso a la configuración crítica.</span><span class="sxs-lookup"><span data-stu-id="724f4-131">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="724f4-132">Si es necesario, el [paso 4](infoprotect-configure-privileged-access-management.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="724f4-132">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="724f4-133">Resultados y siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="724f4-133">Validation and next steps</span></span>

<span data-ttu-id="724f4-134">La infraestructura de protección de información de Microsoft 365 Enterprise usa niveles de seguridad definidos, seguridad aumentada de Office 365, clasificación mediante etiquetas y tipos de datos confidenciales y administración de acceso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="724f4-134">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="724f4-135">Si está siguiendo la implementación de punto a punto de Microsoft 365 Enterprise, ya puede hacer que las [cargas de trabajo y escenarios](deploy-workloads.md) aprovechen todas las características y configuración de la infraestructura de base.</span><span class="sxs-lookup"><span data-stu-id="724f4-135">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
