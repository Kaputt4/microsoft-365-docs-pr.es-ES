---
title: Tipos de explicación en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Más información sobre los tipos de explicación en Microsoft SharePoint Syntex.
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706581"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="284fc-103">Tipos de explicación en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="284fc-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="284fc-104">Las explicaciones se utilizan para ayudar a definir la información que desea etiquetar y extraer en los modelos de comprensión de documentos en Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="284fc-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="284fc-105">Al crear una explicación, debe seleccionar un tipo de explicación.</span><span class="sxs-lookup"><span data-stu-id="284fc-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="284fc-106">Este artículo le ayudará a comprender los distintos tipos de explicación y cómo se usan.</span><span class="sxs-lookup"><span data-stu-id="284fc-106">This article helps you understand the different explanation types and how they're used.</span></span>

![Captura de pantalla del panel Crear una explicación que muestra los tres tipos de explicación.](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="284fc-108">Estos son los tipos de explicación disponibles:</span><span class="sxs-lookup"><span data-stu-id="284fc-108">These explanation types are available:</span></span>

- <span data-ttu-id="284fc-109">[**Lista de frases**](#phrase-list): lista de palabras, frases, números u otros caracteres que se pueden usar en el documento o la información que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="284fc-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="284fc-110">Por ejemplo, la cadena de texto *médico remitente* está en todos los documentos de derivación médica que identifica.</span><span class="sxs-lookup"><span data-stu-id="284fc-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="284fc-111">O la cadena *número de teléfono* del médico remitente está en todos los documentos de derivación médica que identifica.</span><span class="sxs-lookup"><span data-stu-id="284fc-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="284fc-112">[**Expresión regular**](#regular-expression): usa una notación que coincida con patrones de caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="284fc-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="284fc-113">Por ejemplo, puede usar una expresión regular para buscar todas las instancias de una *dirección de correo electrónico* en un conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="284fc-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="284fc-114">[**Proximidad**](#proximity): describe la cercanía que existe entre varias explicaciones.</span><span class="sxs-lookup"><span data-stu-id="284fc-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="284fc-115">Por ejemplo, el *número de la calle* se mostrará justo antes de la lista de *nombre de la calle*, sin tokens entre ellas (aprenderá sobre los tokens más adelante en este artículo).</span><span class="sxs-lookup"><span data-stu-id="284fc-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="284fc-116">Usar el tipo de proximidad requiere que tenga al menos dos explicaciones en su modelo o la opción se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="284fc-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="284fc-117">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="284fc-117">Phrase list</span></span>

<span data-ttu-id="284fc-118">Un tipo de explicación de la lista de frases se usa normalmente para identificar y clasificar un documento a través del modelo.</span><span class="sxs-lookup"><span data-stu-id="284fc-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="284fc-119">Como se describe en el ejemplo de etiqueta *médico remitente*, se trata de una cadena de palabras, frases, números o caracteres que aparece uniformemente en los documentos que se identifican.</span><span class="sxs-lookup"><span data-stu-id="284fc-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="284fc-120">Aunque no es obligatorio, puede tener más éxito con su explicación si la frase que captura se encuentra habitualmente en el mismo lugar en los documentos.</span><span class="sxs-lookup"><span data-stu-id="284fc-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="284fc-121">Por ejemplo, puede que la etiqueta *médico remitente* se encuentre siempre en el primer párrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="284fc-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="284fc-122">También puede usar la opción avanzada **[Configurar dónde aparecen las frases en el documento](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** para seleccionar áreas específicas donde se encuentra la frase, especialmente si existe la posibilidad de que la frase aparezca en varias ubicaciones del documento.</span><span class="sxs-lookup"><span data-stu-id="284fc-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="284fc-123">Si la distinción de mayúsculas y minúsculas es un requisito para identificar la etiqueta, usar el tipo Lista de frases le permite especificarla en la explicación si activa la casilla de verificación **Solo mayúsculas exactas**.</span><span class="sxs-lookup"><span data-stu-id="284fc-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Distinción entre mayúsculas y minúsculas](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="284fc-125">Un tipo de frase es especialmente útil cuando crea una explicación que identifica y extrae información en diferentes formatos, como fechas, números de teléfono y números de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="284fc-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="284fc-126">Por ejemplo, una fecha puede mostrarse en diferentes formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 de enero de 2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="284fc-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="284fc-127">Definir una lista de frases hace que su explicación sea más eficiente cuando capture cualquier posible variación en los datos que trata de identificar y extraer.</span><span class="sxs-lookup"><span data-stu-id="284fc-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="284fc-128">Para el ejemplo del *número de teléfono*, extraiga el número de teléfono de cada médico remitente de todos los documentos de derivación médica que el modelo identifique.</span><span class="sxs-lookup"><span data-stu-id="284fc-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="284fc-129">Cuando cree la explicación, escriba los distintos formatos que pueda mostrar un número de teléfono en el documento para poder capturar posibles variaciones.</span><span class="sxs-lookup"><span data-stu-id="284fc-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![Patrones de frases de número de teléfono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="284fc-131">Para este ejemplo, en **Configuración avanzada**, seleccione la casilla **Cualquier dígito entre 0 y 9** para reconocer cada valor de "0" usado en la lista de frases para ser cualquier dígito del 0 al 9.</span><span class="sxs-lookup"><span data-stu-id="284fc-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Cualquier dígito entre 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="284fc-133">De forma similar, si crea una lista de frases que incluya caracteres de texto, active la casilla de verificación **Cualquier letra de la a a la z** para reconocer cada carácter "a" que se use en la lista de frases como un carácter entre "a" y "z".</span><span class="sxs-lookup"><span data-stu-id="284fc-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="284fc-134">Por ejemplo, si crea una lista de frases de **Fecha** y quiere asegurarse de que un formato de fecha como *1 de enero de 2020* se reconozca, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="284fc-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="284fc-135">Agregar *aaa 0, 0000* y *aaa 00, 0000* a la lista de frases.</span><span class="sxs-lookup"><span data-stu-id="284fc-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="284fc-136">Asegúrese de que **Cualquier letra de la a a la z** también esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="284fc-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![Cualquier letra de la a a la z](../media/content-understanding/any-letter.png)

<span data-ttu-id="284fc-138">Si tiene requisitos de usar mayúsculas y minúsculas en su lista de frases, puede seleccionar la casilla de verificación **Solo usar mayúsculas y minúsculas exactamente**.</span><span class="sxs-lookup"><span data-stu-id="284fc-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="284fc-139">Para el ejemplo de fecha, si requiere que la primera letra del mes esté en mayúscula, debe:</span><span class="sxs-lookup"><span data-stu-id="284fc-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="284fc-140">Agregar *Aaa 0, 0000* y *Aaa 00, 0000* a la lista de frases.</span><span class="sxs-lookup"><span data-stu-id="284fc-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="284fc-141">Asegúrese de que **Solo usar mayúsculas y minúsculas exactamente** también está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="284fc-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![Solo usar mayúsculas y minúsculas exactamente](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="284fc-143">En lugar de crear manualmente una explicación de las listas de frases, utilice la [Biblioteca de explicación](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar plantillas de listas de frases para las listas de frases comunes, como *fecha*, *números de teléfono* o *número de tarjeta de crédito*.</span><span class="sxs-lookup"><span data-stu-id="284fc-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="284fc-144">Expresión regular</span><span class="sxs-lookup"><span data-stu-id="284fc-144">Regular expression</span></span>

<span data-ttu-id="284fc-145">Un tipo de explicación de expresiones regulares le permite crear patrones que ayudan a buscar e identificar determinadas cadenas de texto en los documentos.</span><span class="sxs-lookup"><span data-stu-id="284fc-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="284fc-146">Puede usar expresiones regulares para analizar rápidamente grandes cantidades de texto de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="284fc-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="284fc-147">Buscar patrones de caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="284fc-147">Find specific character patterns.</span></span>
- <span data-ttu-id="284fc-148">Validar el texto para asegurarse de que coincida con un patrón predefinido (por ejemplo, una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="284fc-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="284fc-149">Extraer, editar, reemplazar o eliminar subcadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="284fc-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="284fc-150">Un tipo de expresión regular es especialmente útil cuando se crea una explicación que identifica y extrae información en formatos regulares, como direcciones de correo electrónico, números de cuentas bancarias o direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="284fc-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="284fc-151">Por ejemplo, una dirección de correo electrónico, como megan@contoso.com, se muestra siempre con un patrón determinado (en el ejemplo, "megan" es la primera parte y "com" es la última).</span><span class="sxs-lookup"><span data-stu-id="284fc-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="284fc-152">La expresión regular de una dirección de correo electrónico es: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span><span class="sxs-lookup"><span data-stu-id="284fc-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="284fc-153">Esta expresión se compone de cinco partes, en este orden:</span><span class="sxs-lookup"><span data-stu-id="284fc-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="284fc-154">cualquier cantidad de los siguientes caracteres:</span><span class="sxs-lookup"><span data-stu-id="284fc-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="284fc-155">a.</span><span class="sxs-lookup"><span data-stu-id="284fc-155">a.</span></span> <span data-ttu-id="284fc-156">letras de la "a" a la "z"</span><span class="sxs-lookup"><span data-stu-id="284fc-156">Letters from a to z</span></span>

   <span data-ttu-id="284fc-157">b.</span><span class="sxs-lookup"><span data-stu-id="284fc-157">b.</span></span> <span data-ttu-id="284fc-158">números del 0 al 9</span><span class="sxs-lookup"><span data-stu-id="284fc-158">Numbers from 0-9</span></span>

   <span data-ttu-id="284fc-159">c.</span><span class="sxs-lookup"><span data-stu-id="284fc-159">c.</span></span> <span data-ttu-id="284fc-160">punto, subrayado, porcentaje o guion</span><span class="sxs-lookup"><span data-stu-id="284fc-160">Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="284fc-161">El símbolo @</span><span class="sxs-lookup"><span data-stu-id="284fc-161">The @ symbol</span></span>

3. <span data-ttu-id="284fc-162">cualquier cantidad de los mismos caracteres como en la primera parte de la dirección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="284fc-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="284fc-163">Un punto</span><span class="sxs-lookup"><span data-stu-id="284fc-163">A period</span></span>

5. <span data-ttu-id="284fc-164">De dos a seis letras</span><span class="sxs-lookup"><span data-stu-id="284fc-164">Two to six letters</span></span>

<span data-ttu-id="284fc-165">Para agregar un tipo de explicación de expresiones regulares:</span><span class="sxs-lookup"><span data-stu-id="284fc-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="284fc-166">Desde el panel **Crear una explicación**, en **Tipo de explicación**, seleccione la **Expresión regular**.</span><span class="sxs-lookup"><span data-stu-id="284fc-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![Captura de pantalla que muestra el panel Crear una explicación con la expresión regular seleccionada.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="284fc-168">Puede escribir una expresión en el cuadro de texto **Expresión regular** o seleccionar **Agregar una expresión regular desde una plantilla**.</span><span class="sxs-lookup"><span data-stu-id="284fc-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="284fc-169">Cuando agregue una expresión regular con una plantilla, el nombre y la expresión regular se agregarán automáticamente al cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="284fc-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="284fc-170">Por ejemplo, si elige la plantilla **dirección de correo electrónico**, se rellenará el panel **Crear una explicación**.</span><span class="sxs-lookup"><span data-stu-id="284fc-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![Captura de pantalla que muestra el panel Crear una explicación con la plantilla de dirección de correo electrónico aplicada.](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="284fc-172">Proximidad</span><span class="sxs-lookup"><span data-stu-id="284fc-172">Proximity</span></span> 

<span data-ttu-id="284fc-173">El tipo de explicación de proximidad ayuda al modelo a identificar los datos definiendo la proximidad que otros datos tienen con estos.</span><span class="sxs-lookup"><span data-stu-id="284fc-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="284fc-174">Por ejemplo, en su modelo ha definido dos explicaciones que etiquetan tanto el *número de la dirección de la calle* como el *número de teléfono* del cliente.</span><span class="sxs-lookup"><span data-stu-id="284fc-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="284fc-175">Sabemos que los números de teléfono del cliente siempre aparecen antes que el número de la calle.</span><span class="sxs-lookup"><span data-stu-id="284fc-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="284fc-176">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="284fc-176">Alex Wilburn</span></span><br>
<span data-ttu-id="284fc-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="284fc-177">555-555-5555</span></span><br>
<span data-ttu-id="284fc-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="284fc-178">One Microsoft Way</span></span><br>
<span data-ttu-id="284fc-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="284fc-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="284fc-180">Use la explicación de proximidad para definir el número de teléfono que se debe desplazar para identificar mejor el número de la calle en los documentos.</span><span class="sxs-lookup"><span data-stu-id="284fc-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Explicación de Proximidad](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="284fc-182">¿Qué son los tokens?</span><span class="sxs-lookup"><span data-stu-id="284fc-182">What are tokens?</span></span>

<span data-ttu-id="284fc-183">Para usar el tipo de explicación de proximidad es necesario comprender qué es un token.</span><span class="sxs-lookup"><span data-stu-id="284fc-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="284fc-184">El número de tokens muestra cómo la explicación de proximidad mide la distancia entre una explicación y otra.</span><span class="sxs-lookup"><span data-stu-id="284fc-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="284fc-185">Un token es un intervalo continuo (sin incluir espacios ni signos de puntuación) de letras y números.</span><span class="sxs-lookup"><span data-stu-id="284fc-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="284fc-186">En la siguiente tabla se muestran algunos ejemplos de cómo determinar el número de tokens en una frase.</span><span class="sxs-lookup"><span data-stu-id="284fc-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="284fc-187">Frase</span><span class="sxs-lookup"><span data-stu-id="284fc-187">Phrase</span></span>|<span data-ttu-id="284fc-188">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="284fc-188">Number of tokens</span></span>|<span data-ttu-id="284fc-189">Explicación</span><span class="sxs-lookup"><span data-stu-id="284fc-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="284fc-190">1</span><span class="sxs-lookup"><span data-stu-id="284fc-190">1</span></span>|<span data-ttu-id="284fc-191">Una sola palabra sin signos de puntuación o espacios.</span><span class="sxs-lookup"><span data-stu-id="284fc-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="284fc-192">1</span><span class="sxs-lookup"><span data-stu-id="284fc-192">1</span></span>|<span data-ttu-id="284fc-193">Un número de localizador de registros.</span><span class="sxs-lookup"><span data-stu-id="284fc-193">A record locator number.</span></span> <span data-ttu-id="284fc-194">Puede incluir números y letras, pero no signos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="284fc-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="284fc-195">5</span><span class="sxs-lookup"><span data-stu-id="284fc-195">5</span></span>|<span data-ttu-id="284fc-196">Un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="284fc-196">A phone number.</span></span> <span data-ttu-id="284fc-197">Cada signo de puntuación es un token único, por lo que `425-555-5555` tiene 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="284fc-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="284fc-198">7</span><span class="sxs-lookup"><span data-stu-id="284fc-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="284fc-199">Configurar el tipo de explicación de proximidad</span><span class="sxs-lookup"><span data-stu-id="284fc-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="284fc-200">Para el ejemplo, configure el ajuste de proximidad de manera que podamos definir el rango del número de tokens en la explicación *número de teléfono* a partir de la explicación *número de la dirección de la calle*.</span><span class="sxs-lookup"><span data-stu-id="284fc-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="284fc-201">Vea que el intervalo mínimo es "0", ya que no hay ningún token entre el número de teléfono y el número de la dirección postal.</span><span class="sxs-lookup"><span data-stu-id="284fc-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="284fc-202">Sin embargo, algunos números de teléfono de los documentos de muestra incluyen *(móvil)* al final.</span><span class="sxs-lookup"><span data-stu-id="284fc-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="284fc-203">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="284fc-203">Nestor Wilke</span></span><br>
<span data-ttu-id="284fc-204">111-111-1111 (móvil)</span><span class="sxs-lookup"><span data-stu-id="284fc-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="284fc-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="284fc-205">One Microsoft Way</span></span><br>
<span data-ttu-id="284fc-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="284fc-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="284fc-207">Hay tres tokens en *(móvil)*:</span><span class="sxs-lookup"><span data-stu-id="284fc-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="284fc-208">Frase</span><span class="sxs-lookup"><span data-stu-id="284fc-208">Phrase</span></span>|<span data-ttu-id="284fc-209">Cuenta de tokens</span><span class="sxs-lookup"><span data-stu-id="284fc-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="284fc-210">(</span><span class="sxs-lookup"><span data-stu-id="284fc-210">(</span></span>|<span data-ttu-id="284fc-211">1</span><span class="sxs-lookup"><span data-stu-id="284fc-211">1</span></span>|
|<span data-ttu-id="284fc-212">móvil</span><span class="sxs-lookup"><span data-stu-id="284fc-212">mobile</span></span>|<span data-ttu-id="284fc-213">2</span><span class="sxs-lookup"><span data-stu-id="284fc-213">2</span></span>|
|<span data-ttu-id="284fc-214">)</span><span class="sxs-lookup"><span data-stu-id="284fc-214">)</span></span>|<span data-ttu-id="284fc-215">3</span><span class="sxs-lookup"><span data-stu-id="284fc-215">3</span></span>|

<span data-ttu-id="284fc-216">Configure la opción de proximidad para tener un intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="284fc-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Ejemplo, Proximity](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="284fc-218">Configurar dónde aparecen frases en el documento</span><span class="sxs-lookup"><span data-stu-id="284fc-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="284fc-219">Cuando crea una explicación, de forma predeterminada se busca en todo el documento la frase que intenta extraer.</span><span class="sxs-lookup"><span data-stu-id="284fc-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="284fc-220">Sin embargo, puede usar la opción avanzada **Dónde se aparezcan estas frases** para ayudar a aislar una ubicación específica del documento donde aparezca una frase.</span><span class="sxs-lookup"><span data-stu-id="284fc-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="284fc-221">Esta configuración es útil cuando pueden aparecer instancias similares de una frase en otra parte del documento y quiere asegurarse de que se ha seleccionado la correcta.</span><span class="sxs-lookup"><span data-stu-id="284fc-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="284fc-222">Si nos referimos a nuestro ejemplo de documento de derivación médica, siempre se menciona el *médico remitente* en el primer párrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="284fc-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="284fc-223">Con la opción **Dónde se aparezcan estas frases**, en este ejemplo puede configurar su explicación para que busque esta etiqueta solo en la sección inicial del documento o en cualquier otra ubicación en la que pueda aparecer.</span><span class="sxs-lookup"><span data-stu-id="284fc-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Opción Dónde se aparezcan estas frases](../media/content-understanding/phrase-location.png)

<span data-ttu-id="284fc-225">Puede seleccionar una de las siguientes opciones para este valor:</span><span class="sxs-lookup"><span data-stu-id="284fc-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="284fc-226">En cualquier lugar del archivo: se busca la frase en todo el documento.</span><span class="sxs-lookup"><span data-stu-id="284fc-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="284fc-227">Principio del archivo: se busca en el documento desde el principio hasta la ubicación de la frase.</span><span class="sxs-lookup"><span data-stu-id="284fc-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Principio del archivo](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="284fc-229">En el visor, puede ajustar manualmente el cuadro de selección para que incluya la ubicación donde aparezca la fase.</span><span class="sxs-lookup"><span data-stu-id="284fc-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="284fc-230">El valor **Posición final** se actualizará para mostrar el número de tokens que incluye el área seleccionada.</span><span class="sxs-lookup"><span data-stu-id="284fc-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="284fc-231">Puede actualizar el valor de la **posición final** para ajustar el área seleccionada.</span><span class="sxs-lookup"><span data-stu-id="284fc-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![Cuadro de posición Principio del archivo](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="284fc-233">Final del archivo: se busca en el documento desde el principio hasta la ubicación de la frase.</span><span class="sxs-lookup"><span data-stu-id="284fc-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![Final del archivo](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="284fc-235">En el visor, puede ajustar manualmente el cuadro de selección para que incluya la ubicación donde aparezca la fase.</span><span class="sxs-lookup"><span data-stu-id="284fc-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="284fc-236">El valor **Posición inicial** se actualizará para mostrar el número de tokens que incluye el área seleccionada.</span><span class="sxs-lookup"><span data-stu-id="284fc-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="284fc-237">También puede actualizar el valor Posición inicial para ajustar el área seleccionada.</span><span class="sxs-lookup"><span data-stu-id="284fc-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![Cuadro de posición Final del archivo](../media/content-understanding/end-box.png)

- <span data-ttu-id="284fc-239">Intervalo personalizado: se busca dentro de un rango especificado en el documento.</span><span class="sxs-lookup"><span data-stu-id="284fc-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![Intervalo personalizado](../media/content-understanding/custom-file.png)

    <span data-ttu-id="284fc-241">En el visor, puede ajustar manualmente el cuadro de selección para que incluya la ubicación donde aparezca la fase.</span><span class="sxs-lookup"><span data-stu-id="284fc-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="284fc-242">Para esta opción, necesita seleccionar una posición **Inicio** y una posición **Fin**.</span><span class="sxs-lookup"><span data-stu-id="284fc-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="284fc-243">Estos valores representan el número de tokens desde el principio del documento.</span><span class="sxs-lookup"><span data-stu-id="284fc-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="284fc-244">Aunque puede escribir los valores manualmente, es más fácil ajustarlos en el cuadro de selección en el visor.</span><span class="sxs-lookup"><span data-stu-id="284fc-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="284fc-245">Usar plantillas de explicación</span><span class="sxs-lookup"><span data-stu-id="284fc-245">Use explanation templates</span></span>

<span data-ttu-id="284fc-246">Aunque se pueden agregar manualmente varios valores de la lista de frases para la explicación, puede resultar más fácil usar las plantillas que se le proporcionan en la biblioteca de explicación.</span><span class="sxs-lookup"><span data-stu-id="284fc-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="284fc-247">Por ejemplo, en lugar de añadir manualmente todas las variaciones para *fecha*, puede utilizar la plantilla de la lista de frases para *fecha* que ya incluye una serie de valores de la lista de frases:</span><span class="sxs-lookup"><span data-stu-id="284fc-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![Biblioteca de explicación](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="284fc-249&quot;>La biblioteca de explicación incluye varias explicaciones de la *lista de frases* más utilizadas, entre las que se incluyen:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;284fc-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;284fc-250&quot;>Fecha: fechas del calendario, todos los formatos.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;284fc-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;284fc-251&quot;>Incluye texto y números (por ejemplo, &quot;9 de diciembre de 2020").</span><span class="sxs-lookup"><span data-stu-id="284fc-251">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="284fc-252">Fecha (numérica): fechas del calendario, todos los formatos.</span><span class="sxs-lookup"><span data-stu-id="284fc-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="284fc-253">Incluye números (por ejemplo, 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="284fc-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="284fc-254">Hora: formatos de 12 y 24 horas.</span><span class="sxs-lookup"><span data-stu-id="284fc-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="284fc-255">Número: números positivos y negativos, hasta 2 decimales.</span><span class="sxs-lookup"><span data-stu-id="284fc-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="284fc-256">Porcentaje: una lista de patrones que representan un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="284fc-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="284fc-257">Por ejemplo, 1 %, 11 %, 100 % o 11,11 %.</span><span class="sxs-lookup"><span data-stu-id="284fc-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="284fc-258">Número de teléfono: formatos comunes de EE. UU. e internacionales.</span><span class="sxs-lookup"><span data-stu-id="284fc-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="284fc-259">Por ejemplo, 000 000 0000, 000-000-0000, (000)000-0000 o (000) 000-0000.</span><span class="sxs-lookup"><span data-stu-id="284fc-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="284fc-260">Código postal: formatos de código postal de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="284fc-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="284fc-261">Por ejemplo, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="284fc-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="284fc-262">Primera palabra de una frase: patrones comunes para palabras de hasta nueve caracteres.</span><span class="sxs-lookup"><span data-stu-id="284fc-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="284fc-263">Final de una oración: signos de puntuación comunes para el final de una oración</span><span class="sxs-lookup"><span data-stu-id="284fc-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="284fc-264">Tarjeta de crédito: formatos de número de tarjeta de crédito comunes.</span><span class="sxs-lookup"><span data-stu-id="284fc-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="284fc-265">Por ejemplo, 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="284fc-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="284fc-p132">Número de la seguridad social: formato de número del seguro social de EE. UU. Por ejemplo, 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="284fc-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="284fc-268">Casilla: una lista de frases que representa variaciones en una casilla rellenada.</span><span class="sxs-lookup"><span data-stu-id="284fc-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="284fc-269">Por ejemplo, _X_, _ _X_.</span><span class="sxs-lookup"><span data-stu-id="284fc-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="284fc-270">Moneda: principales símbolos internacionales.</span><span class="sxs-lookup"><span data-stu-id="284fc-270">Currency: Major international symbols.</span></span> <span data-ttu-id="284fc-271">Por ejemplo: .$</span><span class="sxs-lookup"><span data-stu-id="284fc-271">For example, $.</span></span> 
- <span data-ttu-id="284fc-272">Correo electrónico CC: lista de frases con el término "CC:" que se suele encontrar cerca de los nombres o direcciones de correo electrónico de otras personas o grupos a los que se envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="284fc-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="284fc-273">Fecha del correo electrónico: lista de frases con el término "Enviado el:", que se suele encontrar cerca de la fecha en que se envió el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="284fc-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="284fc-274">Saludo de correo electrónico: líneas de apertura comunes de los correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="284fc-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="284fc-275">Destinatario de correo electrónico: lista de frases con el término "Para:", que a menudo se encuentra cerca de los nombres o direcciones de correo electrónico de personas o grupos a los que se envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="284fc-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="284fc-276">Remitente de correo electrónico: lista de frases con el término "De:" que se suele encontrar cerca del nombre o la dirección de correo del remitente.</span><span class="sxs-lookup"><span data-stu-id="284fc-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="284fc-277">Asunto del correo electrónico: lista de frases con el término "Asunto:" que se suele encontrar cerca del asunto del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="284fc-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="284fc-278">La biblioteca de explicación incluye varias explicaciones de *expresiones regulares* frecuentemente utilizadas, entre ellas:</span><span class="sxs-lookup"><span data-stu-id="284fc-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="284fc-279">Números de 6 a 17 dígitos: coincide con cualquier número de 6 a 17 dígitos de longitud.</span><span class="sxs-lookup"><span data-stu-id="284fc-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="284fc-280">Los números de cuenta bancaria de EE. UU. se ajustan a este patrón.</span><span class="sxs-lookup"><span data-stu-id="284fc-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="284fc-281">Correo electrónico: coincide con un tipo común de dirección de correo electrónico como meganb@contoso.com</span><span class="sxs-lookup"><span data-stu-id="284fc-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="284fc-282">Número de identificación fiscal de los EE. UU.: coincide con un número de tres dígitos que empieza por nueve seguido de un número de seis dígitos que empieza por siete u ocho.</span><span class="sxs-lookup"><span data-stu-id="284fc-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="284fc-283">Dirección web (URL): coincide con el formato de una dirección web que empieza por http:// o https://.</span><span class="sxs-lookup"><span data-stu-id="284fc-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="284fc-284">La biblioteca de explicación también incluye tres tipos de plantillas automáticas que funcionan con los datos que ha etiquetado en los archivos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="284fc-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="284fc-285">Después de la etiqueta: las palabras o caracteres que aparecen después de las etiquetas en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="284fc-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="284fc-286">Antes de la etiqueta: las palabras o caracteres que aparecen antes de las etiquetas en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="284fc-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="284fc-287">Etiquetas: hasta las 10 primeras etiquetas de los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="284fc-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="284fc-288">Para ilustrar cómo funcionan las plantillas automáticas, en el siguiente archivo de ejemplo usaremos la plantilla de explicación Antes de la etiqueta para dar más información al modelo y obtener una coincidencia más precisa.</span><span class="sxs-lookup"><span data-stu-id="284fc-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![Archivos de ejemplo](../media/content-understanding/before-label.png)

<span data-ttu-id="284fc-290">Al seleccionar la plantilla de explicación Antes de la etiqueta, buscará el primer conjunto de palabras que aparezca antes de la etiqueta en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="284fc-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="284fc-291">Como puede ver en la imagen, las palabras que se identifican en el primer archivo de ejemplo son "As of".</span><span class="sxs-lookup"><span data-stu-id="284fc-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![Plantilla Antes de la etiqueta](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="284fc-293">Puede seleccionar **Agregar** para crear una explicación a partir de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="284fc-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="284fc-294">A medida que agregue más archivos de ejemplo, se identificarán y agregarán palabras adicionales a la lista de frases.</span><span class="sxs-lookup"><span data-stu-id="284fc-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Agregar la etiqueta](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="284fc-296">Para usar una plantilla de la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="284fc-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="284fc-297">En la sección de **Explicaciones** de la página de **Entrenamiento** de su modelo, seleccione **Nuevo**, y luego seleccione **De Una Plantilla**.</span><span class="sxs-lookup"><span data-stu-id="284fc-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Agregar Antes de etiqueta](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="284fc-299">En la página **Plantillas de explicación**, seleccione la explicación que desee usar y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="284fc-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Seleccionar una plantilla](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="284fc-301">La información de la plantilla que ha seleccionado se mostrará en la página **Crear una explicación**.</span><span class="sxs-lookup"><span data-stu-id="284fc-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="284fc-302">Si es necesario, edite el nombre de la explicación y agregue o elimine elementos de la lista de frases.</span><span class="sxs-lookup"><span data-stu-id="284fc-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Editar plantilla](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="284fc-304">Cuando finalice, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="284fc-304">When finished, select **Save**.</span></span>