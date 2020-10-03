---
title: Tipos de explicación
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Más información sobre los tipos de explicación en Microsoft SharePoint Syntex
ms.openlocfilehash: 7d78337fd91bc7e5a71bccd4867f019ae663417a
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321802"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="52146-103">Introducción a los tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="52146-103">Introduction to explanation types</span></span>

<span data-ttu-id="52146-104">Las explicaciones se utilizan para ayudar a definir la información que desea etiquetar y extraer en los modelos de comprensión de documentos en Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="52146-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="52146-105">Al crear una explicación, debe seleccionar un tipo de explicación.</span><span class="sxs-lookup"><span data-stu-id="52146-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="52146-106">Este artículo le ayudará a obtener más información sobre los distintos tipos de explicación y cómo se usan.</span><span class="sxs-lookup"><span data-stu-id="52146-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![Tipos de explicación](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="52146-108">Estos son los tipos de explicación disponibles:</span><span class="sxs-lookup"><span data-stu-id="52146-108">These explanation types are available:</span></span>

- <span data-ttu-id="52146-109">**Lista de frases**: lista de palabras, frases, números u otros caracteres que se pueden usar en el documento o la información que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="52146-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="52146-110">Por ejemplo, la cadena de texto: **el médico remitente** está en todos los documentos de referencia médica que está identificando.</span><span class="sxs-lookup"><span data-stu-id="52146-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="52146-111">\*\* Lista de patrones:\*\* enumera los modelos de números, letras u otros caracteres que se pueden utilizar para identificar la información que se está extrayendo.</span><span class="sxs-lookup"><span data-stu-id="52146-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="52146-112">Por ejemplo, puede extraer el **número de teléfono** del médico remitente de todos los documentos de referencia médica que está identificando.</span><span class="sxs-lookup"><span data-stu-id="52146-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="52146-113">**Proximidad:** Describe cómo se aproximan las explicaciones entre sí.</span><span class="sxs-lookup"><span data-stu-id="52146-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="52146-114">Por ejemplo, el *número de la calle* se mostrará justo antes de la lista de *nombre de la calle*, sin tokens entre ellas (aprenderá sobre los tokens más adelante en este artículo).</span><span class="sxs-lookup"><span data-stu-id="52146-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="52146-115">Usar el tipo de proximidad requiere que tenga al menos dos explicaciones en su modelo o la opción se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="52146-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="52146-116">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="52146-116">Phrase list</span></span>

<span data-ttu-id="52146-117">Un tipo de explicación de la lista de frases se usa normalmente para identificar y clasificar un documento a través del modelo.</span><span class="sxs-lookup"><span data-stu-id="52146-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="52146-118">Como se describe en el ejemplo de etiqueta *médico remitente*, se trata de una cadena de palabras, frases, números o caracteres que es coherente en los documentos que se están identificando.</span><span class="sxs-lookup"><span data-stu-id="52146-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="52146-119">Aunque no es un requisito, puede lograr un mejor éxito con su explicación si la frase que está registrando se encuentra en un lugar consistente en su documento.</span><span class="sxs-lookup"><span data-stu-id="52146-119">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="52146-120">Por ejemplo, es posible que la etiqueta*médico remitente* puede encontrarse sistemáticamente en el primer párrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="52146-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="52146-121">Si la distinción de mayúsculas y minúsculas es un requisito para identificar la etiqueta, usar el tipo Lista de frases le permite especificarla en la explicación si activa la casilla de verificación **Solo mayúsculas exactas**.</span><span class="sxs-lookup"><span data-stu-id="52146-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Distinción entre mayúsculas y minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="52146-123">Listas de patrones</span><span class="sxs-lookup"><span data-stu-id="52146-123">Pattern lists</span></span>

