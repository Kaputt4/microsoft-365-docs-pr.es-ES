---
title: Referencia de filtros de tipo de información confidencial personalizada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: En este artículo se presenta una lista de los filtros que se pueden codificar en tipos de información confidencial personalizados.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322968"
---
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="2b47e-103">Referencia de filtros de tipo de información confidencial personalizada</span><span class="sxs-lookup"><span data-stu-id="2b47e-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="2b47e-104">En Microsoft puede definir filtros o comprobaciones adicionales al crear un tipo de información confidencial personalizado (SIT).</span><span class="sxs-lookup"><span data-stu-id="2b47e-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="2b47e-105">Lista de filtros admitidos y casos de uso</span><span class="sxs-lookup"><span data-stu-id="2b47e-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="2b47e-106">AllDigitsSame Exclude</span><span class="sxs-lookup"><span data-stu-id="2b47e-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="2b47e-107">Descripción: permite excluir coincidencias que tienen todos los dígitos como dígitos duplicados, como 111111111 o 111-111-111</span><span class="sxs-lookup"><span data-stu-id="2b47e-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="2b47e-108">Definición de filtros</span><span class="sxs-lookup"><span data-stu-id="2b47e-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="2b47e-109">Usarlo en el paquete de reglas en el nivel de entidad</span><span class="sxs-lookup"><span data-stu-id="2b47e-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="2b47e-110">Usarlo en el paquete de reglas en el nivel de patrón</span><span class="sxs-lookup"><span data-stu-id="2b47e-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="2b47e-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="2b47e-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="2b47e-112">Descripción: permite definir los caracteres iniciales de la entidad.</span><span class="sxs-lookup"><span data-stu-id="2b47e-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="2b47e-113">Tiene dos variantes, incluir y excluir.</span><span class="sxs-lookup"><span data-stu-id="2b47e-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="2b47e-114">Por ejemplo, para excluir los números a partir de 0500, 91, 091, 010 en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="2b47e-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="2b47e-115">0500-4500-027</span></span>
- <span data-ttu-id="2b47e-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="2b47e-116">91564721450</span></span>
- <span data-ttu-id="2b47e-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="2b47e-117">91-8523697410</span></span>
- <span data-ttu-id="2b47e-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="2b47e-118">700-8956-7844</span></span>
- <span data-ttu-id="2b47e-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="2b47e-119">1000-3265-9874</span></span>
- <span data-ttu-id="2b47e-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="2b47e-120">0100-7892-3012</span></span>

<span data-ttu-id="2b47e-121">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-121">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
<span data-ttu-id="2b47e-122">Por ejemplo, para incluir los números a partir de 0500, 91, 091, 0100 en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="2b47e-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="2b47e-123">0500-4500-027</span></span>
- <span data-ttu-id="2b47e-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="2b47e-124">91564721450</span></span>
- <span data-ttu-id="2b47e-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="2b47e-125">91-8523697410</span></span>
- <span data-ttu-id="2b47e-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="2b47e-126">700-8956-7844</span></span>
- <span data-ttu-id="2b47e-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="2b47e-127">1000-3265-9874</span></span>
- <span data-ttu-id="2b47e-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="2b47e-128">0100-7892-3012</span></span>

<span data-ttu-id="2b47e-129">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="2b47e-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="2b47e-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="2b47e-131">Descripción: permite definir los caracteres finales de la entidad.</span><span class="sxs-lookup"><span data-stu-id="2b47e-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="2b47e-132">Por ejemplo, para excluir los números que terminan con 0500,91.091, 0100 en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="2b47e-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="2b47e-133">1234567891</span></span>
- <span data-ttu-id="2b47e-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="2b47e-134">1234-5678-0091</span></span>
- <span data-ttu-id="2b47e-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="2b47e-135">1234.4567.7091</span></span>
- <span data-ttu-id="2b47e-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="2b47e-136">1234-8091-4564</span></span>

<span data-ttu-id="2b47e-137">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-137">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="2b47e-138">Por ejemplo, para incluir los números que terminan con 0500, 91, 091, 0100, en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="2b47e-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="2b47e-139">1234567891</span></span>
- <span data-ttu-id="2b47e-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="2b47e-140">1234-5678-0091</span></span>
- <span data-ttu-id="2b47e-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="2b47e-141">1234.4567.7091</span></span>
- <span data-ttu-id="2b47e-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="2b47e-142">1234-8091-4564</span></span>

<span data-ttu-id="2b47e-143">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="2b47e-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="2b47e-144">TextMatchFilter Full</span></span>

<span data-ttu-id="2b47e-145">Descripción: permite prohibir determinadas coincidencias para evitar que activen la regla.</span><span class="sxs-lookup"><span data-stu-id="2b47e-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="2b47e-146">Por ejemplo, excluya 4111111111111 de la lista de coincidencias válidas de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="2b47e-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="2b47e-147">Por ejemplo, para excluir números de tarjeta de crédito como 4111111111111111111 y 3241891031111111 en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="2b47e-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="2b47e-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="2b47e-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="2b47e-149">4111111111111111</span></span>
- <span data-ttu-id="2b47e-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="2b47e-150">3241891031113111</span></span>

<span data-ttu-id="2b47e-151">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-151">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="2b47e-152">Por ejemplo, para incluir números de tarjeta de crédito como 4111111111111111111 y 3241891031111111 en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="2b47e-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="2b47e-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="2b47e-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="2b47e-154">4111111111111111</span></span>
- <span data-ttu-id="2b47e-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="2b47e-155">3241891031113111</span></span>

