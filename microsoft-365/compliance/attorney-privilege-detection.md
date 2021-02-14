---
title: Configurar la detección de privilegios abogado-cliente en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el modelo de detección de privilegios abogado-cliente para usar la detección basada en aprendizaje automático del contenido con privilegios al revisar el contenido en un caso de eDiscovery avanzado.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358046"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="64de5-103">Configurar la detección de privilegios abogado-cliente en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="64de5-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="64de5-104">Un aspecto importante y costoso de la fase de revisión de cualquier proceso de exhibición de documentos electrónicos es la revisión de documentos para obtener contenido con privilegios.</span><span class="sxs-lookup"><span data-stu-id="64de5-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="64de5-105">EDiscovery avanzado proporciona detección basada en aprendizaje automático de contenido con privilegios para que este proceso sea más eficaz.</span><span class="sxs-lookup"><span data-stu-id="64de5-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="64de5-106">Esta característica se denomina *detección de privilegios abogado-cliente.*</span><span class="sxs-lookup"><span data-stu-id="64de5-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="64de5-107">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="64de5-107">How does it work?</span></span>

<span data-ttu-id="64de5-108">Cuando se habilita la detección de privilegios abogado-cliente, el modelo de detección [](analyzing-data-in-review-set.md) de privilegios abogado-cliente procesará todos los documentos de un conjunto de revisión al analizar los datos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="64de5-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="64de5-109">El modelo busca dos cosas:</span><span class="sxs-lookup"><span data-stu-id="64de5-109">The model looks for two things:</span></span>

