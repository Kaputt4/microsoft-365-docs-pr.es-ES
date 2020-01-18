---
title: Configuración de la detección de privilegios de clientes de abogado en eDiscovery avanzado
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Use el modelo de detección de privilegios de cliente abogado para usar la detección de contenido privilegiado basada en el aprendizaje de la máquina al revisar el contenido en un caso de exhibición avanzada de documentos electrónicos.
ms.openlocfilehash: f4d5252a44183f5e2e38e4f4676c73d350befaf2
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233730"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="415ab-103">Configuración de la detección de privilegios de clientes de abogado en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="415ab-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="415ab-104">Uno de los aspectos más importantes y costosos de la fase de revisión de cualquier proceso de eDiscovery es la revisión de los documentos para obtener un contenido privilegiado.</span><span class="sxs-lookup"><span data-stu-id="415ab-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="415ab-105">La exhibición avanzada de documentos electrónicos proporciona detección de contenido privilegiado basada en aprendizaje automático para que este proceso sea más eficaz.</span><span class="sxs-lookup"><span data-stu-id="415ab-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="415ab-106">Esta característica se denomina *detección de privilegios de cliente de abogado*.</span><span class="sxs-lookup"><span data-stu-id="415ab-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="415ab-107">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="415ab-107">How does it work?</span></span>

<span data-ttu-id="415ab-108">Cuando se habilita la detección de privilegios de clientes de abogados, el modelo de detección de privilegios de cliente-cliente procesa todos los documentos de un conjunto de revisión cuando se [analizan los datos](analyzing-data-in-review-set.md) del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="415ab-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="415ab-109">El modelo busca dos cosas:</span><span class="sxs-lookup"><span data-stu-id="415ab-109">The model looks for two things:</span></span>

