---
title: Qué buscan las funciones de DLP
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
description: Obtenga información sobre qué buscan las funciones de prevención de pérdida de datos (DLP) para ayudarle a comprender cómo funcionan los tipos de información confidencial predefinidos.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819280"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="d1355-103">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="d1355-103">What the DLP functions look for</span></span>

<span data-ttu-id="d1355-p101">La Prevención de pérdida de datos (DLP) incluye tipos de información confidencial, como el número de tarjeta de crédito y el número de tarjeta de débito de la UE, que están listos para su uso en las directivas de DLP. Estos tipos de información confidencial buscan un patrón específico y lo comprueban asegurándose de que el formato es el adecuado, forzando las sumas de comprobación y buscando palabras clave pertinentes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial de la tarjeta de crédito usa una función para buscar fechas con formato como la fecha de vencimiento, que ayuda a comprobar que un número es un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="d1355-p101">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="d1355-108">En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos.</span><span class="sxs-lookup"><span data-stu-id="d1355-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="d1355-109">Para obtener más información, vea [tipos de información confidencial definiciones de entidades](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="d1355-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="d1355-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="d1355-110">Func_us_date</span></span>

<span data-ttu-id="d1355-111">Esta función busca una fecha con el formato que se usa habitualmente en Estados Unidos. Esto incluye los formatos "month/Day/Year", "month-Day-Year" y "month Day Year".</span><span class="sxs-lookup"><span data-stu-id="d1355-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="d1355-112">Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d1355-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="d1355-113">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1355-113">Examples:</span></span>
  
- <span data-ttu-id="d1355-114">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-114">December 2, 2016</span></span>
    
- <span data-ttu-id="d1355-115">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="d1355-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-116">dec 02 2016</span></span>
    
- <span data-ttu-id="d1355-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="d1355-117">12/2/2016</span></span>
    
- <span data-ttu-id="d1355-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="d1355-118">12/02/16</span></span>
    
- <span data-ttu-id="d1355-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="d1355-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="d1355-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="d1355-120">12-2-16</span></span>
    
<span data-ttu-id="d1355-121">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="d1355-121">Accepted month names:</span></span>
  
- <span data-ttu-id="d1355-122">English</span><span class="sxs-lookup"><span data-stu-id="d1355-122">English</span></span>
    
  - <span data-ttu-id="d1355-123">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="d1355-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d1355-124">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="d1355-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="d1355-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="d1355-125">Func_eu_date</span></span>

<span data-ttu-id="d1355-p104">Esta función busca una fecha en el formato que suele usarse en la UE (y en la mayoría de lugares fuera de los Estados Unidos). Esto incluye los formatos de "día/mes/año", "día-mes-año" y "día mes año". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d1355-p104">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="d1355-130">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1355-130">Examples:</span></span>
  
- <span data-ttu-id="d1355-131">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="d1355-132">02 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-132">02 dec 2016</span></span>
    
- <span data-ttu-id="d1355-133">2 16 de diciembre</span><span class="sxs-lookup"><span data-stu-id="d1355-133">2 Dec 16</span></span>
    
- <span data-ttu-id="d1355-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d1355-134">2/12/2016</span></span>
    
- <span data-ttu-id="d1355-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d1355-135">02/12/16</span></span>
    
- <span data-ttu-id="d1355-136">2-Dic-2016</span><span class="sxs-lookup"><span data-stu-id="d1355-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="d1355-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d1355-137">2-12-16</span></span>
    
<span data-ttu-id="d1355-138">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="d1355-138">Accepted month names:</span></span>
  
- <span data-ttu-id="d1355-139">English</span><span class="sxs-lookup"><span data-stu-id="d1355-139">English</span></span>
    
  - <span data-ttu-id="d1355-140">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="d1355-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d1355-141">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="d1355-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="d1355-142">Dutch</span><span class="sxs-lookup"><span data-stu-id="d1355-142">Dutch</span></span>
    
  - <span data-ttu-id="d1355-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="d1355-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="d1355-144">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="d1355-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="d1355-145">French</span><span class="sxs-lookup"><span data-stu-id="d1355-145">French</span></span>
    
  - <span data-ttu-id="d1355-146">Janvier, février, Mars, Avril, Mai, juin Juillet, Août, Septembre, octobre, Novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="d1355-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="d1355-147">janv.</span><span class="sxs-lookup"><span data-stu-id="d1355-147">janv.</span></span> <span data-ttu-id="d1355-148">févr.</span><span class="sxs-lookup"><span data-stu-id="d1355-148">févr.</span></span> <span data-ttu-id="d1355-149">Mars Avril Mai juin juil.</span><span class="sxs-lookup"><span data-stu-id="d1355-149">mars avril mai juin juil.</span></span> <span data-ttu-id="d1355-150">Août Sept.</span><span class="sxs-lookup"><span data-stu-id="d1355-150">août sept.</span></span> <span data-ttu-id="d1355-151">Oct.</span><span class="sxs-lookup"><span data-stu-id="d1355-151">oct.</span></span> <span data-ttu-id="d1355-152">noviembre.</span><span class="sxs-lookup"><span data-stu-id="d1355-152">nov.</span></span> <span data-ttu-id="d1355-153">déc.</span><span class="sxs-lookup"><span data-stu-id="d1355-153">déc.</span></span>
    