<span data-ttu-id="52146-124">Un tipo de lista de patrones es especialmente útil cuando se crea una explicación que identifica y extrae la información de un documento.</span><span class="sxs-lookup"><span data-stu-id="52146-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="52146-125">Por lo general, se presenta en diferentes formatos, como fechas, números de teléfono o números de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="52146-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="52146-126">Por ejemplo, una fecha puede ser mostrada en diferentes formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 de enero de 2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="52146-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="52146-127">Definir una lista de patrones hace que su explicación sea más eficiente al capturar cualquier posible variación en los datos que está tratando de identificar y extraer.</span><span class="sxs-lookup"><span data-stu-id="52146-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="52146-128">Para el ejemplo del **número de teléfono**, extraiga el número de teléfono de cada médico remitente de todos los documentos de remisión médica que el modelo identifica.</span><span class="sxs-lookup"><span data-stu-id="52146-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="52146-129">Cuando cree la explicación, seleccione el tipo Lista de patrones para permitir que se devuelvan los distintos formatos que esperaba.</span><span class="sxs-lookup"><span data-stu-id="52146-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Lista de patrones de números de teléfono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="52146-131">Para este ejemplo, active la casilla de verificación **Cualquier dígito entre 0-9**.</span><span class="sxs-lookup"><span data-stu-id="52146-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="52146-132">Si selecciona esta opción, el valor "0" que se usa en la lista de patrones se reconoce como cualquier dígito entre 0 y 9.</span><span class="sxs-lookup"><span data-stu-id="52146-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Cualquier dígito entre 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="52146-134">De forma similar, si crea una lista de patrones que incluya caracteres de texto, active la casilla de verificación **Cualquier letra de la a a la z**.</span><span class="sxs-lookup"><span data-stu-id="52146-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="52146-135">Al seleccionar esta opción se reconoce cada carácter "a" que se usa en la lista trama para que sea cualquier carácter entre "a" y "z".</span><span class="sxs-lookup"><span data-stu-id="52146-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="52146-136">Por ejemplo, si crea una lista de patrones**Fecha** y desea asegurarse de que un formato de fecha como *el 1 de enero de 2020* se reconozca, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="52146-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="52146-137">Agregar *aaa 0, 0000* y *aaa 00, 0000* a la lista de patrones</span><span class="sxs-lookup"><span data-stu-id="52146-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="52146-138">Asegúrese de que **Cualquier letra de la a a la z** también esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="52146-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Cualquier letra de la a a la z](../media/content-understanding/any-letter.png)

