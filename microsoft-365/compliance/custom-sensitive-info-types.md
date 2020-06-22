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
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817969"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="19e4b-103">Tipos de información confidencial personalizada</span><span class="sxs-lookup"><span data-stu-id="19e4b-103">Custom sensitive information types</span></span>

<span data-ttu-id="19e4b-104">Microsoft 365 incluye muchos tipos de información confidencial que están listos para usarse en su organización, como [prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP), o con [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="19e4b-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="19e4b-105">Los tipos de información confidencial integrados pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte y más, en función de los patrones definidos por una expresión regular (regex) o una función.</span><span class="sxs-lookup"><span data-stu-id="19e4b-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="19e4b-106">Para obtener más información, consulte [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="19e4b-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="19e4b-107">Pero, ¿qué sucede si necesita identificar y proteger un tipo diferente de información confidencial, como el id. de empleados o los números de proyecto, mediante un formato específico para su organización?</span><span class="sxs-lookup"><span data-stu-id="19e4b-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="19e4b-108">Para ello, puede crear un tipo de información confidencial personalizado.</span><span class="sxs-lookup"><span data-stu-id="19e4b-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="19e4b-109">Estas son las partes básicas de un tipo personalizado de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="19e4b-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="19e4b-110">**Patrón principal**: números de id. de empleado, números de proyecto, etc. Suele identificarse mediante una expresión regular (regex), pero también puede ser una lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="19e4b-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="19e4b-111">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number.</span><span class="sxs-lookup"><span data-stu-id="19e4b-111">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number.</span></span> <span data-ttu-id="19e4b-112">Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions.</span><span class="sxs-lookup"><span data-stu-id="19e4b-112">Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions.</span></span> <span data-ttu-id="19e4b-113">This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span><span class="sxs-lookup"><span data-stu-id="19e4b-113">This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="19e4b-114">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for.</span><span class="sxs-lookup"><span data-stu-id="19e4b-114">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for.</span></span> <span data-ttu-id="19e4b-115">You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span><span class="sxs-lookup"><span data-stu-id="19e4b-115">You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagrama de evidencia corroborativa y ventana de proximidad](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="19e4b-117">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for.</span><span class="sxs-lookup"><span data-stu-id="19e4b-117">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for.</span></span> <span data-ttu-id="19e4b-118">You can assign higher levels of confidence for matches that are detected by using more evidence.</span><span class="sxs-lookup"><span data-stu-id="19e4b-118">You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="19e4b-119">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies.</span><span class="sxs-lookup"><span data-stu-id="19e4b-119">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies.</span></span> <span data-ttu-id="19e4b-120">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span><span class="sxs-lookup"><span data-stu-id="19e4b-120">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Opciones de precisión de coincidencia y recuento de instancias](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="19e4b-122">Crear tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="19e4b-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="19e4b-123">Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="19e4b-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="19e4b-124">**Usar EDM** (nuevo). Puede establecer los tipos de información confidencial mediante la clasificación basada en la exacta coincidencia de los datos (EDM).</span><span class="sxs-lookup"><span data-stu-id="19e4b-124">**Use EDM** (NEW!) You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="19e4b-125">Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente.</span><span class="sxs-lookup"><span data-stu-id="19e4b-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="19e4b-126">Vea [Crear un tipo de información confidencial personalizado con coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="19e4b-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="19e4b-127">**Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19e4b-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="19e4b-128">Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="19e4b-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="19e4b-129">Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="19e4b-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="19e4b-130">**Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="19e4b-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="19e4b-131">Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="19e4b-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="19e4b-132">Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="19e4b-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>



