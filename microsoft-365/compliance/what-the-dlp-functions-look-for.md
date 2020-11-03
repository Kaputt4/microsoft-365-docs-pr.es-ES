---
title: Qué buscan las funciones de prevención de pérdida de datos (DLP)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841451"
---
# <a name="what-the-dlp-functions-look-for"></a>Qué buscan las funciones de DLP

Las directivas de prevención de pérdida de datos (DLP) pueden usar tipos de información confidencial para identificar elementos confidenciales. Número de tarjeta de crédito y número de tarjeta de débito de la UE son ejemplos de tipos de información confidencial. Los tipos de información confidencial buscan patrones específicos. Los tipos de información confidencial validan los datos mirando su formato, sus sumas de comprobación y buscan palabras clave u otra información relevantes. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial de número de tarjeta de crédito usa una función para buscar las fechas que tienen formato de fecha de caducidad. Esto ayuda a corroborar que un número es un número de tarjeta de crédito.
  
En este artículo se explica lo que buscan estas funciones para ayudarle a comprender cómo funcionan los tipos de información confidencial predefinidos. Para obtener más información, vea [tipos de información confidencial definiciones de entidades](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Tabla de funciones

|nombre de la función  |acción de la función  |es un validador|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|detecta y valida la clave fiscal única de Argentina|no|
|Func_aba_routing|detecta el número de enrutamiento ABA| sí|
|Func_alabama_drivers_license_number|detecta el número de permiso de conducción de Alabama|no|
|Func_alaska_delaware_oregon_drivers_license_number|detecta el número de permiso de conducción de Alaska, Delaware y Oregón|no|
|Func_alaska_drivers_license_number|detecta el número de permiso de conducción de Alaska|no|
|Func_alberta_drivers_license_number|detecta el número de permiso de conducción de Alberta|no|
|Func_Argentina_Unique_Tax_Key|detecta la clave fiscal única de Argentina|no|
|Func_arizona_drivers_license_number|detecta el número de permiso de conducción de Arizona|no|
|Func_arkansas_drivers_license_number|detecta el número de licencia de conducir de Arkansas|no|
|Func_australian_business_number|detecta el número de empresa de Australia|no|
|Func_Australian_Company_Number|detecta el número de empresa de Australia|no|
|Func_australian_medical_account_number|detecta el número de cuenta médica de Australia|no|
|Func_australian_tax_file_number|detecta el número de archivo de impuestos de Australia|sí|
|Func_austria_eu_ssn_or_equivalent|detecta el número de la seguridad social de Austria|no|
|Func_austria_eu_tax_file_number|detecta el número de archivo de impuestos de Austria|no|
|Func_Austria_Value_Added_Tax|detecta el impuesto sobre el valor añadido de Austria|no|
|Func_belgium_national_number|detecta el número nacional de Bélgica|no|
|Func_belgium_value_added_tax_number|detecta el número del impuesto sobre el valor añadido de Bélgica|no|
|Func_brazil_cnpj|detecta el número de entidad legal de Brasil (CNPJ)|sí|
|Func_brazil_cpf|detecta la CPF de Brasil|sí|
|Func_brazil_rg|detecta el RG de Brasil|no|
|Func_british_columbia_drivers_license_number|detecta el número de permiso de conducción de British Columbia|no|
|Func_bulgaria_eu_national_id_card|detecta el número civil uniforme de Bulgaria|no|
|Func_california_drivers_license_number|detecta el número de permiso de conducción de California|no|
|Func_canadian_sin|detecta Canada sin|sí|
|Func_chile_id_card|detecta la tarjeta de identificación de Chile|no|
|Func_china_resident_id|detecta el identificador residente de China|no|
|Func_colorado_drivers_license_number|detecta el número de permiso de conducción de Colorado|no|
|Func_connecticut_drivers_license_number|detecta el número de licencia de conducir de Connecticut|no|
|Func_credit_card|detecta una tarjeta de crédito|sí|no|
|Func_croatia_id_card|detecta la tarjeta de identificación de Croacia|no|
|Func_croatia_oib_number|detecta el número de OIB de Croacia|no|
|Func_cyprus_eu_tax_file_number|detecta el número de archivo de impuestos de Chipre|no|
|Func_czech_id_card|detecta la tarjeta de identificación Checa|no|
|Func_czech_id_card_new_format|detecta la tarjeta de identificación Checa en el nuevo formato|no|
|Func_dea_number|detecta el número de DEA|sí|
|Func_denmark_eu_tax_file_number|detecta el número de identificación personal de Dinamarca|no|
|Func_district_of_columbia_drivers_license_number|detecta el distrito del número de permiso de conducción de Columbia|no|
|Func_estonia_eu_national_id_card|detecta el código de identificación personal de Estonia|no|
|Func_eu_debit_card|detecta una tarjeta de débito de la UE|no|
|Func_finnish_national_id|detecta el identificador nacional finlandés|no|
|Func_florida_drivers_license_number|detecta el número de licencia de conducir de Florida|no|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|detecta el número de permiso de conducción de Florida, Maryland, Michigan y Minnesota.|no|
|Func_formatted_itin|detecta el formato US ÉLEN|sí|
|Func_fr_insee|detecta la INSEE de Francia|no|
|Func_fr_passport|detecta el pasaporte de Francia|no|
|Func_france_eu_tax_file_number|detecta el número de archivo de impuestos de Francia|no|
|Func_france_value_added_tax_number|detecta el número de impuesto sobre el valor añadido de Francia|no|
|Func_french_drivers_license|detecta la licencia de la conducción francesa|no|
|Func_french_insee|detecta INSEE en francés|no|
|Func_georgia_drivers_license_number|detecta el número de permiso de conducción de Georgia|no|
|Func_german_drivers_license|detecta el permiso de conducción de Alemania|no|
|Func_german_passport|detecta el pasaporte de Alemania|no|
|Func_german_passport_data|detecta el pasaporte de Alemania|no|
|Func_germany_eu_tax_file_number|detecta el número de archivo de impuestos de Alemania|no|
|Func_germany_value_added_tax_number|detecta el número de impuesto sobre el valor añadido de Alemania|no|
|Func_greece_eu_ssn|detecta Grecia sin (AMKA)|no|
|Func_hawaii_drivers_license_number|detecta el número de permiso de conducción de Hawai|no|
|Func_hong_kong_id_card |detecta la tarjeta de identificación de Hong Kong|no|
|Func_hungarian_value_added_tax_number|detecta el número de impuesto sobre el valor añadido en Hungría|no|
|Func_hungary_eu_national_id_card|detecta el número de identificación personal de Hungría|no|
|Func_hungary_eu_ssn_or_equivalent|detecta el número de seguridad social de Hungría|no|
|Func_hungary_eu_tax_file_number|detecta el número de archivo de impuestos de Hungría|no|
|Func_iban|detecta el IBAN|sí|
|Func_idaho_drivers_license_number|detecta el número de licencia de conducir de Idaho|no|
|Func_illinois_drivers_license_number|detecta el número de licencia de conducir de Illinois|no|
|Func_india_aadhaar|detecta la India Aadhaar|sí|
|Func_indiana_drivers_license_number|detecta el número de licencia de conducir de Indiana|no|
|Func_iowa_drivers_license_number|detecta el número de licencia de conducir de Iowa|no|
|Func_ireland_pps|detecta el PPS de Irlanda|no|
|Func_israeli_national_id_number|detecta el número de identificación nacional de Israel|no|
|Func_italy_eu_national_id_card |detecta el código fiscal de Italia|no|
|Func_italy_value_added_tax_number|detecta el número de impuesto sobre el valor añadido en Italia|no|
|Func_japanese_my_number_corporate|detecta el número corporativo de Japón|sí|
|Func_japanese_my_number_personal|detecta el número personal de Japón|sí|
|Func_jp_bank_account|detecta la cuenta bancaria de Japón|no|
|Func_jp_bank_account_branch_code|detecta el código de sucursal de la cuenta bancaria de Japón|no|
|Func_jp_drivers_license_number|detecta el número de permiso de conducción de Japón|no|
|Func_jp_passport|detecta Passport para Japón|no|
|Func_jp_resident_registration_number|detecta el número de registro de residente de Japón|no|
|Func_jp_sin|detecta japonés SIN|no|
|Func_jp_sin_pre_1997|detecta Japón sin pre 1997|no|
|Func_kansas_drivers_license_number|detecta el número de permiso de conducción de Kansas|no|
|Func_kentucky_drivers_license_number|detecta el número de permiso de conducción de Kentucky|no|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detecta el número de permiso de conducción de Kentucky, Massachusetts y Virginia|no|
|Func_latvia_eu_national_id_card|detecta el código personal de Letonia|no|
|Func_lithuania_eu_tax_file_number|detecta el código personal de Lituania|no|
|Func_louisiana_drivers_license_number|detecta el número de permiso de conducción de Louisiana|no|
|Func_luxemburg_eu_tax_file_number|detecta el número de identificación nacional de Luxemburgo (personas físicas)|no|
|Func_luxemburg_eu_tax_file_number_non_natural|detecta el número de identificación nacional de Luxemburgo (personas no físicas)|no|
|Func_maine_drivers_license_number|detecta el número de permiso de conducción de Maine|no|
|Func_manitoba_drivers_license_number|detecta el número de permiso de conducción del Manitoba|no|
|Func_maryland_drivers_license_number|detecta el número de permiso de conducción de la Maryland|no|
|Func_massachusetts_drivers_license_number|detecta el número de permiso de conducción de Massachusetts|no|
|Func_mexico_population_registry_code|detecta el código del registro de llenado de México|no|
|Func_michigan_minnesota_drivers_license_number|detecta el número de licencia de conductor de Michigan, Minnesota|no|
|Func_minnesota_drivers_license_number|detecta el número de permiso de conducción de Minnesota|no|
|Func_mississippi_oklahoma_drivers_license_number|detecta Misisipi, número de licencia de conducir de Oklahoma|no|
|Func_missouri_drivers_license_number|detecta el número de permiso de conducción de Missouri|no|
|Func_montana_drivers_license_number|detecta el número de licencia de conducir de Montana|no|
|Func_nebraska_drivers_license_number|detecta el número de licencia de conducir de Nebraska|no|
|Func_netherlands_bsn|detecta los países bajos BSN|no|
|Func_netherlands_eu_tax_file_number|detecta el número de archivo de impuestos de Holanda|no|
|Func_netherlands_value_added_tax_number|detecta el número del impuesto sobre el valor añadido para los países bajos|no|
|Func_nevada_drivers_license_number|detecta el número de permiso de conducción de Nevada|no|
|Func_new_brunswick_drivers_license_number|detecta el nuevo número de licencia del conductor de Brunswick|no|
|Func_new_hampshire_drivers_license_number|detecta el nuevo número de permiso de conducción de la Hampshire|no|
|Func_new_jersey_drivers_license_number |detecta el número de licencia del nuevo conductor de Jersey.|no|
|Func_new_mexico_drivers_license_number |detecta el número de permiso de conducción de un nuevo México|no|
|Func_new_york_drivers_license_number   |detecta el número de permiso de conducción de Nueva York|no|
|Func_new_zealand_bank_account_number   |detecta el número de cuenta bancaria de Nueva Zelanda|no|
|Func_new_zealand_inland_revenue_number |detecta el número de ingresos interiores de Nueva Zelanda|no|
|Func_new_zealand_ministry_of_health_number|detecta un número de Ministerio de salud de Nueva Zelanda|no|
|Func_newfoundland_labrador_drivers_license_number|detecta el número de licencia de conducción del Labrador de Terranova|no|
|Func_newzealand_driver_license_number  |detecta el número de licencia del controlador de Nueva Zelanda|no|
|Func_newzealand_social_welfare_number  |detecta un número de bienestar social de Nueva Zelanda|no|
|Func_north_carolina_drivers_license_number|detecta el número de permiso de conducción de Carolina del norte|no|
|Func_north_dakota_drivers_license_number|detecta el número de licencia de conducir del norte Dakota|no|
|Func_norway_id_number  |detecta el número de identificación de Noruega|no|
|Func_nova_scotia_drivers_license_number|detecta el número de permiso de conducir Escocia de nueva|no|
|Func_ohio_drivers_license_number   |detecta el número de licencia de conducir de Ohio|no|
|Func_ontario_drivers_license_number    |detecta el número de permiso de conducción de Ontario|no|
|Func_pennsylvania_drivers_license_number|detecta el número de permiso de conducción de Pensilvania|no|
|Func_pesel_identification_number   |detecta el identificador Nacional de Polonia (PESEL)|no|
|Func_poland_eu_tax_file_number |detecta el número de archivo de impuestos de Polonia|no|
|Func_polish_national_id    |detecta la tarjeta de identidad de Polonia|no|
|Func_polish_passport_number    |detecta el número de pasaporte Polaco|no|
|Func_polish_regon_number   |detecta el número de REGON Polaco|no|
|Func_portugal_eu_tax_file_number|detecta el número de identificación fiscal de Portugal|no|
|Func_prince_edward_island_drivers_license_number|detecta el número de permiso de conducción de la isla del príncipe Eduardo|no|
|Func_quebec_drivers_license_number |detecta el número de permiso de conducción de Quebec|no|
|Func_randomized_formatted_ssn  |detecta el SSN con el formato aleatorio SSN|sí|
|Func_randomized_unformatted_ssn|detecta el SSN de los Estados Unidos sin formato aleatorio.|sí|
|Func_rhode_island_drivers_license_number|detecta el número de permiso de conducción de la isla de Rhode|no|
|Func_romania_eu_national_id_card   |detecta el código numérico personal de Rumania (CNP)|no|
|Func_saskatchewan_drivers_license_number|detecta el número de permiso de conducción de Saskatchewan|no|
|Func_slovakia_eu_national_id_card  |detecta el número personal de Eslovaquia|no|
|Func_slovenia_eu_national_id_card  |detecta el número de ciudadano principal único de Eslovenia|no|
|Func_slovenia_eu_tax_file_number   |detecta el número de archivo de impuestos de Eslovenia|no|
|Func_south_africa_identification_number|detecta el número de identificación de Sudáfrica|sí|
|Func_south_carolina_drivers_license_number|detecta el número de permiso de conducción de Carolina del sur|no|
|Func_south_dakota_drivers_license_number|detecta el número de licencia de conducir de South Dakota|no|
|Func_south_korea_resident_number   |detecta el número residente de Corea del sur|no|
|Func_spain_eu_DL_and_NI_number_citizen |detecta la DL de España y el ciudadano NI el número|no|
|Func_spain_eu_DL_and_NI_number_foreigner|detecta la DL de España y NI el extranjero de números.|no|
|Func_spain_eu_driver ' s_license_number  |detecta el número de permiso de conducción de España|no|
|Func_spain_eu_tax_file_number  |detecta el número de archivo de impuestos de España|no|
|Func_spanish_social_security_number|detecta el número de la seguridad social en Español|no|
|Func_ssn   |Función para detectar el SSN con el formato no aleatorio SSN|sí|
|Func_sweden_eu_tax_file_number|detecta el número de archivo de impuestos de Suecia|no|
|Func_swedish_national_identifier|detecta el identificador nacional sueco|sí|
|Func_swiss_social_security_number_ahv|detecta la AHV del número de la seguridad social suizo|no|
|Func_taiwanese_national_id |detecta el identificador nacional del taiwanés|no|
|Func_tennessee_drivers_license_number|detecta el número de permiso de conducción de Tennessee|no|
|Func_texas_drivers_license_number  |detecta el número de permiso de conducción de Texas|no|
|Func_Thai_Citizen_Id   |detecta el identificador del ciudadano tailandés|no|
|Func_Turkish_National_Id|detecta el identificador nacional turco|sí|
|Func_uk_drivers_license|detecta el permiso de conducción del Reino Unido|no|
|Func_uk_eu_tax_file_number|detecta el número fiscal único de RU|no|
|Func_uk_nhs_number |detecta el número de NHS del Reino Unido|sí|
|Func_uk_nino   |detecta NINO de Reino Unido|no|
|Func_unformatted_canadian_sin|detecta el SIN formato canadiense|no|
|Func_unformatted_itin  |detecta ÉLEN de los Estados Unidos sin formato|sí|
|Func_unformatted_ssn   |detecta los no aleatorios SSN no aleatorios en el formato estadounidense|sí|
|Func_usa_uk_passport   |detecta los Estados Unidos y Passport de Reino Unido|sí|
|Func_utah_drivers_license_number|detecta el número de permiso de conducción de Utah|no|
|Func_vermont_drivers_license_number|detecta el número de licencia de conducir de Vermont|no|
|Func_virginia_drivers_license_number|detecta el número de permiso de conducción de Virginia|no|
|Func_washington_drivers_license_number|detecta el número de permiso de conducción de Washington|no|
|Func_west_virginia_drivers_license_number|detecta el número de licencia del controlador de Virginia Occidental|no|
|Func_wisconsin_drivers_license_number  |detecta el número de permiso de conducción de Wisconsin|no|
|Func_wyoming_drivers_license_number    |detecta el número de licencia de conducir de Wyoming|no|


## <a name="func_us_date"></a>Func_us_date

Func_us_date busca fechas en formatos estadounidenses comunes. Los formatos comunes son "month/Day/Year", "month-Day-Year" y "month Day Year". Los nombres o abreviaturas de los meses no distinguen mayúsculas de minúsculas. 
  
Ejemplos:
  
- 2 de diciembre de 2016
    
- 2 de diciembre de 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates busca fechas en la UE comunes formatos (y la mayoría de los lugares fuera de Estados Unidos), como "día/mes/año", "día-mes-año" y "día mes año". Los nombres o abreviaturas de los meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- 2 Dec 2016
    
- 02 Dec 2016
    
- 2 16 de diciembre
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dic-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.
    
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec
    
- Francés
    
  - Janvier, février, Mars, Avril, Mai, juin Juillet, Août, Septembre, octobre, Novembre, décembre
    
  - janv. févr. Mars Avril Mai juin juil. Août Sept. Oct. noviembre. déc.
    
- Alemán
    
  - Januar, Februar, März, April, Mai, Juni Juli, agosto, septiembre, Oktober, noviembre, Dezember
    
  - Ene./Jän. Feb. März Apr. Mai Juni Juli agosto de la OKT. Nov dez.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. graduación. TA. magg. Giugno Luglio AG. sett. ott. noviembre. Dic.
    
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV mar abr Mai Jun-Nov hace dez
    
- Español
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Enero Feb. marzo Abr. Mayo Jun. Julio. Agosto Sept./set. Oct. noviembre. Dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes en Portugués, que ahora están incluidos en la  `Func_eu_date` función anterior. 
  
Esta función busca una fecha en el formato que suele usarse en portugués. El formato de esta función es el mismo que  `Func_eu_date` en el idioma usado.
  
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
> Esta función está en desuso porque solo admite nombres de mes en holandés, que ahora están incluidos en la  `Func_eu_date` función anterior. 
  
Esta función busca una fecha en el formato que suele usarse en neerlandés. El formato de esta función es el mismo que  `Func_eu_date` en el idioma usado.
  
Ejemplos:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart Apr Mei Jun-Jul-Sep-Sept OKT Nov Dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date busca fechas con formatos usados comúnmente por tarjetas de crédito y débito. Esta función coincidirá con las fechas en el formato "mes/año", "mes-año", "[nombre del mes]" y "[abreviatura del mes] año". Los nombres o abreviaturas de los meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- MM/AA: por ejemplo, 01/11 o 1/11
    
- MM/AAAA: por ejemplo, 01/2011 o 1/2011
    
- MM-AA: por ejemplo 01-11 o 1-11
    
- MM-AAAA: por ejemplo 01-2000 o 1-2000
    
Los formatos siguientes admiten AA o AAAA:
  
- Mes-YYYY--por ejemplo, Ene-2010 o enero-2010 o ene-10 o enero-10
    
- Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"
    
- MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"
    
- Mes/AAAA: por ejemplo, "enero/2010" o "ene/2010" o "enero/10" o "ene/10"
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Jan Feb Marzo Apr mayo junio julio agosto Sept Oct Nov Dic
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address busca un nombre de estado de Estados Unidos o una abreviatura postal seguida de un código postal válido. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.
  
Ejemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
