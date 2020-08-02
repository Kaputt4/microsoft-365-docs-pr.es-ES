---
title: Qué buscan las funciones de prevención de pérdida de datos (DLP)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre qué buscan las funciones de prevención de pérdida de datos (DLP).
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536315"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="a0088-103">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="a0088-103">What the DLP functions look for</span></span>

<span data-ttu-id="a0088-104">La prevención de pérdida de datos (DLP) incluye tipos de información confidencial, como el número de tarjeta de crédito y el número de tarjeta de débito de la UE, que están listos para usarlos en las directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="a0088-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="a0088-105">Estos tipos de información confidencial buscan un patrón específico y lo comprueban asegurándose de que el formato es el adecuado, forzando las sumas de comprobación y buscando palabras clave pertinentes u otra información.</span><span class="sxs-lookup"><span data-stu-id="a0088-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="a0088-106">Parte de esta funcionalidad la realizan funciones internas.</span><span class="sxs-lookup"><span data-stu-id="a0088-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="a0088-107">Por ejemplo, el tipo de información confidencial de la tarjeta de crédito usa una función para buscar fechas con formato como la fecha de vencimiento, que ayuda a comprobar que un número es un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="a0088-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="a0088-108">En este artículo se explica lo que buscan estas funciones para ayudarle a comprender cómo funcionan los tipos de información confidencial predefinidos.</span><span class="sxs-lookup"><span data-stu-id="a0088-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="a0088-109">Para obtener más información, vea [tipos de información confidencial definiciones de entidades](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="a0088-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="a0088-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="a0088-110">Func_us_date</span></span>

<span data-ttu-id="a0088-111">Esta función busca una fecha con el formato que se usa habitualmente en Estados Unidos. Esto incluye los formatos "month/Day/Year", "month-Day-Year" y "month Day Year".</span><span class="sxs-lookup"><span data-stu-id="a0088-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="a0088-112">Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a0088-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="a0088-113">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a0088-113">Examples:</span></span>
  
- <span data-ttu-id="a0088-114">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-114">December 2, 2016</span></span>
    
- <span data-ttu-id="a0088-115">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="a0088-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-116">dec 02 2016</span></span>
    
- <span data-ttu-id="a0088-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="a0088-117">12/2/2016</span></span>
    
- <span data-ttu-id="a0088-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="a0088-118">12/02/16</span></span>
    
- <span data-ttu-id="a0088-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="a0088-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="a0088-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="a0088-120">12-2-16</span></span>
    
<span data-ttu-id="a0088-121">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a0088-121">Accepted month names:</span></span>
  
- <span data-ttu-id="a0088-122">English</span><span class="sxs-lookup"><span data-stu-id="a0088-122">English</span></span>
    
  - <span data-ttu-id="a0088-123">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a0088-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a0088-124">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="a0088-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="a0088-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="a0088-125">Func_eu_date</span></span>

<span data-ttu-id="a0088-126">Esta función busca una fecha con el formato usado habitualmente en la UE</span><span class="sxs-lookup"><span data-stu-id="a0088-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="a0088-127">(y la mayoría de los lugares fuera de Estados Unidos), como "día/mes/año", "día-mes-año" y "día mes año".</span><span class="sxs-lookup"><span data-stu-id="a0088-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="a0088-128">Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a0088-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="a0088-129">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a0088-129">Examples:</span></span>
  
- <span data-ttu-id="a0088-130">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="a0088-131">02 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-131">02 dec 2016</span></span>
    
- <span data-ttu-id="a0088-132">2 16 de diciembre</span><span class="sxs-lookup"><span data-stu-id="a0088-132">2 Dec 16</span></span>
    
- <span data-ttu-id="a0088-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="a0088-133">2/12/2016</span></span>
    
- <span data-ttu-id="a0088-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="a0088-134">02/12/16</span></span>
    
- <span data-ttu-id="a0088-135">2-Dic-2016</span><span class="sxs-lookup"><span data-stu-id="a0088-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="a0088-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a0088-136">2-12-16</span></span>
    