<span data-ttu-id="2b47e-156">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="2b47e-157">Prefijo TextMatchFilter</span><span class="sxs-lookup"><span data-stu-id="2b47e-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="2b47e-158">Descripción: permite definir los caracteres anteriores que deben incluirse o excluirse siempre.</span><span class="sxs-lookup"><span data-stu-id="2b47e-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="2b47e-159">Por ejemplo, si el número de tarjeta de crédito está precedido por "Id. de pedido:", quita la coincidencia de las coincidencias válidas.</span><span class="sxs-lookup"><span data-stu-id="2b47e-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="2b47e-160">Por ejemplo, para excluir las repeticiones de números de teléfono que **tienen Teléfono número** y **llamarme** en cadenas antes del número de teléfono, en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="2b47e-161">número de teléfono 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="2b47e-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="2b47e-162">Teléfono 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="2b47e-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="2b47e-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="2b47e-163">45-124576532-123</span></span>

<span data-ttu-id="2b47e-164">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-164">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="2b47e-165">Por ejemplo, para incluir  repeticiones que tienen cadenas de tarjeta de crédito y **#tarjeta** antes del número de tarjeta de crédito, en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="2b47e-166">Tarjeta de crédito 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="2b47e-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="2b47e-167">45-124576532-123 (que podría ser número de teléfono)</span><span class="sxs-lookup"><span data-stu-id="2b47e-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="2b47e-168">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-168">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="2b47e-169">Sufijo TextMatchFilter</span><span class="sxs-lookup"><span data-stu-id="2b47e-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="2b47e-170">Descripción: permite definir los siguientes caracteres que deben incluirse o excluirse siempre.</span><span class="sxs-lookup"><span data-stu-id="2b47e-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="2b47e-171">Por ejemplo, si el número de tarjeta de crédito va seguido de '/xuid', quite la coincidencia de las coincidencias válidas.</span><span class="sxs-lookup"><span data-stu-id="2b47e-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="2b47e-172">Por ejemplo, las repeticiones de exclusión superior si hay 5 instancias más de cuatro dígitos como sufijo en una lista como esta:</span><span class="sxs-lookup"><span data-stu-id="2b47e-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="2b47e-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="2b47e-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="2b47e-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="2b47e-174">1234-5678-9321</span></span>

<span data-ttu-id="2b47e-175">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="2b47e-176">Por ejemplo, para excluir repeticiones si se siguen por **/xuidsuffix**, como una de esta lista:</span><span class="sxs-lookup"><span data-stu-id="2b47e-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="2b47e-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="2b47e-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="2b47e-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="2b47e-178">1234-5678-9321</span></span>

<span data-ttu-id="2b47e-179">puede usar este xml</span><span class="sxs-lookup"><span data-stu-id="2b47e-179">you can use this xml</span></span>

<span data-ttu-id="2b47e-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="2b47e-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="2b47e-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="2b47e-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="2b47e-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="2b47e-182">/xuid</span></span></Term>
    <span data-ttu-id="2b47e-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="2b47e-183"></Group> </Keyword></span></span>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="2b47e-184">Uso de filtros en paquetes de reglas</span><span class="sxs-lookup"><span data-stu-id="2b47e-184">Using filters in rule packages</span></span>

<span data-ttu-id="2b47e-185">Los filtros se pueden definir en el SIT completo o en un patrón.</span><span class="sxs-lookup"><span data-stu-id="2b47e-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="2b47e-186">Estos son algunos ejemplos de fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="2b47e-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="2b47e-187">En el nivel de tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="2b47e-187">At sensitive information type level</span></span>

<span data-ttu-id="2b47e-188">Filters at Entity: cubrirá todos los patrones secundarios</span><span class="sxs-lookup"><span data-stu-id="2b47e-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="2b47e-189">Los filtros se aplicarán en **todas las** instancias clasificadas por cualquiera de los patrones de esa entidad o tipo confidencial</span><span class="sxs-lookup"><span data-stu-id="2b47e-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="2b47e-190">En el patrón individual del nivel de tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="2b47e-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="2b47e-191">Filtra solo en el nivel de patrón.</span><span class="sxs-lookup"><span data-stu-id="2b47e-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="2b47e-192">El filtro se aplicará en las instancias coincidentes con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2b47e-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="2b47e-193">En el nivel de tipo de información confidencial y un filtro adicional en algunos de los patrones de esa entidad</span><span class="sxs-lookup"><span data-stu-id="2b47e-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="2b47e-194">Filtros en entidad + patrón</span><span class="sxs-lookup"><span data-stu-id="2b47e-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="2b47e-195">Los filtros se aplicarán en **todas las** instancias clasificadas por cualquiera de los patrones de esa entidad o tipo confidencial.</span><span class="sxs-lookup"><span data-stu-id="2b47e-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="2b47e-196">El filtro de nivel de patrón filtrará las instancias coincidentes con ese patrón.</span><span class="sxs-lookup"><span data-stu-id="2b47e-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="2b47e-197">Más información</span><span class="sxs-lookup"><span data-stu-id="2b47e-197">More information</span></span>

- [<span data-ttu-id="2b47e-198">Obtenga más información acerca de la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="2b47e-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="2b47e-199">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="2b47e-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="2b47e-200">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="2b47e-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