- <span data-ttu-id="d1355-154">German</span><span class="sxs-lookup"><span data-stu-id="d1355-154">German</span></span>
    
  - <span data-ttu-id="d1355-155">Januar, Februar, März, April, Mai, Juni Juli, agosto, septiembre, Oktober, noviembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="d1355-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="d1355-156">Ene./Jän.</span><span class="sxs-lookup"><span data-stu-id="d1355-156">Jan./Jän.</span></span> <span data-ttu-id="d1355-157">Feb. März Apr. Mai Juni Juli agosto de la OKT.</span><span class="sxs-lookup"><span data-stu-id="d1355-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="d1355-158">Nov dez.</span><span class="sxs-lookup"><span data-stu-id="d1355-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="d1355-159">Italian</span><span class="sxs-lookup"><span data-stu-id="d1355-159">Italian</span></span>
    
  - <span data-ttu-id="d1355-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="d1355-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="d1355-161">genn.</span><span class="sxs-lookup"><span data-stu-id="d1355-161">genn.</span></span> <span data-ttu-id="d1355-162">febbr.</span><span class="sxs-lookup"><span data-stu-id="d1355-162">febbr.</span></span> <span data-ttu-id="d1355-163">graduación.</span><span class="sxs-lookup"><span data-stu-id="d1355-163">mar.</span></span> <span data-ttu-id="d1355-164">TA.</span><span class="sxs-lookup"><span data-stu-id="d1355-164">apr.</span></span> <span data-ttu-id="d1355-165">magg.</span><span class="sxs-lookup"><span data-stu-id="d1355-165">magg.</span></span> <span data-ttu-id="d1355-166">Giugno Luglio AG.</span><span class="sxs-lookup"><span data-stu-id="d1355-166">giugno luglio ag.</span></span> <span data-ttu-id="d1355-167">sett.</span><span class="sxs-lookup"><span data-stu-id="d1355-167">sett.</span></span> <span data-ttu-id="d1355-168">ott.</span><span class="sxs-lookup"><span data-stu-id="d1355-168">ott.</span></span> <span data-ttu-id="d1355-169">noviembre.</span><span class="sxs-lookup"><span data-stu-id="d1355-169">nov.</span></span> <span data-ttu-id="d1355-170">Dic.</span><span class="sxs-lookup"><span data-stu-id="d1355-170">dic.</span></span>
    
- <span data-ttu-id="d1355-171">Portugués</span><span class="sxs-lookup"><span data-stu-id="d1355-171">Portuguese</span></span>
    
  - <span data-ttu-id="d1355-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="d1355-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="d1355-173">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="d1355-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="d1355-174">Spanish</span><span class="sxs-lookup"><span data-stu-id="d1355-174">Spanish</span></span>
    
  - <span data-ttu-id="d1355-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="d1355-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="d1355-176">Enero Feb.</span><span class="sxs-lookup"><span data-stu-id="d1355-176">enero feb.</span></span> <span data-ttu-id="d1355-177">marzo Abr.</span><span class="sxs-lookup"><span data-stu-id="d1355-177">marzo abr.</span></span> <span data-ttu-id="d1355-178">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="d1355-178">mayo jun.</span></span> <span data-ttu-id="d1355-179">Julio.</span><span class="sxs-lookup"><span data-stu-id="d1355-179">jul.</span></span> <span data-ttu-id="d1355-180">Agosto Sept./set.</span><span class="sxs-lookup"><span data-stu-id="d1355-180">agosto sept./set.</span></span> <span data-ttu-id="d1355-181">Oct.</span><span class="sxs-lookup"><span data-stu-id="d1355-181">oct.</span></span> <span data-ttu-id="d1355-182">noviembre.</span><span class="sxs-lookup"><span data-stu-id="d1355-182">nov.</span></span> <span data-ttu-id="d1355-183">Dic.</span><span class="sxs-lookup"><span data-stu-id="d1355-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="d1355-184">Func_eu_date1 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="d1355-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="d1355-185">Esta función está en desuso porque solo admite nombres de mes en Portugués, que ahora están incluidos en la `Func_eu_date` función anterior.</span><span class="sxs-lookup"><span data-stu-id="d1355-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="d1355-186">Esta función busca una fecha en el formato que suele usarse en portugués.</span><span class="sxs-lookup"><span data-stu-id="d1355-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="d1355-187">El formato de esta función es el mismo que `Func_eu_date` en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="d1355-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="d1355-188">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1355-188">Examples:</span></span>
  
- <span data-ttu-id="d1355-189">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="d1355-190">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-190">02 dez 2016</span></span>
    
