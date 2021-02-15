---
title: 'Modo de accesibilidad de SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Aprenda a usar el modo de accesibilidad al entrenar un modelo en SharePoint Syntex.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50081024"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="31cbd-103">Modo de accesibilidad de SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="31cbd-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="31cbd-104">En [SharePoint Syntex,](index.md)los usuarios pueden activar el modo de accesibilidad en todas las etapas de aprendizaje de modelos (etiqueta, aprendizaje, prueba) al trabajar con documentos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="31cbd-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="31cbd-105">El uso del modo de accesibilidad puede ayudar a los usuarios a tener una accesibilidad de teclado más fácil a medida que navegan y etiquetan elementos en el visor de documentos.</span><span class="sxs-lookup"><span data-stu-id="31cbd-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="31cbd-106">Esto ayuda a los usuarios a usar sus teclados para desplazarse por el texto del visor de documentos y escuchar una narración no solo de los valores seleccionados, sino también de acciones (como etiquetar o quitar etiquetas del texto seleccionado) o valores de etiquetas previstos mientras entrena el modelo con documentos de ejemplo adicionales.</span><span class="sxs-lookup"><span data-stu-id="31cbd-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Modo de accesibilidad](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="31cbd-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="31cbd-108">Requirements</span></span>

<span data-ttu-id="31cbd-109">Para escuchar el audio de la narración, asegúrate de activar la aplicación [Narrador](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) en la configuración del Narrador en el sistema Windows 10.</span><span class="sxs-lookup"><span data-stu-id="31cbd-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Activar narrador](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="31cbd-111">Etiquetado para usuarios de teclado</span><span class="sxs-lookup"><span data-stu-id="31cbd-111">Labeling for keyboard users</span></span>

<span data-ttu-id="31cbd-112">Para los usuarios de teclado que usan el modo de accesibilidad, si va a etiquetar texto en un documento de ejemplo en el visor, puede usar las siguientes teclas:</span><span class="sxs-lookup"><span data-stu-id="31cbd-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="31cbd-113">Pestaña: mueve hacia delante y selecciona la siguiente palabra.</span><span class="sxs-lookup"><span data-stu-id="31cbd-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="31cbd-114">Tab + Mayús: mueve hacia atrás y selecciona la palabra anterior.</span><span class="sxs-lookup"><span data-stu-id="31cbd-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="31cbd-115">Escriba: Etiqueta o quite una etiqueta de la palabra seleccionada.</span><span class="sxs-lookup"><span data-stu-id="31cbd-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="31cbd-116">Flecha hacia delante: mueve hacia delante los caracteres individuales de una palabra seleccionada.</span><span class="sxs-lookup"><span data-stu-id="31cbd-116">Forward arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="31cbd-117">Flecha hacia atrás: mueve hacia atrás los caracteres individuales de una palabra seleccionada.</span><span class="sxs-lookup"><span data-stu-id="31cbd-117">Backward arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="31cbd-118">Si va a etiquetar varias palabras para una sola etiqueta, debe etiquetar cada palabra.</span><span class="sxs-lookup"><span data-stu-id="31cbd-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="31cbd-119">Narración</span><span class="sxs-lookup"><span data-stu-id="31cbd-119">Narration</span></span>

<span data-ttu-id="31cbd-120">Para los usuarios del Narrador que usan el modo de accesibilidad, use la misma navegación por teclado descrita para que los usuarios de teclado pasen por el documento de ejemplo en el visor.</span><span class="sxs-lookup"><span data-stu-id="31cbd-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="31cbd-121">Al navegar por los documentos de ejemplo y etiquetar valores de cadena, Narrador le dará al usuario los siguientes mensajes de audio:</span><span class="sxs-lookup"><span data-stu-id="31cbd-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="31cbd-122">Cuando use el teclado para navegar por el visor de documentos, el audio del Narrador mostrará la cadena seleccionada.</span><span class="sxs-lookup"><span data-stu-id="31cbd-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="31cbd-123">Dentro de una cadena seleccionada, el audio del Narrador mostrará cada carácter de la cadena a medida que los selecciones mediante la flecha hacia delante o hacia atrás.</span><span class="sxs-lookup"><span data-stu-id="31cbd-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the forward or backward arrow.</span></span>
- <span data-ttu-id="31cbd-124">Si selecciona una cadena que se ha etiquetado, narrador mostrará el valor y, a continuación, "etiquetado".</span><span class="sxs-lookup"><span data-stu-id="31cbd-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="31cbd-125">Por ejemplo, si el valor de la etiqueta es "Contoso", el estado será "Costoso etiquetado".</span><span class="sxs-lookup"><span data-stu-id="31cbd-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="31cbd-126">En la pestaña de aprendizaje, si selecciona una cadena en el visor de documentos que solo se ha previsto, el audio del Narrador mostrará el valor y, a continuación, "previsto".</span><span class="sxs-lookup"><span data-stu-id="31cbd-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="31cbd-127">Esto ocurre cuando el aprendizaje predice un valor en el archivo que no coincide con lo que el usuario ha etiquetado.</span><span class="sxs-lookup"><span data-stu-id="31cbd-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="31cbd-128">En la pestaña de aprendizaje, si selecciona una cadena en el visor de documentos que se ha etiquetado y previsto, el audio del Narrador mostrará el valor y, a continuación, "etiquetado y previsto".</span><span class="sxs-lookup"><span data-stu-id="31cbd-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="31cbd-129">Esto ocurre cuando el aprendizaje se realiza correctamente y hay una coincidencia entre un valor previsto y la etiqueta de usuario.</span><span class="sxs-lookup"><span data-stu-id="31cbd-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="31cbd-130">Después de etiquetar una cadena o de quitar una etiqueta en el visor, el audio del Narrador te advertirá de que guardes los cambios antes de salir.</span><span class="sxs-lookup"><span data-stu-id="31cbd-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="31cbd-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31cbd-131">See Also</span></span>

[<span data-ttu-id="31cbd-132">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="31cbd-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="31cbd-133">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="31cbd-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



