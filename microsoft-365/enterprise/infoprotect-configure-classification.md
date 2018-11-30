---
title: 'Paso 2: Configurar la clasificación para el entorno'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure varias formas de clasificar los datos de su organización.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871357"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="4e1fd-103">Paso 2: Configurar la clasificación para el entorno</span><span class="sxs-lookup"><span data-stu-id="4e1fd-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="4e1fd-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4e1fd-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="4e1fd-105">En este paso, trabajará con los equipos legales y de cumplimiento para definir un esquema de clasificación para los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4e1fd-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="4e1fd-106">Clasificaciones de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e1fd-106">Microsoft classifications</span></span>

<span data-ttu-id="4e1fd-107">Microsoft 365 incluye tres tipos de clasificación:</span><span class="sxs-lookup"><span data-stu-id="4e1fd-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="4e1fd-108">Tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="4e1fd-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="4e1fd-109">Etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="4e1fd-109">Office 365 labels</span></span>
- <span data-ttu-id="4e1fd-110">Etiquetas y protección de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4e1fd-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="4e1fd-111">Tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="4e1fd-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="4e1fd-p101">Los tipos de información confidencial de Office 365 definen cómo los procesos automatizados (por ejemplo, la búsqueda) reconocen tipos de información específicos (por ejemplo, los números de servicios de salud y de tarjetas de crédito). Los tipos de información confidencial se usan para buscar información confidencial y aplicar reglas y directivas de prevención de pérdida de datos para proteger estos datos. Para obtener más información, vea [Información general sobre directivas de prevención de pérdida de datos](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Por ejemplo, los tipos de información confidencial son especialmente útiles para cumplir los requisitos de cumplimiento y normativas, por ejemplo, para el Reglamento general de protección de datos (RGPD).</span><span class="sxs-lookup"><span data-stu-id="4e1fd-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="4e1fd-116">Etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="4e1fd-116">Office 365 labels</span></span>
<span data-ttu-id="4e1fd-p102">Puede usar etiquetas de Office 365 para datos personales y para archivos de secretos empresariales muy regulados almacenados en SharePoint Online y OneDrive para la Empresa. Para obtener más información, incluido cómo crearlas, vea [Información general de etiquetas](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span><span class="sxs-lookup"><span data-stu-id="4e1fd-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="4e1fd-p103">Si decide usar etiquetas de Office 365, debe configurar al menos una para cada nivel de protección. Por ejemplo, cree tres etiquetas para:</span><span class="sxs-lookup"><span data-stu-id="4e1fd-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="4e1fd-121">Línea base</span><span class="sxs-lookup"><span data-stu-id="4e1fd-121">Baseline</span></span>
- <span data-ttu-id="4e1fd-122">Confidencial</span><span class="sxs-lookup"><span data-stu-id="4e1fd-122">Sensitive</span></span>
- <span data-ttu-id="4e1fd-123">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="4e1fd-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="4e1fd-124">Etiquetas y protección de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4e1fd-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="4e1fd-p104">Puede usar etiquetas de Azure Information Protection para clasificar y, opcionalmente, proteger correos electrónicos y documentos de su organización. Estas etiquetas se pueden aplicar a documentos almacenados fuera de Office 365. Los administradores que definen reglas y condiciones pueden aplicar automáticamente estas etiquetas, los usuarios las pueden aplicar manualmente o se puede usar una combinación donde los usuarios reciben recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="4e1fd-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="4e1fd-128">Para planear e implementar etiquetas y protección de Azure Information Protection, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="4e1fd-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="4e1fd-129">Revise los [requisitos de Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="4e1fd-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="4e1fd-130">Siga el [mapa de ruta de implementación para clasificación, etiquetado y protección](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="4e1fd-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="4e1fd-131">Para obtener más información, vea la [biblioteca de documentación de Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="4e1fd-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="4e1fd-132">Clasificación para el RGPD</span><span class="sxs-lookup"><span data-stu-id="4e1fd-132">Classification for GDPR</span></span>

<span data-ttu-id="4e1fd-133">Para obtener un esquema de clasificación de ejemplo que incluye datos personales para el RGPD, consulte [Diseño de un esquema de clasificación de datos personales](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="4e1fd-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4e1fd-135">Guía del entorno de pruebas: clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="4e1fd-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="4e1fd-136">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="4e1fd-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="4e1fd-137">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="4e1fd-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="4e1fd-138">Configurar una mayor seguridad para Office 365</span><span class="sxs-lookup"><span data-stu-id="4e1fd-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

