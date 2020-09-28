---
title: Tipos de explicación
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga más información sobre los tipos de explicación en Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295990"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="e5d4d-103">Introducción a los tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="e5d4d-103">Introduction to explanation types</span></span>

<span data-ttu-id="e5d4d-104">Use explicaciones para definir la información que desea etiquetar y extraiga en el documento los conceptos de comprensión de los modelos de Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="e5d4d-105">Al crear una explicación, asegúrese de seleccionar un tipo de explicación.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="e5d4d-106">Este artículo ayuda a comprender los diferentes tipos de explicación y cómo se usan.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![Tipos de explicación](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="e5d4d-108">Estos son los tipos de explicación disponibles:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-108">These explanation types are available:</span></span>

- <span data-ttu-id="e5d4d-109">**Lista de frases**: lista de palabras, frases, números u otros caracteres que se pueden usar en el documento o la información que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="e5d4d-110">Por ejemplo, la cadena de texto que **hace referencia al doctor** está en todos los documentos de referencia médica que está identificando.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="e5d4d-111">**Lista de patrones**: enumerar los patrones de números, letras u otros caracteres que puede usar para identificar la información que va a extraer.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="e5d4d-112">Por ejemplo, puede extraer el **número de teléfono** del médico de referencia de todos los documentos de referencia médica que va a identificar.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="e5d4d-113">**Proximidad**: describe cómo se explican las explicaciones de cierre.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="e5d4d-114">Por ejemplo, una lista de patrones de *números de calle* se coloca justo antes de la lista de frases con *nombre de calle* , sin tokens entre (obtendrá información sobre los tokens más adelante en este artículo).</span><span class="sxs-lookup"><span data-stu-id="e5d4d-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="e5d4d-115">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="e5d4d-115">Phrase list</span></span>

<span data-ttu-id="e5d4d-116">Un tipo de explicación de la lista de frases se suele usar para identificar y clasificar un documento a través del modelo.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="e5d4d-117">Como se describe en el ejemplo de la etiqueta *doctor de referencia* , es una cadena de palabras, frases, números o caracteres que se encuentran de forma coherente en los documentos que se identifican.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="e5d4d-118">Aunque no es un requisito, puede lograr un mejor éxito con su explicación si la frase que está capturando se encuentra en una ubicación coherente en el documento.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="e5d4d-119">Por ejemplo, la etiqueta de *médico de referencia* puede encontrarse de forma coherente en el primer párrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="e5d4d-120">Si la distinción entre mayúsculas y minúsculas es un requisito para identificar la etiqueta, al usar el tipo de lista de frases podrá especificarla en su explicación seleccionando la casilla de verificación **sólo mayúsculas exactas** .</span><span class="sxs-lookup"><span data-stu-id="e5d4d-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Distinción entre mayúsculas y minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="e5d4d-122">Listas de patrones</span><span class="sxs-lookup"><span data-stu-id="e5d4d-122">Pattern lists</span></span>

<span data-ttu-id="e5d4d-123">Un tipo de lista de patrones es especialmente útil cuando se crea una explicación que identifica y extrae información de un documento.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="e5d4d-124">Por lo general, se presenta en diferentes formatos, como fechas, números de teléfono o números de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="e5d4d-125">Por ejemplo, una fecha se puede mostrar en varios formatos diferentes (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 de enero de 2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="e5d4d-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="e5d4d-126">La definición de una lista de patrones hace que la explicación sea más eficaz al capturar cualquier variación posible en los datos que se intenta identificar y extraer.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="e5d4d-127">Para el ejemplo de **número de teléfono** , extraiga el número de teléfono de cada médico de referencia de todos los documentos de referencia médica que identifique el modelo.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="e5d4d-128">Al crear la explicación, seleccione el tipo de lista trama para permitir los diferentes formatos que puede espera que se devuelvan.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Lista de diseños de números de teléfono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="e5d4d-130">Para este ejemplo, active la casilla **cualquier dígito de 0-9** .</span><span class="sxs-lookup"><span data-stu-id="e5d4d-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="e5d4d-131">La selección de esta opción reconoce cada valor "0" que se usa en la lista de patrones para que sea cualquier dígito comprendido entre 0 y 9.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Cualquier dígito desde 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="e5d4d-133">De forma similar, si crea una lista de tramas que incluya caracteres de texto, active la casilla **cualquier letra de a-z** .</span><span class="sxs-lookup"><span data-stu-id="e5d4d-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="e5d4d-134">Al seleccionar esta opción, se reconoce cada carácter "a" usado en la lista de patrones para que sea cualquier carácter de "a" a "z".</span><span class="sxs-lookup"><span data-stu-id="e5d4d-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="e5d4d-135">Por ejemplo, si crea una lista de patrones de **fecha** y desea asegurarse de que se reconoce un formato de fecha como el *1 de enero de 2020* , debe:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="e5d4d-136">Agregue *AAA 0, 0000* y *AAA 00, 0000* a la lista de tramas.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="e5d4d-137">Asegúrese de que **cualquier letra de la a a la z** también está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Cualquier letra de la a a la z](../media/content-understanding/any-letter.png)

<span data-ttu-id="e5d4d-139">Además, si tiene requisitos de capitalización en la lista trama, tiene la opción de activar la casilla de verificación **sólo mayúsculas exactas** .</span><span class="sxs-lookup"><span data-stu-id="e5d4d-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="e5d4d-140">Para el ejemplo de la fecha, si necesita que la primera letra del mes esté en mayúsculas, debe:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="e5d4d-141">Agregue *AAA 0, 0000* y *AAA 00, 0000* a la lista de tramas.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="e5d4d-142">Asegúrese de que **solo se selecciona mayúsculas exactas** .</span><span class="sxs-lookup"><span data-stu-id="e5d4d-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Solo mayúsculas exactas](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="e5d4d-144">En lugar de crear manualmente una explicación de la lista de patrones, use la [biblioteca de explicación]() para usar plantillas de lista de patrones predefinidas para la lista de patrones comunes, como *fecha*, *número de teléfono*, número de *tarjeta de crédito*, etc.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="e5d4d-145">Proximidad</span><span class="sxs-lookup"><span data-stu-id="e5d4d-145">Proximity</span></span> 

<span data-ttu-id="e5d4d-146">El tipo de explicación de proximidad ayuda a que el modelo identifique los datos mediante la definición del modo en que se va a cerrar otro dato.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="e5d4d-147">Por ejemplo, en el modelo, ha definido dos explicaciones que etiquetan tanto el número de teléfono de la *calle* del cliente como el *número de teléfono*.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="e5d4d-148">También tiene en cuenta que los números de teléfono del cliente siempre aparecen antes del número de la dirección postal.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="e5d4d-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="e5d4d-149">Alex Wilburn</span></span><br>
<span data-ttu-id="e5d4d-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="e5d4d-150">555-555-5555</span></span><br>
<span data-ttu-id="e5d4d-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e5d4d-151">One Microsoft Way</span></span><br>
<span data-ttu-id="e5d4d-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="e5d4d-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="e5d4d-153">Use la explicación de Proximity para definir la distancia a la que se explica el número de teléfono para identificar mejor el número de la calle en los documentos.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Explicación de proximidad](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="e5d4d-155">¿Qué son los tokens?</span><span class="sxs-lookup"><span data-stu-id="e5d4d-155">What are tokens?</span></span>

<span data-ttu-id="e5d4d-156">Para usar el tipo de explicación de proximidad, comprenda qué es un token, ya que el número de tokens es cómo la explicación de proximidad mide la distancia de una explicación a otra.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="e5d4d-157">Un token es un intervalo continuo (sin espacios ni signos de puntuación) de letras y números.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="e5d4d-158">Un espacio no es un token.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-158">A space is NOT a token.</span></span> <span data-ttu-id="e5d4d-159">Cada carácter de puntuación es un token.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-159">Each punctuation character is a token.</span></span> <span data-ttu-id="e5d4d-160">En la tabla siguiente se muestran algunos ejemplos de cómo determinar el número de tokens en una frase.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="e5d4d-161">Frase</span><span class="sxs-lookup"><span data-stu-id="e5d4d-161">Phrase</span></span>|<span data-ttu-id="e5d4d-162">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="e5d4d-162">Number of tokens</span></span>|<span data-ttu-id="e5d4d-163">Explicación</span><span class="sxs-lookup"><span data-stu-id="e5d4d-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="e5d4d-164">1 </span><span class="sxs-lookup"><span data-stu-id="e5d4d-164">1</span></span>|<span data-ttu-id="e5d4d-165">Una sola palabra sin signos de puntuación o espacios.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="e5d4d-166">1 </span><span class="sxs-lookup"><span data-stu-id="e5d4d-166">1</span></span>|<span data-ttu-id="e5d4d-167">Un número de localizador de registros.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-167">A record locator number.</span></span> <span data-ttu-id="e5d4d-168">Puede tener números y letras, pero no tiene ningún signo de puntuación.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="e5d4d-169">5 </span><span class="sxs-lookup"><span data-stu-id="e5d4d-169">5</span></span>|<span data-ttu-id="e5d4d-170">Un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-170">A phone number.</span></span> <span data-ttu-id="e5d4d-171">Cada signo de puntuación es un único token que  `425-555-5555` puede ser 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="e5d4d-172">7 </span><span class="sxs-lookup"><span data-stu-id="e5d4d-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="e5d4d-173">Configurar el tipo de explicación de proximidad</span><span class="sxs-lookup"><span data-stu-id="e5d4d-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="e5d4d-174">Para la muestra, configure el valor de Proximity para que podamos definir el intervalo del número de tokens que la explicación del *número de teléfono* proviene de la explicación del número de dirección de la *calle* .</span><span class="sxs-lookup"><span data-stu-id="e5d4d-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="e5d4d-175">Debe ver que el intervalo mínimo es "0", ya que no hay tokens entre el número de teléfono y el número de dirección postal.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="e5d4d-176">Sin embargo, algunos números de teléfono de los documentos de muestra se anexan *(móviles)*.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="e5d4d-177">Sergio Wilke</span><span class="sxs-lookup"><span data-stu-id="e5d4d-177">Nestor Wilke</span></span><br>
<span data-ttu-id="e5d4d-178">111-111-1111 (móvil)</span><span class="sxs-lookup"><span data-stu-id="e5d4d-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="e5d4d-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e5d4d-179">One Microsoft Way</span></span><br>
<span data-ttu-id="e5d4d-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="e5d4d-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="e5d4d-181">Hay tres tokens en *(móvil)*:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="e5d4d-182">Frase</span><span class="sxs-lookup"><span data-stu-id="e5d4d-182">Phrase</span></span>|<span data-ttu-id="e5d4d-183">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="e5d4d-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="e5d4d-184">(</span><span class="sxs-lookup"><span data-stu-id="e5d4d-184">(</span></span>|<span data-ttu-id="e5d4d-185">1 </span><span class="sxs-lookup"><span data-stu-id="e5d4d-185">1</span></span>|
|<span data-ttu-id="e5d4d-186">móviles</span><span class="sxs-lookup"><span data-stu-id="e5d4d-186">mobile</span></span>|<span data-ttu-id="e5d4d-187">2 </span><span class="sxs-lookup"><span data-stu-id="e5d4d-187">2</span></span>|
|<span data-ttu-id="e5d4d-188">)</span><span class="sxs-lookup"><span data-stu-id="e5d4d-188">)</span></span>|<span data-ttu-id="e5d4d-189">3 </span><span class="sxs-lookup"><span data-stu-id="e5d4d-189">3</span></span>|