<span data-ttu-id="52146-140">Además, si tiene requisitos de usar mayúsculas y minúsculas en su lista de patrones, tiene la opción de seleccionar la casilla de verificación **Solo usar mayúsculas y minúsculas exactamente**.</span><span class="sxs-lookup"><span data-stu-id="52146-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="52146-141">En el ejemplo de la fecha, si necesita que la primera letra del mes se ponga en mayúsculas, deberá:</span><span class="sxs-lookup"><span data-stu-id="52146-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="52146-142">Agregar \*Aaa 0, 0000 \* y *Aaa 00, 0000* a la lista de patrones.</span><span class="sxs-lookup"><span data-stu-id="52146-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="52146-143">Asegúrese de que **Solo usar mayúsculas y minúsculas exactamente** también está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="52146-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Solo usar mayúsculas y minúsculas exactamente](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="52146-145">En lugar de crear manualmente una explicación de las listas de patrones, utilice la[biblioteca de explicación ]() para usar plantillas de listas de patrones predefinidas para las listas de patrones comunes, como *fecha*, *números de teléfono*, *número de tarjeta de crédito*, etc.</span><span class="sxs-lookup"><span data-stu-id="52146-145">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="52146-146">Proximidad</span><span class="sxs-lookup"><span data-stu-id="52146-146">Proximity</span></span> 

<span data-ttu-id="52146-147">El tipo explicación de la proximidad ayuda a que el modelo identifique los datos en la definición de cómo se cierra otro elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="52146-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="52146-148">Por ejemplo, en el modelo, ha definido dos explicaciones que etiquetan tanto el *Número de la dirección de la calle* como el *número de teléfono* del cliente.</span><span class="sxs-lookup"><span data-stu-id="52146-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="52146-149">También tiene en cuenta que los números de teléfono del cliente siempre aparecen antes que el número de la calle.</span><span class="sxs-lookup"><span data-stu-id="52146-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="52146-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="52146-150">Alex Wilburn</span></span><br>
<span data-ttu-id="52146-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="52146-151">555-555-5555</span></span><br>
<span data-ttu-id="52146-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="52146-152">One Microsoft Way</span></span><br>
<span data-ttu-id="52146-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="52146-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="52146-154">Use la explicación de proximidad para definir el número de teléfono que se debe desplazar para identificar mejor el número de la calle en los documentos.</span><span class="sxs-lookup"><span data-stu-id="52146-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Explicación de Proximidad](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="52146-156">¿Qué son los tokens?</span><span class="sxs-lookup"><span data-stu-id="52146-156">What are tokens?</span></span>

<span data-ttu-id="52146-157">Para poder usar el tipo de explicación de proximidad, entienda lo que es un token, ya que el número de tokens es cómo la explicación de la proximidad mide la distancia entre una explicación y otra.</span><span class="sxs-lookup"><span data-stu-id="52146-157">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="52146-158">Un token es un intervalo continuo (sin espacios ni signos de puntuación) de letras y números.</span><span class="sxs-lookup"><span data-stu-id="52146-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="52146-159">Un espacio NO es un token.</span><span class="sxs-lookup"><span data-stu-id="52146-159">A space is NOT a token.</span></span> <span data-ttu-id="52146-160">Cada signo de puntuación es un token.</span><span class="sxs-lookup"><span data-stu-id="52146-160">Each punctuation character is a token.</span></span> <span data-ttu-id="52146-161">En la siguiente tabla se muestran algunos ejemplos de cómo determinar el número de tokens en una frase.</span><span class="sxs-lookup"><span data-stu-id="52146-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="52146-162">Frase</span><span class="sxs-lookup"><span data-stu-id="52146-162">Phrase</span></span>|<span data-ttu-id="52146-163">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="52146-163">Number of tokens</span></span>|<span data-ttu-id="52146-164">Explicación</span><span class="sxs-lookup"><span data-stu-id="52146-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="52146-165">1</span><span class="sxs-lookup"><span data-stu-id="52146-165">1</span></span>|<span data-ttu-id="52146-166">Una sola palabra sin signos de puntuación o espacios.</span><span class="sxs-lookup"><span data-stu-id="52146-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="52146-167">1</span><span class="sxs-lookup"><span data-stu-id="52146-167">1</span></span>|<span data-ttu-id="52146-168">Un número de localizador de registros.</span><span class="sxs-lookup"><span data-stu-id="52146-168">A record locator number.</span></span> <span data-ttu-id="52146-169">Es posible que tenga números y letras, pero no tiene signos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="52146-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="52146-170">5</span><span class="sxs-lookup"><span data-stu-id="52146-170">5</span></span>|<span data-ttu-id="52146-171">Un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="52146-171">A phone number.</span></span> <span data-ttu-id="52146-172">Cada signo de puntuación es un token único, por lo que  `425-555-5555` serían 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="52146-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="52146-173">7</span><span class="sxs-lookup"><span data-stu-id="52146-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="52146-174">Configurar el tipo de explicación de proximidad</span><span class="sxs-lookup"><span data-stu-id="52146-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="52146-175">Para la muestra, configure el ajuste de proximidad de manera que podamos definir el rango del número de tokens que la explicación es del*número de teléfono*la explicación es del *número de la dirección de la calle*.</span><span class="sxs-lookup"><span data-stu-id="52146-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="52146-176">Debería ver que el intervalo mínimo es "0", ya que no hay ningún token entre el número de teléfono y el número de la dirección postal.</span><span class="sxs-lookup"><span data-stu-id="52146-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="52146-177">Sin embargo, algunos números de teléfono de los documentos de muestra se adjuntan con *(móvil)*.</span><span class="sxs-lookup"><span data-stu-id="52146-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="52146-178">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="52146-178">Nestor Wilke</span></span><br>
<span data-ttu-id="52146-179">111-111-1111 (móvil)</span><span class="sxs-lookup"><span data-stu-id="52146-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="52146-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="52146-180">One Microsoft Way</span></span><br>
<span data-ttu-id="52146-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="52146-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="52146-182">Hay tres tokens en *(móvil)*:</span><span class="sxs-lookup"><span data-stu-id="52146-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="52146-183">Frase</span><span class="sxs-lookup"><span data-stu-id="52146-183">Phrase</span></span>|<span data-ttu-id="52146-184">Cuenta de tokens</span><span class="sxs-lookup"><span data-stu-id="52146-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="52146-185">(</span><span class="sxs-lookup"><span data-stu-id="52146-185">(</span></span>|<span data-ttu-id="52146-186">1</span><span class="sxs-lookup"><span data-stu-id="52146-186">1</span></span>|
|<span data-ttu-id="52146-187">móvil</span><span class="sxs-lookup"><span data-stu-id="52146-187">mobile</span></span>|<span data-ttu-id="52146-188">2</span><span class="sxs-lookup"><span data-stu-id="52146-188">2</span></span>|
|<span data-ttu-id="52146-189">)</span><span class="sxs-lookup"><span data-stu-id="52146-189">)</span></span>|<span data-ttu-id="52146-190">3</span><span class="sxs-lookup"><span data-stu-id="52146-190">3</span></span>|

<span data-ttu-id="52146-191">Configure la opción de proximidad para tener un intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="52146-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Ejemplo, Proximity](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="52146-193">Usar plantillas de explicación</span><span class="sxs-lookup"><span data-stu-id="52146-193">Use explanation templates</span></span>

<span data-ttu-id="52146-194">Aunque se pueden agregar manualmente varios valores de la lista de patrones para la explicación, puede resultar mucho más fácil usar las plantillas creadas previamente que se le proporcionan en la biblioteca de explicación.</span><span class="sxs-lookup"><span data-stu-id="52146-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="52146-195">Por ejemplo, en lugar de añadir manualmente todas las variaciones para *Fecha*, se puede utilizar la plantilla de la lista de patrones para *Fecha*que ya incluye una serie de valores de la lista de patrones:</span><span class="sxs-lookup"><span data-stu-id="52146-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Biblioteca de explicación](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="52146-197">La biblioteca de explicación incluye varias explicaciones de la lista de patrones más utilizados, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="52146-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="52146-198">Fecha</span><span class="sxs-lookup"><span data-stu-id="52146-198">Date</span></span></br>
- <span data-ttu-id="52146-199">Fecha (numérica)</span><span class="sxs-lookup"><span data-stu-id="52146-199">Date (numeric)</span></span></br>
- <span data-ttu-id="52146-200">Hora</span><span class="sxs-lookup"><span data-stu-id="52146-200">Time</span></span></br>
- <span data-ttu-id="52146-201">Número</span><span class="sxs-lookup"><span data-stu-id="52146-201">Number</span></span></br>
- <span data-ttu-id="52146-202">Número de teléfono</span><span class="sxs-lookup"><span data-stu-id="52146-202">Phone number</span></span></br>
- <span data-ttu-id="52146-203">Código postal</span><span class="sxs-lookup"><span data-stu-id="52146-203">Zip code</span></span></br>
- <span data-ttu-id="52146-204">Primera palabra de la frase</span><span class="sxs-lookup"><span data-stu-id="52146-204">First word of sentence</span></span></br>
- <span data-ttu-id="52146-205">Tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="52146-205">Credit card</span></span></br>
- <span data-ttu-id="52146-206">Número de la seguridad social</span><span class="sxs-lookup"><span data-stu-id="52146-206">Social security number</span></span></br>

<span data-ttu-id="52146-207">Tenga en cuenta que la biblioteca de explicación también incluye plantillas para las explicaciones de la lista de frases, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="52146-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="52146-208">Final de la oración</span><span class="sxs-lookup"><span data-stu-id="52146-208">End of sentence</span></span>
- <span data-ttu-id="52146-209">Divisa</span><span class="sxs-lookup"><span data-stu-id="52146-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="52146-210">Para usar una plantilla de la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="52146-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="52146-211">En la sección de **Explicaciones** de la página de \*\* Entrenamiento **de su modelo, seleccione**Nuevo**, y luego seleccione**De Una Plantilla\*\*.</span><span class="sxs-lookup"><span data-stu-id="52146-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Crear desde plantilla](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="52146-213">En la página **plantillas de explicación**, seleccione la explicación que desee usar y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="52146-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Seleccionar una plantilla](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="52146-215">La información de la plantilla que ha seleccionado se mostrará en la página **crear una explicación**.</span><span class="sxs-lookup"><span data-stu-id="52146-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="52146-216">Si es necesario, edite el nombre de la explicación y agregue o elimine elementos de la lista de patrones.</span><span class="sxs-lookup"><span data-stu-id="52146-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Editar plantilla](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="52146-218">Cuando finalice, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="52146-218">When finished, select **Save**.</span></span>
