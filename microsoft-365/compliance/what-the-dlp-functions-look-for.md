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
recommendations: false
description: Obtenga información sobre lo que buscan las funciones de prevención de pérdida de datos (DLP).
ms.openlocfilehash: 47eda79470fd131939c493ac4f66af6efea01dd6
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086517"
---
# <a name="what-the-dlp-functions-look-for"></a>Qué buscan las funciones de DLP

Las directivas de prevención de pérdida de datos (DLP) pueden usar tipos de información confidencial para identificar elementos confidenciales. El número de tarjeta de crédito y el número de tarjeta de débito de la UE son ejemplos de tipos de información confidencial. Los tipos de información confidencial buscan patrones específicos. Los tipos de información confidencial validan los datos mirando su formato, sus sumas de comprobación y busca palabras clave relevantes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial Número de tarjeta de crédito usa una función para buscar fechas con formato como una fecha de expiración. Esto ayuda a corroborar que un número es un número de tarjeta de crédito.
  
En este artículo se explica lo que buscan estas funciones, para ayudarle a comprender cómo funcionan los tipos de información confidencial predefinidos. Para obtener más información, vea [Definiciones de entidad de tipo de información confidencial](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Tabla de funciones

|nombre de función  |acción de función  |es un validador|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|detecta y valida la clave fiscal única de Argentina|no|
|Func_aba_routing|detecta el número de enrutamiento de ABA| sí|
|Func_alabama_drivers_license_number|detecta el número de licencia de conducir de Alabama|no|
|Func_alaska_delaware_oregon_drivers_license_number|detecta el número de licencia de conducir de Alaska, Delaware, Oregón|no|
|Func_alaska_drivers_license_number|detecta el número de licencia de conductor de Alaska|no|
|Func_alberta_drivers_license_number|detecta el número de licencia de conducir de Albertoa|no|
|Func_Argentina_Unique_Tax_Key|detecta clave fiscal única de Argentina|no|
|Func_arizona_drivers_license_number|detecta el número de licencia de conducir de Arizona|no|
|Func_arkansas_drivers_license_number|detecta el número de licencia de conducir de Arkansas|no|
|Func_australian_business_number|detecta número de negocio de Australia|no|
|Func_Australian_Company_Number|detecta el número de empresa de Australia|no|
|Func_australian_medical_account_number|detecta el número de cuenta médica de Australia|no|
|Func_australian_tax_file_number|detecta el número de archivo fiscal de Australia|sí|
|Func_austria_eu_ssn_or_equivalent|detecta el número de seguridad social de Austria|no|
|Func_austria_eu_tax_file_number|detecta el número de archivo fiscal de Austria|no|
|Func_Austria_Value_Added_Tax|Detecta Austria Value Added Tax|no|
|Func_belgium_national_number|detecta el número nacional de Bélgica|no|
|Func_belgium_value_added_tax_number|detecta el número de impuestos sobre el valor agregado de Bélgica|no|
|Func_brazil_cnpj|detecta el número de entidad jurídica de Brasil (CNPJ)|sí|
|Func_brazil_cpf|detecta CPF de Brasil|sí|
|Func_brazil_rg|detecta RG de Brasil|no|
|Func_british_columbia_drivers_license_number|detecta el número de licencia de conducir de British Columbia|no|
|Func_bulgaria_eu_national_id_card|detecta el número civil uniforme de Bulgaria|no|
|Func_california_drivers_license_number|detecta el número de licencia de conducir de California|no|
|Func_canadian_sin|detecta el pecado de Canadá|sí|
|Func_chile_id_card|Detecta tarjeta de identificación de Chile|no|
|Func_china_resident_id|detecta el identificador de residente de China|no|
|Func_colorado_drivers_license_number|detecta el número de licencia de conducir de Colorado|no|
|Func_connecticut_drivers_license_number|detecta el número de licencia de conductor de Connecticut|no|
|Func_credit_card|detecta tarjeta de crédito|sí|no|
|Func_croatia_id_card|detecta la tarjeta de identificación de Croacia|no|
|Func_croatia_oib_number|detecta el número OIB de Croacia|no|
|Func_cyprus_eu_tax_file_number|detecta el número de archivo fiscal de Chipre|no|
|Func_czech_id_card|detecta la tarjeta de identificación checa|no|
|Func_czech_id_card_new_format|detecta la tarjeta de identificación checa en nuevo formato|no|
|Func_dea_number|detecta el número de DEA|sí|
|Func_denmark_eu_tax_file_number|detecta el número de identificación personal de Dinamarca|no|
|Func_district_of_columbia_drivers_license_number|detecta el número de licencia de conducir del Distrito de Columbia|no|
|Func_estonia_eu_national_id_card|detecta el código de identificación personal de Estonia|no|
|Func_eu_debit_card|detecta tarjeta de débito de la UE|no|
|Func_finnish_national_id|detecta el id. nacional finlandés|no|
|Func_florida_drivers_license_number|detecta el número de licencia de conductor de Florida|no|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|detecta el número de licencia de conducir de Florida, Maryland, Míchigan y Minnesota|no|
|Func_formatted_itin|detecta EL ITIN de EE. UU. con formato|sí|
|Func_fr_insee|detecta Francia INSEE|no|
|Func_fr_passport|detecta el pasaporte de Francia|no|
|Func_france_eu_tax_file_number|detecta el número de archivo fiscal de Francia|no|
|Func_france_value_added_tax_number|detecta el número de impuestos de valor agregado de Francia|no|
|Func_french_drivers_license|detecta la licencia de conducir francesa|no|
|Func_french_insee|detecta insee francés|no|
|Func_georgia_drivers_license_number|detecta el número de licencia de conducir de Georgia|no|
|Func_german_drivers_license|detecta la licencia de conducir de Alemania|no|
|Func_german_passport|detecta el pasaporte de Alemania|no|
|Func_german_passport_data|detecta el pasaporte de Alemania|no|
|Func_germany_eu_tax_file_number|detecta el número de archivo fiscal de Alemania|no|
|Func_germany_value_added_tax_number|detecta el número de impuesto sobre el valor agregado de Alemania|no|
|Func_greece_eu_ssn|detecta el pecado de Grecia (AMKA)|no|
|Func_hawaii_drivers_license_number|detecta el número de licencia de conductor de Hawái|no|
|Func_hong_kong_id_card |detecta tarjeta de identificación de Hong Kong|no|
|Func_hungarian_value_added_tax_number|detecta el número de impuestos de valor agregado de Hungría|no|
|Func_hungary_eu_national_id_card|detecta el número de identificación personal de Hungría|no|
|Func_hungary_eu_ssn_or_equivalent|detecta el número de seguridad social de Hungría|no|
|Func_hungary_eu_tax_file_number|detecta el número de archivo fiscal de Hungría|no|
|Func_iban|detecta IBAN|sí|
|Func_idaho_drivers_license_number|detecta el número de licencia de conducir de Idaho|no|
|Func_illinois_drivers_license_number|detecta el número de licencia de conducir de Illinois|no|
|Func_india_aadhaar|detecta india aadhaar|sí|
|Func_indiana_drivers_license_number|detecta el número de licencia de conducir de Indiana|no|
|Func_iowa_drivers_license_number|detecta el número de licencia de conducir de Iowa|no|
|Func_ireland_pps|detecta PPS de Irlanda|no|
|Func_israeli_national_id_number|detecta el número de identificación nacional de Israel|no|
|Func_italy_eu_national_id_card |detecta el código fiscal de Italia|no|
|Func_italy_value_added_tax_number|detecta el número de impuestos sobre el valor agregado de Italia|no|
|Func_japanese_my_number_corporate|detecta Japón mi número corporativo|sí|
|Func_japanese_my_number_personal|detecta Japón mi número personal|sí|
|Func_jp_bank_account|detecta cuenta bancaria de Japón|no|
|Func_jp_bank_account_branch_code|detecta el código de sucursal de la cuenta bancaria de Japón|no|
|Func_jp_drivers_license_number|detecta el número de licencia de conducir de Japón|no|
|Func_jp_passport|detecta el pasaporte de Japón|no|
|Func_jp_resident_registration_number|detecta el número de registro residente en Japón|no|
|Func_jp_sin|detecta Sin de Japón|no|
|Func_jp_sin_pre_1997|detecta el pecado de Japón anterior a 1997|no|
|Func_kansas_drivers_license_number|detecta el número de licencia de conducir de Kansas|no|
|Func_kentucky_drivers_license_number|detecta el número de licencia de conducir de Kentucky|no|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detecta el número de licencia de conducir de Kentucky, Massachusetts, Virginia|no|
|Func_latvia_eu_national_id_card|detecta código personal de Letonia|no|
|Func_lithuania_eu_tax_file_number|detecta código personal de Lituania|no|
|Func_louisiana_drivers_license_number|detecta el número de licencia de conducir de Louisiana|no|
|Func_luxemburg_eu_tax_file_number|detecta el número de identificación nacional de Luxemburgo (personas físicas)|no|
|Func_luxemburg_eu_tax_file_number_non_natural|detecta el número de identificación nacional de Luxemburgo (personas no físicas)|no|
|Func_maine_drivers_license_number|detecta el número de licencia de conductor de Maine|no|
|Func_manitoba_drivers_license_number|detecta el número de licencia de conducir de Manitoba|no|
|Func_maryland_drivers_license_number|detecta el número de licencia de conducir de Maryland|no|
|Func_massachusetts_drivers_license_number|detecta el número de licencia de conductor de Massachusetts|no|
|Func_mexico_population_registry_code|detecta código de registro de población de México|no|
|Func_michigan_minnesota_drivers_license_number|detecta el número de licencia de conducir de Míchigan, Minnesota|no|
|Func_minnesota_drivers_license_number|detecta el número de licencia de conducir de Minnesota|no|
|Func_mississippi_oklahoma_drivers_license_number|detecta el número de licencia de conducir de Misisipi, Oklahoma|no|
|Func_missouri_drivers_license_number|detecta el número de licencia de conducir de Misuri|no|
|Func_montana_drivers_license_number|detecta el número de licencia de conducir de Montana|no|
|Func_nebraska_drivers_license_number|detecta el número de licencia de conducir de Nebraska|no|
|Func_netherlands_bsn|detecta BSN neerlandés|no|
|Func_netherlands_eu_tax_file_number|detecta el número de archivo fiscal de Países Bajos|no|
|Func_netherlands_value_added_tax_number|detecta el número de impuestos sobre el valor agregado de Países Bajos|no|
|Func_nevada_drivers_license_number|detecta el número de licencia de conducir de Nevada|no|
|Func_new_brunswick_drivers_license_number|detecta el número de licencia de conductor de New Brunswick|no|
|Func_new_hampshire_drivers_license_number|detecta el número de licencia de conducir de New Hampshire|no|
|Func_new_jersey_drivers_license_number |detecta el número de licencia de conducir de Nueva Jersey|no|
|Func_new_mexico_drivers_license_number |detecta el número de licencia de conducir de Nuevo México|no|
|Func_new_york_drivers_license_number   |detecta el número de licencia de conducir de Nueva York|no|
|Func_new_zealand_bank_account_number   |detecta el número de cuenta bancaria de Nueva Zelanda|no|
|Func_new_zealand_inland_revenue_number |detecta el número de ingresos adicionales de Nueva Zelanda|no|
|Func_new_zealand_ministry_of_health_number|detecta el número de ministerio de salud de Nueva Zelanda|no|
|Func_newfoundland_labrador_drivers_license_number|detecta el número de licencia de conducir de Newfoundland Labrador|no|
|Func_newzealand_driver_license_number  |detecta el número de licencia de conducir de Nueva Zelanda|no|
|Func_newzealand_social_welfare_number  |detecta el número de bienestar social de Nueva Zelanda|no|
|Func_north_carolina_drivers_license_number|detecta el número de licencia de conducir de North Carolina|no|
|Func_north_dakota_drivers_license_number|detecta el número de licencia de conducir de North Dakota|no|
|Func_norway_id_number  |detecta el número de id. de Noruega|no|
|Func_nova_scotia_drivers_license_number|detecta el número de licencia de conducir de Nueva Escocia|no|
|Func_ohio_drivers_license_number   |detecta el número de licencia de conducir de Ohio|no|
|Func_ontario_drivers_license_number    |detecta el número de licencia de conducir de Ontario|no|
|Func_pennsylvania_drivers_license_number|detecta el número de licencia de conducir de Pensilvania|no|
|Func_pesel_identification_number   |detecta el identificador nacional de Polonia (PESEL)|no|
|Func_poland_eu_tax_file_number |detecta el número de archivo fiscal de Polonia|no|
|Func_polish_national_id    |detecta la tarjeta de identidad de Polonia|no|
|Func_polish_passport_number    |detecta el número de pasaporte polaco|no|
|Func_polish_regon_number   |detecta el número regon polaco|no|
|Func_portugal_eu_tax_file_number|detecta el número de identificación fiscal de Portugal|no|
|Func_prince_edward_island_drivers_license_number|detecta el número de licencia de conducir de isla Príncipe Eduardo|no|
|Func_quebec_drivers_license_number |detecta el número de licencia de conducir de Quebec|no|
|Func_randomized_formatted_ssn  |detecta el SSN de EE. UU. con formato aleatorio|sí|
|Func_randomized_unformatted_ssn|detecta el SSN de EE. UU. aleatorio sin formato|sí|
|Func_rhode_island_drivers_license_number|detecta el número de licencia de conducir de Rhode Island|no|
|Func_romania_eu_national_id_card   |detecta código numérico personal (CNP) de Rumania|no|
|Func_saskatchewan_drivers_license_number|detecta el número de licencia de conducir de Saskatchewan|no|
|Func_slovakia_eu_national_id_card  |detecta el número personal de Eslovaquia|no|
|Func_slovenia_eu_national_id_card  |detecta el número único de ciudadano principal de Eslovenia|no|
|Func_slovenia_eu_tax_file_number   |detecta el número de archivo fiscal de Eslovenia|no|
|Func_south_africa_identification_number|detecta el número de identificación de Sudáfrica|sí|
|Func_south_carolina_drivers_license_number|detecta el número de licencia de conducir de Carolina del Sur|no|
|Func_south_dakota_drivers_license_number|detecta el número de licencia de conducir de South Dakota|no|
|Func_south_korea_resident_number   |detecta el número de residente de Corea del Sur|no|
|Func_spain_eu_DL_and_NI_number_citizen |detecta el ciudadano de números DL y NI de España|no|
|Func_spain_eu_DL_and_NI_number_foreigner|detecta el extranjero de números DL y NI de España|no|
|Func_spain_eu_driver de s_license_number  |detecta el número de licencia de conducir de España|no|
|Func_spain_eu_tax_file_number  |detecta el número de archivo fiscal de España|no|
|Func_spanish_social_security_number|detecta el número de seguridad social español|no|
|Func_ssn   |Función para detectar SSN de ESTADOS UNIDOS con formato no aleatorio|sí|
|Func_sweden_eu_tax_file_number|detecta el número de archivo fiscal de Suecia|no|
|Func_swedish_national_identifier|detecta el identificador nacional sueco|sí|
|Func_swiss_social_security_number_ahv|detecta el número de seguridad social suiza AHV|no|
|Func_taiwanese_national_id |detecta el id. nacional taiwanés|no|
|Func_tennessee_drivers_license_number|detecta el número de licencia de conducir de Tennessee|no|
|Func_texas_drivers_license_number  |detecta el número de licencia de conductor de Texas|no|
|Func_Thai_Citizen_Id   |detecta el id. de ciudadano tailandés|no|
|Func_Turkish_National_Id|detecta el id. nacional turco|sí|
|Func_uk_drivers_license|detecta la licencia de conducir del Reino Unido|no|
|Func_uk_eu_tax_file_number|detecta el número de contribuyente único del Reino Unido|no|
|Func_uk_nhs_number |detecta el número de NHS de Reino Unido|sí|
|Func_uk_nino   |detecta NINO de Reino Unido|no|
|Func_unformatted_canadian_sin|detecta sin formato canadiense|no|
|Func_unformatted_itin  |detecta EL ITIN de EE. UU. sin formato|sí|
|Func_unformatted_ssn   |detecta SSN de EE. UU. sin formato no aleatorio|sí|
|Func_usa_uk_passport   |detecta el pasaporte de Estados Unidos y Reino Unido|sí|
|Func_utah_drivers_license_number|detecta el número de licencia de conducir de Utah|no|
|Func_vermont_drivers_license_number|detecta el número de licencia de conducir de Vermont|no|
|Func_virginia_drivers_license_number|detecta el número de licencia de conducir de Virginia|no|
|Func_washington_drivers_license_number|detecta el número de licencia de conducir de Washington|no|
|Func_west_virginia_drivers_license_number|detecta el número de licencia de conducir de West Virginia|no|
|Func_wisconsin_drivers_license_number  |detecta el número de licencia de conducir de Wisconsin|no|
|Func_wyoming_drivers_license_number    |detecta el número de licencia de conducir de Wyoming|no|


## <a name="func_us_date"></a>Func_us_date

Func_us_date busca fechas en formatos comunes de Estados Unidos. Los formatos comunes son "mes/día/año", "mes-día-año" y "mes día año". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas. 
  
Ejemplos:
  
- 2 de diciembre de 2016
    
- 2 de diciembre de 2016
    
- 02 de diciembre de 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb. Mar. Abr. May June July Aug. Oct. Nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates busca fechas en E.U comunes. formatos (y la mayoría de los lugares fuera de Estados Unidos), como "día/mes/año", "día-mes-año" y "año de mes de día". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- 2 dic 2016
    
- 02 dic 2016
    
- 2 dic 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dic-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb. Mar. Abr. May June July Aug. Oct. Nov. Dec.
    
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep sept oct okt nov dec
    
- Francés
    
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre
    
  - janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.
    
- Alemán
    
  - jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember
    
  - Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.
    
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
- Español
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes portugueses, que ahora se incluyen en  `Func_eu_date` la función anterior. 
  
Esta función busca una fecha en el formato que suele usarse en portugués. El formato de esta función es el mismo que  `Func_eu_date` , que sólo difiere en el idioma usado.
  
Ejemplos:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes neerlandés, que ahora se incluyen en  `Func_eu_date` la función anterior. 
  
Esta función busca una fecha en el formato que suele usarse en neerlandés. El formato de esta función es el mismo que  `Func_eu_date` , que sólo difiere en el idioma usado.
  
Ejemplos:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr jun jun jul aug sep sept out okt nov dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date busca fechas que se encuentran en formatos usados habitualmente por tarjetas de crédito y débito. Esta función coincidirá con fechas en formato de "mes/año", "mes-año", "[nombre de mes] año" y "[abreviatura de mes] año". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- MM/AA: por ejemplo, 01/11 o 1/11
    
- MM/AAAA: por ejemplo, 01/2011 o 1/2011
    
- MM-AA: por ejemplo 01-11 o 1-11
    
- MM-AAAA: por ejemplo 01-2000 o 1-2000
    
Los formatos siguientes admiten AA o AAAA:
  
- Month-YYYY: por ejemplo, enero-2010 o enero-2010, 10 de enero o enero-10
    
- Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"
    
- MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"
    
- Month/YYYY: por ejemplo, 'january/2010' o 'Jan/2010' o 'january/10' or 'Jan/10'
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene Feb Mar Apr May June July Aug Oct Nov Dic
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address busca un nombre de estado de Estados Unidos o una abreviatura postal seguida de un código postal válido. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.
  
Ejemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