<span data-ttu-id="a0088-137">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a0088-137">Accepted month names:</span></span>
  
- <span data-ttu-id="a0088-138">English</span><span class="sxs-lookup"><span data-stu-id="a0088-138">English</span></span>
    
  - <span data-ttu-id="a0088-139">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a0088-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a0088-140">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="a0088-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="a0088-141">Dutch</span><span class="sxs-lookup"><span data-stu-id="a0088-141">Dutch</span></span>
    
  - <span data-ttu-id="a0088-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="a0088-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="a0088-143">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="a0088-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="a0088-144">French</span><span class="sxs-lookup"><span data-stu-id="a0088-144">French</span></span>
    
  - <span data-ttu-id="a0088-145">Janvier, février, Mars, Avril, Mai, juin Juillet, Août, Septembre, octobre, Novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="a0088-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="a0088-146">janv.</span><span class="sxs-lookup"><span data-stu-id="a0088-146">janv.</span></span> <span data-ttu-id="a0088-147">févr.</span><span class="sxs-lookup"><span data-stu-id="a0088-147">févr.</span></span> <span data-ttu-id="a0088-148">Mars Avril Mai juin juil.</span><span class="sxs-lookup"><span data-stu-id="a0088-148">mars avril mai juin juil.</span></span> <span data-ttu-id="a0088-149">Août Sept.</span><span class="sxs-lookup"><span data-stu-id="a0088-149">août sept.</span></span> <span data-ttu-id="a0088-150">Oct.</span><span class="sxs-lookup"><span data-stu-id="a0088-150">oct.</span></span> <span data-ttu-id="a0088-151">noviembre.</span><span class="sxs-lookup"><span data-stu-id="a0088-151">nov.</span></span> <span data-ttu-id="a0088-152">déc.</span><span class="sxs-lookup"><span data-stu-id="a0088-152">déc.</span></span>
    
- <span data-ttu-id="a0088-153">German</span><span class="sxs-lookup"><span data-stu-id="a0088-153">German</span></span>
    
  - <span data-ttu-id="a0088-154">Januar, Februar, März, April, Mai, Juni Juli, agosto, septiembre, Oktober, noviembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="a0088-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="a0088-155">Ene./Jän.</span><span class="sxs-lookup"><span data-stu-id="a0088-155">Jan./Jän.</span></span> <span data-ttu-id="a0088-156">Feb. März Apr. Mai Juni Juli agosto de la OKT.</span><span class="sxs-lookup"><span data-stu-id="a0088-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="a0088-157">Nov dez.</span><span class="sxs-lookup"><span data-stu-id="a0088-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="a0088-158">Italian</span><span class="sxs-lookup"><span data-stu-id="a0088-158">Italian</span></span>
    
  - <span data-ttu-id="a0088-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="a0088-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="a0088-160">genn.</span><span class="sxs-lookup"><span data-stu-id="a0088-160">genn.</span></span> <span data-ttu-id="a0088-161">febbr.</span><span class="sxs-lookup"><span data-stu-id="a0088-161">febbr.</span></span> <span data-ttu-id="a0088-162">graduación.</span><span class="sxs-lookup"><span data-stu-id="a0088-162">mar.</span></span> <span data-ttu-id="a0088-163">TA.</span><span class="sxs-lookup"><span data-stu-id="a0088-163">apr.</span></span> <span data-ttu-id="a0088-164">magg.</span><span class="sxs-lookup"><span data-stu-id="a0088-164">magg.</span></span> <span data-ttu-id="a0088-165">Giugno Luglio AG.</span><span class="sxs-lookup"><span data-stu-id="a0088-165">giugno luglio ag.</span></span> <span data-ttu-id="a0088-166">sett.</span><span class="sxs-lookup"><span data-stu-id="a0088-166">sett.</span></span> <span data-ttu-id="a0088-167">ott.</span><span class="sxs-lookup"><span data-stu-id="a0088-167">ott.</span></span> <span data-ttu-id="a0088-168">noviembre.</span><span class="sxs-lookup"><span data-stu-id="a0088-168">nov.</span></span> <span data-ttu-id="a0088-169">Dic.</span><span class="sxs-lookup"><span data-stu-id="a0088-169">dic.</span></span>
    
