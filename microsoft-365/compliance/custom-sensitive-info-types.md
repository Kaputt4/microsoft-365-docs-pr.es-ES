---
title: Tipos de información confidencial personalizada para DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga una visión general de los tipos de información confidencial personalizada para la Prevención de pérdida de datos (DLP), como el patrón primario, la proximidad de caracteres y el nivel de confianza.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3b3e30c75641dde16726e1d98c8f12c4437b0df6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685480"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="f21f8-103">Tipos de información confidencial personalizada</span><span class="sxs-lookup"><span data-stu-id="f21f8-103">Custom sensitive information types</span></span>

<span data-ttu-id="f21f8-104">Microsoft 365 incluye muchos tipos de información confidencial que están listos para usarse en su organización, como [prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP), o con [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="f21f8-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="f21f8-105">Los tipos de información confidencial integrados pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte y más, en función de los patrones definidos por una expresión regular (regex) o una función.</span><span class="sxs-lookup"><span data-stu-id="f21f8-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="f21f8-106">Para obtener más información, consulte [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f21f8-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="f21f8-107">Pero, ¿qué sucede si necesita identificar y proteger un tipo diferente de información confidencial, como el id. de empleados o los números de proyecto, mediante un formato específico para su organización?</span><span class="sxs-lookup"><span data-stu-id="f21f8-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="f21f8-108">Para ello, puede crear un tipo de información confidencial personalizado.</span><span class="sxs-lookup"><span data-stu-id="f21f8-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="f21f8-109">Estas son las partes básicas de un tipo personalizado de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="f21f8-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="f21f8-110">**Patrón principal**: números de id. de empleado, números de proyecto, etc. Suele identificarse mediante una expresión regular (regex), pero también puede ser una lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="f21f8-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="f21f8-p103">**Evidencia adicional**: imagine que busca un número de id. de empleado de nueve dígitos. No todos los números de nueve dígitos son números de id. de empleado, pero puede buscar texto adicional (palabras clave como “empleado”, “identificación” o “id.”, o bien otros patrones de texto basados en expresiones regulares). Esta evidencia complementaria (también conocida como _evidencia_ _corroborativa_) incrementa la probabilidad de que el número de nueve dígitos encontrado en el contenido sea realmente un número de id. de empleado.</span><span class="sxs-lookup"><span data-stu-id="f21f8-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="f21f8-p104">**Proximidad de caracteres**: tiene sentido que, cuanto más próximos estén entre sí el patrón principal y la evidencia complementaria, más probabilidades habrá de que el contenido detectado sea lo que busca. Puede especificar la distancia de caracteres entre el patrón principal y la evidencia complementaria (también conocida como _ventana de proximidad_), como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21f8-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagrama de evidencia corroborativa y ventana de proximidad](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="f21f8-p105">**Nivel de confianza**: cuantas más evidencias complementarias tenga, mayor será la probabilidad de que una coincidencia contenga la información confidencial que busca. Puede asignar mayores niveles de confianza a las coincidencias detectadas mediante el uso de más evidencias.</span><span class="sxs-lookup"><span data-stu-id="f21f8-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="f21f8-p106">Cuando esté conforme, un patrón devolverá un recuento y un nivel de confianza, que podrá usar en las condiciones de las directivas DLP. Al agregar a una directiva DLP una condición para detectar un tipo de información confidencial, puede editar el recuento y el nivel de confianza, como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21f8-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Opciones de precisión de coincidencia y recuento de instancias](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="f21f8-122">Crear tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="f21f8-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="f21f8-123">Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="f21f8-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="f21f8-124">**Usar EDM** Puede establecer los tipos de información confidencial mediante la clasificación basada en la coincidencia exacta de los datos (EDM).</span><span class="sxs-lookup"><span data-stu-id="f21f8-124">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="f21f8-125">Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente.</span><span class="sxs-lookup"><span data-stu-id="f21f8-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="f21f8-126">Vea [Crear un tipo de información confidencial personalizado con coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="f21f8-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="f21f8-127">**Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f21f8-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="f21f8-128">Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="f21f8-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="f21f8-129">Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f21f8-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="f21f8-130">**Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="f21f8-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="f21f8-131">Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="f21f8-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="f21f8-132">Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="f21f8-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f21f8-133">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="f21f8-133">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="f21f8-134">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="f21f8-134">Chinese (simplified)</span></span>
> - <span data-ttu-id="f21f8-135">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="f21f8-135">Chinese (traditional)</span></span>
> - <span data-ttu-id="f21f8-136">Coreano</span><span class="sxs-lookup"><span data-stu-id="f21f8-136">Korean</span></span>
> - <span data-ttu-id="f21f8-137">Japonés</span><span class="sxs-lookup"><span data-stu-id="f21f8-137">Japanese</span></span>
> 
><span data-ttu-id="f21f8-138">Esta vista previa solo se encuentra en la nube comercial y la implementación está limitada a:</span><span class="sxs-lookup"><span data-stu-id="f21f8-138">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="f21f8-139">Japón</span><span class="sxs-lookup"><span data-stu-id="f21f8-139">Japan</span></span>
> - <span data-ttu-id="f21f8-140">Corea</span><span class="sxs-lookup"><span data-stu-id="f21f8-140">Korea</span></span>
> - <span data-ttu-id="f21f8-141">China</span><span class="sxs-lookup"><span data-stu-id="f21f8-141">China</span></span>
> - <span data-ttu-id="f21f8-142">RAE de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="f21f8-142">Hong Kong</span></span>
> - <span data-ttu-id="f21f8-143">RAE de Macao</span><span class="sxs-lookup"><span data-stu-id="f21f8-143">Macau</span></span>
> - <span data-ttu-id="f21f8-144">Taiwán</span><span class="sxs-lookup"><span data-stu-id="f21f8-144">Taiwan</span></span>
>
><span data-ttu-id="f21f8-145">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="f21f8-145">This support is available for sensitive information types.</span></span> <span data-ttu-id="f21f8-146">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="f21f8-146">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