- <span data-ttu-id="415ab-110">Contenido privilegiado: el modelo usa el aprendizaje automático para determinar la probabilidad de que el documento incluya contenido que sea legal por naturaleza.</span><span class="sxs-lookup"><span data-stu-id="415ab-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="415ab-111">Participantes: como parte de la configuración de la detección de privilegios de clientes de abogados, tiene que enviar una lista de abogados para su organización.</span><span class="sxs-lookup"><span data-stu-id="415ab-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="415ab-112">A continuación, el modelo compara los participantes del documento con la lista de abogados para determinar si un documento tiene al menos un participante del abogado.</span><span class="sxs-lookup"><span data-stu-id="415ab-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="415ab-113">El modelo genera las siguientes tres propiedades para cada documento:</span><span class="sxs-lookup"><span data-stu-id="415ab-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="415ab-114">**AttorneyClientPrivilegeScore:** La probabilidad de que el documento tenga carácter legal; los valores de la puntuación están comprendidos entre **0** y **1**.</span><span class="sxs-lookup"><span data-stu-id="415ab-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="415ab-115">**HasAttorney:** Esta propiedad se establece en **true** si uno de los participantes del documento aparece en la lista de abogados; de lo contrario, el valor es **false**.</span><span class="sxs-lookup"><span data-stu-id="415ab-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="415ab-116">El valor también se establece en **false** si la organización no ha cargado una lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="415ab-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="415ab-117">**IsPrivilege:** Esta propiedad se establece en **true** si el valor de **AttorneyClientPrivilegeScore** está por encima del umbral *o* si el documento tiene un participante del abogado; de lo contrario, el valor se establece en **false**.</span><span class="sxs-lookup"><span data-stu-id="415ab-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="415ab-118">Estas propiedades (y sus valores correspondientes) se agregan a los metadatos de archivo de los documentos en un conjunto de revisión, como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="415ab-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Abogado-propiedades de privilegio de cliente mostradas en metadatos de archivo](media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="415ab-120">Estas tres propiedades también se pueden buscar dentro de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="415ab-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="415ab-121">Para obtener más información, consulte [consultar los datos de un conjunto de revisión](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="415ab-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="415ab-122">Configuración del modelo de detección de privilegios de clientes de abogados</span><span class="sxs-lookup"><span data-stu-id="415ab-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="415ab-123">Para habilitar el modelo de detección de privilegios de clientes de abogados, su organización debe activarlo y, a continuación, cargar una lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="415ab-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="415ab-124">Paso 1: activar la detección de privilegios de clientes de abogado</span><span class="sxs-lookup"><span data-stu-id="415ab-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="415ab-125">Una persona que sea administrador de eDiscovery en su organización (un miembro del subgrupo de administradores de eDiscovery en el grupo de roles de eDiscovery Manager) debe hacer que el modelo esté disponible en los casos de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="415ab-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="415ab-126">En el centro de seguridad & cumplimiento, vaya a **ediscovery > la exhibición avanzada**de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="415ab-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="415ab-127">En la Página principal de **EDiscovery avanzado** , en el icono **configuración** , haga clic en **configurar la configuración global de análisis**.</span><span class="sxs-lookup"><span data-stu-id="415ab-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Seleccione "configurar características experimentales"](media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="415ab-129">En la pestaña **configuración de Analytics** , seleccione **administrar el privilegio de cliente de abogado**.</span><span class="sxs-lookup"><span data-stu-id="415ab-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="415ab-130">En la página de control flotante de **privilegios de cliente** , use el botón de alternancia para activar la característica y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="415ab-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="415ab-131">Paso 2: cargar una lista de abogados (opcional)</span><span class="sxs-lookup"><span data-stu-id="415ab-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="415ab-132">Para sacar el máximo provecho del modelo de detección de privilegios de clientes de abogado y usar los resultados de la detección de **abogados** o **potencialmente privilegiados** que se describió anteriormente, le recomendamos que cargue una lista de direcciones de correo electrónico para los abogados y el personal legal que trabajan para su organización.</span><span class="sxs-lookup"><span data-stu-id="415ab-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="415ab-133">Para cargar una lista de abogados para su uso por parte del modelo de detección de privilegios de clientes de abogados:</span><span class="sxs-lookup"><span data-stu-id="415ab-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="415ab-134">Cree un archivo. csv (sin una fila de encabezado) y agregue la dirección de correo electrónico de cada persona apropiada en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="415ab-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="415ab-135">Guarde este archivo en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="415ab-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="415ab-136">En la Página principal de **EDiscovery avanzado** , en el icono **configuración** , seleccione **configurar características experimentales**y, a continuación, seleccione **administrar el privilegio de cliente de abogado**.</span><span class="sxs-lookup"><span data-stu-id="415ab-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="415ab-137">Se muestra la página de **privilegios abogado-Client** y se activa el botón de alternancia **detección de privilegios de clientes o abogados** .</span><span class="sxs-lookup"><span data-stu-id="415ab-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Abogado-página desplegable de privilegios de cliente](media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="415ab-139">Seleccione **examinar** y, a continuación, busque y seleccione el archivo. csv que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="415ab-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="415ab-140">Seleccione **Guardar** para cargar la lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="415ab-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="415ab-141">Usar el modelo de detección de privilegios de cliente de abogado</span><span class="sxs-lookup"><span data-stu-id="415ab-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="415ab-142">Siga los pasos descritos en esta sección para usar la detección de privilegios de clientes de abogados para documentos en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="415ab-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="415ab-143">Paso 1: crear un grupo de etiquetas inteligentes con un modelo de detección de privilegios de clientes de abogados</span><span class="sxs-lookup"><span data-stu-id="415ab-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="415ab-144">Una de las principales formas de ver los resultados de la detección de privilegios de clientes de abogados en el proceso de revisión consiste en usar un grupo de etiquetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="415ab-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="415ab-145">Un grupo de etiquetas inteligentes indica los resultados de la detección de privilegios de clientes de abogados y muestra los resultados en línea junto a las etiquetas en un grupo de etiquetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="415ab-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="415ab-146">Esto le permite identificar rápidamente los documentos potencialmente privilegiados durante la revisión del documento.</span><span class="sxs-lookup"><span data-stu-id="415ab-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="415ab-147">Además, también puede usar las etiquetas del grupo de etiquetas inteligentes para etiquetar los documentos como privilegiados o sin privilegios.</span><span class="sxs-lookup"><span data-stu-id="415ab-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="415ab-148">Para obtener más información acerca de las etiquetas inteligentes, consulte [configurar las etiquetas inteligentes en la exhibición avanzada de](smart-tags.md)documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="415ab-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="415ab-149">En el conjunto de revisiones que contiene los documentos que analizó en el paso 1, seleccione **administrar conjunto de revisiones** y, a continuación, seleccione **administrar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="415ab-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="415ab-150">En **etiquetas**, seleccione la opción desplegable junto a **Agregar grupo** y, a continuación, seleccione **Agregar grupo de etiquetas inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="415ab-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Seleccione "Agregar grupo de etiquetas inteligentes"](media/AeDCreateSmartTag.png)