- <span data-ttu-id="a0088-170">Portugués</span><span class="sxs-lookup"><span data-stu-id="a0088-170">Portuguese</span></span>
    
  - <span data-ttu-id="a0088-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="a0088-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="a0088-172">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="a0088-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="a0088-173">Spanish</span><span class="sxs-lookup"><span data-stu-id="a0088-173">Spanish</span></span>
    
  - <span data-ttu-id="a0088-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a0088-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="a0088-175">Enero Feb.</span><span class="sxs-lookup"><span data-stu-id="a0088-175">enero feb.</span></span> <span data-ttu-id="a0088-176">marzo Abr.</span><span class="sxs-lookup"><span data-stu-id="a0088-176">marzo abr.</span></span> <span data-ttu-id="a0088-177">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="a0088-177">mayo jun.</span></span> <span data-ttu-id="a0088-178">Julio.</span><span class="sxs-lookup"><span data-stu-id="a0088-178">jul.</span></span> <span data-ttu-id="a0088-179">Agosto Sept./set.</span><span class="sxs-lookup"><span data-stu-id="a0088-179">agosto sept./set.</span></span> <span data-ttu-id="a0088-180">Oct.</span><span class="sxs-lookup"><span data-stu-id="a0088-180">oct.</span></span> <span data-ttu-id="a0088-181">noviembre.</span><span class="sxs-lookup"><span data-stu-id="a0088-181">nov.</span></span> <span data-ttu-id="a0088-182">Dic.</span><span class="sxs-lookup"><span data-stu-id="a0088-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="a0088-183">Func_eu_date1 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="a0088-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="a0088-184">Esta función está en desuso porque solo admite nombres de mes en Portugués, que ahora están incluidos en la `Func_eu_date` función anterior.</span><span class="sxs-lookup"><span data-stu-id="a0088-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="a0088-185">Esta función busca una fecha en el formato que suele usarse en portugués.</span><span class="sxs-lookup"><span data-stu-id="a0088-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="a0088-186">El formato de esta función es el mismo que `Func_eu_date` en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="a0088-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="a0088-187">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a0088-187">Examples:</span></span>
  
- <span data-ttu-id="a0088-188">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="a0088-189">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-189">02 dez 2016</span></span>
    
- <span data-ttu-id="a0088-190">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="a0088-190">2 Dez 16</span></span>
    
- <span data-ttu-id="a0088-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="a0088-191">2/12/2016</span></span>
    
- <span data-ttu-id="a0088-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="a0088-192">02/12/16</span></span>
    
- <span data-ttu-id="a0088-193">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="a0088-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="a0088-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a0088-194">2-12-16</span></span>
    
<span data-ttu-id="a0088-195">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a0088-195">Accepted month names:</span></span>
  
- <span data-ttu-id="a0088-196">Portugués</span><span class="sxs-lookup"><span data-stu-id="a0088-196">Portuguese</span></span>
    
  - <span data-ttu-id="a0088-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="a0088-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="a0088-198">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="a0088-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="a0088-199">Func_eu_date2 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="a0088-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="a0088-200">Esta función está en desuso porque solo admite nombres de mes en holandés, que ahora están incluidos en la `Func_eu_date` función anterior.</span><span class="sxs-lookup"><span data-stu-id="a0088-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="a0088-201">Esta función busca una fecha en el formato que suele usarse en neerlandés.</span><span class="sxs-lookup"><span data-stu-id="a0088-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="a0088-202">El formato de esta función es el mismo que `Func_eu_date` en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="a0088-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="a0088-203">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a0088-203">Examples:</span></span>
  
