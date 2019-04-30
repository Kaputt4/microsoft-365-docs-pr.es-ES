---
title: 'Fase 6: Protección de la información'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Pasos para implementar la infraestructura de protección de la información para Microsoft 365 Enterprise.
ms.openlocfilehash: a0d2c485b05e0969fe45cfd79c86e4e7dcb1d5ff
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400004"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="3c387-103">Fase 6: Protección de la información</span><span class="sxs-lookup"><span data-stu-id="3c387-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="3c387-p101">La protección de la información es un conjunto de directivas y tecnologías que definen la forma en que se transmite, almacena y procesa la información confidencial. En la fase 6, se describen características y opciones de configuración de protección de la información de Microsoft 365 Enterprise que le permiten proteger los datos de sus cargas de trabajo y escenarios basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="3c387-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="3c387-106">Si ya implementó la protección de la información, vea los [criterios de salida](infoprotect-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3c387-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="3c387-107">Planear e implementar la infraestructura de protección de la información de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c387-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="3c387-p102">Es importante que trabaje con sus equipos legales y de cumplimiento para determinar si su organización necesita cumplir normas de cumplimiento, como HIPPA, CJIS o el RGPD. También necesita trabajar con su grupo de seguridad para determinar los objetivos de protección de la información para su organización, así como para departamentos o grupos que necesiten seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="3c387-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="3c387-110">Después, siga este procedimiento para preparar la protección de la información para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3c387-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="3c387-111">Definir los niveles de protección de la información y la seguridad</span><span class="sxs-lookup"><span data-stu-id="3c387-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="3c387-112">Configurar la clasificación para el entorno</span><span class="sxs-lookup"><span data-stu-id="3c387-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="3c387-113">Configurar Microsoft 365 con una mayor seguridad</span><span class="sxs-lookup"><span data-stu-id="3c387-113">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|<span data-ttu-id="3c387-114">[Configurar Windows Information Protection](infoprotect-deploy-windows-information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="3c387-114">[](infoprotect-deploy-windows-information-protection.md)Configure Azure Information Protection</span></span>|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="3c387-115">Configurar la Prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="3c387-115">Office 365 Data Loss Prevention (DLP)</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="3c387-116">Configurar Privileged Access Management para Office 365</span><span class="sxs-lookup"><span data-stu-id="3c387-116">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


<span data-ttu-id="3c387-117">Cuando complete estos pasos, vaya a los [criterios de salida](infoprotect-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3c387-117">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="3c387-118">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c387-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3c387-119">Descubra cómo los expertos en TI de Microsoft utilizan las capacidades de protección de la información de Microsoft 356 Enterprise para proteger la información y defenderse de los ataques cibernéticos:</span><span class="sxs-lookup"><span data-stu-id="3c387-119">Learn how IT experts at Microsoft use the information protection capabilities of Microsoft 356 Enterprise to protect information and defend against cyber attacks:</span></span>

- <span data-ttu-id="3c387-120">[Protecting files in the cloud with Azure Information Protection](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection) (Proteger los archivos en la nube con Azure Information Protection)</span><span class="sxs-lookup"><span data-stu-id="3c387-120">[Protecting files in the cloud with Azure Information Protection](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)</span></span>
- <span data-ttu-id="3c387-121">[Microsoft uses threat intelligence to protect, detect, and respond to threats](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats) (Microsoft usa inteligencia de amenazas para proteger, detectar y responder a las amenazas)</span><span class="sxs-lookup"><span data-stu-id="3c387-121">[Microsoft uses threat intelligence to protect, detect, and respond to threats](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)</span></span>
- <span data-ttu-id="3c387-122">[Microsoft thwarts phishing attempts with Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365) (Microsoft frustra intentos de suplantación de identidad (phishing) con Office 365)</span><span class="sxs-lookup"><span data-stu-id="3c387-122">[Microsoft thwarts phishing attempts with Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="3c387-123">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c387-123">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3c387-124">Vea cómo Contoso Corporation, una empresa multinacional ficticia, pero representativa, [implementó Information Protection](contoso-info-protect.md) con los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c387-124">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="3c387-125">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="3c387-125">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="3c387-126">Definir los niveles de protección de la información y la seguridad</span><span class="sxs-lookup"><span data-stu-id="3c387-126">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

