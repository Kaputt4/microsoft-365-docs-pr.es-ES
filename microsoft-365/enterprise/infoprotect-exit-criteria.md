---
title: Criterios de salida de infraestructura de protección de información
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Examine los criterios para la infraestructura y los servicios basados en la protección de información a fin de asegurarse de que su configuración cumple los requisitos de Microsoft 365 Enterprise.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871687"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="626e7-103">Criterios de salida de infraestructura de protección de información</span><span class="sxs-lookup"><span data-stu-id="626e7-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="626e7-104">Antes de que complete su infraestructura base, asegúrese de que su infraestructura de protección de información cumple estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="626e7-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="626e7-105">Obligatorio: se han definido los niveles de protección de información y seguridad de su organización</span><span class="sxs-lookup"><span data-stu-id="626e7-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="626e7-p101">Ha planeado y determinado los niveles de seguridad que necesita su organización. Estos niveles definen un nivel mínimo de seguridad y niveles adicionales para la información cada vez más confidencial y su seguridad de datos necesaria.</span><span class="sxs-lookup"><span data-stu-id="626e7-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="626e7-108">Como mínimo, usa tres niveles de seguridad:</span><span class="sxs-lookup"><span data-stu-id="626e7-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="626e7-109">Línea base</span><span class="sxs-lookup"><span data-stu-id="626e7-109">Baseline</span></span>
- <span data-ttu-id="626e7-110">Confidencial</span><span class="sxs-lookup"><span data-stu-id="626e7-110">Sensitive</span></span>
- <span data-ttu-id="626e7-111">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="626e7-111">Highly regulated</span></span>

<span data-ttu-id="626e7-112">Si es necesario, el [paso 1](infoprotect-define-sec-infoprotect-levels.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="626e7-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="626e7-113">Obligatorio: se ha configurado una mayor seguridad para Office 365</span><span class="sxs-lookup"><span data-stu-id="626e7-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="626e7-114">Ha configurado las siguientes opciones para obtener una mayor seguridad en función de la información disponible en [Configurar al inquilino de Office 365 para una mayor seguridad](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span><span class="sxs-lookup"><span data-stu-id="626e7-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="626e7-115">Directivas de administración de amenazas en el Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="626e7-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="626e7-116">Configuración adicional de todo el espacio empresarial de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="626e7-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="626e7-117">Directivas de uso compartidas de todo el espacio empresarial en el Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="626e7-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="626e7-118">Configuración en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="626e7-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="626e7-119">También ha [habilitado la Protección contra amenazas avanzada de Office 365 (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="626e7-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="626e7-120">Si es necesario, el [paso 3](infoprotect-configure-increased-security-office-365.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="626e7-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="626e7-121">Opcional: se ha configurado la clasificación en el entorno</span><span class="sxs-lookup"><span data-stu-id="626e7-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="626e7-122">Ha trabajado con sus equipos legales y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para los datos de su organización, que incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="626e7-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="626e7-123">Tipos de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="626e7-123">Sensitive data types</span></span>
- <span data-ttu-id="626e7-124">Etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="626e7-124">Office 365 labels</span></span>
- <span data-ttu-id="626e7-125">Etiquetas de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="626e7-125">Azure Information Protection labels</span></span>

<span data-ttu-id="626e7-126">Si es necesario, el [paso 2](infoprotect-configure-classification.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="626e7-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="626e7-127">Opcional: se ha configurado la administración del acceso con privilegios para Office 365</span><span class="sxs-lookup"><span data-stu-id="626e7-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="626e7-p102">Ha usado la información del artículo [Configurar la administración del acceso con privilegios de Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en la organización de Office 365. Ha configurado estas directivas y el acceso puntual está habilitado para el acceso a los datos confidenciales o a las opciones de configuración críticas.</span><span class="sxs-lookup"><span data-stu-id="626e7-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="626e7-130">Si es necesario, el [paso 4](infoprotect-configure-privileged-access-management.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="626e7-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="626e7-131">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="626e7-131">Next Step</span></span>

<span data-ttu-id="626e7-132">Ya está preparado para implementar [cargas de trabajo y escenarios](deploy-workloads.md), como Microsoft Teams y Exchange Online, que se ejecutan en función de la infraestructura base de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="626e7-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
