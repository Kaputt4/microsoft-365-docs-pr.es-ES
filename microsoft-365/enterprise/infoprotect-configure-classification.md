---
title: 'Paso 2: Configurar la clasificación para el entorno'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure varias formas de clasificar los datos de su organización.
ms.openlocfilehash: 483549e7eaa7f6b77b775cf35bda7b0f42834ad2
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072260"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="69450-103">Paso 2: Configurar la clasificación para el entorno</span><span class="sxs-lookup"><span data-stu-id="69450-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="69450-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="69450-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="69450-105">En este paso, trabajará con los equipos legales y de cumplimiento para definir un esquema de clasificación para los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="69450-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="69450-106">Tipos de clasificación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69450-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="69450-107">Microsoft 365 incluye cuatro tipos de clasificación:</span><span class="sxs-lookup"><span data-stu-id="69450-107">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="69450-108">Tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="69450-108">Sensitive information types</span></span>
- <span data-ttu-id="69450-109">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="69450-109">Retention labels</span></span>
- <span data-ttu-id="69450-110">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="69450-110">Sensitivity labels</span></span>
- <span data-ttu-id="69450-111">Etiquetas y protección de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="69450-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="69450-112">Tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="69450-112">Sensitive information types</span></span>

<span data-ttu-id="69450-113">Los tipos de información confidencial de Microsoft 365 definen cómo procesos automatizados como la búsqueda reconocen tipos específicos de información.</span><span class="sxs-lookup"><span data-stu-id="69450-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="69450-114">Estos incluyen datos confidenciales de empleados o clientes, como números de tarjeta de crédito y de servicio de salud.</span><span class="sxs-lookup"><span data-stu-id="69450-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="69450-115">Se usan los tipos de información confidencial para buscar información confidencial y aplicar reglas y directivas de prevención de pérdida de datos (DLP) para proteger estos datos.</span><span class="sxs-lookup"><span data-stu-id="69450-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="69450-116">Para obtener más información, vea [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains) (qué contiene una directiva DLP).</span><span class="sxs-lookup"><span data-stu-id="69450-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="69450-117">Los tipos de información confidencial son especialmente útiles para cumplir los requisitos de cumplimiento y normativa, como en el caso del Reglamento general de protección de datos (RGPD).</span><span class="sxs-lookup"><span data-stu-id="69450-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="69450-118">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="69450-118">Retention labels</span></span>

<span data-ttu-id="69450-119">Parte de la definición de una estrategia de gobierno de datos es decidir durante cuánto tiempo deben conservarse determinados tipos de documentos o documentos con contenido específico de acuerdo con las directivas de la organización y los reglamentos regionales.</span><span class="sxs-lookup"><span data-stu-id="69450-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="69450-120">Por ejemplo, algunos tipos de documentos se deben conservar durante un tiempo determinado y eliminarse después, mientras que otros deben conservarse indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="69450-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="69450-121">En el caso de los documentos almacenados en Microsoft 365, puede definir y aplicar etiquetas de retención a los documentos y datos almacenados en el correo electrónico de Exchange, SharePoint Online, OneDrive para la Empresa, y mensajes de canal y de chat de Teams.</span><span class="sxs-lookup"><span data-stu-id="69450-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="69450-122">Si usa etiquetas de retención, debe configurar una etiqueta para cada categoría de archivo que deba tener una directiva de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="69450-122">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="69450-123">En la etiqueta de retención, puede especificar:</span><span class="sxs-lookup"><span data-stu-id="69450-123">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="69450-124">Un conjunto de descriptores para los archivos (por ejemplo, por departamento de empresa, categoría de archivo o reglamento).</span><span class="sxs-lookup"><span data-stu-id="69450-124">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="69450-125">La configuración de retención de los archivos que tengan la etiqueta de retención asociada, como el tiempo de conservación y el comportamiento tras haberse superado el tiempo de conservación.</span><span class="sxs-lookup"><span data-stu-id="69450-125">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="69450-126">También puede aplicar una etiqueta de retención a los archivos automáticamente si configura un sitio de SharePoint Online para aplicar una etiqueta de retención predeterminada a todos los documentos nuevos en el sitio.</span><span class="sxs-lookup"><span data-stu-id="69450-126">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="69450-127">Para obtener más información, vea la [Introducción a las etiquetas de retención](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="69450-127">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="69450-128">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="69450-128">Sensitivity labels</span></span>

