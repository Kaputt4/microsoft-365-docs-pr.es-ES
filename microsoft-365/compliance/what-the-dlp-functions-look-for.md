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
# <a name="what-the-dlp-functions-look-for"></a>Qué buscan las funciones de DLP

Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.
  
En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos. Para obtener más información, vea [tipos de información confidencial definiciones de entidades](sensitive-information-type-entity-definitions.md)
  
## <a name="func_us_date"></a>Func_us_date

Esta función busca una fecha con el formato que se usa habitualmente en Estados Unidos. Esto incluye los formatos "month/Day/Year", "month-Day-Year" y "month Day Year". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas. 
  
Ejemplos:
  
- 2 de diciembre de 2016
    
- 2 de diciembre de 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nombres de mes aceptados:
  
- English
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.
    
## <a name="func_eu_date"></a>Func_eu_date

This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.
  
Ejemplos:
  
- 2 Dec 2016
    
- 02 Dec 2016
    
- 2 16 de diciembre
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dic-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- English
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.
    
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec
    
- French
    
  - Janvier, février, Mars, Avril, Mai, juin Juillet, Août, Septembre, octobre, Novembre, décembre
    
  - janv. févr. Mars Avril Mai juin juil. Août Sept. Oct. noviembre. déc.
    
- German
    
  - Januar, Februar, März, April, Mai, Juni Juli, agosto, septiembre, Oktober, noviembre, Dezember
    
  - Ene./Jän. Feb. März Apr. Mai Juni Juli agosto de la OKT. Nov dez.
    
- Italian
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. graduación. TA. magg. Giugno Luglio AG. sett. ott. noviembre. Dic.
    
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV mar abr Mai Jun-Nov hace dez
    
- Spanish
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Enero Feb. marzo Abr. Mayo Jun. Julio. Agosto Sept./set. Oct. noviembre. Dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes en Portugués, que ahora están incluidos en la `Func_eu_date` función anterior. 
  
Esta función busca una fecha en el formato que suele usarse en portugués. El formato de esta función es el mismo que `Func_eu_date` en el idioma usado.
  
Ejemplos:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV mar abr Mai Jun-Nov hace dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes en holandés, que ahora están incluidos en la `Func_eu_date` función anterior. 
  
Esta función busca una fecha en el formato que suele usarse en neerlandés. El formato de esta función es el mismo que `Func_eu_date` en el idioma usado.
  
Ejemplos:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Esta función busca una fecha en los formatos que suelen usarse en las tarjetas de crédito y débito, que excluyen los días a favor de los meses. Esta función coincidirá con las fechas en el formato "mes/año", "mes-año", "[nombre del mes]" y "[abreviatura del mes] año". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- MM/AA: por ejemplo, 01/11 o 1/11
    
- MM/AAAA: por ejemplo, 01/2011 o 1/2011
    
- MM-AA: por ejemplo 01-11 o 1-11
    
- MM-AAAA: por ejemplo 01-2000 o 1-2000
    
Los formatos siguientes admiten AA o AAAA:
  
- Mes-AAAA: por ejemplo, ene-2010, enero-2010, ene-10 o enero-10
    
- Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"
    
- MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"
    
- Mes/AAAA: por ejemplo, "enero/2010" o "ene/2010" o "enero/10" o "ene/10"
    
Nombres de mes aceptados:
  
- English
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Jan Feb Marzo Apr mayo junio julio agosto Sept Oct Nov Dic
    
## <a name="func_us_address"></a>Func_us_address

This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.
  
Ejemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

