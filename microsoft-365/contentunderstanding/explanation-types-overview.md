---
title: Tipos de explicación
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Más información sobre los tipos de explicación en Microsoft SharePoint Syntex
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087648"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="0a8b8-103">Introducción a los tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="0a8b8-103">Introduction to explanation types</span></span>

<span data-ttu-id="0a8b8-104">Las explicaciones se utilizan para ayudar a definir la información que desea etiquetar y extraer en los modelos de comprensión de documentos en Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="0a8b8-105">Al crear una explicación, debe seleccionar un tipo de explicación.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="0a8b8-106">Este artículo le ayudará a comprender los distintos tipos de explicación y cómo se usan.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Tipos de explicación](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="0a8b8-108">Estos son los tipos de explicación disponibles:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-108">These explanation types are available:</span></span>

- <span data-ttu-id="0a8b8-109">**Lista de frases**: lista de palabras, frases, números u otros caracteres que se pueden usar en el documento o la información que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="0a8b8-110">Por ejemplo, la cadena de texto: **el médico remitente** está en todos los documentos de referencia médica que está identificando.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="0a8b8-111">**Lista de patrones:** enumera los modelos de números, letras u otros caracteres que se pueden utilizar para identificar la información que se está extrayendo.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="0a8b8-112">Por ejemplo, puede extraer el **número de teléfono** del médico remitente de todos los documentos de referencia médica que está identificando.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="0a8b8-113">**Proximidad:** Describe cómo se aproximan las explicaciones entre sí.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="0a8b8-114">Por ejemplo, el *número de la calle* se mostrará justo antes de la lista de *nombre de la calle*, sin tokens entre ellas (aprenderá sobre los tokens más adelante en este artículo).</span><span class="sxs-lookup"><span data-stu-id="0a8b8-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="0a8b8-115">Usar el tipo de proximidad requiere que tenga al menos dos explicaciones en su modelo o la opción se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="0a8b8-116">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="0a8b8-116">Phrase list</span></span>

<span data-ttu-id="0a8b8-117">Un tipo de explicación de la lista de frases se usa normalmente para identificar y clasificar un documento a través del modelo.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="0a8b8-118">Como se describe en el ejemplo de etiqueta *médico remitente*, se trata de una cadena de palabras, frases, números o caracteres que es coherente en los documentos que se están identificando.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="0a8b8-119">Aunque no es un requisito, puede lograr un mayor éxito con su explicación si la frase que está registrando se encuentra en un lugar consistente en su documento.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="0a8b8-120">Por ejemplo, puede que la etiqueta *médico remitente* se encuentre sistemáticamente en el primer párrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="0a8b8-121">Si la distinción de mayúsculas y minúsculas es un requisito para identificar la etiqueta, usar el tipo Lista de frases le permite especificarla en la explicación si activa la casilla de verificación **Solo mayúsculas exactas**.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Distinción entre mayúsculas y minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="0a8b8-123">Listas de patrones</span><span class="sxs-lookup"><span data-stu-id="0a8b8-123">Pattern lists</span></span>

<span data-ttu-id="0a8b8-124">Un tipo de lista de patrones es especialmente útil cuando se crea una explicación que identifica y extrae la información de un documento.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="0a8b8-125">Por lo general, se presenta en diferentes formatos, como fechas, números de teléfono o números de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="0a8b8-126">Por ejemplo, una fecha puede ser mostrada en diferentes formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 de enero de 2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="0a8b8-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="0a8b8-127">Definir una lista de patrones hace que su explicación sea más eficiente al capturar cualquier posible variación en los datos que está tratando de identificar y extraer.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="0a8b8-128">Para el ejemplo del **número de teléfono**, extraiga el número de teléfono de cada médico remitente de todos los documentos de remisión médica que el modelo identifica.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="0a8b8-129">Cuando cree la explicación, seleccione el tipo Lista de patrones para permitir que se devuelvan los distintos formatos que esperaba.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Lista de patrones de números de teléfono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="0a8b8-131">Para este ejemplo, active la casilla de verificación **Cualquier dígito entre 0-9** para reconocer cada valor "0" que se usa en la lista de patrones como un dígito entre 0 y 9.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Cualquier dígito entre 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="0a8b8-133">De forma similar, si crea una lista de patrones que incluya caracteres de texto, active la casilla de verificación **Cualquier letra de la a a la z** para reconocer cada carácter "a" que se use en la lista de patrones como un carácter entre "a" y "z".</span><span class="sxs-lookup"><span data-stu-id="0a8b8-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="0a8b8-134">Por ejemplo, si crea una lista de patrones **Fecha** y desea asegurarse de que un formato de fecha como *el 1 de enero de 2020* se reconozca, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="0a8b8-135">Agregar *aaa 0, 0000* y *aaa 00, 0000* a la lista de patrones</span><span class="sxs-lookup"><span data-stu-id="0a8b8-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="0a8b8-136">Asegúrese de que **Cualquier letra de la a a la z** también esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Cualquier letra de la a a la z](../media/content-understanding/any-letter.png)

<span data-ttu-id="0a8b8-138">Además, si tiene requisitos de usar mayúsculas y minúsculas en su lista de patrones, tiene la opción de seleccionar la casilla de verificación **Solo usar mayúsculas y minúsculas exactamente**.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="0a8b8-139">En el ejemplo de la fecha, si necesita que la primera letra del mes se ponga en mayúsculas, deberá:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="0a8b8-140">Agregar *Aaa 0, 0000* y *Aaa 00, 0000* a la lista de patrones.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="0a8b8-141">Asegúrese de que **Solo usar mayúsculas y minúsculas exactamente** también está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Solo usar mayúsculas y minúsculas exactamente](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="0a8b8-143">En lugar de crear manualmente una explicación de las listas de patrones, utilice la [Biblioteca de explicación](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar plantillas de listas de patrones para las listas de patrones comunes, como *fecha*, *números de teléfono*, *número de tarjeta de crédito*, etc.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="0a8b8-144">Proximidad</span><span class="sxs-lookup"><span data-stu-id="0a8b8-144">Proximity</span></span> 

<span data-ttu-id="0a8b8-145">El tipo de explicación de proximidad ayuda al modelo a identificar los datos definiendo la proximidad que otros datos tienen con estos.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="0a8b8-146">Por ejemplo, en su modelo ha definido dos explicaciones que etiquetan tanto el *Número de la dirección de la calle* como el *Número de teléfono* del cliente.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="0a8b8-147">Sabemos que los números de teléfono del cliente siempre aparecen antes que el número de la calle.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="0a8b8-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="0a8b8-148">Alex Wilburn</span></span><br>
<span data-ttu-id="0a8b8-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="0a8b8-149">555-555-5555</span></span><br>
<span data-ttu-id="0a8b8-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="0a8b8-150">One Microsoft Way</span></span><br>
<span data-ttu-id="0a8b8-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="0a8b8-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="0a8b8-152">Use la explicación de proximidad para definir el número de teléfono que se debe desplazar para identificar mejor el número de la calle en los documentos.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Explicación de Proximidad](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="0a8b8-154">¿Qué son los tokens?</span><span class="sxs-lookup"><span data-stu-id="0a8b8-154">What are tokens?</span></span>

<span data-ttu-id="0a8b8-155">Para poder usar el tipo de explicación de proximidad, necesita entender qué es un token, ya que la explicación de proximidad utiliza el número de tokens para medir la distancia entre una explicación y otra.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="0a8b8-156">Un token es un intervalo continuo (sin incluir espacios ni signos de puntuación) de letras y números.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="0a8b8-157">En la siguiente tabla se muestran algunos ejemplos de cómo determinar el número de tokens en una frase.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="0a8b8-158">Frase</span><span class="sxs-lookup"><span data-stu-id="0a8b8-158">Phrase</span></span>|<span data-ttu-id="0a8b8-159">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="0a8b8-159">Number of tokens</span></span>|<span data-ttu-id="0a8b8-160">Explicación</span><span class="sxs-lookup"><span data-stu-id="0a8b8-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="0a8b8-161">1</span><span class="sxs-lookup"><span data-stu-id="0a8b8-161">1</span></span>|<span data-ttu-id="0a8b8-162">Una sola palabra sin signos de puntuación o espacios.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="0a8b8-163">1</span><span class="sxs-lookup"><span data-stu-id="0a8b8-163">1</span></span>|<span data-ttu-id="0a8b8-164">Un número de localizador de registros.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-164">A record locator number.</span></span> <span data-ttu-id="0a8b8-165">Es posible que tenga números y letras, pero no tiene signos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="0a8b8-166">5</span><span class="sxs-lookup"><span data-stu-id="0a8b8-166">5</span></span>|<span data-ttu-id="0a8b8-167">Un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="0a8b8-167">A phone number.</span></span> <span data-ttu-id="0a8b8-168">Cada signo de puntuación es un token único, por lo que `425-555-5555` tiene 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="0a8b8-169">7</span><span class="sxs-lookup"><span data-stu-id="0a8b8-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="0a8b8-170">Configurar el tipo de explicación de proximidad</span><span class="sxs-lookup"><span data-stu-id="0a8b8-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="0a8b8-171">Para el ejemplo, configure el ajuste de proximidad de manera que podamos definir el rango del número de tokens en la explicación *Número de teléfono* a partir de la explicación *Número de la dirección de la calle*.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="0a8b8-172">Vea que el intervalo mínimo es "0", ya que no hay ningún token entre el número de teléfono y el número de la dirección postal.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="0a8b8-173">Sin embargo, algunos números de teléfono de los documentos de muestra incluyen *(móvil)* al final.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="0a8b8-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="0a8b8-174">Nestor Wilke</span></span><br>
<span data-ttu-id="0a8b8-175">111-111-1111 (móvil)</span><span class="sxs-lookup"><span data-stu-id="0a8b8-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="0a8b8-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="0a8b8-176">One Microsoft Way</span></span><br>
<span data-ttu-id="0a8b8-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="0a8b8-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="0a8b8-178">Hay tres tokens en *(móvil)*:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="0a8b8-179">Frase</span><span class="sxs-lookup"><span data-stu-id="0a8b8-179">Phrase</span></span>|<span data-ttu-id="0a8b8-180">Cuenta de tokens</span><span class="sxs-lookup"><span data-stu-id="0a8b8-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="0a8b8-181">(</span><span class="sxs-lookup"><span data-stu-id="0a8b8-181">(</span></span>|<span data-ttu-id="0a8b8-182">1</span><span class="sxs-lookup"><span data-stu-id="0a8b8-182">1</span></span>|
|<span data-ttu-id="0a8b8-183">móvil</span><span class="sxs-lookup"><span data-stu-id="0a8b8-183">mobile</span></span>|<span data-ttu-id="0a8b8-184">2</span><span class="sxs-lookup"><span data-stu-id="0a8b8-184">2</span></span>|
|<span data-ttu-id="0a8b8-185">)</span><span class="sxs-lookup"><span data-stu-id="0a8b8-185">)</span></span>|<span data-ttu-id="0a8b8-186">3</span><span class="sxs-lookup"><span data-stu-id="0a8b8-186">3</span></span>|