3. <span data-ttu-id="415ab-152">En la página **Elija un modelo para la etiqueta inteligente** , elija **seleccionar** junto a **abogado-privilegio de cliente**.</span><span class="sxs-lookup"><span data-stu-id="415ab-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="415ab-153">Se muestra un grupo de etiquetas con el **privilegio abogado-Client** .</span><span class="sxs-lookup"><span data-stu-id="415ab-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="415ab-154">Contiene dos etiquetas secundarias denominadas **positivo** y **negativo**, que corresponden a los posibles resultados generados por el modelo.</span><span class="sxs-lookup"><span data-stu-id="415ab-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Grupo de etiquetas inteligentes abogado-privilegio de cliente](media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="415ab-156">Cambie el nombre del grupo de etiquetas y las etiquetas según corresponda para su revisión.</span><span class="sxs-lookup"><span data-stu-id="415ab-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="415ab-157">Por ejemplo, puede cambiar el nombre de **positivo** a **privilegiado** y de **negativo** a **no privilegiado**.</span><span class="sxs-lookup"><span data-stu-id="415ab-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="415ab-158">Paso 2: analizar un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="415ab-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="415ab-159">Al analizar los documentos de un conjunto de revisiones, también se ejecutará el modelo de detección de privilegios de clientes de abogados y las propiedades correspondientes (que se describen en [¿Cómo funciona?](#how-does-it-work) se agregarán a todos los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="415ab-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="415ab-160">Para obtener más información acerca del análisis de datos en el conjunto de revisiones, consulte [analizar datos en un conjunto de revisión en EDiscovery avanzado](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="415ab-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="415ab-161">Paso 3: usar el grupo de etiquetas inteligentes para revisar el contenido privilegiado</span><span class="sxs-lookup"><span data-stu-id="415ab-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="415ab-162">Después de analizar el conjunto de revisión y configurar las etiquetas inteligentes, el siguiente paso es revisar los documentos.</span><span class="sxs-lookup"><span data-stu-id="415ab-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="415ab-163">Si el modelo ha determinado que el documento tiene potencialmente privilegios, la etiqueta inteligente correspondiente en el **Panel de etiquetado** indicará los siguientes resultados generados por la detección de privilegios de cliente abogado:</span><span class="sxs-lookup"><span data-stu-id="415ab-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="415ab-164">Si el documento tiene contenido que puede ser legal por naturaleza, el **contenido legal** de la etiqueta se muestra junto a la etiqueta inteligente correspondiente (que, en este caso, es la etiqueta **positiva** predeterminada).</span><span class="sxs-lookup"><span data-stu-id="415ab-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="415ab-165">Si el documento tiene un participante que se encuentra en la lista de abogados de la organización, el **abogado** se muestra junto a la etiqueta inteligente correspondiente (que, en este caso, también es la etiqueta **positiva** predeterminada).</span><span class="sxs-lookup"><span data-stu-id="415ab-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="415ab-166">Si el documento tiene contenido que puede ser legal por naturaleza *y* se ha encontrado un participante en la lista de abogados, se muestran las etiquetas de **contenido legal** y **abogados** .</span><span class="sxs-lookup"><span data-stu-id="415ab-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="415ab-167">Si el modelo determina que un documento no tiene contenido legal por naturaleza o que no contiene un participante de la lista de abogados, no se muestra ninguna etiqueta en el panel de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="415ab-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="415ab-168">Por ejemplo, en las siguientes capturas de pantallas se muestran dos documentos.</span><span class="sxs-lookup"><span data-stu-id="415ab-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="415ab-169">El primero incluye contenido que es legal por naturaleza y tiene un participante en la lista de abogados.</span><span class="sxs-lookup"><span data-stu-id="415ab-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="415ab-170">La segunda contiene ninguno y, por lo tanto, no muestra ninguna etiqueta.</span><span class="sxs-lookup"><span data-stu-id="415ab-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Documento con etiquetas de abogados y contenido legal](media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sin etiquetas](media/AeDTaggingPanelNegative.png)

<span data-ttu-id="415ab-173">Después de revisar un documento para ver si contiene contenido privilegiado, puede etiquetar el documento con la etiqueta adecuada.</span><span class="sxs-lookup"><span data-stu-id="415ab-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
