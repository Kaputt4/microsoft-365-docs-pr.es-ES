---
title: Aplicar automáticamente una etiqueta de confidencialidad al contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Al crear una etiqueta de confidencialidad, puede asignar automáticamente una etiqueta a un documento o correo electrónico, o bien puede pedir a los usuarios que seleccionen la etiqueta recomendada.
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277217"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="88f3a-103">Aplicar automáticamente una etiqueta de confidencialidad al contenido</span><span class="sxs-lookup"><span data-stu-id="88f3a-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="88f3a-104">Al crear una etiqueta de confidencialidad, puede asignar automáticamente esa etiqueta a contenido con información confidencial, o bien puede solicitar a los usuarios que apliquen la etiqueta recomendada.</span><span class="sxs-lookup"><span data-stu-id="88f3a-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="88f3a-105">La capacidad de aplicar automáticamente etiquetas de confidencialidad al contenido es importante por estos motivos:</span><span class="sxs-lookup"><span data-stu-id="88f3a-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="88f3a-106">No es necesario proporcionar aprendizaje a los usuarios para que conozcan todas las clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="88f3a-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="88f3a-107">No es necesario depender de los usuarios para clasificar todo el contenido correctamente.</span><span class="sxs-lookup"><span data-stu-id="88f3a-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="88f3a-108">Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.</span><span class="sxs-lookup"><span data-stu-id="88f3a-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="88f3a-109">El etiquetado automático en las aplicaciones de Office para Windows es compatible con el cliente de etiquetado unificado de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="88f3a-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="88f3a-110">Para las etiquetas integradas en las aplicaciones de Office, esta funcionalidad está [en versión preliminar para algunas aplicaciones](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="88f3a-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="88f3a-111">La configuración de autoetiquetado para las aplicaciones de Office está disponible cuando [crea o edita una etiqueta de confidencial](create-sensitivity-labels.md):</span><span class="sxs-lookup"><span data-stu-id="88f3a-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![Opciones de etiquetado automático para etiquetas de confidencialidad](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="88f3a-113">Cómo configurar el etiquetado automático para las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="88f3a-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="88f3a-114">Una de las características más eficaces de las etiquetas de confidencialidad es la capacidad de aplicarlas automáticamente al contenido que coincide con determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="88f3a-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="88f3a-115">En este caso, no es necesario que las personas de la organización apliquen las etiquetas de confidencialidad: Office 365 realiza el trabajo por ellos.</span><span class="sxs-lookup"><span data-stu-id="88f3a-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="88f3a-116">Puede optar por aplicar las etiquetas de confidencial al contenido automáticamente cuando el contenido contenga determinados tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="88f3a-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="88f3a-117">Elija una opción de la lista de tipos de información confidencial o clasificadores:</span><span class="sxs-lookup"><span data-stu-id="88f3a-117">Choose from a list of sensitive info types or classifers:</span></span>

![Condiciones de etiquetas para el etiquetado automático en las aplicaciones de Office](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="88f3a-119">Actualmente, la opción de **Clasificadores** está en versión preliminar limitada y requiere que el usuario envíe un formulario a Microsoft para habilitar esta función para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="88f3a-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="88f3a-120">Para obtener más información, consulte la entrada del blog que [anuncia el etiquetado automático en las aplicaciones de Office mediante el uso de clasificadores integrados: versión preliminar limitada](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span><span class="sxs-lookup"><span data-stu-id="88f3a-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="88f3a-121">Cuando esta etiqueta de confidencialidad se aplica automáticamente, el usuario ve una notificación en su aplicación de Office.</span><span class="sxs-lookup"><span data-stu-id="88f3a-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="88f3a-122">Pueden elegir **Aceptar** para descartar la notificación.</span><span class="sxs-lookup"><span data-stu-id="88f3a-122">They can choose **OK** to dismiss the notification.</span></span>

![Notificar que un documento tiene una etiqueta aplicada automáticamente](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="88f3a-124">Configuración de tipos de información confidencial para una etiqueta</span><span class="sxs-lookup"><span data-stu-id="88f3a-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="88f3a-125">Si selecciona la opción **tipos de información confidencial**, verá la misma lista de tipos de información confidencial que cuando crea una directiva de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="88f3a-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="88f3a-126">Por ejemplo, puede aplicar automáticamente una etiqueta de altamente confidencial a cualquier contenido que incluya información de identificación personal (PII) de los clientes, como números de tarjeta de crédito o números de la seguridad social:</span><span class="sxs-lookup"><span data-stu-id="88f3a-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Tipos de información confidencial para etiquetado automático en las aplicaciones de Office](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="88f3a-128">Después de seleccionar los tipos de información confidencial, puede restringir la condición al cambiar el recuento de instancias o la precisión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="88f3a-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="88f3a-129">Para obtener más información, vea [Ajustar reglas para hacer más fácil o más difícil la coincidencia](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="88f3a-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="88f3a-130">Además, puede elegir si una condición debe detectar todos los tipos de información confidencial o solo uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="88f3a-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="88f3a-131">Y para hacer que las condiciones sean más flexibles o complejas, puede agregar grupos y usar operadores lógicos entre los grupos.</span><span class="sxs-lookup"><span data-stu-id="88f3a-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="88f3a-132">Para obtener más información, vea [Operadores lógicos y de agrupación](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="88f3a-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![Opciones de precisión de coincidencia y recuento de instancias](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="88f3a-134">Configuración de clasificadores para una etiqueta</span><span class="sxs-lookup"><span data-stu-id="88f3a-134">Configuring classifers for a label</span></span>

<span data-ttu-id="88f3a-135">Si selecciona la opción **Clasificadores**, seleccione uno o más de los clasificadores predefinidos:</span><span class="sxs-lookup"><span data-stu-id="88f3a-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![Opciones de clasificadores y etiquetas de confidencialidad](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="88f3a-137">Para obtener más información sobre estos clasificadores, consulte [Introducción al entrenamiento de clasificadores (vista previa)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="88f3a-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="88f3a-138">Durante el período de versión preliminar, las siguientes aplicaciones son compatibles con clasificadores para las etiquetas de confidencial:</span><span class="sxs-lookup"><span data-stu-id="88f3a-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="88f3a-139">Las aplicaciones de escritorio de Office 365 ProPlus para Windows, de [Office Insider](https://office.com/insider):</span><span class="sxs-lookup"><span data-stu-id="88f3a-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="88f3a-140">Word</span><span class="sxs-lookup"><span data-stu-id="88f3a-140">Word</span></span>
    - <span data-ttu-id="88f3a-141">Excel</span><span class="sxs-lookup"><span data-stu-id="88f3a-141">Excel</span></span>
    - <span data-ttu-id="88f3a-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="88f3a-142">PowerPoint</span></span>

- <span data-ttu-id="88f3a-143">Aplicaciones de Office para la web, si ha [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (versión preliminar pública)](sensitivity-labels-sharepoint-onedrive-files.md):</span><span class="sxs-lookup"><span data-stu-id="88f3a-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="88f3a-144">Word</span><span class="sxs-lookup"><span data-stu-id="88f3a-144">Word</span></span>
    - <span data-ttu-id="88f3a-145">Excel</span><span class="sxs-lookup"><span data-stu-id="88f3a-145">Excel</span></span>
    - <span data-ttu-id="88f3a-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="88f3a-146">PowerPoint</span></span>
    - <span data-ttu-id="88f3a-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="88f3a-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="88f3a-148">Recomendación para que el usuario aplique una etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="88f3a-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="88f3a-149">Si lo prefiere, puede recomendar a los usuarios que apliquen la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="88f3a-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="88f3a-150">Con esta opción, los usuarios pueden aceptar la clasificación y cualquier protección asociada, o descartar la recomendación si la etiqueta no es adecuada para su contenido.</span><span class="sxs-lookup"><span data-stu-id="88f3a-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

<span data-ttu-id="88f3a-151">Las etiquetas recomendadas son compatibles con Word, PowerPoint y Excel.</span><span class="sxs-lookup"><span data-stu-id="88f3a-151">Recommended labels are supported for Word, PowerPoint, and Excel.</span></span>

![Opción para recomendar una etiqueta de confidencialidad a los usuarios](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="88f3a-p110">Este es un ejemplo de un mensaje que se muestra al configurar una condición para aplicar una etiqueta como acción recomendada con una sugerencia de directiva personalizada. Puede elegir el texto que se muestra en la sugerencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="88f3a-p110">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Mensaje para aplicar una etiqueta recomendada](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="88f3a-156">Forma de aplicar etiquetas recomendadas o automáticas</span><span class="sxs-lookup"><span data-stu-id="88f3a-156">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="88f3a-157">El etiquetado automático se aplica a Word, Excel y PowerPoint al guardar un documento, y a Outlook al enviar un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="88f3a-157">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="88f3a-158">Estas condiciones detectan información confidencial en el texto de cuerpo de los documentos y correos electrónicos, y en los encabezados y pies de página, pero no en la línea de asunto o los datos adjuntos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="88f3a-158">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="88f3a-159">No puede usar el etiquetado automático para documentos y mensajes de correo electrónico que se etiquetaron previamente de forma manual o de forma automática con una confidencialidad más alta.</span><span class="sxs-lookup"><span data-stu-id="88f3a-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="88f3a-160">Recuerde, solo se puede aplicar una etiqueta de confidencialidad a un documento o correo electrónico, (además de una sola etiqueta de retención).</span><span class="sxs-lookup"><span data-stu-id="88f3a-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="88f3a-161">El etiquetado recomendado se aplica a Word, Excel y PowerPoint al guardar documentos.</span><span class="sxs-lookup"><span data-stu-id="88f3a-161">Recommended labeling applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="88f3a-162">No puede usar el etiquetado recomendado para documentos que anteriormente se etiquetaron con una confidencialidad más alta.</span><span class="sxs-lookup"><span data-stu-id="88f3a-162">You can't use recommended labeling for documents that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="88f3a-163">Cuando el contenido ya está etiquetado con una confidencialidad más alta, el usuario no verá el mensaje con la recomendación y la sugerencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="88f3a-163">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="88f3a-164">Forma en que se evalúan varias condiciones cuando se aplican en más de una etiqueta</span><span class="sxs-lookup"><span data-stu-id="88f3a-164">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="88f3a-p114">Las etiquetas se ordenan para su evaluación según la posición que especifique en la directiva: la primera etiqueta colocada tiene la posición inferior (menor confidencialidad) y la última etiqueta colocada tiene la posición superior (mayor confidencialidad). Para obtener más información sobre la prioridad, vea [Prioridad de etiqueta (el orden importa)](sensitivity-labels.md#label-priority-order-matters).</span><span class="sxs-lookup"><span data-stu-id="88f3a-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="88f3a-167">No configure una etiqueta principal para que se aplique o recomiende automáticamente</span><span class="sxs-lookup"><span data-stu-id="88f3a-167">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="88f3a-168">Recuerde, no se puede aplicar una etiqueta principal (una etiqueta con subetiquetas) al contenido.</span><span class="sxs-lookup"><span data-stu-id="88f3a-168">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="88f3a-169">Asegúrese de no configurar una etiqueta principal para que se aplique o recomiende automáticamente, ya que la etiqueta principal no se aplicará al contenido en las aplicaciones de Office que usan el cliente de etiquetado unificado de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="88f3a-169">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="88f3a-170">Para obtener más información sobre las etiquetas principales y las subetiquetas, consulte [Subetiquetas (agrupación de etiquetas)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="88f3a-170">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