<span data-ttu-id="69450-129">Parte de la protección y la implementación de seguridad para determinados tipos de documentos o documentos con contenido específico consiste en marcarlos con una etiqueta para que pueda aplicar la seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="69450-129">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="69450-130">Con las etiquetas de confidencialidad de Microsoft 365, puede:</span><span class="sxs-lookup"><span data-stu-id="69450-130">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="69450-131">Aplicar la configuración de protección como el cifrado, los permisos o la agregación de una marca de agua.</span><span class="sxs-lookup"><span data-stu-id="69450-131">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="69450-132">Impedir que salga contenido confidencial de su organización en dispositivos con Windows mediante Endpoint Protection de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="69450-132">Prevent sensitive content from leaving your organization on devices running Windows, by using endpoint protection in Microsoft Intune.</span></span> 
- <span data-ttu-id="69450-133">Usar Endpoint Protection de Windows Information Protection (WIP) para impedir que el contenido se copie en una aplicación de terceros, como Twitter o Gmail, o se copie en unidades de almacenamiento extraíbles, como una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="69450-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="69450-134">Proteger el contenido en los servicios y aplicaciones de terceros con Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="69450-134">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="69450-135">Clasificar contenido sin usar configuración de protección.</span><span class="sxs-lookup"><span data-stu-id="69450-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="69450-136">Si usa etiquetas de confidencialidad, debe configurar una etiqueta para cada nivel de protección de información y seguridad.</span><span class="sxs-lookup"><span data-stu-id="69450-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="69450-137">Por ejemplo, cree tres etiquetas de confidencialidad para:</span><span class="sxs-lookup"><span data-stu-id="69450-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="69450-138">Línea base</span><span class="sxs-lookup"><span data-stu-id="69450-138">Baseline</span></span>
- <span data-ttu-id="69450-139">Confidencial</span><span class="sxs-lookup"><span data-stu-id="69450-139">Sensitive</span></span>
- <span data-ttu-id="69450-140">Extremadamente regulado</span><span class="sxs-lookup"><span data-stu-id="69450-140">Highly regulated</span></span>

<span data-ttu-id="69450-141">Para obtener más información, vea [Información general de etiquetas de confidencialidad](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="69450-141">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="69450-142">Etiquetas y protección de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="69450-142">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="69450-143">Puede usar etiquetas de Azure Information Protection para clasificar correos electrónicos y documentos de su organización, y opcionalmente protegerlos.</span><span class="sxs-lookup"><span data-stu-id="69450-143">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="69450-144">Estas etiquetas se pueden aplicar a los documentos almacenados fuera de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69450-144">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="69450-145">Las etiquetas pueden aplicarse automáticamente por administradores que definen reglas y condiciones, manualmente por los usuarios o mediante una combinación en la que los usuarios reciben recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="69450-145">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="69450-146">Para planear e implementar etiquetas y protección de Azure Information Protection, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="69450-146">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="69450-147">Revise los [requisitos de Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="69450-147">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="69450-148">Siga el [mapa de ruta de implementación para clasificación, etiquetado y protección](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="69450-148">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="69450-149">Para obtener más información, vea la [biblioteca de documentación de Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="69450-149">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="69450-150">Las etiquetas de confidencialidad funcionan a la perfección con las etiquetas existentes de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="69450-150">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="69450-151">Por ejemplo, puede mantener sus etiquetas existentes de Azure Information Protection y las etiquetas que se aplican a los documentos y correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="69450-151">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="69450-152">Si tiene etiquetas de confidencialidad y de Azure Information Protection, debe [migrar las etiquetas de Azure Information Protection a las etiquetas de confidencialidad](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span><span class="sxs-lookup"><span data-stu-id="69450-152">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="69450-153">Ejemplo: clasificación para el RGPD</span><span class="sxs-lookup"><span data-stu-id="69450-153">Example: Classification for GDPR</span></span>

<span data-ttu-id="69450-154">Para obtener un esquema de clasificación de ejemplo que incluye datos personales para el RGPD, consulte [Diseño de un esquema de clasificación de datos personales](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="69450-154">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="69450-155">Pruébelo</span><span class="sxs-lookup"><span data-stu-id="69450-155">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="69450-157">Guía del entorno de pruebas: clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="69450-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="69450-158">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step2) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="69450-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="69450-159">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="69450-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="69450-160">Configurar una mayor seguridad para Office 365</span><span class="sxs-lookup"><span data-stu-id="69450-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

