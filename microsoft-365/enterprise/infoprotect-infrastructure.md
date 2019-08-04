---
title: 'Fase 6: Protección de la información'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Pasos para implementar la infraestructura de protección de la información para Microsoft 365 Enterprise.
ms.openlocfilehash: a00f61cbf2f8d00929a67dae6d401fd99014ec26
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073690"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="0af75-103">Fase 6: Protección de la información</span><span class="sxs-lookup"><span data-stu-id="0af75-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="0af75-p101">La protección de la información es un conjunto de directivas y tecnologías que definen la forma en que se transmite, almacena y procesa la información confidencial. En la fase 6, se describen características y opciones de configuración de protección de la información de Microsoft 365 Enterprise que le permiten proteger los datos de sus cargas de trabajo y escenarios basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="0af75-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="0af75-106">Si ya implementó la protección de la información, vea los [criterios de salida](infoprotect-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0af75-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="0af75-107">Planear e implementar la infraestructura de protección de la información de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0af75-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="0af75-p102">Es importante que trabaje con sus equipos legales y de cumplimiento para determinar si su organización necesita cumplir normas de cumplimiento, como HIPPA, CJIS o el RGPD. También necesita trabajar con su grupo de seguridad para determinar los objetivos de protección de la información para su organización, así como para departamentos o grupos que necesiten seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="0af75-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="0af75-110">Después, siga este procedimiento para preparar la protección de la información para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0af75-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="0af75-111">Definir los niveles de protección de la información y la seguridad</span><span class="sxs-lookup"><span data-stu-id="0af75-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="0af75-112">Configurar la clasificación para el entorno</span><span class="sxs-lookup"><span data-stu-id="0af75-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="0af75-113">Configurar Microsoft 365 con una mayor seguridad</span><span class="sxs-lookup"><span data-stu-id="0af75-113">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="0af75-114">Configurar Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="0af75-114">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="0af75-115">Configurar la Prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="0af75-115">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="0af75-116">Configurar Privileged Access Management para Office 365</span><span class="sxs-lookup"><span data-stu-id="0af75-116">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


<span data-ttu-id="0af75-117">Cuando complete estos pasos, vaya a los [criterios de salida](infoprotect-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0af75-117">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="0af75-118">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0af75-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0af75-119">Obtenga información sobre cómo los expertos de TI de Microsoft usan [Azure Information Protection para salvaguardar los datos](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span><span class="sxs-lookup"><span data-stu-id="0af75-119">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="0af75-120">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0af75-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0af75-121">Vea cómo Contoso Corporation, una empresa multinacional ficticia, pero representativa, [implementó Information Protection](contoso-info-protect.md) con los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0af75-121">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="0af75-122">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="0af75-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="0af75-123">Definir los niveles de protección de la información y la seguridad</span><span class="sxs-lookup"><span data-stu-id="0af75-123">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

