---
title: Definiciones de entidad de tipos de información confidencial
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La prevención de pérdida de datos (DLP) del centro de seguridad &amp; y cumplimiento incluye los tipos de información confidencial de 80 que están listos para que pueda usarlos en las directivas de DLP. Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.
ms.openlocfilehash: a91459652d785f6536cb50e381ab139057a3eae8
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024648"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definiciones de entidad de tipos de información confidencial

La prevención de pérdida de datos (DLP) en el centro de cumplimiento incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP. Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos. Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función. Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial. El nivel de confianza y la proximidad también se usan en el proceso de evaluación.
  
## <a name="aba-routing-number"></a>Número de enrutamiento ABA

### <a name="format"></a>Formato

9 dígitos, que pueden tener un patrón con o sin formato

### <a name="pattern"></a>Pattern

Con formato
- Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8
- Un guión 
- Cuatro dígitos
- Un guión 
- Un dígito

Sin formato: 9 dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8 

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_aba_routing encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ABA_Routing.

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>Keywords

#### <a name="keyword_aba_routing"></a>Keyword_ABA_Routing

- ABA
- aba #
- aba routing #
- aba routing number
- ABA #
- abarouting #
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bank routing number
- bankrouting #
- bankroutingnumber
- routing transit number
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>Número de identidad nacional (DNI) de Argentina

### <a name="format"></a>Formato

Ocho dígitos separados por puntos

### <a name="pattern"></a>Pattern

Ocho dígitos:
- Dos dígitos
- Un punto 
- Tres dígitos 
- Un punto 
- Tres dígitos 

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_argentina_national_id.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Número de identidad nacional de Argentina 
- Identidad 
- Tarjeta de identidad nacional de identificación 
- DNI 
- Registro Nacional de NIC de personas 
- Documento Nacional de Identidad 
- Registro nacional de las personas 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>Número de cuenta bancaria de Australia

### <a name="format"></a>Formato

De 6 a 10 dígitos con o sin número de sucursal bancaria de estado

### <a name="pattern"></a>Pattern

El número de cuenta tiene entre 6 y 10 dígitos.
Número de sucursal bancaria de Australia:
- Tres dígitos 
- Un guion 
- Tres dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_australia_bank_account_number.
- La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_australia_bank_account_number.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- OIEA

   
## <a name="australia-drivers-license-number"></a>Número de permiso de conducción de Australia

### <a name="format"></a>Formato

Nueve letras y dígitos

### <a name="pattern"></a>Pattern

Nueve letras y dígitos: 

- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas) 
- Dos dígitos 
- Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)

O

- 1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas)  
- 4-9 dígitos

O

- Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_australia_drivers_license_number.
- No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- N.º carné
- N.º carnés
- N.º carné
- N.º carnés
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- N.º carné #
- N.º carnés #
- N.º carné #
- N.º carnés #
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Conducción
- Conducción
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Permisos de conducción
- DriverLicense #
- DriverLicenses #
- Driver License#
- Driver Licenses#
- DriversLicense #
- DriversLicenses #
- Drivers License#
- Drivers Licenses#
- Conducción #
- Conducción #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Número de cuenta médica de Australia

### <a name="format"></a>Formato

Entre 10 y 11 dígitos

### <a name="pattern"></a>Pattern

Entre 10 y 11 dígitos:
- el primer dígito está en el intervalo de 2 a 6
- El noveno dígito es un dígito de comprobación
- El décimo dígito es el dígito de emisión
- El undécimo dígito (opcional) es el número individual

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- Medicare

   
## <a name="australia-passport-number"></a>Número de pasaporte de Australia

### <a name="format"></a>Formato

Una letra seguida de siete dígitos

### <a name="pattern"></a>Pattern

Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_passport o Keyword_australia_passport_number.

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Usuarios #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- usuarios
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- régimen
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>Número de archivo de impuestos de Australia

### <a name="format"></a>Formato

Entre 8 y 9 dígitos

### <a name="pattern"></a>Pattern

8-9 dígitos que normalmente se presentan con espacios como sigue:
- Tres dígitos 
- Un espacio opcional 
- Tres dígitos 
- Un espacio opcional 
- 2-3 dígitos donde el último dígito es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.
- Se supera la suma de comprobación.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_tax_file_number"></a>Keyword_Australia_Tax_File_Number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number

#### <a name="keyword_number_exclusions"></a>Keyword_number_exclusions

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999

## <a name="austria-drivers-license-number"></a>Número de permiso de conducción de Austria
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_austria_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de `Keywords_austria_eu_driver's_license_number` . 
    
```xml
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_austria_eu_driver ' s_license_number**
- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- driver's licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- fuhrerschein
- fuhrerschein republik osterreich

## <a name="austria-national-identification-number"></a>Número de identificación nacional de Austria
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Una combinación de letras, dígitos y caracteres especiales de 24 caracteres
  
### <a name="pattern"></a>Pattern

24 caracteres:
  
-  22 letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más 
    
- Dos letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales, signos más o signos igual
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_austria_eu_national_id_card` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de `Keywords_austria_eu_national_id_card` . 
   
```xml
<!-- EU austria_eu_national_id -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- número de identidad
- 
national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Número de pasaporte de Austria
Esta entidad de tipo de información confidencial solo está disponible en el tipo sensitiveinformation de número de pasaporte de la UE.

### <a name="format"></a>Formato

Una letra seguida de un espacio opcional y siete dígitos
  
### <a name="pattern"></a>Pattern

Una combinación de una letra, siete dígitos y un espacio:
  
- Una letra (no distingue entre mayúsculas y minúsculas)
    
- Un espacio (opcional)
    
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_austria_eu_passport_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de `Keywords_austria_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_austria_eu_passport_number**
- passport number
- número de pasaporte austriaco
- n.º de pasaporte
- reisepass
- österreichisch reisepass

## <a name="austria-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Austria o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

10 dígitos en el formato especificado
  
### <a name="pattern"></a>Pattern

10 dígitos:
  
-  Tres dígitos que corresponden a un número de serie 
- Un dígito de control
- Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de `Keywords_austria_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- n.º de seguridad social
- social security number
- social security code
- número de seguro
- SSN austriaco
- SSN #
- SSN
- código de seguro
- código de seguro #
- socialsecurityno #
- sozialversicherungsnummer
- soziale sicherheit kein
- versicherungsnummer

## <a name="austria-tax-identification-number"></a>Número de identificación fiscal de Austria
Esta entidad de tipo de información confidencial solo está disponible el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Nueve dígitos con guión opcional y barra diagonal
  
### <a name="pattern"></a>Pattern

Nueve dígitos con guión opcional y barra diagonal:
  
- Dos dígitos
- Un guion (opcional)
- Tres dígitos
- Una barra diagonal (opcional)
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_austria_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr.
- steuernummer
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de impuesto

## <a name="azure-documentdb-auth-key"></a>Clave de autenticación de Azure DocumentDB

### <a name="format"></a>Formato

La cadena "DocumentDb" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.

### <a name="pattern"></a>Pattern

- La cadena "DocumentDb"
- Cualquier combinación de entre 3-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- Un símbolo mayor que (>), un signo igual (=), una comilla (") o un apóstrofo (')
- Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- Dos signos de igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureDocumentDBAuthKey encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Cadena de conexión de base de datos IAAS de Azure y cadena de conexión SQL de Azure

### <a name="format"></a>Formato

La cadena "Server", "Server" o "Data Source" seguida de los caracteres y las cadenas que se describen en el siguiente patrón, incluida la cadena "CloudApp. Azure.<!--no-hyperlink-->com "o" CloudApp. Azure.<!--no-hyperlink-->net "o" Database. Windows.<!--no-hyperlink-->net "y la cadena" Password "o" Password "o" pwd ".

### <a name="pattern"></a>Pattern

- La cadena "servidor", "servidor" o "origen de datos"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "CloudApp. Azure.<!--no-hyperlink-->com "," CloudApp. Azure.<!--no-hyperlink-->net "o" Database. Windows.<!--no-hyperlink-->ADO.net
- Cualquier combinación de entre 1-300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "Password", "Password" o "pwd"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Uno o más caracteres que no son un punto y coma (;), Comillas (") o apóstrofe (')
- Un punto y coma (;), Comillas (") o apóstrofe (')

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureConnectionString encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="azure-iot-connection-string"></a>Cadena de conexión de Azure IoT

### <a name="format"></a>Formato

La cadena "HostName" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "Azure-Devices.<!--no-hyperlink-->net "y" SharedAccessKey ".

### <a name="pattern"></a>Pattern

- La cadena "HostName"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "Azure-Devices.<!--no-hyperlink-->ADO.net
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "SharedAccessKey"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de 43 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- Un signo igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureIoTConnectionString encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="azure-publish-setting-password"></a>Contraseña de configuración de publicación de Azure

### <a name="format"></a>Formato

La cadena "userpwd =" seguida de una cadena alfanumérica.

### <a name="pattern"></a>Pattern

- La cadena "userpwd ="
- Cualquier combinación de 60 letras minúsculas o dígitos
- Un signo de Comillas (")

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzurePublishSettingPasswords encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="azure-redis-cache-connection-string"></a>Cadena de conexión de la caché de Redis de Azure

### <a name="format"></a>Formato

La cadena "Redis. Cache. Windows.<!--no-hyperlink-->net "seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena" Password "o" pwd ".

### <a name="pattern"></a>Pattern

- La cadena "Redis. Cache. Windows.<!--no-hyperlink-->ADO.net
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "Password" o "pwd"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- Un signo igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureRedisCacheConnectionString encuentra contenido que coincide con el patrón..
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="azure-sas"></a>ASOCIACIONES de Microsoft Azure

### <a name="format"></a>Formato

La cadena "SIG" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.

### <a name="pattern"></a>Pattern

- La cadena "SIG"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de entre 43-53 caracteres que sean letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)
- La cadena "% 3D"
- Cualquier carácter que no sea una letra minúscula o mayúscula, un dígito o un signo de porcentaje (%)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureSAS encuentra contenido que coincide con el patrón.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Cadena de conexión del bus de servicio de Azure

### <a name="format"></a>Formato

La cadena "EndPoint" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluidas las cadenas "ServiceBus. Windows.<!--no-hyperlink-->net "y" SharedAccesKey ".

### <a name="pattern"></a>Pattern

- La cadena "EndPoint"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "ServiceBus. Windows.<!--no-hyperlink-->ADO.net
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "SharedAccessKey"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- Un signo igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureServiceBusConnectionString encuentra contenido que coincide con el patrón..
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="azure-storage-account-key"></a>Clave de cuenta de almacenamiento de Azure

### <a name="format"></a>Formato

La cadena "DefaultEndpointsProtocol" seguida de los caracteres y las cadenas que se describen en el patrón siguiente, incluida la cadena "AccountKey".

### <a name="pattern"></a>Pattern

- La cadena "DefaultEndpointsProtocol"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "AccountKey"
- 0-2 caracteres de espacio en blanco
- Un signo igual (=)
- 0-2 caracteres de espacio en blanco
- Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- Dos signos de igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureStorageAccountKey encuentra contenido que coincide con el patrón.
- La expresión regular CEP_AzureEmulatorStorageAccountFilter **no** encuentra contenido que coincida con el patrón.
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_azureemulatorstorageaccountfilter"></a>CEP_AzureEmulatorStorageAccountFilter

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="azure-storage-account-key-generic"></a>Clave de cuenta de almacenamiento de Azure (Genérico)

### <a name="format"></a>Formato

Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+), precedido o seguido por los caracteres descritos en el patrón siguiente.

### <a name="pattern"></a>Pattern

- 0-1 del símbolo mayor que (>), apóstrofe ('), signo de igual (=), Comillas (") o almohadilla (#)
- Cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+)
- Dos signos de igual (=)


### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureStorageAccountKeyGeneric encuentra contenido que coincide con el patrón.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Número de permiso de conducción de Bélgica
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_belgium_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_belgium_eu_driver's_license_number` .
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords__belgium_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- dlno #
- rijbewijs
- rijbewijsnummer
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- Führerschein-NR
- fuehrerschein-NR
- fuehrerschein-NR

## <a name="belgium-national-number"></a>Número nacional de Bélgica
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

11 dígitos más delimitadores

### <a name="pattern"></a>Pattern

11 dígitos más delimitadores:
- Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento  
- Un guión  
- Tres dígitos secuenciales (impares para hombres, pares para mujeres)  
- Un punto  
- Dos dígitos que son un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_belgium_national_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_belgium_national_number.
- Se supera la suma de comprobación.

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- la última aantal
- bnn #
- bnn
- Carta d'identité
- Nacional del identificador
- identifiantnational #
- identificatie
- determinación
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identifica
- indicación
- número nacional
- Registro Nacional
- nationalnumber #
- nationalnumber
- NIF #
- NIF
- numéro d'assuré
- numéro de registros nacionales
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- numéro nacional
- numéronational #
- número de identificación personal
- personalausweis
- personalidnumber #
- registratie
- registro
- registrationsnumme
- registrierung
- social security number

- SSN #
- SSN
- steuernummer
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="belgium-passport-number"></a>Número de pasaporte de Bélgica
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Dos letras y seguidas de seis dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_belgium_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_belgium_eu_passport_number` .

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_belgium_eu_passport_number**
- passport number
- número de pasaporte belga
- n.º de pasaporte
- paspoort
- paspoortnummer
- reisepass kein
- reisepass

## <a name="belgium-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Bélgica o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_belgium_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

- número nacional belga
- número nacional
- social security number
- nationalnumber #
- SSN #
- SSN
- nationalnumber
- bnn #
- bnn
- número de identificación personal
- personalidnumber #
- numéro nacional
- numéro de sécurité
- numéro d'assuré
- Nacional del identificador
- identifiantnational #
- numéronational #

## <a name="belgium-tax-identification-number"></a>Número de identificación fiscal de Bélgica
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de la UE Identificaiton número de información confidencial.

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos:
  
- Dos dígitos
- Un "0" o "1"
- Un dígito
- Un "0" o "1" o "2" o "3" 
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_belgium_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_belgium_eu_tax_file_number` . 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

