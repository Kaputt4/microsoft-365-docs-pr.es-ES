---
title: Criterios de salida de infraestructura de protección de información
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examine los criterios para la infraestructura y los servicios basados en la protección de información a fin de asegurarse de que su configuración cumple los requisitos de Microsoft 365 Enterprise.
ms.openlocfilehash: f4896baeb4c18fc1eabac10b15f3ad8e150ab260
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370137"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="93c02-103">Criterios de salida de infraestructura de protección de información</span><span class="sxs-lookup"><span data-stu-id="93c02-103">Information protection infrastructure exit criteria</span></span>

![Fase 6: Protección de la información](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="93c02-105">Asegúrese de que su infraestructura de protección de información cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="93c02-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="93c02-106">Obligatorio: se han definido los niveles de protección de información y seguridad de su organización</span><span class="sxs-lookup"><span data-stu-id="93c02-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="93c02-p101">Ha planeado y determinado los niveles de seguridad que necesita su organización. Estos niveles definen un nivel mínimo de seguridad y niveles adicionales para la información cada vez más confidencial y su seguridad de datos necesaria.</span><span class="sxs-lookup"><span data-stu-id="93c02-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="93c02-109">Como mínimo, usa tres niveles de seguridad:</span><span class="sxs-lookup"><span data-stu-id="93c02-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="93c02-110">Línea base</span><span class="sxs-lookup"><span data-stu-id="93c02-110">Baseline</span></span>
- <span data-ttu-id="93c02-111">Confidencial</span><span class="sxs-lookup"><span data-stu-id="93c02-111">Sensitive</span></span>
- <span data-ttu-id="93c02-112">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="93c02-112">Highly regulated</span></span>

<span data-ttu-id="93c02-113">Si es necesario, el [Paso 1](infoprotect-define-sec-infoprotect-levels.md) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="93c02-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="93c02-114">Obligatorio: se ha configurado una mayor seguridad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93c02-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="93c02-115">Ha configurado los siguientes valores para [mayor seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="93c02-115">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="93c02-116">Directivas de administración de amenazas en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93c02-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="93c02-117">Configuración adicional de todo el espacio empresarial de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="93c02-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="93c02-118">Directivas de uso compartido aplicables a todo en el espacio empresarial en el centro de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="93c02-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="93c02-119">Configuración de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="93c02-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="93c02-120">También ha [habilitado la Protección contra amenazas avanzada (ATP) de Office 365 para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="93c02-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="93c02-121">Si es necesario, el [paso 3](infoprotect-configure-increased-security-office-365.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="93c02-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="93c02-122">Opcional: se ha configurado la clasificación en el entorno</span><span class="sxs-lookup"><span data-stu-id="93c02-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="93c02-123">Ha trabajado con sus equipos legales y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para el gobierno de datos y las directivas de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="93c02-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="93c02-124">Dichas directivas se corresponden con la configuración y la implementación de:</span><span class="sxs-lookup"><span data-stu-id="93c02-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="93c02-125">Tipos de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="93c02-125">Sensitive data types</span></span>
- <span data-ttu-id="93c02-126">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="93c02-126">Retention labels</span></span>
- <span data-ttu-id="93c02-127">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="93c02-127">Sensitivity labels</span></span>
- <span data-ttu-id="93c02-128">Etiquetas de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="93c02-128">Azure Information Protection labels</span></span>

<span data-ttu-id="93c02-129">Si es necesario, el [paso 2](infoprotect-configure-classification.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="93c02-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="93c02-130">Opcional: Windows Information Protection está implementado en su entorno</span><span class="sxs-lookup"><span data-stu-id="93c02-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="93c02-131">Los dispositivos Windows 10 Enterprise inscritos tienen una directiva de Intune implementada y aplicada que determina:</span><span class="sxs-lookup"><span data-stu-id="93c02-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="93c02-132">Qué aplicaciones proteger.</span><span class="sxs-lookup"><span data-stu-id="93c02-132">Which apps to protect.</span></span>
- <span data-ttu-id="93c02-133">El nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="93c02-133">The level of protection.</span></span>
- <span data-ttu-id="93c02-134">Dónde se extiende la protección.</span><span class="sxs-lookup"><span data-stu-id="93c02-134">Where the protection extends.</span></span>

<span data-ttu-id="93c02-135">Si es necesario, el [Paso 4](infoprotect-deploy-windows-information-protection.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="93c02-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="93c02-136">Opcional: Prevención de pérdida de datos (DLP) de Office 365 está implementada</span><span class="sxs-lookup"><span data-stu-id="93c02-136">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="93c02-137">Tiene analizado, probar y, a continuación, implementan el conjunto de directivas DLP, con las ubicaciones y reglas con condiciones y acciones, que su organización necesita para proteger los clientes y otros tipos de datos privados y se ajusten a normativas regionales y del sector y requisitos.</span><span class="sxs-lookup"><span data-stu-id="93c02-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="93c02-138">El personal de cumplimiento y seguridad de datos usa el panel de seguridad y cumplimiento de Office 365 para supervisar incidentes de DLP.</span><span class="sxs-lookup"><span data-stu-id="93c02-138">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="93c02-139">Si es necesario, el [Paso 5](infoprotect-data-loss-prevention.md) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="93c02-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="93c02-140">Opcional: El cifrado del correo electrónico está configurado:</span><span class="sxs-lookup"><span data-stu-id="93c02-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="93c02-141">Configuró la siguiente codificación de correo electrónico necesaria para su organización:</span><span class="sxs-lookup"><span data-stu-id="93c02-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="93c02-142">**Método de cifrado**</span><span class="sxs-lookup"><span data-stu-id="93c02-142">**Encryption method**</span></span> | <span data-ttu-id="93c02-143">**Para el correo electrónico enviado**</span><span class="sxs-lookup"><span data-stu-id="93c02-143">**For email sent**</span></span> |
| [<span data-ttu-id="93c02-144">Cifrado de mensajes de Office 365 (OME)</span><span class="sxs-lookup"><span data-stu-id="93c02-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="93c02-145">Fuera de su organización con cifrado</span><span class="sxs-lookup"><span data-stu-id="93c02-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="93c02-146">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="93c02-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="93c02-147">Con cifrado y permisos</span><span class="sxs-lookup"><span data-stu-id="93c02-147">With both encryption and permissions</span></span> |
| <span data-ttu-id="93c02-148">[Extensiones seguras multipropósito de correo electrónico en Internet (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)</span><span class="sxs-lookup"><span data-stu-id="93c02-148">[](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="93c02-149">Tanto con el cifrado como las firmas digitales que usan la criptografía de clave pública</span><span class="sxs-lookup"><span data-stu-id="93c02-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="93c02-150">Si es necesario, el [Paso 6](infoprotect-email-encryption.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="93c02-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="93c02-151">Opcional: se ha configurado la administración del acceso con privilegios para Office 365</span><span class="sxs-lookup"><span data-stu-id="93c02-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="93c02-152">Ha usado la información en el tema [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (Configuración de la administración del acceso con privilegios en Office 365) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en su organización.</span><span class="sxs-lookup"><span data-stu-id="93c02-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="93c02-153">Ha configurado estas directivas y el acceso Just-in-time está habilitado para el acceso a la información confidencial o el acceso a la configuración crítica.</span><span class="sxs-lookup"><span data-stu-id="93c02-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="93c02-154">Si es necesario, el [paso 7](infoprotect-configure-privileged-access-management.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="93c02-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="93c02-155">Resultados y siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="93c02-155">Results and next steps</span></span>

<span data-ttu-id="93c02-156">Su infraestructura de protección de información para Microsoft 365 Enterprise utiliza niveles de seguridad definidos, seguridad ampliada de Office 365, clasificación con etiquetas y tipos de datos confidenciales, Windows Information Protection, Prevención de pérdida de datos, cifrado del correo electrónico y administración del acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="93c02-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="93c02-157">Si está siguiendo la implementación de punto a punto de Microsoft 365 Enterprise, ya puede hacer que las [cargas de trabajo y escenarios](deploy-workloads.md) aprovechen todas las características y configuración de la infraestructura de base.</span><span class="sxs-lookup"><span data-stu-id="93c02-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