- <span data-ttu-id="d1355-191">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="d1355-191">2 Dez 16</span></span>
    
- <span data-ttu-id="d1355-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d1355-192">2/12/2016</span></span>
    
- <span data-ttu-id="d1355-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d1355-193">02/12/16</span></span>
    
- <span data-ttu-id="d1355-194">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="d1355-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="d1355-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d1355-195">2-12-16</span></span>
    
<span data-ttu-id="d1355-196">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="d1355-196">Accepted month names:</span></span>
  
- <span data-ttu-id="d1355-197">Portugués</span><span class="sxs-lookup"><span data-stu-id="d1355-197">Portuguese</span></span>
    
  - <span data-ttu-id="d1355-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="d1355-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="d1355-199">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="d1355-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="d1355-200">Func_eu_date2 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="d1355-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="d1355-201">Esta función está en desuso porque solo admite nombres de mes en holandés, que ahora están incluidos en la `Func_eu_date` función anterior.</span><span class="sxs-lookup"><span data-stu-id="d1355-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="d1355-202">Esta función busca una fecha en el formato que suele usarse en neerlandés.</span><span class="sxs-lookup"><span data-stu-id="d1355-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="d1355-203">El formato de esta función es el mismo que `Func_eu_date` en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="d1355-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="d1355-204">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1355-204">Examples:</span></span>
  
- <span data-ttu-id="d1355-205">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="d1355-206">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="d1355-206">02 mei 2016</span></span>
    
- <span data-ttu-id="d1355-207">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="d1355-207">2 Mei 16</span></span>
    
- <span data-ttu-id="d1355-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d1355-208">2/12/2016</span></span>
    
- <span data-ttu-id="d1355-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d1355-209">02/12/16</span></span>
    
- <span data-ttu-id="d1355-210">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="d1355-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="d1355-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d1355-211">2-12-16</span></span>
    
<span data-ttu-id="d1355-212">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="d1355-212">Accepted month names:</span></span>
  
- <span data-ttu-id="d1355-213">Dutch</span><span class="sxs-lookup"><span data-stu-id="d1355-213">Dutch</span></span>
    
  - <span data-ttu-id="d1355-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="d1355-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="d1355-215">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="d1355-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="d1355-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="d1355-216">Func_expiration_date</span></span>

<span data-ttu-id="d1355-217">Esta función busca una fecha en los formatos que suelen usarse en las tarjetas de crédito y débito, que excluyen los días a favor de los meses.</span><span class="sxs-lookup"><span data-stu-id="d1355-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="d1355-218">Esta función coincidirá con las fechas en el formato "mes/año", "mes-año", "[nombre del mes]" y "[abreviatura del mes] año".</span><span class="sxs-lookup"><span data-stu-id="d1355-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="d1355-219">Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d1355-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="d1355-220">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1355-220">Examples:</span></span>
  
- <span data-ttu-id="d1355-221">MM/AA: por ejemplo, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="d1355-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="d1355-222">MM/AAAA: por ejemplo, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="d1355-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="d1355-223">MM-AA: por ejemplo 01-11 o 1-11</span><span class="sxs-lookup"><span data-stu-id="d1355-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="d1355-224">MM-AAAA: por ejemplo 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="d1355-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="d1355-225">Los formatos siguientes admiten AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="d1355-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="d1355-226">Mes-AAAA: por ejemplo, ene-2010, enero-2010, ene-10 o enero-10</span><span class="sxs-lookup"><span data-stu-id="d1355-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="d1355-227">Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"</span><span class="sxs-lookup"><span data-stu-id="d1355-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="d1355-228">MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"</span><span class="sxs-lookup"><span data-stu-id="d1355-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="d1355-229">Mes/AAAA: por ejemplo, "enero/2010" o "ene/2010" o "enero/10" o "ene/10"</span><span class="sxs-lookup"><span data-stu-id="d1355-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="d1355-230">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="d1355-230">Accepted month names:</span></span>
  
- <span data-ttu-id="d1355-231">English</span><span class="sxs-lookup"><span data-stu-id="d1355-231">English</span></span>
    
  - <span data-ttu-id="d1355-232">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="d1355-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d1355-233">Jan Feb Marzo Apr mayo junio julio agosto Sept Oct Nov Dic</span><span class="sxs-lookup"><span data-stu-id="d1355-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="d1355-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="d1355-234">Func_us_address</span></span>

<span data-ttu-id="d1355-p112">Esta función busca un nombre de estado de los Estados Unidos o una abreviatura postal seguidos de un código postal válido, tal como se usan en las direcciones postales. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.</span><span class="sxs-lookup"><span data-stu-id="d1355-p112">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="d1355-238">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1355-238">Examples:</span></span>
  
- <span data-ttu-id="d1355-239">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="d1355-239">Washington 98052</span></span>
    
- <span data-ttu-id="d1355-240">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="d1355-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="d1355-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="d1355-241">WA 98052</span></span>
    
- <span data-ttu-id="d1355-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="d1355-242">WA 98052-9998</span></span>
    