- la última aantal
- bnn #
- bnn
- Carta d'identité
- Nacional del identificador
- identifiantnational #
- identificatie
- determinación
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identifica
- indicación
- número nacional
- Registro Nacional
- nationalnumber #
- nationalnumber
- NIF #
- NIF
- numéro d'assuré
- numéro de registros nacionales
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- numéro nacional
- numéronational #
- número de identificación personal
- personalausweis
- personalidnumber #
- registratie
- registro
- registrationsnumme
- registrierung
- social security number

- SSN #
- SSN
- steuernummer
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #


## <a name="brazil-cpf-number"></a>Número de CPF de Brasil

### <a name="format"></a>Formato

11 dígitos incluido un dígito de control y que pueden tener o no formato

### <a name="pattern"></a>Pattern

Con formato
- Tres dígitos
- Un punto 
- Tres dígitos
- Un punto 
- Tres dígitos
- Un guión 
- Dos dígitos que son dígitos de control

Sin formato
- 11 dígitos, donde los dos últimos dígitos son dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cpf encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_cpf.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cpf encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Determinación
- Registro
- Generar
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 
   
## <a name="brazil-legal-entity-number-cnpj"></a>Número de entidad jurídica de Brasil (CNPJ)

### <a name="format"></a>Formato

14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores

### <a name="pattern"></a>Pattern
14 dígitos más delimitadores:
- Dos dígitos 
- Un punto  
- Tres dígitos 
- Un punto  
- Tres dígitos (estos ocho primeros dígitos son el número de registro)  
- Una barra diagonal  
- Número de sucursal de cuatro dígitos  
- Un guión  
- Dos dígitos que son dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_cnpj.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- Registro nacional de entidades jurídicas 
- Registro de contribuyentes 
- Entidad jurídica 
- Entidades jurídicas 
- Estado de registro 
- Negocio 
- Company
- CNPJ 
- Cadastro Nacional da Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- Inscrição 
- Empresa 
   
## <a name="brazil-national-identification-card-rg"></a>Tarjeta de identificación nacional de Brasil (RG)

### <a name="format"></a>Formato

Registro geral (formato anterior): nueve dígitos

Registro de Identidade (RIC) (nuevo formato): 11 dígitos

### <a name="pattern"></a>Pattern

Registro de Geral (formato antiguo):
- Dos dígitos 
- Un punto  
- Tres dígitos 
- Un punto  
- Tres dígitos 
- Un guión  
- Un dígito que es un dígito de control

Registro de Identidade (RIC) (nuevo formato):
- 10 dígitos 
- Un guión  
- Un dígito que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_rg encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_rg.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_rg encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- documento de identidad
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG (esta palabra clave distingue entre mayúsculas y minúsculas) 
- RIC (esta palabra clave distingue entre mayúsculas y minúsculas) 


## <a name="bulgaria-drivers-license-number"></a>Número de permiso de conducción de Bulgaria
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_bulgaria_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_bulgaria_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    
```

### <a name="keywords"></a>Keywords

**Keywords_bulgaria_eu_driver ' s_license_number**
- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка

## <a name="bulgaria-national-identification-number"></a>Número de identificación nacional de Bulgaria
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Diez dígitos sin espacios y delimitadores
  
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- Dos dígitos que corresponden a la orden de nacimiento
- Un dígito que corresponde al género: un dígito par para macho y un dígito impar para hembra
- Un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_bulgaria_national_number` . 

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

- bnn #
- bnn
- bucn #
- bucn
- edinen grazhdanski nomer
- egn #
- egn
- identification number

- 
national id
- número nacional
- nationalnumber #
- nationalnumber
- identificador personal
- no personal
- número personal
- personalidnumber #
- social security number

- SSN #
- SSN
- identificador civil uniforme
- Uniform civil no
- número civil uniforme
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- número de ciudadanía único
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- identificador униформ
- униформ граждански ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #

## <a name="bulgaria-passport-number"></a>Número de pasaporte de Bulgaria
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_bulgaria_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_bulgaria_eu_passport_number` . 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

**Keywords_bulgaria_eu_passport_number**
- passport number
- número de pasaporte búlgaro
- n.º de pasaporte
- номер на паспорта

## <a name="bulgaria-tax-identification-number"></a>Número de identificación fiscal de Bulgaria
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_bulgaria_eu_tax_file_number` . 

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_bulgaria_eu_tax_file_number` busca contenido que coincide con el patrón. 

```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number
- bnn #
- bnn
- bucn #
- bucn
- edinen grazhdanski nomer
- egn #
- egn
- identification number

- 
national id
- número nacional
- nationalnumber #
- nationalnumber
- identificador personal
- no personal
- número personal
- personalidnumber #
- social security number

- SSN #
- SSN
- identificador civil uniforme
- Uniform civil no
- número civil uniforme
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- número de ciudadanía único
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- identificador униформ
- униформ граждански ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="canada-bank-account-number"></a>Número de cuenta bancaria de Canadá

### <a name="format"></a>Formato

Siete o doce dígitos

### <a name="pattern"></a>Pattern

El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.

Un número de tránsito de cuenta bancaria de Canadá es:
- Cinco dígitos 
- Un guion 
- Tres dígitos o
- Un cero "0"  
- Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_bank_account_number.
- La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_bank_account_number.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit
   
## <a name="canada-drivers-license-number"></a>Número de permiso de conducción de Canadá

### <a name="format"></a>Formato

Varía según la provincia

### <a name="pattern"></a>Pattern

Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.
- Se encuentra una palabra clave de Keyword_canada_drivers_license.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

- La abreviatura de la provincia, por ejemplo, AB
- El nombre de la provincia, por ejemplo, Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- LISTAS
- DISTRIBUCIÓN
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- N.º carné
- N.º carnés
- Conducción
- Conducción
- N.º carné
- N.º carnés
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- tarjeta
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- determinación 
- LISTAS #
- DISTRIBUCIÓN # 
- CDL # 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- N.º carné # 
- N.º carnés # 
- Conducción # 
- Conducción # 
- N.º carné # 
- N.º carnés # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- identificador # 
- falta # 
- idcard card# 
- idcard cards# 
- tarjeta # 
- identification card# 
- identification cards# 
- determinación # 
   
## <a name="canada-health-service-number"></a>Número de servicio de salud de Canadá

### <a name="format"></a>Formato

10 dígitos

### <a name="pattern"></a>Pattern

10 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_health_service_number.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- psychiatrist
- workers compensation
- discapacidad
      
## <a name="canada-passport-number"></a>Número de pasaporte de Canadá

### <a name="format"></a>Formato

Dos letras mayúsculas seguidas por seis dígitos

### <a name="pattern"></a>Pattern

Dos letras mayúsculas seguidas por seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_passport_number o Keyword_passport.

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Usuarios #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>Número de identificación sanitaria personal de Canadá (PHIN)

### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Pattern

Nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón.
Se encuentran al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces..

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- Quebec
- Northwest Territories
- Ontario
- British Columbia
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Canadá
   
## <a name="canada-social-insurance-number"></a>Número del seguro social de Canadá

### <a name="format"></a>Formato

Nueve dígitos con guiones opcionales o espacios

### <a name="pattern"></a>Pattern

Con formato
- Tres dígitos  
- Un guion o un espacio 
- Tres dígitos 
- Un guion o un espacio 
- Tres dígitos

Sin formato: nueve dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_canadian_sin encuentra contenido que coincide con el patrón.
- Al menos dos de cualquier combinación de lo siguiente:
    - Se encuentra una palabra clave de Keyword_sin.
    - Se encuentra una palabra clave de Keyword_sin_collaborative.
    - La función Func_eu_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_sin.
- Se supera la suma de comprobación.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- pecados 
- SSN 
- SSN 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- PIN # 
- soc ins 
- social ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- NACIMIENTO 
- Fecha de nacimiento 
- Birthday 
- Fecha de nacimiento 
   
## <a name="chile-identity-card-number"></a>Número de tarjeta de identidad de Chile

### <a name="format"></a>Formato

7-8 dígitos más delimitadores, un dígito de control o una letra

### <a name="pattern"></a>Pattern

7 u 8 dígitos más delimitadores:
- 1 o 2 dígitos  
- Un punto  
- Tres dígitos 
- Un punto  
- Tres dígitos 
- Un guión  
- Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_chile_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_chile_id_card.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_chile_id_card encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- Número de identificación nacional 
- tarjeta de identidad 
- ID 
- Determinación 
- Rol Único Nacional 
- REALIZAR 
- Rol Único Tributario 
- ESTANCARSE 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## <a name="china-resident-identity-card-prc-number"></a>Número de tarjeta de identidad de residente de China (PRC)

### <a name="format"></a>Formato

18 dígitos

### <a name="pattern"></a>Pattern

18 dígitos:
- Seis dígitos que son un código de dirección  
- Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento  
- Tres dígitos que son un código de pedido  
- Un dígito que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_china_resident_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_china_resident_id.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_china_resident_id encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Tarjeta de identidad de residente 
- China 
- Tarjeta de identificación nacional 
- 身份证 
- 居民 身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民 身份證
- 鑑定 
   
## <a name="credit-card-number"></a>Número de tarjeta de crédito

### <a name="format"></a>Formato

de 14 a 16 dígitos que pueden ser formateados o sin formato (dddddddddddddddd) y que deben pasar la prueba Luhn.

### <a name="pattern"></a>Pattern

Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.

### <a name="checksum"></a>Suma de comprobación

Sí, la suma de comprobación de Luhn

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_credit_card encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_cc_verification.
    - Se encuentra una palabra clave de Keyword_cc_name.
    - La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_credit_card encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- COD. sicurezza
- cod sicurezza
- n autorizzazione
- Código
- codigo
- COD. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- campos. segurança
- COD. DQO SEGURANCA. segurança
- campos. seguranca
- cód segurança
- Bacalao SEGURANCA contra reembolso de segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- 1er
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valorar
- vencimento
- Venc 

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- AMEX
- american express
- americanexpress
- Régimen
- MasterCard
- master card
- valuación 
- MasterCard
- master cards
- diner's Club
- diners club
- dinersclub
- discover card
- detectar tarjeta
- discover cards
- JCB
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- CC #
- # CC:
- expiration date
- exp date
- expiry date
- fecha d'expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- crédito
- credit cards
- creditcards
- CCN
- card holder
- titular
- card holders
- titulares de la titular
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
- atm card
- atmcard
- atm cards
- atmcards
- enrutar
- en route
- card type
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr 
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- cobro
- n carta
- Nº. cobro
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- No. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão 
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- Nº. do cartão
- no do cartão
- no do cartao
- No. do cartão
- No. do cartao 

## <a name="croatia-drivers-license-number"></a>Número de permiso de conducción de Croacia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_croatia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_croatia_eu_driver's_license_number` . 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_croatia_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- vozačka dozvola

## <a name="croatia-identity-card-number"></a>Número de tarjeta de identidad de Croacia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.


### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Pattern

Nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_croatia_id_card.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- número de ciudadano principal
- nacionalni identifikacijski broj
- número de identificación nacional
- OIB #
- OIB
- osobna iskaznica
- identificador osobni
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="croatia-passport-number"></a>Número de pasaporte de Croacia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_croatia_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_croatia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

**Keywords_croatia_eu_passport_number**

- passport number
- número de pasaporte de croata
- n.º de pasaporte
- broj putovnice

   
## <a name="croatia-personal-identification-oib-number"></a>Número de identificación personal de Croacia (OIB)

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Pattern

11 dígitos:
- 10 dígitos 
- El dígito final es un dígito de control para el intercambio internacional de datos, se agregan las letras h antes de los once dígitos.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_croatia_oib_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- Número de identificación personal
- Osobni identifikacijski broj 
- OIB 

## <a name="croatia-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Croacia o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 11 dígitos:
  
- Diez dígitos
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_croatia_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- número de identificación personal
- número de ciudadano principal
- national identification number
- social security number
- nationalnumber #
- SSN #
- SSN
- nationalnumber
- bnn #
- bnn
- número de identificación personal
- personalidnumber #
- OIB
- osobni identifikacijski broj
   
## <a name="croatia-tax-identification-number"></a>Número de identificación fiscal de Croacia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de Identificaiton de impuestos de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos:
  
- Diez dígitos, elegidos aleatoriamente
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_croatia_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_croatia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

- majstorski broj građana
- número de ciudadano principal
- nacionalni identifikacijski broj
- número de identificación nacional
- OIB #
- OIB
- osobna iskaznica
- identificador osobni
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="cyprus-drivers-license-number"></a>Número de licencia de controladores de Chipre
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

12 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

12 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_cyprus_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_cyprus_eu_driver's_license_number` .

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_cyprus_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- άδεια οδήγησης

## <a name="cyprus-national-identification-number"></a>Número de identificación nacional de Chipre
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 Diez dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_cyprus_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_cyprus_eu_national_id_card` . 
    
```xml 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- número de tarjeta de identificación
- número de tarjeta de identidad
- kimlik karti
- número de identificación nacional
- número de identificación personal
- ταυτοτητασ

## <a name="cyprus-passport-number"></a>Número de pasaporte de Chipre
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Una letra seguida de 6-8 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Una letra seguida de seis a ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_cyprus_eu_passport_number` busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_cyprus_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_cyprus_eu_passport_number**

- passport number
- número de pasaporte de Chipre
- n.º de pasaporte
- αριθμό διαβατηρίου

## <a name="cyprus-tax-identification-number"></a>Número de identificación fiscal de Chipre
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Ocho dígitos y una letra en el patrón especificado
  
### <a name="pattern"></a>Pattern

Ocho dígitos y una letra:
  
-  Un "0" 
- Siete dígitos 
- Una letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_cyprus_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id

- código de identificación de impuestos
- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- verticales #
- verticales
- ID de estaño
- n.º de estaño
- / #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού
- número de impuesto

## <a name="czech-drivers-license-number"></a>Número de permiso de conducción de Checo
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Pattern

Ocho letras y dígitos:
  
- Dos letras (sin distinción entre mayúsculas y minúsculas)
- Un espacio (opcional) 
- Seis dígitos

### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_czech_republic_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_czech_republic_eu_driver's_license_number` . 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