- <span data-ttu-id="64de5-110">Contenido con privilegios: el modelo usa aprendizaje automático para determinar la probabilidad de que el documento contenga contenido de naturaleza legal.</span><span class="sxs-lookup"><span data-stu-id="64de5-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="64de5-111">Participantes: como parte de la configuración de la detección de privilegios abogado-cliente, debe enviar una lista de abogados para su organización.</span><span class="sxs-lookup"><span data-stu-id="64de5-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="64de5-112">A continuación, el modelo compara los participantes del documento con la lista de abogados para determinar si un documento tiene al menos un abogado participante.</span><span class="sxs-lookup"><span data-stu-id="64de5-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="64de5-113">El modelo genera las tres propiedades siguientes para cada documento:</span><span class="sxs-lookup"><span data-stu-id="64de5-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="64de5-114">**AttorneyClientPrivilegeScore:** La probabilidad de que el documento sea legal por naturaleza; los valores de la puntuación están entre **0** y **1**.</span><span class="sxs-lookup"><span data-stu-id="64de5-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="64de5-115">**HasAttorney:** Esta propiedad se establece en **true si** uno de los participantes del documento aparece en la lista de abogados; de lo contrario, el valor es **false**.</span><span class="sxs-lookup"><span data-stu-id="64de5-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="64de5-116">El valor también se establece en **false** si su organización no ha cargado una lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="64de5-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="64de5-117">**IsPrivilege:** Esta propiedad se establece en **true** si el valor de  **AttorneyClientPrivilegeScore** está por encima del umbral o si el documento tiene un abogado participante; de lo contrario, el valor se establece en **false**.</span><span class="sxs-lookup"><span data-stu-id="64de5-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="64de5-118">Estas propiedades (y sus valores correspondientes) se agregan a los metadatos de archivo de los documentos en un conjunto de revisión, como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="64de5-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Propiedades de privilegios abogado-cliente que se muestran en metadatos de archivo](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="64de5-120">Estas tres propiedades también se pueden buscar dentro de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="64de5-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="64de5-121">Para obtener más información, [vea Consultar los datos de un conjunto de revisión.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="64de5-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="64de5-122">Configurar el modelo de detección de privilegios abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="64de5-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="64de5-123">Para habilitar el modelo de detección de privilegios abogado-cliente, su organización debe activarlo y, a continuación, cargar una lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="64de5-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="64de5-124">Paso 1: Activar la detección de privilegios abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="64de5-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="64de5-125">Una persona que sea administrador de exhibición de documentos electrónicos en su organización (miembro del subgrupo administrador de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos) debe hacer que el modelo esté disponible en los casos de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="64de5-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="64de5-126">En el Centro de & cumplimiento, vaya a **eDiscovery > eDiscovery avanzado.**</span><span class="sxs-lookup"><span data-stu-id="64de5-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="64de5-127">En la **página principal de eDiscovery** avanzado, en **el** icono Configuración, haga clic **en Configurar la configuración de análisis global.**</span><span class="sxs-lookup"><span data-stu-id="64de5-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Seleccione "Configurar características experimentales"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="64de5-129">En la **pestaña Configuración de Análisis,** seleccione **Administrar la configuración de privilegios abogado-cliente.**</span><span class="sxs-lookup"><span data-stu-id="64de5-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="64de5-130">En la **página desplegable de privilegios abogado-cliente,** use el botón de alternancia para activar la característica y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="64de5-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="64de5-131">Paso 2: Cargar una lista de abogados (opcional)</span><span class="sxs-lookup"><span data-stu-id="64de5-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="64de5-132">Para aprovechar al máximo el modelo de detección de privilegios abogado-cliente y usar los resultados de la detección de Has **Attorney** o **Potentially Privileged** que se describió anteriormente, le recomendamos que cargue una lista de direcciones de correo electrónico para los abogados y el personal legal que trabajan para su organización.</span><span class="sxs-lookup"><span data-stu-id="64de5-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="64de5-133">Para cargar una lista de abogados para que la use el modelo de detección de privilegios abogado-cliente:</span><span class="sxs-lookup"><span data-stu-id="64de5-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="64de5-134">Cree un archivo .csv (sin una fila de encabezado) y agregue la dirección de correo electrónico para cada persona adecuada en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="64de5-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="64de5-135">Guarde este archivo en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="64de5-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="64de5-136">En la **página principal de eDiscovery** avanzado, en el icono Configuración, seleccione Configurar características **experimentales** y, a continuación, seleccione Administrar la configuración de **privilegios abogado-cliente.** </span><span class="sxs-lookup"><span data-stu-id="64de5-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="64de5-137">Se **muestra la página de** privilegios abogado-cliente y se activa el botón de alternancia de detección de privilegios **abogado-cliente.**</span><span class="sxs-lookup"><span data-stu-id="64de5-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Página desplegable de privilegios abogado-cliente](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="64de5-139">Seleccione **Examinar** y, a continuación, busque y seleccione el archivo .csv que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="64de5-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="64de5-140">Seleccione **Guardar para** cargar la lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="64de5-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="64de5-141">Usar el modelo de detección de privilegios abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="64de5-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="64de5-142">Siga los pasos de esta sección para usar la detección de privilegios abogado-cliente para los documentos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="64de5-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="64de5-143">Paso 1: Crear un grupo de etiquetas inteligentes con el modelo de detección de privilegios abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="64de5-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="64de5-144">Una de las formas principales de ver los resultados de la detección de privilegios abogado-cliente en el proceso de revisión es mediante el uso de un grupo de etiquetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="64de5-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="64de5-145">Un grupo de etiquetas inteligentes indica los resultados de la detección de privilegios abogado-cliente y muestra los resultados en línea junto a las etiquetas de un grupo de etiquetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="64de5-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="64de5-146">Esto le permite identificar rápidamente documentos con privilegios potenciales durante la revisión del documento.</span><span class="sxs-lookup"><span data-stu-id="64de5-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="64de5-147">Además, también puede usar las etiquetas del grupo de etiquetas inteligentes para etiquetar documentos como con privilegios o sin privilegios.</span><span class="sxs-lookup"><span data-stu-id="64de5-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="64de5-148">Para obtener más información acerca de las etiquetas inteligentes, vea [Configurar etiquetas inteligentes en eDiscovery avanzado.](smart-tags.md)</span><span class="sxs-lookup"><span data-stu-id="64de5-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="64de5-149">En el conjunto de revisión que contiene los documentos  que ha analizado en el paso 1, seleccione Administrar conjunto de revisión y, a continuación, **seleccione Administrar etiquetas.**</span><span class="sxs-lookup"><span data-stu-id="64de5-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="64de5-150">En **Etiquetas,** seleccione el menú desplegable junto **a Agregar** grupo y, a continuación, seleccione Agregar grupo de **etiquetas inteligentes.**</span><span class="sxs-lookup"><span data-stu-id="64de5-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Seleccione "Agregar grupo de etiquetas inteligentes"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="64de5-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span><span class="sxs-lookup"><span data-stu-id="64de5-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="64de5-153">Se muestra un grupo de etiquetas denominado **Privilegio abogado-cliente.**</span><span class="sxs-lookup"><span data-stu-id="64de5-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="64de5-154">Contiene dos etiquetas secundarias **denominadas Positive** y **Negative**, que corresponden a los posibles resultados producidos por el modelo.</span><span class="sxs-lookup"><span data-stu-id="64de5-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Grupo de etiquetas inteligentes con privilegios abogado-cliente](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="64de5-156">Cambie el nombre del grupo de etiquetas y las etiquetas según corresponda para su revisión.</span><span class="sxs-lookup"><span data-stu-id="64de5-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="64de5-157">Por ejemplo, puede cambiar el nombre **De positivo** a **Privilegiado** y **Negativo** a **No privilegiado.**</span><span class="sxs-lookup"><span data-stu-id="64de5-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="64de5-158">Paso 2: Analizar un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="64de5-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="64de5-159">Al analizar los documentos de un conjunto de revisión, también se ejecutará el modelo de detección de privilegios abogado-cliente y se agregarán las propiedades correspondientes (que se describen en Cómo [funciona?](#how-does-it-work) a todos los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="64de5-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="64de5-160">Para obtener más información acerca del análisis de datos en el conjunto de revisión, vea Analizar datos en un [conjunto de revisión en eDiscovery avanzado.](analyzing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="64de5-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="64de5-161">Paso 3: Usar el grupo de etiquetas inteligentes para revisar el contenido con privilegios</span><span class="sxs-lookup"><span data-stu-id="64de5-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="64de5-162">Después de analizar el conjunto de revisión y configurar las etiquetas inteligentes, el siguiente paso es revisar los documentos.</span><span class="sxs-lookup"><span data-stu-id="64de5-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="64de5-163">Si el modelo ha determinado que el documento tiene privilegios potenciales, la etiqueta inteligente correspondiente en el **panel** de etiquetado indicará los siguientes resultados producidos por la detección de privilegios abogado-cliente:</span><span class="sxs-lookup"><span data-stu-id="64de5-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="64de5-164">Si el documento tiene contenido que puede ser legal, la etiqueta **Contenido** legal se muestra junto a la etiqueta inteligente correspondiente (que en este caso es la **etiqueta positiva** predeterminada).</span><span class="sxs-lookup"><span data-stu-id="64de5-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="64de5-165">Si el documento tiene un participante que se encuentra en la lista de abogados de su organización, la etiqueta **Abogado** se muestra junto a la etiqueta inteligente correspondiente (que en este caso también es la etiqueta **positiva** predeterminada).</span><span class="sxs-lookup"><span data-stu-id="64de5-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="64de5-166">Si el documento tiene contenido que puede ser legal y tiene un  participante  que se encuentra en la lista de abogados, se muestran tanto el contenido legal como las etiquetas de abogado. </span><span class="sxs-lookup"><span data-stu-id="64de5-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="64de5-167">Si el modelo determina que un documento no contiene contenido de naturaleza legal o que no contiene un participante de la lista de abogados, no se muestra ninguna etiqueta en el panel de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="64de5-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="64de5-168">Por ejemplo, las capturas de pantalla siguientes muestran dos documentos.</span><span class="sxs-lookup"><span data-stu-id="64de5-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="64de5-169">El primero contiene contenido de naturaleza legal y tiene un participante que se encuentra en la lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="64de5-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="64de5-170">El segundo no contiene ninguno y, por lo tanto, no muestra ninguna etiqueta.</span><span class="sxs-lookup"><span data-stu-id="64de5-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Documento con etiquetas de contenido abogado y jurídico](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sin etiquetas](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="64de5-173">Después de revisar un documento para ver si contiene contenido con privilegios, puede etiquetar el documento con la etiqueta adecuada.</span><span class="sxs-lookup"><span data-stu-id="64de5-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