<span data-ttu-id="0a8b8-187">Configure la opción de proximidad para tener un intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Ejemplo, Proximity](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="0a8b8-189">Usar plantillas de explicación</span><span class="sxs-lookup"><span data-stu-id="0a8b8-189">Use explanation templates</span></span>

<span data-ttu-id="0a8b8-190">Aunque se pueden agregar manualmente varios valores de la lista de patrones para la explicación, puede resultar más fácil usar las plantillas que se le proporcionan en la biblioteca de explicación.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-190">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="0a8b8-191">Por ejemplo, en lugar de añadir manualmente todas las variaciones para *Fecha*, se puede utilizar la plantilla de la lista de patrones para *Fecha* que ya incluye una serie de valores de la lista de patrones:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-191">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![Biblioteca de explicación](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="0a8b8-193">La biblioteca de explicación incluye varias explicaciones de la lista de patrones más utilizados, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-193">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="0a8b8-194">Fecha</span><span class="sxs-lookup"><span data-stu-id="0a8b8-194">Date</span></span></br>
- <span data-ttu-id="0a8b8-195">Fecha (numérica)</span><span class="sxs-lookup"><span data-stu-id="0a8b8-195">Date (numeric)</span></span></br>
- <span data-ttu-id="0a8b8-196">Hora</span><span class="sxs-lookup"><span data-stu-id="0a8b8-196">Time</span></span></br>
- <span data-ttu-id="0a8b8-197">Número</span><span class="sxs-lookup"><span data-stu-id="0a8b8-197">Number</span></span></br>
- <span data-ttu-id="0a8b8-198">Número de teléfono</span><span class="sxs-lookup"><span data-stu-id="0a8b8-198">Phone number</span></span></br>
- <span data-ttu-id="0a8b8-199">Código postal</span><span class="sxs-lookup"><span data-stu-id="0a8b8-199">Zip code</span></span></br>
- <span data-ttu-id="0a8b8-200">Primera palabra de la frase</span><span class="sxs-lookup"><span data-stu-id="0a8b8-200">First word of sentence</span></span></br>
- <span data-ttu-id="0a8b8-201">Tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="0a8b8-201">Credit card</span></span></br>
- <span data-ttu-id="0a8b8-202">Número de la seguridad social</span><span class="sxs-lookup"><span data-stu-id="0a8b8-202">Social security number</span></span></br>

<span data-ttu-id="0a8b8-203">Tenga en cuenta que la biblioteca de explicación también incluye plantillas para las explicaciones de la lista de frases:</span><span class="sxs-lookup"><span data-stu-id="0a8b8-203">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="0a8b8-204">Final de la oración</span><span class="sxs-lookup"><span data-stu-id="0a8b8-204">End of sentence</span></span>
- <span data-ttu-id="0a8b8-205">Divisa</span><span class="sxs-lookup"><span data-stu-id="0a8b8-205">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="0a8b8-206">Para usar una plantilla de la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="0a8b8-206">To use a template from the explanation library</span></span>

1. <span data-ttu-id="0a8b8-207">En la sección de **Explicaciones** de la página de **Entrenamiento** de su modelo, seleccione **Nuevo**, y luego seleccione **De Una Plantilla**.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-207">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Crear desde plantilla](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="0a8b8-209">En la página **Plantillas de explicación**, seleccione la explicación que desee usar y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-209">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Seleccionar una plantilla](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="0a8b8-211">La información de la plantilla que ha seleccionado se mostrará en la página **Crear una explicación**.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-211">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="0a8b8-212">Si es necesario, edite el nombre de la explicación y agregue o elimine elementos de la lista de patrones.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-212">If needed, edit the explanation name and add or remove items from the pattern list.</span></span> </br> 

   ![Editar plantilla](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="0a8b8-214">Cuando finalice, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0a8b8-214">When finished, select **Save**.</span></span>
