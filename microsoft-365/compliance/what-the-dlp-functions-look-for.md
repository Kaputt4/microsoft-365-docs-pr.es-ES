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
description: Obtenga información sobre lo que buscan las funciones de prevención de pérdida de datos (DLP).
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841451"
---
# <a name="what-the-dlp-functions-look-for"></a>Qué buscan las funciones de DLP

Las directivas de prevención de pérdida de datos (DLP) pueden usar tipos de información confidencial para identificar elementos confidenciales. El número de tarjeta de crédito y el número de tarjeta de débito de la UE son ejemplos de tipos de información confidencial. Los tipos de información confidencial buscan patrones específicos. Los tipos de información confidencial validan los datos mirando su formato, sus sumas de comprobación y busca palabras clave relevantes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial Número de tarjeta de crédito usa una función para buscar fechas con formato como una fecha de expiración. Esto ayuda a corroborar que un número es un número de tarjeta de crédito.
  
En este artículo se explica qué buscan estas funciones para ayudarle a comprender cómo funcionan los tipos de información confidencial predefinidos. Para obtener más información, vea [Definiciones de entidad de tipo de información confidencial](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Tabla de funciones

|nombre de la función  |acción de función  |es un validador|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|detecta y valida la clave de impuestos única de Argentina|no|
|Func_aba_routing|detecta el número de enrutamiento de ABA| sí|
|Func_alabama_drivers_license_number|detecta el número de licencia de conductor de Alabama|no|
|Func_alaska_delaware_oregon_drivers_license_number|detecta el número de licencia de conductor de Alaska, Alaska, Oregon|no|
|Func_alaska_drivers_license_number|detecta el número de licencia de conducción de Alaska|no|
|Func_alberta_drivers_license_number|detecta el número de licencia de conductor de Alberta|no|
|Func_Argentina_Unique_Tax_Key|detecta la clave fiscal única de Argentina|no|
|Func_arizona_drivers_license_number|detecta el número de licencia de conductor de Driver|no|
|Func_arkansas_drivers_license_number|detecta el número de licencia de conductor de Arkansas|no|
|Func_australian_business_number|detecta el número de negocio de Australia|no|
|Func_Australian_Company_Number|detecta el número de empresa de Australia|no|
|Func_australian_medical_account_number|detecta el número de cuenta médica de Australia|no|
|Func_australian_tax_file_number|detecta el número de archivo fiscal de Australia|sí|
|Func_austria_eu_ssn_or_equivalent|detecta el número de la seguridad social de Austria|no|
|Func_austria_eu_tax_file_number|detecta el número de archivo fiscal de Austria|no|
|Func_Austria_Value_Added_Tax|detecta el impuesto sobre el valor agregado de Austria|no|
|Func_belgium_national_number|detecta el número nacional de Bélgica|no|
|Func_belgium_value_added_tax_number|detecta el número de impuestos sobre el valor agregado de Bélgica|no|
|Func_brazil_cnpj|detecta el número de entidad jurídica de Brasil (CNPJ)|sí|
|Func_brazil_cpf|detecta CPF de Brasil|sí|
|Func_brazil_rg|detecta RG de Brasil|no|
|Func_british_columbia_drivers_license_number|detecta el número de licencia de conductor de British Columbia|no|
|Func_bulgaria_eu_national_id_card|detecta el número civil uniforme de Bulgaria|no|
|Func_california_drivers_license_number|detecta el número de licencia de conductor de California|no|
|Func_canadian_sin|detecta el seno de Canadá|sí|
|Func_chile_id_card|detecta la tarjeta de identificación de Chile|no|
|Func_china_resident_id|detecta el id. de residente de China|no|
|Func_colorado_drivers_license_number|detecta el número de licencia de conducción de Colorado|no|
|Func_connecticut_drivers_license_number|detecta el número de licencia de conductor de Driver|no|
|Func_credit_card|detecta la tarjeta de crédito|sí|no|
|Func_croatia_id_card|detecta la tarjeta de identificación de Croacia|no|
|Func_croatia_oib_number|detecta el número OIB de Croacia|no|
|Func_cyprus_eu_tax_file_number|detecta el número de archivo fiscal de Chipre|no|
|Func_czech_id_card|detecta la tarjeta de identificación checa|no|
|Func_czech_id_card_new_format|detecta la tarjeta de identificación checa en nuevo formato|no|
|Func_dea_number|detecta el número de DEA|sí|
|Func_denmark_eu_tax_file_number|detecta el número de identificación personal de Dinamarca|no|
|Func_district_of_columbia_drivers_license_number|detecta el número de licencia de conductor del Distrito de Colombia|no|
|Func_estonia_eu_national_id_card|detecta el código de identificación personal de Estonia|no|
|Func_eu_debit_card|detecta la tarjeta de débito de la UE|no|
|Func_finnish_national_id|detecta el identificador nacional finlandés|no|
|Func_florida_drivers_license_number|detecta el número de licencia de conductor de Driver|no|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|detecta el número de licencia de conductor de Detroit, Chicago, Detroit|no|
|Func_formatted_itin|detecta el ITIN de EE. UU. con formato|sí|
|Func_fr_insee|detecta Francia INSEE|no|
|Func_fr_passport|detecta el pasaporte de Francia|no|
|Func_france_eu_tax_file_number|detecta el número de archivo fiscal de Francia|no|
|Func_france_value_added_tax_number|detecta el número de impuestos del valor agregado de Francia|no|
|Func_french_drivers_license|detecta la licencia de conducir en francés|no|
|Func_french_insee|detecta insee en francés|no|
|Func_georgia_drivers_license_number|detecta el número de licencia de conductor de Georgia|no|
|Func_german_drivers_license|detecta la licencia de conducir de Alemania|no|
|Func_german_passport|detecta el pasaporte de Alemania|no|
|Func_german_passport_data|detecta el pasaporte de Alemania|no|
|Func_germany_eu_tax_file_number|detecta el número de archivo fiscal de Alemania|no|
|Func_germany_value_added_tax_number|detecta el número de impuestos del valor agregado de Alemania|no|
|Func_greece_eu_ssn|detecta el seno de Grecia (AMKA)|no|
|Func_hawaii_drivers_license_number|detecta el número de licencia de conductor de Hawaii|no|
|Func_hong_kong_id_card |detecta la tarjeta de identificación de Hong Kong|no|
|Func_hungarian_value_added_tax_number|detecta el número de impuestos del valor agregado de Hungría|no|
|Func_hungary_eu_national_id_card|detecta el número de identificación personal de Hungría|no|
|Func_hungary_eu_ssn_or_equivalent|detecta el número de la seguridad social de Hungría|no|
|Func_hungary_eu_tax_file_number|detecta el número de archivo fiscal de Hungría|no|
|Func_iban|detecta iban|sí|
|Func_idaho_drivers_license_number|detecta el número de licencia de conductor de Odbc|no|
|Func_illinois_drivers_license_number|detecta el número de licencia de conductor de Chicago|no|
|Func_india_aadhaar|detecta india aadhaar|sí|
|Func_indiana_drivers_license_number|detecta el número de licencia de conducción de Indiana|no|
|Func_iowa_drivers_license_number|detecta el número de licencia de conductor de Odbc|no|
|Func_ireland_pps|detecta PPS de Irlanda|no|
|Func_israeli_national_id_number|detecta el número de identificación nacional de Israel|no|
|Func_italy_eu_national_id_card |detecta código fiscal de Italia|no|
|Func_italy_value_added_tax_number|detecta el número de impuestos del valor agregado de Italia|no|
|Func_japanese_my_number_corporate|detecta mi número corporativo de Japón|sí|
|Func_japanese_my_number_personal|detecta mi número personal de Japón|sí|
|Func_jp_bank_account|detecta la cuenta bancaria de Japón|no|
|Func_jp_bank_account_branch_code|detecta el código de sucursal de la cuenta bancaria de Japón|no|
|Func_jp_drivers_license_number|detecta el número de licencia de conductor de Japón|no|
|Func_jp_passport|detecta el pasaporte de Japón|no|
|Func_jp_resident_registration_number|detecta el número de registro de residente en Japón|no|
|Func_jp_sin|detecta Japón SIN|no|
|Func_jp_sin_pre_1997|detecta el seno de Japón anterior a 1997|no|
|Func_kansas_drivers_license_number|detecta el número de licencia de conducción de Kansas|no|
|Func_kentucky_drivers_license_number|detecta el número de licencia de conductor de Driver|no|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detecta el número de licencia de conductor de Massachusetts, Massachusetts y Massachusetts|no|
|Func_latvia_eu_national_id_card|detecta código personal de Letonia|no|
|Func_lithuania_eu_tax_file_number|detecta código personal de Lituania|no|
|Func_louisiana_drivers_license_number|detecta el número de licencia de conducción de Louisiana|no|
|Func_luxemburg_eu_tax_file_number|detecta el número de identificación nacional de Luxemburgo (personas físicas)|no|
|Func_luxemburg_eu_tax_file_number_non_natural|detecta el número de identificación nacional de Luxemburgo (personas no naturales)|no|
|Func_maine_drivers_license_number|detecta el número de licencia de conductor de Maine|no|
|Func_manitoba_drivers_license_number|detecta el número de licencia de conducción de Manitoba|no|
|Func_maryland_drivers_license_number|detecta el número de licencia de conductor de Odbc|no|
|Func_massachusetts_drivers_license_number|detecta el número de licencia de conductor de Massachusetts|no|
|Func_mexico_population_registry_code|detecta código de registro de población de México|no|
|Func_michigan_minnesota_drivers_license_number|detecta el número de licencia de conductor de Detroit, Minnesota|no|
|Func_minnesota_drivers_license_number|detecta el número de licencia de conductor de Minnesota|no|
|Func_mississippi_oklahoma_drivers_license_number|detecta el número de licencia de conducción de Odbc, Driver's License Number|no|
|Func_missouri_drivers_license_number|detecta el número de licencia de conductor de Driver|no|
|Func_montana_drivers_license_number|detecta el número de licencia de conductor de Odbc|no|
|Func_nebraska_drivers_license_number|detecta el número de licencia de conductor de Odbc|no|
|Func_netherlands_bsn|detecta el BSN de Países Bajos|no|
|Func_netherlands_eu_tax_file_number|detecta el número de archivo fiscal de países bajos|no|
|Func_netherlands_value_added_tax_number|detecta el número de impuestos sobre el valor agregado de Países Bajos|no|
|Func_nevada_drivers_license_number|detecta el número de licencia de conducción de Aldán|no|
|Func_new_brunswick_drivers_license_number|detecta el número de licencia de conductor de New DriverCk|no|
|Func_new_hampshire_drivers_license_number|detecta el número de licencia de conductor de NewShire|no|
|Func_new_jersey_drivers_license_number |detecta el número de licencia de conductor de Nueva Jersey|no|
|Func_new_mexico_drivers_license_number |detecta el número de licencia de conductor de Nuevo México|no|
|Func_new_york_drivers_license_number   |detecta el número de licencia de conductor de Nueva York|no|
|Func_new_zealand_bank_account_number   |detecta el número de cuenta bancaria de Nueva Zelanda|no|
|Func_new_zealand_inland_revenue_number |detecta el número de ingresos del interior de Nueva Zelanda|no|
|Func_new_zealand_ministry_of_health_number|detecta el número de estado del ministerio de Salud de Nueva Zelanda|no|
|Func_newfoundland_labrador_drivers_license_number|detecta el número de licencia de conductor de Newfoundland Labrador|no|
|Func_newzealand_driver_license_number  |detecta el número de licencia de conducción de Nueva Zelanda|no|
|Func_newzealand_social_welfare_number  |detecta el número de redes sociales de Nueva Zelanda|no|
|Func_north_carolina_drivers_license_number|detecta el número de licencia de conducción de North Driver|no|
|Func_north_dakota_drivers_license_number|detecta el número de licencia de conductor de North Driver|no|
|Func_norway_id_number  |detecta el número de identificación de Noruega|no|
|Func_nova_scotia_drivers_license_number|detecta el número de licencia de conducción de Scotia|no|
|Func_ohio_drivers_license_number   |detecta el número de licencia de conducción de Ohio|no|
|Func_ontario_drivers_license_number    |detecta el número de licencia de conductor de Driver|no|
|Func_pennsylvania_drivers_license_number|detecta el número de licencia de conductor de Driver|no|
|Func_pesel_identification_number   |detecta el id. nacional de Polonia (PESEL)|no|
|Func_poland_eu_tax_file_number |detecta el número de archivo fiscal de Polonia|no|
|Func_polish_national_id    |detecta la tarjeta de identidad de Polonia|no|
|Func_polish_passport_number    |detecta el número de pasaporte polaco|no|
|Func_polish_regon_number   |detecta el número REGON polaco|no|
|Func_portugal_eu_tax_file_number|detecta el número de identificación fiscal de Portugal|no|
|Func_prince_edward_island_drivers_license_number|detecta el número de licencia de conductor de la isla Deián|no|
|Func_quebec_drivers_license_number |detecta el número de licencia de conductor de Quebec|no|
|Func_randomized_formatted_ssn  |detecta el SSN de EE. UU. con formato aleatorio|sí|
|Func_randomized_unformatted_ssn|detecta el SSN de EE. UU. sin formato aleatorio|sí|
|Func_rhode_island_drivers_license_number|detecta el número de licencia de conductor de Island Island|no|
|Func_romania_eu_national_id_card   |detecta el código numérico personal (CNP) de Rumania|no|
|Func_saskatchewan_drivers_license_number|detecta el número de licencia de conductor de Saskatchewan|no|
|Func_slovakia_eu_national_id_card  |detecta el número personal de Eslovaquia|no|
|Func_slovenia_eu_national_id_card  |detecta el número de ciudadano maestro único de Eslovenia|no|
|Func_slovenia_eu_tax_file_number   |detecta el número de archivo fiscal de Eslovenia|no|
|Func_south_africa_identification_number|detecta el número de identificación de Sudáfrica|sí|
|Func_south_carolina_drivers_license_number|detecta el número de licencia de conducción de Distrito Sur|no|
|Func_south_dakota_drivers_license_number|detecta el número de licencia de conducción de South Driver|no|
|Func_south_korea_resident_number   |detecta el número de residente de Corea del Sur|no|
|Func_spain_eu_DL_and_NI_number_citizen |detecta el ciudadano de números DL y NI de España|no|
|Func_spain_eu_DL_and_NI_number_foreigner|detecta la presencia de números DL y NI de España|no|
|Func_spain_eu_driver de s_license_number  |detecta el número de licencia de conductor de España|no|
|Func_spain_eu_tax_file_number  |detecta el número de archivo fiscal de España|no|
|Func_spanish_social_security_number|detecta el número de la seguridad social en español|no|
|Func_ssn   |Función para detectar SSN de EE. UU. con formato no aleatorio|sí|
|Func_sweden_eu_tax_file_number|detecta el número de archivo fiscal de Suecia|no|
|Func_swedish_national_identifier|detecta el identificador nacional sueco|sí|
|Func_swiss_social_security_number_ahv|detecta el número de la seguridad social suiza AHV|no|
|Func_taiwanese_national_id |detecta el id. nacional de Taiwán|no|
|Func_tennessee_drivers_license_number|detecta el número de licencia de conductor de Odbc|no|
|Func_texas_drivers_license_number  |detecta el número de licencia de conductor de Texas|no|
|Func_Thai_Citizen_Id   |detecta el id. de ciudadano tailandés|no|
|Func_Turkish_National_Id|detecta el id. nacional turco|sí|
|Func_uk_drivers_license|detecta la licencia de conducir del Reino Unido|no|
|Func_uk_eu_tax_file_number|detecta el número único de contribuyentes del Reino Unido|no|
|Func_uk_nhs_number |detecta el número de NHS del Reino Unido|sí|
|Func_uk_nino   |detecta NINO de Reino Unido|no|
|Func_unformatted_canadian_sin|detecta sin formato canadiense|no|
|Func_unformatted_itin  |detecta el ITIN de EE. UU. sin formato|sí|
|Func_unformatted_ssn   |detecta el SSN de EE. UU. no aleatorizado sin formato|sí|
|Func_usa_uk_passport   |detecta el pasaporte de EE. UU. y Reino Unido|sí|
|Func_utah_drivers_license_number|detecta el número de licencia de conductor de Odbc|no|
|Func_vermont_drivers_license_number|detecta el número de licencia de conductor de Driver|no|
|Func_virginia_drivers_license_number|detecta el número de licencia de conducción de María|no|
|Func_washington_drivers_license_number|detecta el número de licencia de conductor de Washington|no|
|Func_west_virginia_drivers_license_number|detecta el número de licencia de conducción de West Driver|no|
|Func_wisconsin_drivers_license_number  |detecta el número de licencia de conductor de Driver|no|
|Func_wyoming_drivers_license_number    |detecta el número de licencia de conducción de Alcándalo|no|


## <a name="func_us_date"></a>Func_us_date

Func_us_date busca fechas en formatos comunes de Estados Unidos. Los formatos comunes son "mes/día/año", "mes-día-año" y "mes día año". Los nombres o abreviaturas de los meses no distinguen mayúsculas de minúsculas. 
  
Ejemplos:
  
- 2 de diciembre de 2016
    
- 2 de diciembre de 2016
    
- 2 de diciembre de 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dic-2-2016
    
- 12-2-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb. Mar. Abr. May June July Aug. Sept. Oct. Nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates busca fechas en E.U. comunes formatos (y la mayoría de los lugares fuera de Estados Unidos), como "día/mes/año", "día-mes-año" y "día mes año". Los nombres o abreviaturas de los meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- 2 dic 2016
    
- 02 de diciembre de 2016
    
- 2 dic 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dic-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene. Feb. Mar. Abr. May June July Aug. Sept. Oct. Nov. Dec.
    
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr vez jun jul aug sep sept oct okt nov dec
    
- Francés
    
  - janvier, février, mars, avril, mai, juin juillet, aoretat, septembre, octobre, novembre, décembre
    
  - janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.
    
- Alemán
    
  - jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember
    
  - Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, mograma, giugno, luograma, agosto, settembre, quebre, novembre, dicembre
    
  - genn. febbr. mar. apr. magg. giugno lugno ag. sett. ott. nov. dic.
    
- Portugués
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
- Español
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (en desuso)

> [!NOTE]
> Esta función está en desuso porque solo admite nombres de mes en portugués, que ahora se incluyen en  `Func_eu_date` la función anterior. 
  
Esta función busca una fecha en el formato que suele usarse en portugués. El formato de esta función es el mismo que  `Func_eu_date` , difiere sólo en el idioma usado.
  
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
  
Esta función busca una fecha en el formato que suele usarse en neerlandés. El formato de esta función es el mismo que  `Func_eu_date` , difiere sólo en el idioma usado.
  
Ejemplos:
  
- 2 Vez 2016
    
- 02 vez 2016
    
- 2 Vez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Vez-2016
    
- 2-12-16
    
Nombres de mes aceptados:
  
- Neerlandés
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr vez jun jul aug sep sept out okt nov dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date busca fechas que se encuentran en formatos usados habitualmente por las tarjetas de crédito y débito. Esta función coincidirá con las fechas en formato de "mes/año", "mes-año", "[nombre del mes] año" y "[abreviatura del mes] año". Los nombres o abreviaturas de los meses no distinguen mayúsculas de minúsculas.
  
Ejemplos:
  
- MM/AA: por ejemplo, 01/11 o 1/11
    
- MM/AAAA: por ejemplo, 01/2011 o 1/2011
    
- MM-AA: por ejemplo 01-11 o 1-11
    
- MM-AAAA: por ejemplo 01-2000 o 1-2000
    
Los formatos siguientes admiten AA o AAAA:
  
- Month-YYYY: por ejemplo, enero de 2010, enero de 2010, 10 de enero o 10 de enero
    
- Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"
    
- MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"
    
- Mes/AÑO: por ejemplo, "enero/2010", "Ene/2010", "enero/10" o "Ene/10"
    
Nombres de mes aceptados:
  
- Inglés
    
  - Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Ene Feb Mar Apr May June July Aug Oct Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address busca un nombre de estado de Estados Unidos o una abreviatura postal seguido de un código postal válido. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.
  
Ejemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