- <span data-ttu-id="a0088-204">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="a0088-205">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="a0088-205">02 mei 2016</span></span>
    
- <span data-ttu-id="a0088-206">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="a0088-206">2 Mei 16</span></span>
    
- <span data-ttu-id="a0088-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="a0088-207">2/12/2016</span></span>
    
- <span data-ttu-id="a0088-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="a0088-208">02/12/16</span></span>
    
- <span data-ttu-id="a0088-209">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="a0088-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="a0088-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a0088-210">2-12-16</span></span>
    
<span data-ttu-id="a0088-211">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a0088-211">Accepted month names:</span></span>
  
- <span data-ttu-id="a0088-212">Dutch</span><span class="sxs-lookup"><span data-stu-id="a0088-212">Dutch</span></span>
    
  - <span data-ttu-id="a0088-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="a0088-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="a0088-214">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="a0088-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="a0088-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="a0088-215">Func_expiration_date</span></span>

<span data-ttu-id="a0088-216">Esta función busca una fecha en los formatos que suelen usarse en las tarjetas de crédito y débito, que excluyen los días a favor de los meses.</span><span class="sxs-lookup"><span data-stu-id="a0088-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="a0088-217">Esta función coincidirá con las fechas en el formato "mes/año", "mes-año", "[nombre del mes]" y "[abreviatura del mes] año".</span><span class="sxs-lookup"><span data-stu-id="a0088-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="a0088-218">Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a0088-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="a0088-219">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a0088-219">Examples:</span></span>
  
- <span data-ttu-id="a0088-220">MM/AA: por ejemplo, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="a0088-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="a0088-221">MM/AAAA: por ejemplo, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="a0088-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="a0088-222">MM-AA: por ejemplo 01-11 o 1-11</span><span class="sxs-lookup"><span data-stu-id="a0088-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="a0088-223">MM-AAAA: por ejemplo 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="a0088-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="a0088-224">Los formatos siguientes admiten AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="a0088-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="a0088-225">Mes-YYYY--por ejemplo, Ene-2010 o enero-2010 o ene-10 o enero-10</span><span class="sxs-lookup"><span data-stu-id="a0088-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="a0088-226">Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"</span><span class="sxs-lookup"><span data-stu-id="a0088-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="a0088-227">MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"</span><span class="sxs-lookup"><span data-stu-id="a0088-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="a0088-228">Mes/AAAA: por ejemplo, "enero/2010" o "ene/2010" o "enero/10" o "ene/10"</span><span class="sxs-lookup"><span data-stu-id="a0088-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="a0088-229">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a0088-229">Accepted month names:</span></span>
  
- <span data-ttu-id="a0088-230">English</span><span class="sxs-lookup"><span data-stu-id="a0088-230">English</span></span>
    
  - <span data-ttu-id="a0088-231">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a0088-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a0088-232">Jan Feb Marzo Apr mayo junio julio agosto Sept Oct Nov Dic</span><span class="sxs-lookup"><span data-stu-id="a0088-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="a0088-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="a0088-233">Func_us_address</span></span>

<span data-ttu-id="a0088-234">Esta función busca un nombre de estado de Estados Unidos o una abreviatura postal seguida de un código postal válido, tal y como se usan en las direcciones postales.</span><span class="sxs-lookup"><span data-stu-id="a0088-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="a0088-235">El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura.</span><span class="sxs-lookup"><span data-stu-id="a0088-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="a0088-236">El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.</span><span class="sxs-lookup"><span data-stu-id="a0088-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="a0088-237">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a0088-237">Examples:</span></span>
  
- <span data-ttu-id="a0088-238">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="a0088-238">Washington 98052</span></span>
    
- <span data-ttu-id="a0088-239">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="a0088-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="a0088-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="a0088-240">WA 98052</span></span>
    
- <span data-ttu-id="a0088-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="a0088-241">WA 98052-9998</span></span>
    