<span data-ttu-id="e5d4d-190">Configure el valor de Proximity para que tenga un intervalo comprendido entre 0 y 3.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Ejemplo de proximidad](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="e5d4d-192">Usar la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="e5d4d-192">Use the explanation library</span></span>

<span data-ttu-id="e5d4d-193">Aunque puede Agregar de forma manual varios valores de la lista de patrones para la explicación, es mucho más fácil usar las plantillas creadas previamente que se proporcionan en la biblioteca de explicación.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="e5d4d-194">Por ejemplo, en lugar de agregar manualmente todas las variaciones de la *fecha*, use la plantilla de lista de patrones para *Date*, que ya incluye un número de valores de listas de patrones:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Biblioteca de explicación](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="e5d4d-196">La biblioteca de explicación incluye varias explicaciones de la lista de patrones que se usan con más frecuencia, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="e5d4d-197">Fecha</span><span class="sxs-lookup"><span data-stu-id="e5d4d-197">Date</span></span></br>
- <span data-ttu-id="e5d4d-198">Fecha (numérica)</span><span class="sxs-lookup"><span data-stu-id="e5d4d-198">Date (numeric)</span></span></br>
- <span data-ttu-id="e5d4d-199">Time</span><span class="sxs-lookup"><span data-stu-id="e5d4d-199">Time</span></span></br>
- <span data-ttu-id="e5d4d-200">Número</span><span class="sxs-lookup"><span data-stu-id="e5d4d-200">Number</span></span></br>
- <span data-ttu-id="e5d4d-201">Número de teléfono</span><span class="sxs-lookup"><span data-stu-id="e5d4d-201">Phone number</span></span></br>
- <span data-ttu-id="e5d4d-202">Código postal</span><span class="sxs-lookup"><span data-stu-id="e5d4d-202">Zip code</span></span></br>
- <span data-ttu-id="e5d4d-203">Primera palabra de la oración</span><span class="sxs-lookup"><span data-stu-id="e5d4d-203">First word of sentence</span></span></br>
- <span data-ttu-id="e5d4d-204">Tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="e5d4d-204">Credit card</span></span></br>
- <span data-ttu-id="e5d4d-205">Número de la seguridad social</span><span class="sxs-lookup"><span data-stu-id="e5d4d-205">Social security number</span></span></br>

<span data-ttu-id="e5d4d-206">Tenga en cuenta que la biblioteca de explicación también incluye plantillas para las explicaciones de la lista de frases, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e5d4d-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="e5d4d-207">Fin de la oración</span><span class="sxs-lookup"><span data-stu-id="e5d4d-207">End of sentence</span></span>
- <span data-ttu-id="e5d4d-208">Moneda</span><span class="sxs-lookup"><span data-stu-id="e5d4d-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="e5d4d-209">Para usar una plantilla de la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="e5d4d-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="e5d4d-210">En la sección **explicaciones** de la página **tren** de su modelo, seleccione **nuevo**y, a continuación, seleccione **desde una plantilla**.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Crear a partir de una plantilla](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="e5d4d-212">En la página **plantillas de explicación** , seleccione la explicación que desea usar y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Seleccionar una plantilla](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="e5d4d-214">La información de la plantilla seleccionada se mostrará en la página **crear una explicación** .</span><span class="sxs-lookup"><span data-stu-id="e5d4d-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="e5d4d-215">Si es necesario, edite el nombre de la explicación y agregue o quite los elementos de la lista trama.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Editar plantilla](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="e5d4d-217">Cuando termine, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e5d4d-217">When finished, select **Save**.</span></span>