**Keywords_czech_republic_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- řidičský prúkaz

## <a name="czech-passport-number"></a>Número de pasaporte Checo
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Ocho dígitos sin espacios ni delimitadores
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_czech_republic_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_czech_republic_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_czech_republic_eu_passport_number**

- passport number
- número de pasaporte Checo
- n.º de pasaporte
- Cestovní PAS
- PAS

## <a name="czech-personal-identity-number"></a>Número de identidad personal en Checo
Esta entidad de tipo de información confidencial se incluye en el paquete de números de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Nueve dígitos con barra diagonal (formato antiguo) 10 dígitos con barra diagonal (nuevo formato) opcional

### <a name="pattern"></a>Pattern

Nueve dígitos (formato antiguo):
- Nueve dígitos

O

- Seis dígitos que representan la fecha de nacimiento
- Una barra diagonal 
- Tres dígitos

10 dígitos (nuevo formato):
- 10 dígitos

O

- Seis dígitos que representan la fecha de nacimiento
- Una barra diagonal  
- Cuatro dígitos donde el último dígito es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_czech_id_card encuentra contenido que coincide con el patrón.
Se encuentra una palabra clave de Keyword_czech_id_card.
Se supera la suma de comprobación.

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

- número de identidad personal en Checo
- Rodné číslo



## <a name="czech-social-security-number-or-equivalent-identification"></a>Número de la seguridad social en Checo o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

Diez dígitos y una barra diagonal inversa en el patrón especificado
  
### <a name="pattern"></a>Pattern

Diez dígitos y una barra diagonal inversa:
  
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD): 
    
- Una barra diagonal inversa
    
- Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha.
    
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_czech_republic_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 

```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- número de nacimiento
- national identification number
- número de identificación personal
- social security number
- nationalnumber #
- SSN #
- SSN
- número nacional
- número de identificación personal
- personalidnumber #
- rč
- rodné číslo
- rodne cislo

## <a name="czech-tax-identification-number"></a>Número de identificación fiscal Checa
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Nueve o diez dígitos con una barra diagonal inversa opcional
  
### <a name="pattern"></a>Pattern

Nueve o diez dígitos con una barra diagonal inversa opcional:
  
- Seis dígitos 
- Una barra diagonal inversa (opcional)
- Tres o cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_czech_republic_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_czech_republic_eu_tax_file_number` . 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

- identificador de República Checa
- czechidno #
- daňové číslo
- identifikační číslo
- n.º de identidad
- número de identidad
- identityno #
- identityno
- número de seguro
- número de identificación nacional
- número nacional
- osobní číslo
- número de identificación personal
- número personal
- ID #
- pid
- pojištění číslo
- rodné číslo
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de identificación único
- número de impuesto

## <a name="denmark-drivers-license-number"></a>Número de permiso de conducción de Dinamarca
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_denmark_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_denmark_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_denmark_eu_driver ' s_license_number**

- | DL #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Número de pasaporte de Dinamarca
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_denmark_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_denmark_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_denmark_eu_passport_number**

- passport number
- número de pasaporte danés
- n.º de pasaporte
- PAS
- pasnummer

## <a name="denmark-personal-identification-number"></a>Número de identificación personal de Dinamarca
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

10 dígitos que contienen un guión

### <a name="pattern"></a>Pattern

10 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un guión  
- 4 dígitos en los que el último dígito es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la expresión regular Regex_denmark_id encuentra contenido que coincide con el patrón.
Se encuentra una palabra clave de Keyword_denmark_id.
Se supera la suma de comprobación.

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- registreringssystem civil
- RCP
- RCP #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- tarjeta de mantenimiento
- número de tarjeta de seguro de salud
- número de seguro de salud
- identification number

- identifikationsnummer
- identifikationsnummer #
- número de identidad
- krankenkassennummer
- nationalid #
- personalidentityno #
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- identificador de patinaje
- Kode de patinaje
- Nummer de patinaje
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- código de impuestos
- ficha de seguro de mantenimiento de viajes
- uniqueidentityno #
- número de impuesto
- NIF-CIF
- tax id

- número de identificación fiscal
- taxi #
- taxnumber #
- Nº de impuestos
- taxno #
- taxnumber
- n.º de identificación fiscal
- / #
- taxidno #
- taxidnumber #
- Nº de impuestos #
- ID de estaño
- n.º de estaño

## <a name="denmark-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Dinamarca o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

Diez dígitos y un guión en el patrón especificado
  
### <a name="pattern"></a>Pattern

Diez dígitos y un guión:
  
- Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
- Un guión 
- Cuatro dígitos que corresponden a un número de secuencia
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_denmark_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- número de identificación personal
- national identification number
- social security number
- nationalnumber #
- SSN #
- SSN
- número nacional
- número de identificación personal
- personalidnumber #
- CPR-Nummer
- personnummer

## <a name="denmark-tax-identification-number"></a>Número de identificación fiscal de Dinamarca
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Diez dígitos que contienen un guión
  
### <a name="pattern"></a>Pattern

Diez dígitos que contienen un guión:
  
-  Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)
- Un guión 
- Cuatro dígitos que corresponden a un número de secuencia en el que el primer dígito corresponde al siglo de nacimiento y el último dígito corresponde al sexo de la persona (impar para macho e incluso para hembras)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_denmark_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_denmark_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

- centrale personregister
- registreringssystem civil
- RCP
- RCP #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- tarjeta de mantenimiento
- número de tarjeta de seguro de salud
- número de seguro de salud
- identification number

- identifikationsnummer
- identifikationsnummer #
- número de identidad
- krankenkassennummer
- nationalid #
- personalidentityno #
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- identificador de patinaje
- Kode de patinaje
- Nummer de patinaje
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- código de impuestos
- ficha de seguro de mantenimiento de viajes
- uniqueidentityno #
- número de impuesto
- NIF-CIF
- tax id

- número de identificación fiscal
- taxi #
- taxnumber #
- Nº de impuestos
- taxno #
- taxnumber
- n.º de identificación fiscal
- / #
- taxidno #
- taxidnumber #
- Nº de impuestos #
- ID de estaño
- n.º de estaño


## <a name="drug-enforcement-agency-dea-number"></a>Número de la Agencia para la imposición de drogas (DEA)

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos

### <a name="pattern"></a>Pattern

El patrón debe incluir todo lo siguiente:
- Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito 
- Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito. 
- Siete dígitos, el último de los cuales es el dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_dea_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

Ninguno

## <a name="estonia-drivers-license-number"></a>Número de permiso de conducción de Estonia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Pattern

Dos letras y seis dígitos:
  
-  Las letras "ET" (sin distinción entre mayúsculas y minúsculas) 
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_estonia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_estonia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_estonia_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- permis de conduire

## <a name="estonia-national-identification-number"></a>Estonia número de identificación nacional
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos:
  
- Un dígito que corresponde al sexo y al siglo de nacimiento (número impar macho, par hembra; 1-2: siglo XIX; 3-4: siglo XX; 5-6: siglo XXI)
    
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
- Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_estonia_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- ID-Kaart
- IK
- isikukood #
- isikukood
- identificador maksu
- maksukohustuslase identifitseerimisnumber
- maksunumber
- número de identificación nacional
- número nacional
- código personal
- número de identificación personal
- código de identificación personal
- número de identificación personal
- personalidnumber #
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="estonia-passport-number"></a>Número de pasaporte de Estonia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Una letra seguida de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Una letra seguida de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_estonia_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_estonia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_estonia_eu_passport_number**

- passport number
- número de pasaporte de estonio
- n.º de pasaporte
- Eesti kodaniku Pass

## <a name="estonia-tax-identification-number"></a>Número de identificación de impuestos de Estonia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos:
  
-  Un dígito que corresponde al sexo y al siglo de nacimiento donde un número impar indica macho y el número par indica hembra de la siguiente manera: 1,2 para el siglo XIX; 3, 4 para el siglo XX; y 5, 6 para el siglo XXI 
    
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
- Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_estonia_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_estonia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

- ID-Kaart
- IK
- isikukood #
- isikukood
- identificador maksu
- maksukohustuslase identifitseerimisnumber
- maksunumber
- número de identificación nacional
- número nacional
- código personal
- número de identificación personal
- código de identificación personal
- número de identificación personal
- personalidnumber #
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="eu-debit-card-number"></a>Número de tarjeta de débito de la UE

### <a name="format"></a>Formato

16 dígitos

### <a name="pattern"></a>Pattern

Patrón muy complejo y robusto

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_eu_debit_card encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_eu_debit_card.
    - Se encuentra una palabra clave de Keyword_card_terms_dict.
    - Se encuentra una palabra clave de Keyword_card_security_terms_dict.
    - Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.
    - La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- CC # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- americanexpress 
- americano espresso 
- AMEX 
- atm card 
- atm cards 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- bancontact 
- bank card 
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- titular 
- titulares de la titular 
- cardnumber 
- cardnumbers 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- carte bancaire 
- carte blanche 
- carte bleue 
- carte de credit 
- carte de crédit 
- carte di credito 
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- CCN 
- check card 
- check cards 
- checkcard
- checkcards 
- chequekaart 
- Logic 
- Cirrus-EDC-maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- crédito 
- creditcards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- debitcard 
- debitcards 
- debito automatico 
- diners club 
- dinersclub 
- advierte 
- discover card 
- discover cards 
- detectar tarjeta 
- discovercards 
- débito automático
- EDC 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- JCB 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- dispositivos 
- master card 
- master cards 
- MasterCard 
- MasterCard 
- valuación 
- mister cash 
- n carta 
- cobro 
- no de tarjeta 
- no do cartao 
- no do cartão 
- No. de tarjeta 
- No. do cartao 
- No. do cartão 
- nr carta 
- Nº. cobro 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de carte 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero do cartao 
- numero do cartão 
- numéro de carte 
- nº carta 
- nº de carte 
- nº de la carte 
- nº de tarjeta 
- nº do cartao 
- nº do cartão 
- Nº. do cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número do cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- solo 
- supporti di scheda 
- supporto di scheda 
- cambia 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-Pay 
- régimen 
- visa plus 
- visa electron 
- a 
- visum 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- COD. seg 
- COD. seguranca 
- COD. segurança 
- COD. sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- criptograma 
- cryptogramme 
- cv2 
- cvc 
- cvc2 
- cvn 
- CVV 
- cvv2 
- cód seguranca 
- cód segurança 
- campos. seguranca 
- campos. segurança 
- Código 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- issue no 
- issue number 
- kaartidentificatienummer 
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- No. dell'edizione 
- No. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- pin block 
- prufziffer 
- prüfziffer 
- security code 
- security no 
- security number 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid nr 
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf 
- data de expiracao 
- data de expiração 
- data del exp 
- data di exp 
- data di scadenza 
- data em que expira 
- data scad 
- data scadenza 
- date de validité 
- datum afloop 
- datum van exp 
- de afloop 
- espira 
- espira 
- exp date 
- exp datum 
- expiración 
- expiran 
- expira 
- expiración 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- validade 
- valido hasta 
- valorar 
- venc 
- vencimento 
- 1er 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 

## <a name="eu-drivers-license-number"></a>Número de permiso de conducción de la UE
Estas son las entidades en el tipo de información confidencial del número de licencia de conductor de la UE.

- [Austria](#austria-drivers-license-number) 
- [Bélgica](#belgium-drivers-license-number)
- [Bulgaria](#bulgaria-drivers-license-number)
- [Croacia](#croatia-drivers-license-number)
- [Chipre](#cyprus-drivers-license-number)
- [Czech](#czech-drivers-license-number)
- [Dinamarca](#denmark-drivers-license-number)
- [Estonia](#estonia-drivers-license-number)
- [Finlandia](#finland-drivers-license-number)
- [Francia](#france-drivers-license-number) 
- [Alemania](#germany-drivers-license-number)
- [Grecia](#greece-drivers-license-number)
- [Hungría](#hungary-drivers-license-number)
- [Irlanda](#ireland-drivers-license-number)
- [Italia](#italy-drivers-license-number)
- [Letonia](#latvia-drivers-license-number)
- [Lituania](#lithuania-drivers-license-number)
- [Luxemburgo](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Países Bajos](#netherlands-drivers-license-number)
- [Polonia](#poland-drivers-license-number) 
- [Portugal](#portugal-drivers-license-number)
- [Rumania](#romania-drivers-license-number)
- [Eslovaquia](#slovakia-drivers-license-number)
- [Eslovenia](#slovenia-drivers-license-number)
- [España](#spain-drivers-license-number)
- [Suecia](#sweden-drivers-license-number)
- [RU](#uk-drivers-license-number)

## <a name="eu-national-identification-number"></a>Número de identificación nacional de la UE
Estas son las entidades en el tipo de información confidencial de número de identificación nacional de la UE.

- [Austria](#austria-national-identification-number)
- [Bélgica](#belgium-national-number)
- [Bulgaria](#bulgaria-national-identification-number)
- [Croacia](#croatia-identity-card-number)
- [Chipre](#cyprus-national-identification-number)
- [Czech](#czech-personal-identity-number)
- [Dinamarca](#denmark-personal-identification-number)
- [Estonia](#estonia-national-identification-number)
- [Finlandia](#finland-national-identification-number)
- [Francia](#france-national-identification-card-cni)
- [Alemania](#germany-identity-card-number)
- [Grecia](#greece-national-id-card)
- [Hungría](#hungary-national-identification-number)
- [Irlanda](#ireland-national-identification-number)
- [Italia](#italy-national-identification-number)
- [Letonia](#latvia-national-identification-number)
- [Lituania](#lithuania-national-identification-number)
- [Luxemburgo](#luxemburg-national-identification-number)
- [Malta](#malta-national-identification-number)
- [Países Bajos](#netherlands-national-identification-number)
- [Polonia](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Rumania](#romania-national-identification-number)
- [Eslovaquia](#slovakia-national-identification-number)
- [Eslovenia](#slovenia-national-identification-number)
- [España](#spain-national-identification-number)
- [RU](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>Número de pasaporte de la UE 
Estas son las entidades de la información confidencial de los números de pasaporte de la UE typeThese son las entidades de la agrupación de números de pasaporte de la UE.

- [Austria](#austria-passport-number)
- [Bélgica](#belgium-passport-number)
- [Bulgaria](#bulgaria-passport-number)
- [Croacia](#croatia-passport-number)
- [Chipre](#cyprus-passport-number)
- [Czech](#czech-passport-number)
- [Dinamarca](#denmark-passport-number)
- [Estonia](#estonia-passport-number)
- [Finlandia](#finland-passport-number)
- [Francia](#france-passport-number)
- [Alemania](#germany-passport-number)
- [Grecia](#greece-passport-number)
- [Hungría](#hungary-passport-number)
- [Irlanda](#ireland-passport-number)
- [Italia](#italy-passport-number)
- [Letonia](#latvia-passport-number)
- [Lituania](#lithuania-passport-number)
- [Luxemburgo](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Países Bajos](#netherlands-passport-number)
- [Polonia](#poland-passport-number)
- [Portugal](#portugal-passport-number)
- [Rumania](#romania-passport-number)
- [Eslovaquia](#slovakia-passport-number)
- [Eslovenia](#slovenia-passport-number)
- [España](#spain-passport-number)
- [Suecia](#sweden-passport-number)
- [RU](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de la UE o identificación equivalente
Estas son las entidades que se encuentran en el número de la seguridad social de la UE o el tipo de información confidencial de identificación equivalente.

- [Austria](#austria-social-security-number-or-equivalent-identification)
- [Bélgica](#belgium-social-security-number-or-equivalent-identification)
- [Croacia](#croatia-social-security-number-or-equivalent-identification)
- [Czech](#czech-social-security-number-or-equivalent-identification)
- [Dinamarca](#denmark-social-security-number-or-equivalent-identification)
- [Finlandia](#finland-social-security-number-or-equivalent-identification)
- [Francia](#france-social-security-number-insee-or-equivalent-identification)
- [Alemania](#germany-identity-card-number)
- [Grecia](#greece-national-id-card)
- [Hungría](#hungary-social-security-number-or-equivalent-identification)
- [Portugal](#portugal-citizen-card-number)
- [España](#spain-social-security-number-ssn)
- [Suecia](#sweden-social-security-number-or-equivalent-identification)

## <a name="eu-tax-identification-number"></a>Número de identificación fiscal de la UE

las entidades de hese se encuentran en el tipo de información confidencial de número de identificación de impuestos de la UE.

- [Austria](#austria-tax-identification-number)
- [Bélgica](#belgium-tax-identification-number)
- [Bulgaria](#bulgaria-tax-identification-number)
- [Croacia](#croatia-tax-identification-number)
- [Chipre](#cyprus-tax-identification-number)
- [Czech](#czech-tax-identification-number)
- [Dinamarca](#denmark-tax-identification-number)
- [Estonia](#estonia-tax-identification-number)
- [Finlandia](#finland-tax-identification-number)
- [Francia](#france-tax-identification-number)
- [Alemania](#germany-tax-identification-number)
- [Grecia](#greece-tax-identification-number)
- [Hungría](#hungary-tax-identification-number)
- [Irlanda](#ireland-tax-identification-number)
- [Italia](#italy-tax-identification-number)
- [Letonia](#latvia-tax-identification-number)
- [Lituania](#lithuania-tax-identification-number)
- [Luxemburgo](#luxemburg-tax-identification-number)
- [Malta](#malta-tax-identification-number)
- [Países Bajos](#netherlands-tax-identification-number)
- [Polonia](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Rumania](#romania-tax-identification-number)
- [Eslovaquia](#slovakia-tax-identification-number)
- [Eslovenia](#slovenia-tax-identification-number)
- [España](#spain-tax-identification-number)
- [Suecia](#sweden-tax-identification-number)
- [RU](#uk-tax-identification-number)


## <a name="finland-drivers-license-number"></a>Número de permiso de conducción de Finlandia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

10 dígitos que contienen un guión
  
### <a name="pattern"></a>Pattern

10 dígitos que contienen un guión:
  
-  Seis dígitos 
- Un guión
-  Cuatro dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_finland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de `Keywords_finland_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_finland_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- ajokortti

## <a name="finland-national-identification-number"></a>Número de identificación nacional de Finlandia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control

### <a name="pattern"></a>Pattern

El patrón debe incluir todo lo siguiente:
- Seis dígitos en el formato DDMMAA que son una fecha de nacimiento 
- Marcador del siglo (ya sea '-', '+' o 'a') 
- Número de identificación personal de tres dígitos 
- Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_finnish_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_finnish_national_id.
- Se supera la suma de comprobación.

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- identificador no
- número de identificador
- identification number

- identiteetti numero
- número de identidad
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- tarjeta de identificación nacional
- n.º de identificación nacional
- identificador personal
- código de identidad personal
- personalidnumber #
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus

## <a name="finland-passport-number"></a>Número de pasaporte de Finlandia
Esta entidad de tipo de información confidencial está disponible en el tipo de información confidencial de la UE número de pasaporte y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato
Combinación de nueve letras y dígitos

### <a name="pattern"></a>Pattern
Combinación de nueve letras y dígitos: dos letras (no distingue entre mayúsculas y minúsculas), siete dígitos

### <a name="checksum"></a>Suma de comprobación
No

### <a name="definition"></a>Definición
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_finland_passport_number.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords
- Keyword_finland_passport_number
- Usuarios
- Passi

## <a name="finland-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Finlandia o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

Una combinación de 11 caracteres en el formato especificado
  
### <a name="pattern"></a>Pattern

Una combinación de 11 caracteres en el formato especificado:
  
-  Seis dígitos 
- Una instancia de una de las siguientes opciones:
  - Símbolo más
  - Símbolo menos
  - La letra "A" (sin distinción entre mayúsculas y minúsculas)
- Tres dígitos
- Una letra o un dígito
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_finland_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

- identification number
- identificador personal
- número de identidad
- número de identificación nacional finlandesa
- personalidnumber #
- national identification number
- número de identificador
- n.º de identificación nacional
- número de identificación nacional
- identificador no
- tunnistenumero
- henkilötunnus
- yksilöllinen henkilökohtainen tunnistenumero
- ainutlaatuinen henkilökohtainen tunnus
- identiteetti numero
- suomen kansallinen henkilötunnus
- henkilötunnusnumero #
- kansallisen tunnistenumero
- tunnusnumero
- kansallinen tunnus numero
- hetu

## <a name="finland-tax-identification-number"></a>Número de identificación fiscal de Finlandia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Una combinación de 11 caracteres de dígitos, letras y más y un signo menos
  
### <a name="pattern"></a>Pattern

Una combinación de 11 caracteres de dígitos, letras y más y un signo menos:
  
- Seis dígitos
- Uno de los siguientes: un signo más, un signo menos o la letra "A" (no distingue entre mayúsculas y minúsculas) donde el signo más significa que nació entre 1800-1899, el signo menos significa que nació entre 1900-1999, y "A" significa que nació 2000 y posterior
- Tres dígitos
- Una letra o un número
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_finland_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_finland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- identificador no
- número de identificador
- identification number

- identiteetti numero
- número de identidad
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- tarjeta de identificación nacional
- n.º de identificación nacional
- identificador personal
- código de identidad personal
- personalidnumber #
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- suomen kansallinen henkilötunnus
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="france-drivers-license-number"></a>Número de permiso de conducción de Francia
Esta entidad de tipo de información confidencial está disponible en el tipo de información confidencial del número de licencia de conductor de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Pattern

12 dígitos con validación para descontar patrones similares como los números de teléfono franceses

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_french_drivers_license encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
- Se encuentra una palabra clave de Keyword_french_drivers_license.
- La función Func_eu_date encuentra una fecha en el formato de fecha correcto.

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers

## <a name="france-national-identification-card-cni"></a>Tarjeta de identificación nacional de Francia (CNI)
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Pattern

12 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

- card number

- Carte de Nationale d'identité
- decir Nationale d'idenite no
- CNI #
- CNI
- compte bancaire
- número de identificación nacional
- identidad nacional
- nationalidno #
- numéro d'assurance maladie
- numéro de la Vitale de la carte

   
## <a name="france-passport-number"></a>Número de pasaporte de Francia
Esta entidad de tipo de información confidencial está disponible en el tipo de información confidencial de la UE número de pasaporte y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Nueve dígitos y letras

### <a name="pattern"></a>Pattern

Nueve dígitos y letras:
- Dos dígitos 
- Dos letras (no distingue entre mayúsculas y minúsculas) 
- Cinco dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_fr_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_passport.

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Usuarios #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Número de la seguridad social de Francia (INSEE) o identificación equivalente
Esta entidad de tipo de información confidencial se incluye en el número de la seguridad social de la UE y el tipo de información confidencial del identificador equivalente, y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

15 dígitos

### <a name="pattern"></a>Pattern

Debe coincidir uno de los dos patrones:
- 13 dígitos seguidos de un espacio seguido de dos dígitos<br/>
o
- 15 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_fr_insee.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_fr_insee.
- Se supera la suma de comprobación.

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- INSEE
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- No. d'identité
- numero d'identite
- no d'identite
- No. d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 

## <a name="france-tax-identification-number"></a>Número de identificación fiscal de Francia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

13 dígitos para personas y nueve dígitos para entidades
  
### <a name="pattern"></a>Pattern

13 dígitos para los usuarios:
  
- Un dígito que debe ser 0, 1, 2 o 3
- 12 dígitos
    
Nueve dígitos para entidades
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_france_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscal
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="germany-drivers-license-number"></a>Número de permiso de conducción de Alemania
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial del número de licencia de conductor de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Combinación de 11 dígitos y letras

### <a name="pattern"></a>Pattern

11 dígitos y letras (no distingue entre mayúsculas y minúsculas):
- Un dígito o letra 
- Dos dígitos 
- Seis dígitos o letras 
- Un dígito 
- Un dígito o letra

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_drivers_license encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_german_drivers_license_number.
    - Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.
    - Se encuentra una palabra clave de Keyword_german_drivers_license.
- Se supera la suma de comprobación.

```xml
<!-- Germany Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- Führerschein
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr
- Fuhrerschein- Nr
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr 
- Fuhrerschein- Nr 
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- LISTAS 
- DISTRIBUCIÓN
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-fuehrerschein
- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-fuehrerschein 

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde

## <a name="germany-identity-card-number"></a>Número de tarjeta de identidad de Alemania
- Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.
- Esta entidad de tipo de información confidencial se incluye en el número de la seguridad social de la UE o en el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

Desde el 1 de noviembre de 2010: nueve letras y dígitos

Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:10 dígitos

### <a name="pattern"></a>Pattern

Desde el 1 de noviembre de 2010:
- Una letra (no distingue entre mayúsculas y minúsculas) 
- Ocho dígitos

Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:
- 10 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_germany_id_card.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- determinación
- identifikation
- identifizierungsnummer
- tarjeta de identidad
- número de identidad
- ID-Nummer
- identificador personal
- personalausweis
- persönliche ID Nummer
- persönliche identifikationsnummer
- persönliche-ID-Nummer


## <a name="germany-passport-number"></a>Número de pasaporte de Alemania
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de la UE número de pasaporte y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

10 dígitos o letras

### <a name="pattern"></a>Pattern

El patrón debe incluir todo lo siguiente:
- El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K) 
- Tres dígitos 
- Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z) 
- Un dígito

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_passport_data encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.
- Se supera la suma de comprobación.

```xml
<!-- Germany Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepass
- reisepasse
- reisepassnummer
- usuarios
- passports

#### <a name="keyword_german_passport_collaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keyword_german_passport_number"></a>Keyword_german_passport_number

No-Reisepass NR-Reisepass

#### <a name="keyword_german_passport1"></a>Keyword_german_passport1

Reisepass-NR

#### <a name="keyword_german_passport2"></a>Keyword_german_passport2

bnationalit. t

## <a name="germany-tax-identification-number"></a>Número de identificación fiscal de Alemania
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos:
  
-  Diez dígitos 
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_germany_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- identificador Steuer
- steueridentifikationsnummer
- steuernummer
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- zinn #
- zinn
- zinnnummer

## <a name="greece-drivers-license-number"></a>Número de permiso de conducción de Grecia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial del número de licencia de conductor de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_greece_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_greece_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_greece_eu_driver ' s_license_number**

- Biblioteca #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- δεια οδήγησης
- Adeia odigisis


## <a name="greece-national-id-card"></a>Tarjeta de identificación nacional de Grecia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Combinación de 7 u 8 letras y números más un guión

### <a name="pattern"></a>Pattern

Siete letras y números (formato antiguo):
- Una letra (cualquier letra del alfabeto griego)  
- Un guión  
- Seis dígitos

Ocho letras y números (nuevo formato):
- Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX)  
- Un guión  
- Seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_greece_id_card.

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- identificador griego
- identificación nacional griega
- tarjeta de identificación personal griega
- identificador de policía griega
- tarjeta de identidad
- tautotita
- ταυτότητα
- ταυτότητας

## <a name="greece-passport-number"></a>Número de pasaporte de Grecia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Dos letras seguidas de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_greece_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_greece_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_greece_eu_passport_number**

- passport number
- número de pasaporte griego
- n.º de pasaporte
- διαβατηριο

## <a name="greece-tax-identification-number"></a>Número de identificación fiscal de Grecia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_greece_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de `Keywords_greece_eu_tax_file_number` . 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm #
- afm
- aφμ | aφμ αριθμός
- aφμ
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- n.º de registro de impuestos
- número de registro de impuestos
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- ID de estaño
- n.º de estaño
- / #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Número de tarjeta de identidad de Hong Kong (HKID)

### <a name="format"></a>Formato

Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final

### <a name="pattern"></a>Pattern

Combinación de 8 o 9 letras:
- 1 o 2 letras (no distingue entre mayúsculas y minúsculas)  
- Seis dígitos 
- El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_hong_kong_id_card.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- tarjeta de identidad de Hong Kong
- HKIDC
- id card
- documento de identidad
- tarjeta de identidad HK
- ID de Hong Kong
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証
   
## <a name="hungary-drivers-license-number"></a>Número de permiso de conducción de Hungría
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Pattern

Dos letras y seis dígitos:
  
- Dos letras (sin distinción entre mayúsculas y minúsculas) 
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_hungary_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_hungary_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_hungary_eu_driver ' s_license_number**
- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- vezetoi engedely

## <a name="hungary-national-identification-number"></a>Número de identificación nacional de Hungría
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

11 dígitos
  
### <a name="pattern"></a>Pattern

11 dígitos:
  
-  Un dígito que corresponde a sexo (1-macho, 2-hembra, otros números también son posibles para los ciudadanos nacidos antes del 1900 o los ciudadanos con doble nacionalidad) 
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
- Tres dígitos que corresponden a un número de serie
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_hungary_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- número de identificador
- identification number

- SZ IG
- SZ.IG.
- SZ. IG.
- személyazonosító igazolvány
- személyi igazolvány

## <a name="hungary-passport-number"></a>Número de pasaporte de Hungría
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Dos letras seguidas por seis o siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_hungary_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_hungary_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

**Keywords_hungary_eu_passport_number**

- passport number
- número de pasaporte Húngaro
- n.º de pasaporte
- útlevél száma

## <a name="hungary-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Hungría o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_hungary_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- número de la seguridad social húngara
- social security number
- NúmeroSeguridadSocial #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- SSN
- SSN #
- n.º de seguridad social
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Número de identificación fiscal de Hungría
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Diez dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Diez dígitos:
  
-  Un dígito que debe ser "8" 
- Cinco dígitos que corresponden al número de días entre la fecha 01/01/1867 y la fecha de nacimiento del individuo.
- Tres dígitos que corresponden al número generado por oportunidad para diferenciar a los individuos nacidos en el mismo día
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_hungary_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- NIF Húngaro
- hungatiantin #
- n.º de autoridad fiscal
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de IVA

## <a name="india-permanent-account-number-pan"></a>Número de cuenta permanente de India (PAN)

### <a name="format"></a>Formato

10 letras o dígitos

### <a name="pattern"></a>Pattern

10 letras o dígitos:
- Cinco letras (no distingue entre mayúsculas y minúsculas)  
- Cuatro dígitos 
- Una letra que es un dígito de control alfabético

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_india_permanent_account_number.
- Se supera la suma de comprobación.

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Número de cuenta permanente 
- MANO 
   
## <a name="india-unique-identification-aadhaar-number"></a>Número de identificación única (Aadhaar) de India

### <a name="format"></a>Formato

12 dígitos que contienen espacios o guiones opcionales

### <a name="pattern"></a>Pattern

12 dígitos:
- Cuatro dígitos  
- Un guión o un espacio opcional  
- Cuatro dígitos  
- Un guión o un espacio opcional  
- El dígito final que es el dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está 85% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.
Se encuentra una palabra clave de Keyword_india_aadhar.
Se supera la suma de comprobación.
Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_india_aadhaar encuentra contenido que coincide con el patrón.
Se supera la suma de comprobación.
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>Número de tarjeta de identidad (KTP) de Indonesia

### <a name="format"></a>Formato

16 dígitos que contienen puntos opcionales

### <a name="pattern"></a>Pattern

16 dígitos:
- Código de la provincia de dos dígitos  
- Un punto (opcional)  
- Código de ciudad o regencia de dos dígitos  
- Código de subdistrito de dos dígitos  
- Un punto (opcional)  
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un punto (opcional)  
- Cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_indonesia_id_card.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>Número de cuenta bancaria internacional (IBAN)

### <a name="format"></a>Formato

Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)


### <a name="pattern"></a>Pattern

El patrón debe incluir todo lo siguiente:

- Código de país de dos letras
- Dos dígitos de control (seguidos de un espacio opcional)  
- 1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)
- 1-3 letras o dígitos

The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_iban encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

Ninguno

   

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Clasificación Internacional de enfermedades (ICD-10-CM)

### <a name="format"></a>Formato

Dictionary

### <a name="pattern"></a>Pattern

Keyword

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave de Dictionary_icd_10_updated.
- Se encuentra una palabra clave de Dictionary_icd_10_codes.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave de Dictionary_icd_10_ Updated.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

Keywords

Cualquier término del Diccionario de palabras clave Dictionary_icd_10_updated, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo solo busca el término, no los códigos de seguro.

Cualquier término del Diccionario de palabras clave Dictionary_icd_10_codes, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo busca sólo los códigos de seguros, no la descripción.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Clasificación Internacional de enfermedades (ICD-9-CM)

### <a name="format"></a>Formato

Dictionary

### <a name="pattern"></a>Pattern

Keyword

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave de Dictionary_icd_9_updated.
- Se encuentra una palabra clave de Dictionary_icd_9_codes.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave de Dictionary_icd_9_updated.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

Cualquier término del Diccionario de palabras clave Dictionary_icd_9_updated, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo solo busca el término, no los códigos de seguro.

Cualquier término del Diccionario de palabras clave Dictionary_icd_9_codes, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo busca sólo los códigos de seguros, no la descripción.

## <a name="ip-address"></a>Dirección IP

### <a name="format"></a>Formato

#### <a name="ipv4"></a>IPv4
Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4

#### <a name="ipv6"></a>Protocolo
 Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)

### <a name="pattern"></a>Pattern

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_ipaddress.

Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ipaddress.

Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_ipaddress.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (esta palabra clave distingue entre mayúsculas y minúsculas)
- dirección IP 
- Direcciones IP
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Número de permiso de conducción de Irlanda
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Seis dígitos seguidos de cuatro letras
  
### <a name="pattern"></a>Pattern

Seis dígitos y cuatro letras:
  
- Seis dígitos
- Cuatro letras (sin distinción entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_ireland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_ireland_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_ireland_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- ceadúnas tiomána

## <a name="ireland-national-identification-number"></a>Número de identificación nacional de Irlanda
Esta entidad de tipo de información confidencial solo se incluye en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Una combinación de Letras de nueve caracteres, dígitos y un espacio en el patrón especificado
  
### <a name="pattern"></a>Pattern

Una combinación de Letras de nueve caracteres, dígitos y un espacio en el patrón especificado
  
De 01 de enero de 2013 a ahora:
  
-  Siete dígitos  
- Un dígito de control
- Un espacio o la letra mayúscula "W" (distingue entre mayúsculas y minúsculas)
    
Antes del 01 de enero de 2013:
  
- Siete dígitos  
- Un dígito de control
- Un espacio o una letra mayúscula (distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de.
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función busca contenido que coincide con el patrón.
    
```xml
 <!--Ireland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- servicio de identidad de cliente
- identification number

- número de identificación personal
- número de servicio público personal
- n.º de servicio personal
- phearsanta seirbhíse poiblí
- n.º de PPS
- número de PPS
- n.º de servicio de PPS
- PPS uimh
- ppsn
- ppsno #
- ppsno
- n.º de servicio público
- publicserviceno #
- publicserviceno
- número de la seguridad social y de ingresos
- RSI no
- número de RSI
- rsin
- cliente de seirbhís aitheantais
- uimh.PSP
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí

## <a name="ireland-passport-number"></a>Número de pasaporte de Irlanda
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
- Siete dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_ireland_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_ireland_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_ireland_eu_passport_number**

- passport number
- número de pasaporte irlandés
- n.º de pasaporte
- PAS
- usuarios
- passeport
- passeport numero

## <a name="ireland-personal-public-service-pps-number"></a>Número de servicio público personal (PPS) de Irlanda

### <a name="format"></a>Formato

Formato antiguo (hasta el 31 de diciembre de 2012):
- Siete dígitos seguidos por 1 o 2 letras  

Nuevo formato (1 de enero de 2013 y posterior):
- Siete dígitos seguidos por dos letras

### <a name="pattern"></a>Pattern

Formato antiguo (hasta el 31 de diciembre de 2012):
- Siete dígitos  
- 1 o 2 letras (no distingue entre mayúsculas y minúsculas)  

Nuevo formato (1 de enero de 2013 y posterior):
- Siete dígitos  
- Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético  
- La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ireland_pps encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_ireland_pps.
    - La función Func_eu_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ireland_pps encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ireland_pps"></a>Keyword_ireland_pps

- Número de servicio público personal 
- Número de PPS 
- Núm. PPS
 
- N.º PPS 
- N.ro PPS 
- PPS # 
- PPSN 
- Tarjeta de servicios públicos 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Uimh. PSP 
- PSP 


## <a name="ireland-tax-identification-number"></a>Número de identificación fiscal de Irlanda
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Siete dígitos seguidos de una letra sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Siete dígitos seguidos de una letra:
  
- Siete dígitos  
- Una letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_ireland_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_ireland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

- servicio de identidad de cliente
- identification number

- número de identificación personal
- número de servicio público personal
- n.º de servicio personal
- phearsanta seirbhíse poiblí
- n.º de PPS
- número de PPS
- n.º de servicio de PPS
- PPS uimh
- ppsn
- ppsno #
- ppsno
- n.º de servicio público
- publicserviceno #
- publicserviceno
- número de la seguridad social y de ingresos
- RSI no
- número de RSI
- rsin
- cliente de seirbhís aitheantais
- uimh.PSP
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí


## <a name="israel-bank-account-number"></a>Número de cuenta bancaria de Israel

### <a name="format"></a>Formato

13 dígitos

### <a name="pattern"></a>Pattern

Con formato
- Dos dígitos 
- Guion 
- Tres dígitos 
- Guion 
- Ocho dígitos

Sin formato
- 	13 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_israel_bank_account_number.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Número de cuenta bancaria 
- Cuenta bancaria 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Número de identificación nacional de Israel

### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Pattern

Nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Israel_National_ID.
- Se supera la suma de comprobación.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>Número de permiso de conducción de Italia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial del número de licencia de conductor de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Una combinación de 10 letras y dígitos

### <a name="pattern"></a>Pattern

- Una combinación de 10 letras y dígitos:
- Una letra (no distingue entre mayúsculas y minúsculas) 
- La letra "A" o "V" (no distingue entre mayúsculas y minúsculas) 
- Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado 
- Una letra (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_italy_drivers_license_number.

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 

## <a name="italy-national-identification-number"></a>Número de identificación nacional de Italia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Una combinación de letras y dígitos de 16 caracteres en el patrón especificado
  
### <a name="pattern"></a>Pattern

Una combinación de letras y dígitos de 16 caracteres:
  
- Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia
- Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre
- Dos dígitos que corresponden a los últimos dígitos del año de nacimiento
- Una letra que corresponde a la carta del mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)
- Dos dígitos que corresponden al día del mes de nacimiento: para diferenciar entre los sexos, 40 se agrega al día de nacimiento para las mujeres
- Cuatro dígitos que corresponden al código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros)
- Un dígito de paridad
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_italy_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
<!-- Italy national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- fiscal Codice
- Codice fiscal
- personal del identificador Codice
- personal Codice
- Código fiscal
- numero certificato personal
- Numero di identificazione fiscale
- personal del identificador numero
- personal numero
- número de certificado personal
- código personal
- código de identificación personal
- número de identificación personal
- personalcodeno #
- código de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- número de identidad fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="italy-passport-number"></a>Número de pasaporte de Italia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_italy_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_italy_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_italy_eu_passport_number**

- número de pasaporte Italiano
- repubblica italiana passaporto
- passaporto
- passaporto italiana
- passport number
- italiana passaporto numero
- passaporto numero
- numéro passeport italien
- numéro passeport

## <a name="italy-tax-identification-number"></a>Número de identificación fiscal de Italia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

16 letras y dígitos en el patrón especificado
  
### <a name="pattern"></a>Pattern

16 letras y dígitos:
  
-  Tres letras que corresponden a las tres primeras consonantes en el nombre de la familia 
- Tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre
- Dos dígitos que corresponden a los últimos dígitos del año de nacimiento
- Un dígito que corresponde al mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)
- Dos dígitos que corresponden al día del mes de nacimiento donde se agrega 40 al día de nacimiento para hembras para diferenciar de machos
- Cuatro dígitos que corresponden a un código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros).
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_italy_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_italy_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

- fiscal Codice
- Codice fiscal
- personal del identificador Codice
- personal Codice
- Código fiscal
- numero certificato personal
- Numero di identificazione fiscale
- personal del identificador numero
- personal numero
- número de certificado personal
- código personal
- código de identificación personal
- número de identificación personal
- personalcodeno #
- código de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- número de identidad fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #


## <a name="japan-bank-account-number"></a>Número de cuenta bancaria de Japón

### <a name="format"></a>Formato

Siete u ocho dígitos

### <a name="pattern"></a>Pattern

Número de cuenta bancaria:
- Siete u ocho dígitos
- Código de sucursal del banco:
- Cuatro dígitos 
- Un espacio o un guion (opcional) 
- Tres dígitos

Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_bank_account encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_account.
- Una de las siguientes opciones es verdadera:
- La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_branch_code.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_bank_account encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_account.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 
- 口座番号を当座預金口座の確認 
- #アカウントの確認 、 勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番号 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座＃ 
- 貯蓄勘定の数 
- 貯蓄勘定＃ 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号＃ 
- デビットのacct番号 
- デビット勘定＃ 
- デビットACCTの番号 
- デビット口座番号 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>Número de permiso de conducción de Japón

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Pattern

12 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_drivers_license_number.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- listas # 
- LISTAS 
- distribución # 
- DISTRIBUCIÓN 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- Lic # 
- Lic 
- conducción # 
- state id 
- state identification 
- state identification number 
- 低所得国＃ 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>Número de pasaporte de Japón

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos

### <a name="pattern"></a>Pattern

Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_passport.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 

## <a name="japan-residence-card-number"></a>Número de tarjeta de residencia de Japón

### <a name="format"></a>Formato

12 letras y dígitos

### <a name="pattern"></a>Pattern

12 letras y dígitos:
- Dos letras (no distingue entre mayúsculas y minúsculas) 
- Ocho dígitos 
- Dos letras (no distingue entre mayúsculas y minúsculas) 

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_jp_residence_card_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_residence_card_number.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Número de tarjeta de residencia
- Nº de tarjeta de residencia
- Tarjeta de residencia #
- 在留カード番号

## <a name="japan-resident-registration-number"></a>Número de registro de residente de Japón

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Pattern

11 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_resident_registration_number.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number 
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 住民登録番号、登録番号をレジデント 
- 住民基本登録番号、登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>Número del seguro social de Japón (SIN)

### <a name="format"></a>Formato

De 7 a 12 dígitos

### <a name="pattern"></a>Pattern

7-12 dígitos:
- Cuatro dígitos 
- Un guion (opcional) 
- Seis dígitos o
- De 7 a 12 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_sin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_sin.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_sin.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="latvia-drivers-license-number"></a>Número de permiso de conducción de Letonia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Tres letras seguidas de seis dígitos
  
### <a name="pattern"></a>Pattern

Tres letras y seis dígitos:
  
-  Tres letras (sin distinción entre mayúsculas y minúsculas) 
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_latvia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_latvia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_latvia_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- autovadītāja apliecība

## <a name="latvia-national-identification-number"></a>Número de identificación nacional de Letonia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

11 dígitos y un guión en el formato especificado
  
### <a name="pattern"></a>Pattern

11 dígitos y un guión:
  
-  Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
- Un guión 
- Un dígito que corresponde al siglo de nacimiento ("0" para el siglo XIX, "1" para el siglo XX y "2" para el siglo XXI)
- Cuatro dígitos, generados aleatoriamente
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_latvia_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
<!-- Latvia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- número administrativo
- alvas nē
- número de nacimiento
- número de ciudadano
- número civil
- número de censo electrónico
- número electrónico
- Código fiscal
- número de usuario de asistencia sanitaria
- identificador #
- identificador-código
- identification number

- identifikācijas numurs
- identificador-número
- número individual
- latvija alva
- identificador nacionālais
- 
national id
- número de identificación nacional
- número de identidad nacional
- national insurance number

- número de registro nacional
- nodokļa numurs
- identificador nodokļu
- nodokļu identifikācija numurs
- número de certificado personal
- código personal
- código de identificación personal
- número de identificación personal
- código de identificación personal
- identificador personal
- número de identidad personal
- número personal
- código numérico personal
- personalcodeno #
- roles kods
- código de identificación de población
- número de servicio público
- 
registration number
- número de ingresos
- número del seguro social
- social security number

- código de impuestos estatales
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de votantes

## <a name="latvia-passport-number"></a>Número de pasaporte de Letonia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_latvia_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_latvia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_latvia_eu_passport_number**

- passport number
- número de pasaporte de letón
- n.º de pasaporte
- pase numurs    

## <a name="latvia-tax-identification-number"></a>Número de identificación fiscal de Letonia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos en el patrón especificado
  
- Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
- Un dígito que corresponde al siglo de nacimiento en el que "0" corresponde al siglo XIX, "1" corresponde al siglo XX y "2" corresponde al siglo XXI.
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_latvia_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_latvia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

- número administrativo
- alvas nē
- número de nacimiento
- número de ciudadano
- número civil
- número de censo electrónico
- número electrónico
- Código fiscal
- número de usuario de asistencia sanitaria
- identificador #
- identificador-código
- identification number

- identifikācijas numurs
- identificador-número
- número individual
- latvija alva
- identificador nacionālais
- 
national id
- número de identificación nacional
- número de identidad nacional
- national insurance number

- número de registro nacional
- nodokļa numurs
- identificador nodokļu
- nodokļu identifikācija numurs
- número de certificado personal
- código personal
- código de identificación personal
- número de identificación personal
- código de identificación personal
- identificador personal
- número de identidad personal
- número personal
- código numérico personal
- personalcodeno #
- roles kods
- código de identificación de población
- número de servicio público
- 
registration number
- número de ingresos
- número del seguro social
- social security number

- código de impuestos estatales
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de votantes

## <a name="lithuania-drivers-license-number"></a>Número de permiso de conducción de Lituania
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 Ocho dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_lithuania_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_lithuania_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_lithuania_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- vairuotojo pažymėjimas

## <a name="lithuania-national-identification-number"></a>Número de identificación nacional de Lituania
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos sin espacios y delimitadores:
  
- Un dígito que corresponde al sexo de la persona y al siglo de nacimiento
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- Tres dígitos que corresponden al número de serie de la fecha de nacimiento
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_lithuania_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
<!-- Lithuania national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- número de servicio de ciudadanos
- identificador mokesčių
- mokesčių identifikavimas número
- mokesčių identifikavimo número
- numeración mokesčių
- número de identificación nacional
- código personal
- código numérico personal
- piliečio paslaugos número
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- unikalus identifikavimo kodas
- unikalus identifikavimo número
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Número de pasaporte de Lituania
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Ocho dígitos o letras sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_lithuania_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_lithuania_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_lithuania_eu_passport_number**

número de pasaporte lithunian número de pasaporte Passport no paso numeral

## <a name="lithuania-tax-identification-number"></a>Número de identificación del impuesto de Lituania
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_lithuania_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

- asmeninis skaitmeninis kodas
- asmens kodas
- número de servicio de ciudadanos
- identificador mokesčių
- mokesčių identifikavimas número
- mokesčių identifikavimo número
- numeración mokesčių
- número de identificación nacional
- código personal
- piliečio paslaugos número
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- unikalus identifikavimo kodas
- unikalus identifikavimo número
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="luxemburg-drivers-license-number"></a>Número de permiso de conducción de Luxemburgo
la entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial del número de licencia de la UE driver.

### <a name="format"></a>Formato

Seis dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

 Seis dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_luxemburg_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_luxemburg_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_luxemburg_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- fahrerlaubnis

## <a name="luxemburg-national-identification-number"></a>Número de identificación nacional de Luxemburgo
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

11 dígitos
  
- Un dígito que corresponde al sexo de la persona y al siglo de nacimiento
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- Tres dígitos que corresponden al número de serie de la fecha de nacimiento
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_luxemburg_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_luxemburg_eu_national_id_card` . 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- identificador eindeutige
- eindeutige ID-Nummer
- eindeutigeid #
- identificador personnelle
- idpersonnelle #
- idpersonnelle
- Código individual
- identificador individual
- identificación individual
- identidad individual
- personal de numéro d'identification
- identificador personal
- identificación personal
- identidad personal
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- identificador único
- identidad única
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Número de pasaporte de Luxemburgo
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Ocho dígitos o letras sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_nation_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_nation_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_nation_eu_passport_number**

número de pasaporte en letón número de pasaporte Passport no passnummer

## <a name="luxemburg-tax-identification-number"></a>Número de identificación de impuestos de Luxemburgo
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

13 dígitos:
  
- 11 dígitos 
- Dos dígitos de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_luxemburg_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- Carta de Sécurité Sociale
- étain no
- étain #
- identificador d'impôt
- identifikatiounsnummer de impuestos de Luxemburgo
- numéro d'étain
- numéro d'identification fiscales de Luxembourgeois
- numéro d'identification fiscal
- seguridad social
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- identificador Steier
- steier identifikatiounsnummer
- steier nummer
- identificador Steuer
- steueridentifikationsnummer
- steuernummer
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Número de tarjeta de identificación de Malasia

### <a name="format"></a>Formato

12 dígitos que contienen guiones opcionales

### <a name="pattern"></a>Pattern

12 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un guión (opcional)  
- Código de dos letras del lugar de nacimiento  
- Un guión (opcional)  
- Tres dígitos aleatorios  
- Código de género de un dígito

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_malaysia_id_card_number.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- tarjeta de aplicación digital
- i/c
- i/c no
- i
- no IC
- id card
- Tarjeta de identificación
- documento de identidad
- k/p
- k/p no
- kad akuan diri
- Kad aplikasi digital
- Kad pengenalan Malasia
- PK
- KP no
- mykad
- mykas
- mykid
- mypr
- mytentera
- tarjeta de identidad de Malasia
- tarjeta de identidad malasio
- nric
- tarjeta de identificación personal

## <a name="malta-drivers-license-number"></a>Número de permiso de conducción de Malta
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Combinación de dos caracteres y seis dígitos en el patrón especificado
  
### <a name="pattern"></a>Pattern

Combinación de dos caracteres y seis dígitos:
  
- Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)
- Un espacio (opcional) 
- Tres dígitos
- Un espacio (opcional) 
- Tres dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_malta_eu_driver's_license_number` . 
    
```xml
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_malta_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- liċenzja sewqan

## <a name="malta-national-identification-number"></a>Número de identificación nacional de Malta
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Siete dígitos seguidos de una letra
  
### <a name="pattern"></a>Pattern

Siete dígitos seguidos de una letra:
  
-  Siete dígitos  
- Una letra mayúscula (distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_malta_eu_national_id_card` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
 <!--Malta national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- número de servicio de ciudadanos
- identificador TAT-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni TAT-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' Identità uniku
- numru Servizz taċ-ċittadin
- numru tat-taxxa
- código numérico personal
- número de identificación único
- número de identidad único
- uniqueidentityno #


## <a name="malta-passport-number"></a>Número de pasaporte de Malta
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

 Siete dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_malta_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_malta_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_malta_eu_passport_number**

- passport number
- número de pasaporte de Maltés
- n.º de pasaporte
- numru tal-passaport

## <a name="malta-tax-identification-number"></a>Número de identificación fiscal de Malta
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Para los nacionales de Maltés: 7 dígitos y una letra en el patrón especificado
  
Nacionales no Maltés y entidades de Maltés: 9 dígitos
  
### <a name="pattern"></a>Pattern

Nacionales de Malta: 7 dígitos y una letra
  
-  Siete dígitos  
- Una letra (no distingue entre mayúsculas y minúsculas)
    
Nacionales no Maltés y entidades de Maltés: 9 dígitos
  
-  Nueve dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_malta_eu_tax_file_number` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_malta_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- número de servicio de ciudadanos
- identificador TAT-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni TAT-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' Identità uniku
- numru Servizz taċ-ċittadin
- numru tat-taxxa
- código numérico personal
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>Número de servicio del ciudadano (BSN) de Holanda

### <a name="format"></a>Formato

8 o 9 dígitos que contienen espacios opcionales

### <a name="pattern"></a>Pattern

8 o 9 dígitos:
- Tres dígitos 
- Un espacio (opcional)  
- Tres dígitos 
- Un espacio (opcional)  
- 2 o 3 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_netherlands_bsn.
- La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_netherlands_bsn"></a>Keyword_netherlands_bsn
  
- BSN #
- BSN
- burgerservicenummer
- número de servicio de ciudadanos
- número de persona
- número personal
- código numérico personal
- número relacionado con la persona
- persoonlijk nummer
- persoonlijke numerieke código
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- número social-fiscal
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Número de permiso de conducción de los países bajos
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_netherlands_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_netherlands_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_netherlands_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- permis de conduire
- rijbewijs
- rijbewijsnummer

## <a name="netherlands-national-identification-number"></a>Número de identificación nacional de países bajos
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de.
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
 <!--Netherland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- BSN #
- BSN
- burgerservicenummer
- número de servicio de ciudadanos
- número de persona
- número personal
- código numérico personal
- número relacionado con la persona
- persoonlijk nummer
- persoonlijke numerieke código
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- número social-fiscal
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="netherlands-passport-number"></a>Número de pasaporte de Holanda
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Nueve letras o dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Nueve letras o dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_netherlands_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_netherlands_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_netherlands_eu_passport_number**

- número de pasaporte holandés
- passport number
- número de pasaporte de Holanda
- nederlanden paspoort nummer
- paspoort
- nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>Número de identificación fiscal de países bajos
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_netherlands_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- identificación de impuestos de hollânske
- número de identificador de hulandes impuesto
- identificación de hulandes impuesto
- identificatienummer en último lugar
- identificatienummerto de furgoneta
- número de identificación de impuesto
- número del impuesto
- último identificador de Nummer de países bajos
- último países de la identificatie
- último países de la identificatienummer
- Países Bajos belastingnummer
- Nederlandse de la última identificatie
- identificación de impuestos de países bajos
- identificación de impuestos de Netherland
- NIF-Países Bajos
- estaño de Netherland
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- identificación de impuestos tal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- tal de impuestos
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="new-zealand-ministry-of-health-number"></a>Número de Ministerio de salud de Nueva Zelanda

### <a name="format"></a>Formato

Tres letras, un espacio (opcional) y cuatro dígitos

### <a name="pattern"></a>Pattern

Tres letras (no distingue entre mayúsculas y minúsculas), un espacio (opcional) y cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_nz_terms.
- Se supera la suma de comprobación.

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

Keywords

Keyword_nz_terms

- NHI 
- New Zealand 
- Salud 
- régimen 
   
## <a name="norway-identification-number"></a>Número de identificación de Noruega

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Pattern

11 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Número individual de tres dígitos  
- Dos dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_norway_id_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_norway_id_number.
- Se supera la suma de comprobación.
- Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Número de identificación personal
- Número de id. noruego
- Número de id.
- Determinación
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Número de identificación multiuso Unificado de Filipinas

### <a name="format"></a>Formato

12 dígitos separados por guiones

### <a name="pattern"></a>Pattern

12 dígitos:
- Cuatro dígitos 
- Un guión  
- Siete dígitos  
- Un guión  
- Un dígito

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_philippines_id.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Id. universal unificado
 
- UMID 
- Tarjeta de identidad 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Número de permiso de conducción de Polonia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

14 dígitos que contienen 2 barras diagonales
  
### <a name="pattern"></a>Pattern

14 dígitos y 2 barras diagonales:
  
-  Cinco dígitos 
- Una barra diagonal 
- Dos dígitos
- Una barra diagonal 
- Siete dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_poland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_poland_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_poland_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- prawo jazdy

## <a name="poland-identity-card"></a>Tarjeta de identidad de Polonia

### <a name="format"></a>Formato

Tres letras y seis dígitos

### <a name="pattern"></a>Pattern

Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está 75% segura de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres: la función Func_polish_national_id encuentra contenido que coincide con el patrón.
Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.
Se supera la suma de comprobación.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- Numerar dowodu osobistego
- Nazwa i número dowodu osobistego
- Nazwa i NR dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. MacOS.

   
## <a name="poland-national-id-pesel"></a>Identificación nacional de Polonia (PESEL)
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Pattern

11 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_pesel_identification_number.
- Se supera la suma de comprobación.

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- número de niepowtarzalny
- niepowtarzalnynumer
- Nr.-Pesel
- Nr-Pesel
- números identyfikacyjny
- pesel
- tożsamości narodowej

   
## <a name="poland-passport-number"></a>Número de pasaporte de Polonia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de la UE número de pasaporte y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Dos letras y siete dígitos

### <a name="pattern"></a>Pattern

Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_polish_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.
- Se supera la suma de comprobación.

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Números paszportu
- Nº. Paszportu
- Paszport

## <a name="poland-tax-identification-number"></a>Número de identificación fiscal de Polonia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Once dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Once dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_poland_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

nip #
- nip
- numerar identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- NIF #
- NIF
- número de IVA
- número de IVA
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>Número de tarjeta de ciudadano de Portugal
- Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.
- Esta entidad de tipo de información confidencial se incluye en el número de la seguridad social de la UE o en el tipo de información confidencial del identificador equivalente.


### <a name="format"></a>Formato

Ocho dígitos

### <a name="pattern"></a>Pattern

Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_portugal_citizen_card.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de Identidade
- Cartão de Cidadão
- tarjeta de ciudadanos
- número de documento
- documento de identificação
- número de identificador
- n.º de identificación
- identification number

- Nº de tarjeta de identidad
- número de tarjeta de identidad
- tarjeta de identificación nacional
- tarjetas
- número de BI de Portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- número de BI de Portugal


## <a name="portugal-drivers-license-number"></a>Número de permiso de conducción de Portugal
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Dos letras seguidas de siete números en el patrón especificado
  
### <a name="pattern"></a>Pattern

Dos letras seguidas de siete números con caracteres especiales:
  
- Dos letras (sin distinción entre mayúsculas y minúsculas) 
- Un guión 
- Seis dígitos
- Un espacio
- Un dígito
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_portugal_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_portugal_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_portugal_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- Carteira de motorista

## <a name="portugal-passport-number"></a>Número de pasaporte de Portugal
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Una letra seguida de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Una letra seguida de seis dígitos:
  
- Una letra (no distingue entre mayúsculas y minúsculas)
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_portugal_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_portugal_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_portugal_eu_passport_number**

número de pasaporte pasaporte número de pasaporte Passport no hay número de Passaporte

## <a name="portugal-tax-identification-number"></a>Número de identificación fiscal de Portugal
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_portugal_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf #
- cpf
- NIF #
- NIF
- número de identificação Fisca
- fiscal numero
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #


## <a name="romania-drivers-license-number"></a>Número de permiso de conducción de Rumanía
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Un carácter seguido de ocho dígitos
  
### <a name="pattern"></a>Pattern

Un carácter seguido de ocho dígitos:
  
- Una letra (no distingue entre mayúsculas y minúsculas) o un dígito 
- Ocho dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_romania_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_romania_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_romania_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- Perm de conducere

## <a name="romania-national-identification-number"></a>Número de identificación nacional de Rumania
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

13 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

13 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_romania_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
 <!--Romania national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp #
- cnp
- c.o.d. identificare personal
- personal numérico de pago
- Bacalao UNIC identificare
- codnumericpersonal #
- codul fiscal Nr.
- identificarea fiscală NR #
- ID-ul taxei
- número de seguro
- insurancenumber #
- identificación nacional #
- 
national id
- número de identificación nacional
- număr identificare personal
- număr identitate
- număr personal UNIC
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- código numérico personal
- patilla #
- patilla
- n.º de archivo de impuestos
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de identificación único
- número de identidad único
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Número de pasaporte de Rumanía
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Ocho o nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Ocho o nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_romania_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_romania_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_romania_eu_passport_number**

- passport number
- número de pasaporte de rumano
- n.º de pasaporte
- numărul pașaportului

## <a name="romania-tax-identification-number"></a>Número de identificación fiscal de Rumanía
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

13 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_romania_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_romania_eu_tax_file_number` . 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

- cnp #
- cnp
- c.o.d. identificare personal
- personal numérico de pago
- Bacalao UNIC identificare
- codnumericpersonal #
- codul fiscal Nr.
- identificarea fiscală NR #
- ID-ul taxei
- número de seguro
- insurancenumber #
- identificación nacional #
- 
national id
- número de identificación nacional
- număr identificare personal
- număr identitate
- număr personal UNIC
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- código numérico personal
- patilla #
- patilla
- n.º de archivo de impuestos
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #
- número de identificación único
- número de identidad único
- uniqueidentityno #
- uniqueidentityno



## <a name="saudi-arabia-national-id"></a>Identificación nacional de Arabia Saudí

### <a name="format"></a>Formato

10 dígitos

### <a name="pattern"></a>Pattern

10 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Número de tarjeta de identidad de registro nacional (NRIC) de Singapur

### <a name="format"></a>Formato

Nueve letras y dígitos

### <a name="pattern"></a>Pattern

- Nueve letras y dígitos:
- La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas)  
- Siete dígitos  
- Un dígito de control alfabético

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_singapore_nric.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- Tarjeta de identidad de registro nacional 
- Número de tarjeta de identidad 
- NRIC 
- I 
- Número de identificación de extranjeros 
- AC 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Número de permiso de conducción de Eslovaquia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Un carácter seguido de siete dígitos
  
### <a name="pattern"></a>Pattern

Un carácter seguido de siete dígitos
  
- Una letra (no distingue entre mayúsculas y minúsculas) o un dígito
-  Siete dígitos  
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovakia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovakia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_slovakia_eu_driver ' s_license_number**

número de licencia del controlador de licencia DL
Controladores licencia controladores de licencia del controlador de licencia de conducir el número de licencia de conducir el número de licencia dlno # vodičský preukaz

## <a name="slovakia-national-identification-number"></a>Número de identificación nacional de Eslovaquia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Diez dígitos que contienen una barra diagonal inversa
  
### <a name="pattern"></a>Pattern

Diez dígitos que contienen una barra diagonal inversa:
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovakia_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
 <!-- Slovakia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- número de nacimiento
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- número de identificador
- n.º de identificación
- identification number

- identifikačná karta č
- identifikačné číslo
- Nº de tarjeta de identidad
- número de tarjeta de identidad
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number

- SSN #
- SSN
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- n.º de archivo de impuestos
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="slovakia-passport-number"></a>Número de pasaporte Eslovaquia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovakia_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovakia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_slovakia_eu_passport_number**

- passport number
- número de pasaporte de eslovaco
- n.º de pasaporte
- číslo pasu

## <a name="slovakia-tax-identification-number"></a>Número de identificación fiscal de Eslovaquia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

10 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovakia_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovakia_eu_tax_file_number` . 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

- azonosító szám
- número de nacimiento
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- número de identificador
- n.º de identificación
- identification number

- identifikačná karta č
- identifikačné číslo
- Nº de tarjeta de identidad
- número de tarjeta de identidad
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number

- SSN #
- SSN
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- n.º de archivo de impuestos
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #


## <a name="slovenia-drivers-license-number"></a>Número de permiso de conducción de Eslovenia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovenia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovenia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_slovenia_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license 
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- vozniško dovoljenje

## <a name="slovenia-national-identification-number"></a>Número de identificación nacional de Eslovenia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

13 dígitos en el patrón especificado:
  
-  Siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL) donde "LLL" corresponde a los tres últimos dígitos del año de nacimiento. 
- Dos dígitos que corresponden al área de nacimiento
- Tres dígitos que corresponden a una combinación de sexo y número de serie de las personas nacidos el mismo día (000-499 para macho y 500-999 para hembras)
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovenia_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
 <!-- Slovenia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- tarjeta de identificación
- identification number

- identifikacijska številka
- tarjeta de identidad
- identificador Nacionalna
- lista potni de Nacionalni
- 
national id
- osebna izkaznica
- osebni koda
- NE osebni
- osebni številka
- código personal
- número personal
- código numérico personal
- številka državljana
- número de ciudadano único
- número de identificador único
- número de identidad único
- número único de ciudadano principal
- número de registro único
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Número de pasaporte de Eslovenia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Dos letras seguidas de siete dígitos:
  
- La letra "P"
- Una letra mayúscula
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_slovenia_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovenia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_slovenia_eu_passport_number**

número de pasaporte número de pasaporte de Passport Passport no številka potnega lista

## <a name="slovenia-tax-identification-number"></a>Número de identificación fiscal de Eslovenia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_slovenia_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- n.º de archivo de impuestos
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #



## <a name="south-africa-identification-number"></a>Número de identificación de Sudáfrica

### <a name="format"></a>Formato

13 dígitos que pueden contener espacios

### <a name="pattern"></a>Pattern

13 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Cuatro dígitos 
- Un indicador de ciudadanía de un solo dígito  
- El dígito "8" o "9"  
- Un dígito que es un dígito de suma de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_south_africa_identification_number.
- Se supera la suma de comprobación.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- tarjeta de identidad
- ID
- Determinación 
   
## <a name="south-korea-resident-registration-number"></a>Número de registro de residente de Corea del sur

### <a name="format"></a>Formato

13 dígitos que contienen un guión

### <a name="pattern"></a>Pattern

13 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un guión  
- Un dígito determinado por el siglo y el sexo  
- Código de región de nacimiento de cuatro dígitos  
- Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos  
- Un dígito de control.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_south_korea_resident_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- Tarjeta de id. nacional 
- Número de registro de ciudadano 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Número de permiso de conducción de España
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Ocho dígitos seguidos de un carácter
  
### <a name="pattern"></a>Pattern

Ocho dígitos seguidos de un carácter:
  
- Ocho dígitos 
- Un dígito o letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_spain_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_spain_eu_driver ' s_license_number**

- dlno #
- listas #
- Lic de drivers.
- permiso de conducir
- driver license
- drivers licence
- drivers license
- driver's licence
- driver's license
- driving licence
- driving license
- número de licencia de conductor
- número de licencia de conductor
- número de licencia de drivers
- número de licencia de drivers
- número de permiso de conducción
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- permiso de conducción
- número de permiso de conducir
- permisos de conducción
- permisos conducción
- número de licencia conducir
- número de cuaderno de conducir
- número conducir de cuaderno
- licenciar conducir
- número de permisos de conducir
- número de permisos conducir
- número permisos conducir
- permisos conducir
- licencia de manejo
- el cuaderno de conducir
- conducir del cuaderno

## <a name="spain-national-identification-number"></a>Número de identificación nacional de España
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación nacional de la UE.

### <a name="format"></a>Formato

Siete dígitos seguidos de un carácter
  
### <a name="pattern"></a>Pattern

Siete dígitos seguidos de un carácter
  
- Siete dígitos 
- Un dígito o letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_spain_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_spain_eu_national_id_card"` . 
    
```xml
<!-- Spain national identification number -->
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- DNI #
- DNI
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- número de seguro
- número de identificación nacional
- identidad nacional
- nationalid #
- nationalidno #
- NIE #
- NIE
- nienúmero #
- número de identificación
- número nacional identidad
- número de identificación personal
- número de la identidad personal
- número de identidad único
- UniqueID #

## <a name="spain-passport-number"></a>Número de pasaporte de España
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de pasaporte de UE.

### <a name="format"></a>Formato

Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores
  
### <a name="pattern"></a>Pattern

Una combinación de letras y números de ocho o nueve caracteres:
  
-  Dos dígitos o letras 
- Un dígito o letra (opcional)
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_spain_eu_passport_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_spain_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords_spain_eu_passport_number**

- usuarios
- pasaporte de España
- libro de Passport
- passport number
- n.º de pasaporte
- libreta pasaporte
- número pasaporte
- españa pasaporte
- pasaporte


## <a name="spain-social-security-number-ssn"></a>Número de la seguridad social de España (NSS)
Esta entidad de tipo de información confidencial se incluye en el número de la seguridad social de la UE o en el tipo de información confidencial del identificador equivalente y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

11 o 12 dígitos

### <a name="pattern"></a>Pattern

11-12 dígitos:
- Dos dígitos 
- Una barra diagonal (opcional) 
- 7-8 dígitos 
- Una barra diagonal (opcional) 
- Dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

Ninguno

## <a name="spain-tax-identification-number"></a>Número de identificación fiscal de España
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Siete u ocho dígitos y una o dos letras en el patrón especificado
  
### <a name="pattern"></a>Pattern

Personas físicas españolas con una tarjeta de identidad nacional de España:
  
-  Ocho dígitos 
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Spaniards no residente sin una tarjeta de identidad nacional de España
  
- Una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)
- Siete dígitos 
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:
  
- Una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)
-  Siete dígitos  
- Una letra mayúscula (distingue entre mayúsculas y minúsculas)
    
Foreigners con un número de identificación de un extranjero
  
- Una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas) 
- Siete dígitos 
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Foreigners sin un número de identificación de un extranjero
  
- Una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas) 
- Siete dígitos 
- Una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_spain_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_spain_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- precio
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- n.º de archivo de impuestos
- número de archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #


## <a name="sql-server-connection-string"></a>Cadena de conexión de SQL Server

### <a name="format"></a>Formato

La cadena "User ID", "User ID", "UID" o "UserId" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.

### <a name="pattern"></a>Pattern

- La cadena "User ID", "User ID", "UID" o "UserId"
- Cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "Password" o "pwd" donde "pwd" no está precedida por una letra minúscula.
- Un signo igual (=)
- Cualquier carácter que no sea un signo de dólar ($), un símbolo de porcentaje (%), un símbolo mayor que (>), un símbolo de arroba (@), Comillas ("), punto y coma (;), llave izquierda ([) o corchete de apertura ({)
- Cualquier combinación de 7-128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")
- Un punto y coma (;) o comillas (")

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_SQLServerConnectionString encuentra contenido que coincide con el patrón.
- **No** se encuentra una palabra clave de CEP_GlobalFilter.
- La expresión regular CEP_PasswordPlaceHolder **no** encuentra contenido que coincida con el patrón.
- La expresión regular CEP_CommonExampleKeywords **no** encuentra contenido que coincida con el patrón.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- Some-Password
- somepassword
- secretPassword
- AdventureWorks

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- Password o pwd seguida de 0-2 espacios, un signo igual (=), 0-2 espacios y un asterisco (*)--o--
- Password o pwd seguida de:
    - Signo de igual (=)
    - Símbolo menor que (<)
    - Cualquier combinación de 1-200 caracteres que estén en mayúsculas o minúsculas, dígitos, un asterisco (*), un guión (-), un subrayado (_) o un carácter de espacio en blanco
    - Símbolo mayor que (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- Fabrikam
- Northwind
- entorno
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Puerto
- s-int.<!--no-hyperlink-->ADO.net

## <a name="sweden-drivers-license-number"></a>Número de permiso de conducción de Suecia
Esta entidad de tipo de información confidencial sólo está disponible en el tipo de información confidencial del número de permiso de la UE driver.

### <a name="format"></a>Formato

Diez dígitos que contienen un guión
  
### <a name="pattern"></a>Pattern

Diez dígitos que contienen un guión:
  
-  Seis dígitos 
- Un guión
- Cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular `Regex_sweden_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_sweden_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Keywords

**Keywords_sweden_eu_driver ' s_license_number**

- listas #
- driver license
- número de licencia de conductor
- permiso de conducir
- Lic de drivers.
- drivers license
- drivers licence
- driver's license
- número de permiso de conducción
- número de permiso de conducción
- número de licencia de conducir
- dlno #
- körkort

## <a name="sweden-national-id"></a>Identificación nacional de Suecia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

10 o 12 dígitos y un delimitador opcional

### <a name="pattern"></a>Pattern

10 o 12 dígitos y un delimitador opcional:
- 2-4 dígitos (opcionales) 
- Seis dígitos en fecha de formato AAMMDD 
- Delimitador de "-" o "+" (opcional), más
- Cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

No
   
## <a name="sweden-passport-number"></a>Número de pasaporte de Suecia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de la UE número de pasaporte y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Ocho dígitos

### <a name="pattern"></a>Pattern

Ocho dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_passport.
    - Se encuentra una palabra clave de Keyword_sweden_passport.

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- Usuarios # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Suecia o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente.

### <a name="format"></a>Formato

12 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Pattern

12 dígitos:
  
-  Ocho dígitos que corresponden a la fecha de nacimiento (AAAAMMDD) 
- Tres dígitos que corresponden a un número de serie en el que: 
  - El último dígito del número de serie indica el sexo por la asignación de un número impar para macho y un número par para hembras
  - Hasta 1990, la asignación de número de serie que se corresponde con el condado en el que nació el portador del número o (si nació antes de 1947) donde estuvo viviendo, de acuerdo con los registros fiscales, el 1 de enero de 1947, con un código especial (por lo general, 9 como el séptimo dígito) para Immigrants 
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_sweden_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- número de identificación personal
- identification number
- número de identificación personal
- n.º de identidad
- n.º de identificación
- n.º de identificación personal
- identificador personnummer
- personligt ID-Nummer
- unikt ID-Nummer
- personnummer
- identifikationsnumret
- personnummer #
- identifikationsnumret #

## <a name="sweden-tax-identification-number"></a>Número de identificación fiscal de Suecia
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.

### <a name="format"></a>Formato

Diez dígitos y un símbolo en el patrón especificado
  
### <a name="pattern"></a>Pattern

Diez dígitos y un símbolo:
  
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- Un signo más, un signo menos o una barra diagonal inversa
- Tres dígitos que hacen que el número de identificación sea único donde: 
  - Para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero
  - El dígito en la novena posición indica el género, ya sea impar o incluso para hembras
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de `Keywords_sweden_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- número de identificación personal
- personnummer
- Nummer de identificador de patinaje
- Identifikation de patinaje
- skattebetalarens identifikationsnummer
- Sverige estaño
- archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- número de impuesto
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #



## <a name="swift-code"></a>Código SWIFT

### <a name="format"></a>Formato

Cuatro letras seguidas de 5 a 31 letras o dígitos

### <a name="pattern"></a>Pattern

Cuatro letras seguidas de 5-31 letras o dígitos:
- Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas) 
- Un espacio opcional 
- 4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN)) 
- Un espacio opcional 
- 1-3 letras o dígitos (el resto del BBAN)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_swift encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_swift.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362 
- iso 9362 
- iso9362 
- rápido\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift code 
- swift number # 
- swift routing number 
- bic number 
- bic code 
- BIC\# 
- BIC\# 
- bank identifier code 
- 標準化 9362 
- 迅速＃ 
- SWIFTコード 
- SWIFT番号 
- 迅速なルーティング番号 
- BIC番号 
- BICコード 
- 銀行識別コードのための国際組織 
- Organisation internationale de normalisation 9362 
- rápido\# 
- code SWIFT 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \#BIC 
- code identificateur de banque 
   
## <a name="taiwan-national-identification-number"></a>Número de identificación nacional de Taiwán

### <a name="format"></a>Formato

Una letra  seguida de nueve dígitos

### <a name="pattern"></a>Pattern

Una letra seguida de nueve dígitos:
- Una letra (en inglés, no distingue mayúsculas de minúsculas) 
- El dígito "1" o "2" 
- Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwanese_national_id.
- Se supera la suma de comprobación.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwanese_national_id"></a>Keyword_taiwanese_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>Número de pasaporte de Taiwán

### <a name="format"></a>Formato

- Número de pasaporte biométrico: nueve dígitos
- Número de pasaporte no biométrico: nueve dígitos

### <a name="pattern"></a>Pattern
Número de pasaporte biométrico:
- El dígito "3"  
- Ocho dígitos

Número de pasaporte no biométrico:
- Nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwan_passport.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- Número de pasaporte ROC 
- Número de pasaporte 
- Núm. pasaporte
 
- N.ro pasaporte 
- N.º de pasaporte 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Número de certificado de residente (ARC/TARC) de Taiwán

### <a name="format"></a>Formato

10 letras y dígitos

### <a name="pattern"></a>Pattern

10 letras y dígitos:
- Dos letras (no distingue entre mayúsculas y minúsculas)  
- Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Certificado de residente 
- Cert. residente
 
- Cert. residente
 
- Tarjeta de identificación 
- Certificado de residente extranjero 
- ARC 
- Certificado de residente en el área de Taiwán 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>Código de identificación de población tailandesa

### <a name="format"></a>Formato

13 dígitos

### <a name="pattern"></a>Pattern

13 dígitos:
- El primer dígito no es 0 ni 9 
- 12 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Thai_Citizen_Id.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_thai_citizen_id"></a>Keyword_Thai_Citizen_Id

- Número de id.
- Número de identificación
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Número de identificación nacional de Turco

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Pattern

11 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Turkish_National_Id.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_turkish_national_id"></a>Keyword_Turkish_National_Id

- TC Kimlik no
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>RU número de permiso de conducción
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial del número de licencia de conductor de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Combinación de 18 letras y dígitos en el formato especificado

### <a name="pattern"></a>Pattern

18 letras y dígitos:
- Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra 
- Un dígito 
- Cinco dígitos en el formato de fecha MMDDY para la fecha de nacimiento (el séptimo carácter aumenta en 50 si el impulsor es hembra, es decir, 51 a 62 en lugar de 01 a 12)
- Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra 
- Cinco dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_drivers_license.
- Se supera la suma de comprobación.

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quadbikes 
- motor cars 
- 125cc 
- sidecar 
- Tricycles 
- sidecar 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>RU número de álbum electoral

### <a name="format"></a>Formato

Dos letras seguidas por entre 1 y 4 dígitos

### <a name="pattern"></a>Pattern

Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_electoral.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>RU número de servicio nacional de salud

### <a name="format"></a>Formato

De 10 a 17 dígitos separados por espacios

### <a name="pattern"></a>Pattern

10-17 dígitos:
- 3 o 10 dígitos 
- Un espacio 
- Tres dígitos 
- Un espacio 
- Cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_uk_nhs_number.
    - Se encuentra una palabra clave de Keyword_uk_nhs_number1.
    - Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.
- Se supera la suma de comprobación.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service 
- del NHS del 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- EON 
- NACIMIENTO 
- D. O. B 
- Fecha de nacimiento 
- Fecha de nacimiento 
   
## <a name="uk-national-insurance-number-nino"></a>RU número de seguro nacional (NINO)
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de Identificaiton Nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

7 caracteres o 9 caracteres separados por espacios o guiones

### <a name="pattern"></a>Pattern

Dos patrones posibles:

- Dos letras (los NINO válidos usan solo caracteres determinados en este prefijo, que valida este patrón; no distingue entre mayúsculas y minúsculas)
- Seis dígitos
- ' A ', ' B ', ' C ' o ' t ' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distingue entre mayúsculas y minúsculas)

O

- Dos letras
- Un espacio o un guion
- Dos dígitos
- Un espacio o un guion
- Dos dígitos
- Un espacio o un guion
- Dos dígitos
- Un espacio o un guion
- ' A ', ' B ', ' C ' o ' t '

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nino encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_nino.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nino encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_uk_nino.

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number

- national insurance contributions

- protection act
- Pensión
- social security number

- insurance application

- medical application

- social insurance

- medical attention

- seguridad social
- great britain
- Pensión
    
## <a name="uk-tax-identification-number"></a>RU número de identificación fiscal
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial de número de identificación de impuestos de la UE.


### <a name="format"></a>Formato

Referencia fiscal única (UTR): 10 dígitos sin espacios y delimitadores
 
  
### <a name="pattern"></a>Pattern

Referencia de contribuyente única (UTR): 10 dígitos

  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
- Se encuentra una palabra clave de `Keywords_uk_eu_tax_file_number` . 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- número de impuesto
- archivo de impuestos
- tax id

- n.º de identificación fiscal
- número de identificación fiscal
- Nº de impuestos #
- Nº de impuestos
- NIF-CIF
- taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID de estaño
- n.º de estaño
- / #

## <a name="us-bank-account-number"></a>Número de cuenta bancaria de Estados Unidos

### <a name="format"></a>Formato

Entre 8 y 17 dígitos

### <a name="pattern"></a>Pattern

Entre 8 y 17 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_usa_Bank_Account.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account. 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 

## <a name="us-drivers-license-number"></a>Número de permiso de conducción de Estados Unidos

### <a name="format"></a>Formato

Depende del estado

### <a name="pattern"></a>Pattern

Depende del estado, por ejemplo, Nueva York:
- Nueve dígitos con formato como DDD DDD DDD coincidirán.
- Nueve dígitos como ddddddddd no coinciden con el formato.

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.
- Se encuentra una palabra clave de Keyword_us_drivers_license.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.
- Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.
- No se encuentra ninguna palabra clave de Keyword_us_drivers_license.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- LISTAS 
- DISTRIBUCIÓN 
- CDL 
- CDLS 
- ID 
- Falta 
- LISTAS # 
- DISTRIBUCIÓN # 
- CDL # 
- CDLS # 
- IDENTIFICADOR #
- Falta # 
- ID number 
- ID numbers 
- LIC 
- LIC # 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- DriversLic 
- DriversLics 
- DriversLicense 
- DriversLicenses 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- N.º carné 
- N.º carnés 
- Conducción 
- Conducción 
- Driver' Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- Driver's Lic 
- Driver's Lics 
- Driver's License 
- Permisos de conducción 
- identification number 
- identification numbers 
- identification # 
- id card 
- id cards 
- identification card 
- identification cards 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- N.º carné # 
- N.º carnés # 
- Conducción # 
- Conducción # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- Abreviatura del estado (por ejemplo, "NY") 
- Nombre del estado (por ejemplo, "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Número de identificación fiscal individual de Estados Unidos (ÉLEN)

### <a name="format"></a>Formato

Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones

### <a name="pattern"></a>Pattern

Con formato
- El dígito "9" 
- Dos dígitos 
- Un espacio o un guion 
- Un "7" o "8" 
- Un dígito 
- Un espacio o un guion 
- Cuatro dígitos

Sin formato
- El dígito "9" 
- Dos dígitos 
- Un "7" o "8" 
- Cinco dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_formatted_itin encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_itin.
    - La función Func_us_address encuentra una dirección en el formato de fecha correcto.
    - La función Func_us_date encuentra una fecha en el formato de fecha correcto.
    - Se encuentra una palabra clave de Keyword_itin_collaborative.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_unformatted_itin encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_itin_collaborative.
    - La función Func_us_address encuentra una dirección en el formato de fecha correcto.
    - La función Func_us_date encuentra una fecha en el formato de fecha correcto.

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_itin"></a>Keyword_itin

- contribuyente 
- tax id 
- tax identification 
- élen 
- SSN 
- / 
- social security 
- tax payer 
- itins 
- taxi 
- individual taxpayer 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- Licencia 
- LISTAS 
- NACIMIENTO 
- Fecha de nacimiento 
- Birthday 
- Fecha de nacimiento 

## <a name="us-social-security-number-ssn"></a>Número de la seguridad social de Estados Unidos (SSN)

### <a name="format"></a>Formato

9 dígitos, que pueden ser un patrón con o sin formato

> [!NOTE]
> Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).

### <a name="pattern"></a>Pattern

Cuatro funciones buscan SSN en cuatro patrones diferentes:
- Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)
- Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)
- Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)
- Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)

### <a name="checksum"></a>Suma de comprobación

No


### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ssn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_unformatted_ssn busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.

Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ssn"></a>Keyword_ssn

- Social Security 
- Social Security# 
- Soc Sec 
- SSN 
- SSN 
- SSN # 
- SS # 
- SSID 
   
## <a name="us--uk-passport-number"></a>ESTADOS UNIDOS/REINO UNIDO passport number
El Reino Unido número de pasaporte la entidad tipo de información confidencial está disponible en el tipo de información confidencial de número de pasaporte de UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Pattern

Nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_passport.

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- Usuarios # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 
