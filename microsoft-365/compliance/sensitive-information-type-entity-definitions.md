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
hideEdit: true
feedback_system: None
description: La prevención de pérdida de datos (DLP) del centro de seguridad &amp; y cumplimiento incluye los tipos de información confidencial de 80 que están listos para que pueda usarlos en las directivas de DLP. Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos.
ms.openlocfilehash: 10f45403703130c191f4cbb26d1c0cba168b05ae
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751287"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definiciones de entidad de tipos de información confidencial

La prevención de pérdida de datos (DLP) en el centro de cumplimiento incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP. Este tema enumera todos estos tipos de información confidencial y muestra lo que una directiva DLP busca al detectar cada uno de los tipos. Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función. Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial. El nivel de confianza y la proximidad también se usan en el proceso de evaluación.

Los tipos de información confidencial requieren una de estas suscripciones:
- Microsoft 365 E3
- Microsoft 365 E5

## <a name="aba-routing-number"></a>Número de enrutamiento ABA

### <a name="format"></a>Formato

nueve dígitos que pueden estar en un patrón con o sin formato

### <a name="pattern"></a>Patrón

Con formato
- cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8
- un guión
- cuatro dígitos
- un guión
- un dígito

Sin formato: nueve dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8 

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_aba_routing encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ABA_Routing.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_aba_routing encuentra contenido que coincide con el patrón.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>Palabras clave

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- ABA #
- ABA
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- distribuir #
- Nº de enrutamiento
- número de enrutamiento
- routing transit number
- distribuir #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Número de identidad nacional (DNI) de Argentina

### <a name="format"></a>Formato

Ocho dígitos con o sin puntos

### <a name="pattern"></a>Patrón

Ocho dígitos:
- dos dígitos
- un período opcional
- tres dígitos
- un período opcional
- tres dígitos

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Número de identidad nacional de Argentina 
- cedula 
- cédula 
- DNI 
- documento nacional de identidad 
- número de documento 
- documento numero 
- Registro Nacional de las personas 
- rnp 
   
## <a name="australia-bank-account-number"></a>Número de cuenta bancaria de Australia

### <a name="format"></a>Formato

de seis a diez dígitos con o sin el número de sucursal estatal del Banco

### <a name="pattern"></a>Patrón

El número de cuenta tiene entre seis y diez dígitos.

Número de sucursal bancaria de Australia:
- tres dígitos 
- un guión 
- tres dígitos

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

### <a name="keywords"></a>Palabras clave

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

## <a name="australia-business-number"></a>Número de empresa de Australia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security


### <a name="format"></a>Formato

11 dígitos con delimitadores opcionales

### <a name="pattern"></a>Patrón

11 dígitos con delimitadores opcionales:

- dos dígitos
- un guión o un espacio opcional
- tres dígitos
- un guión o un espacio opcional
- tres dígitos
- un guión o un espacio opcional
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_business_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_australian_business_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_business_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- número de empresa de Australia
- número de empresa
- ABN #
- businessid #
- identificador de empresa
- ABN
- businessno #

## <a name="australia-company-number"></a>Número de compañía de Australia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

nueve dígitos con delimitadores

### <a name="pattern"></a>Patrón

nueve dígitos con delimitadores:

- tres dígitos
- un espacio
- tres dígitos
- un espacio
- tres dígitos


### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Australian_Company_Number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Australian_Company_Number.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Australian_Company_Number encuentra contenido que coincide con el patrón.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- se
- número de empresa de Australia
- número de empresa de Australia #
- número de compañía de Australia
- número de empresa australiano
- número de empresa australiano #
- número de empresa australiano

## <a name="australia-drivers-license-number"></a>Número de permiso de conducción de Australia

### <a name="format"></a>Formato

nueve letras y dígitos

### <a name="pattern"></a>Patrón

nueve letras y dígitos: 

- dos dígitos o letras (no distingue entre mayúsculas y minúsculas) 
- dos dígitos 
- cinco dígitos o letras (no distingue entre mayúsculas y minúsculas)

O

- de una a dos letras opcionales (no distingue entre mayúsculas y minúsculas) 
- de cuatro a nueve dígitos

O

- nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

Entre 10 y 11 dígitos:
- el primer dígito está en el rango 2-6
- noveno dígito es un dígito de control
- el décimo dígito es el dígito de emisión
- el undécimo dígito (opcional) es el número individual

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.
- Se supera la suma de comprobación.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

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

de ocho a nueve dígitos

### <a name="pattern"></a>Patrón

ocho a nueve dígitos normalmente se presentan con espacios como sigue:
- tres dígitos 
- un espacio opcional 
- tres dígitos 
- un espacio opcional 
- dos o tres dígitos donde el último dígito es un dígito de control

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
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- TFN

## <a name="austria-drivers-license-number"></a>Número de permiso de conducción de Austria

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_austria_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_austria_eu_driver's_license_number` found. 
    
```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver ' s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Tarjeta de identidad de Austria
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

Una combinación de letras, dígitos y caracteres especiales de 24 caracteres
  
### <a name="pattern"></a>Patrón

24 caracteres:
  
-  22 letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más 
    
- dos letras (no distinguen entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales, signos más o signos igual
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_austria_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_austria_eu_national_id_card` . 
   
```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- número de identidad
- national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Número de pasaporte de Austria

### <a name="format"></a>Formato

Una letra seguida de un espacio opcional y siete dígitos
  
### <a name="pattern"></a>Patrón

Una combinación de una letra, siete dígitos y un espacio:
  
- una letra (no distingue entre mayúsculas y minúsculas)
- un espacio (opcional)
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_austria_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_austria_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_austria_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_austria_eu_passport_number` found. 
    
```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe


## <a name="austria-social-security-number"></a>Número de la seguridad social de Austria

### <a name="format"></a>Formato

10 dígitos en el formato especificado
  
### <a name="pattern"></a>Patrón

10 dígitos:
  
- tres dígitos que corresponden a un número de serie 
- un dígito de control
- seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- se encuentra una palabra clave de  `Keywords_austria_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- SSN austriaco
- número de EHIC
- EHIC no
- código de seguro
- insurancecode #
- número de seguro
- Nº seguro
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- n.º de seguridad social
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- SSN #
- SSN
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Número de identificación fiscal de Austria

### <a name="format"></a>Formato

nueve dígitos con guión opcional y barra diagonal
  
### <a name="pattern"></a>Patrón

nueve dígitos con guión opcional y barra diagonal:
  
- dos dígitos
- un guión (opcional)
- tres dígitos
- una barra diagonal (opcional)
- cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_austria_eu_tax_file_number` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
 
## <a name="austria-value-added-tax"></a>Impuesto sobre el valor añadido de Austria
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón alfanumérico de 11 caracteres

### <a name="pattern"></a>Patrón

patrón alfanumérico de 11 caracteres:

- A o un
- T o t
- Espacio opcional
- U o u
- espacio opcional
- dos o tres dígitos
- espacio opcional
- cuatro dígitos
- espacio opcional
- uno o dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Austria_Value_Added_Tax encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Austria_Value_Added_Tax.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Austria_Value_Added_Tax encuentra contenido que coincide con el patrón.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- número de IVA
- IVA #
- número de IVA austriaco
- n.º de IVA
- vatno #
- número del impuesto sobre el valor añadido
- IVA austriaco
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- número de identificación del IVA
- número de ATU
- número UID


## <a name="azure-documentdb-auth-key"></a>Clave de autenticación de Azure DocumentDB

### <a name="format"></a>Formato

La cadena "DocumentDb" seguida de los caracteres y las cadenas que se describen en el patrón siguiente.

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

- la cadena "servidor", "servidor" o "origen de datos"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "CloudApp. Azure.<!--no-hyperlink-->com "," CloudApp. Azure.<!--no-hyperlink-->net "o" Database. Windows.<!--no-hyperlink-->ADO.net
- cualquier combinación de entre 1-300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "Password", "Password" o "pwd"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- uno o más caracteres que no son un punto y coma (;), Comillas (") o apóstrofe (')
- un punto y coma (;), Comillas (") o apóstrofe (')

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

### <a name="keywords"></a>Palabras clave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

### <a name="pattern"></a>Patrón

- la cadena "HostName"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "Azure-Devices.<!--no-hyperlink-->ADO.net
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "SharedAccessKey"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de 43 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- un signo igual (=)

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

### <a name="keywords"></a>Palabras clave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

### <a name="pattern"></a>Patrón

- la cadena "userpwd ="
- cualquier combinación de 60 letras minúsculas o dígitos
- un signo de Comillas (")

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

### <a name="keywords"></a>Palabras clave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

### <a name="pattern"></a>Patrón

- la cadena "Redis. Cache. Windows.<!--no-hyperlink-->ADO.net
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "Password" o "pwd"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- un signo igual (=)

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

### <a name="keywords"></a>Palabras clave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

### <a name="pattern"></a>Patrón

- la cadena "SIG"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de entre 43-53 caracteres que sean letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)
- la cadena "% 3D"
- cualquier carácter que no sea una letra minúscula o mayúscula, un dígito o un signo de porcentaje (%)

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

### <a name="pattern"></a>Patrón

- la cadena "EndPoint"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "ServiceBus. Windows.<!--no-hyperlink-->ADO.net
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "SharedAccessKey"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- un signo igual (=)

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

### <a name="keywords"></a>Palabras clave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

### <a name="pattern"></a>Patrón

- la cadena "DefaultEndpointsProtocol"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "AccountKey"
- cero a dos caracteres de espacio en blanco
- un signo igual (=)
- cero a dos caracteres de espacio en blanco
- cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- dos signos de igual (=)

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

### <a name="keywords"></a>Palabras clave

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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

### <a name="pattern"></a>Patrón

- cero a uno de los símbolos mayor que (>), apóstrofe ('), signo de igual (=), Comillas (") o almohadilla (#)
- cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o el signo más (+)
- dos signos de igual (=)

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

### <a name="format"></a>Formato

diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

diez dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_belgium_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from `Keywords_eu_driver's_license_number` o `Keywords_belgium_eu_driver's_license_number` found.
    
```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver ' s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro Permis conduire


## <a name="belgium-national-number"></a>Número nacional de Bélgica

### <a name="format"></a>Formato

11 dígitos más delimitadores opcionales

### <a name="pattern"></a>Patrón

11 dígitos más delimitadores:
- seis dígitos y dos puntos opcionales en el formato AA. MM.DD para la fecha de nacimiento 
- Un delimitador opcional de punto, guión, espacio 
- tres dígitos secuenciales (impares para machos, incluso para hembras) 
- Un delimitador opcional de punto, guión, espacio 
- dos dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_belgium_national_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_belgium_national_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_belgium_national_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
- numéro d'assuré
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

### <a name="format"></a>Formato

dos letras seguidas de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

dos letras y seguidas de seis dígitos
  
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

 Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_belgium_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_belgium_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date2` encuentra la fecha en el formato DD MM AA o una palabra clave de `Keywords_eu_passport_date` o `Keywords_belgium_eu_passport_number` se encuentra

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_belgium_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_belgium_eu_passport_number` found. 

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort NR
- paspoort-NR
- paspoortnummer
- paspoortnummers
- Passeport
- Passeport livre
- Pass-Nr
- Passnummer
- reisepass kein


## <a name="belgium-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de Bélgica
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón alfanumérico de 12 caracteres

### <a name="pattern"></a>Patrón

patrón alfanumérico de 12 caracteres:

- una letra B o b
- una letra E o e
- un dígito del 0
- un dígito del 1 al 9
- un punto o guión o un espacio opcional
- cuatro dígitos
- un punto o guión o un espacio opcional
- cuatro dígitos


### <a name="checksum"></a>Suma de comprobación

Sí


### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_belgium_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_belgium_value_added_tax_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_belgium_value_added_tax_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- Nº TVA
- número de IVA
- número de IVA
- numéro t. v. a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- IVA #


## <a name="brazil-cpf-number"></a>Número de CPF de Brasil

### <a name="format"></a>Formato

11 dígitos incluido un dígito de control y que pueden tener o no formato

### <a name="pattern"></a>Patrón

Con formato
- tres dígitos
- un punto
- tres dígitos
- un punto
- tres dígitos
- un guión
- dos dígitos que son dígitos de control

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

14 dígitos más delimitadores:

- dos dígitos 
- un punto 
- tres dígitos 
- un punto 
- tres dígitos (estos ocho primeros dígitos son el número de registro) 
- barra diagonal 
- número de sucursal de cuatro dígitos 
- un guión 
- dos dígitos que son dígitos de control

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- Registro nacional de entidades jurídicas 
- Registro de contribuyentes 
- Entidad jurídica 
- Entidades jurídicas 
- Estado de registro 
- Business 
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

### <a name="pattern"></a>Patrón

Registro de Geral (formato antiguo):
- dos dígitos 
- un punto 
- tres dígitos 
- un punto 
- tres dígitos 
- un guión 
- un dígito que es un dígito de control

Registro de Identidade (RIC) (nuevo formato):
- diez dígitos 
- un guión 
- un dígito que es un dígito de control

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

### <a name="keywords"></a>Palabras clave

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

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_bulgaria_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_bulgaria_eu_driver's_license_number` found. 
    
```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>    
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver ' s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Número civil uniforme de Bulgaria
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

diez dígitos sin espacios y delimitadores
  
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- dos dígitos que corresponden a la orden de nacimiento
- un dígito que corresponde al género: un dígito par para macho y un dígito impar para hembra
- un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_bulgaria_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_bulgaria_eu_national_id_card` . 

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_bulgaria_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn #
- bnn
- bucn #
- bucn
- edinen grazhdanski nomer
- egn #
- egn
- identification number
- national id
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
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- identificador униформ
- униформ граждански ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Número de pasaporte de Bulgaria

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_bulgaria_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_bulgaria_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_bulgaria_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_bulgaria_eu_passport_number` found. 

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт no

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración

## <a name="canada-bank-account-number"></a>Número de cuenta bancaria de Canadá

### <a name="format"></a>Formato

siete o doce dígitos

### <a name="pattern"></a>Patrón

El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.

Un número de tránsito de cuenta bancaria de Canadá es:
- cinco dígitos 
- un guión 
- tres dígitos o
- un cero "0" 
- ocho dígitos

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

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

diez dígitos

### <a name="pattern"></a>Patrón

diez dígitos

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

### <a name="keywords"></a>Palabras clave

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

dos letras mayúsculas seguidas de seis dígitos

### <a name="pattern"></a>Patrón

dos letras mayúsculas seguidas de seis dígitos

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

### <a name="keywords"></a>Palabras clave

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

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón.
- Se encuentran al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces.

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

### <a name="keywords"></a>Palabras clave

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

nueve dígitos con guiones opcionales o espacios

### <a name="pattern"></a>Patrón

Con formato
- tres dígitos 
- un guión o un espacio 
- tres dígitos 
- un guión o un espacio 
- tres dígitos

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

### <a name="keywords"></a>Palabras clave

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

de siete a ocho dígitos más delimitadores, un dígito de control o una letra

### <a name="pattern"></a>Patrón

de siete a ocho dígitos más delimitadores:
- uno a dos dígitos 
- un período opcional 
- tres dígitos 
- un período opcional 
- tres dígitos 
- un guión 
- un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- Cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- REALIZAR
- ESTANCARSE
- tarjeta de identificación
- Rol unico nacional
- Rol unico tributario
- REALIZAR #
- ESTANCARSE #
- nationaluniqueroleID #
- identidad nacional
- número de identificación
- número de identidad
- numero identificacion
- identidad numero
- Nº de identidad de chileno
- Número de identidad de chileno
- Identidad chileno #
- Registro fiscal único
- Rol tributary único
- Rol de impuestos único
- Número tributary único
- Número nacional único
- Rol nacional único
- Rol nacional único
- N.º de identidad de Chile
- Número de identidad de Chile
- Identidad de Chile #

   
## <a name="china-resident-identity-card-prc-number"></a>Número de tarjeta de identidad de residente de China (PRC)

### <a name="format"></a>Formato

18 dígitos

### <a name="pattern"></a>Patrón

18 dígitos:
- seis dígitos que son un código de dirección 
- ocho dígitos con el formato AAAAMMDD que son la fecha de nacimiento 
- tres dígitos que son un código de pedido 
- un dígito que es un dígito de control

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

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
- COD. seguranca
- COD. segurança
- campos. seguranca
- cód segurança
- cod seguranca
- cod segurança
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
- transacciones
- número de transacción
- número de referencia
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- AMEX
- american express
- americanexpress
- americano espresso
- Régimen
- MasterCard
- master card
- valuación
- MasterCard
- master cards
- diner's Club
- diners club
- dinersclub
- advierte
- discover card
- detectar tarjeta
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- CC #
- # CC:
- expiration date
- exp date
- expiry date
- date d’expiration
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
- Acct Cardmember
- cuenta cardmember
- Cardno
- Tarjeta Corporativa
- Tarjetas corporativas
- Tipo de tarjeta
- número de cuenta de tarjeta
- cuenta de usuario de tarjeta
- Cardmember acct.
- card no.
- Nº de tarjeta
- card number
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
- z.e.n.. cobro
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
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Número de permiso de conducción de Croacia

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_croatia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from `Keywords_eu_driver's_license_number` o `Keywords_croatia_eu_driver's_license_number` found. 

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver ' s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Número de tarjeta de identidad de Croacia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de número de identificación nacional de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos consecutivos

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- número de ciudadano principal
- nacionalni identifikacijski broj
- national identification number
- OIB #
- OIB
- osobna iskaznica
- identificador osobni
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
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

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_croatia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_croatia_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_croatia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_croatia_eu_passport_number` found. 
    
```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice
   
## <a name="croatia-personal-identification-oib-number"></a>Número de identificación personal de Croacia (OIB)

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos:
- diez dígitos 
- el dígito final es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_croatia_eu_tax_file_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- número de ciudadano principal
- nacionalni identifikacijski broj
- national identification number
- OIB #
- OIB
- osobna iskaznica
- identificador osobni
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
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

### <a name="format"></a>Formato

12 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

12 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_cyprus_eu_driver's_license_number` found.

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver ' s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Tarjeta de identidad de Chipre
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

diez dígitos 
  
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_cyprus_eu_national_id_card` . 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- número de tarjeta de identificación
- número de tarjeta de identidad
- kimlik karti
- national identification number
- número de identificación personal
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Número de pasaporte de Chipre

### <a name="format"></a>Formato

una letra seguida de 6-8 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una letra seguida de seis a ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_cyprus_eu_passport_number` found. 
- La expresión regular `Regex_cyprus_eu_passport_date` encuentra la fecha en el formato dd/mm/aaaa o se encuentra una palabra clave de `Keywords_cyprus_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_cyprus_eu_passport_number` found.  
    
```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- expira el
- emitida el


## <a name="cyprus-tax-identification-number"></a>Número de identificación fiscal de Chipre
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

ocho dígitos y una letra en el patrón especificado
  
### <a name="pattern"></a>Patrón

ocho dígitos y una letra:
  
- un "0" o "9"
- siete dígitos
- una letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_cyprus_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_cyprus_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Número de permiso de conducción de Checo

### <a name="format"></a>Formato

dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

ocho letras y dígitos:
  
- letra ' E ' (no distingue entre mayúsculas y minúsculas)
- una carta
- un espacio (opcional)
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_czech_republic_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_czech_republic_eu_driver's_license_number` found. 

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver ' s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>Número de pasaporte Checo

### <a name="format"></a>Formato

ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos sin espacios ni delimitadores
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_czech_republic_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_czech_republic_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_czech_republic_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_czech_republic_eu_passport_number` found. 
    
```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- Cestovní PAS
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="czech-personal-identity-number"></a>Número de identidad personal en Checo

### <a name="format"></a>Formato

nueve dígitos con barra diagonal (formato antiguo) diez dígitos con barra diagonal (nuevo formato) opcional

### <a name="pattern"></a>Patrón

nueve dígitos (formato antiguo):
- seis dígitos que representan la fecha de nacimiento
- barra diagonal inversa opcional
- tres dígitos

diez dígitos (nuevo formato):
- seis dígitos que representan la fecha de nacimiento
- barra diagonal inversa opcional 
- cuatro dígitos donde el último dígito es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:

- La función Func_czech_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_czech_id_card.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:

- La función Func_czech_id_card_new_format encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- número de nacimiento
- identificador de República Checa
- czechidno #
- daňové číslo
- identifikační číslo
- n.º de identidad
- número de identidad
- identityno #
- identityno
- número de seguro
- national identification number
- nationalnumber #
- número nacional
- osobní číslo
- personalidnumber #
- número de identificación personal
- número de identificación personal
- número personal
- ID #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- SSN
- SSN #
- social security number
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


## <a name="denmark-drivers-license-number"></a>Número de permiso de conducción de Dinamarca

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_denmark_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_denmark_eu_driver's_license_number` found. 
    
```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver ' s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Número de pasaporte de Dinamarca

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_denmark_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_denmark_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date2` busca una fecha con el formato dd mm yy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_denmark_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_denmark_eu_passport_number` found. 
    
```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n °
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="denmark-personal-identification-number"></a>Número de identificación personal de Dinamarca

### <a name="format"></a>Formato

diez dígitos que contienen un guión

### <a name="pattern"></a>Patrón

diez dígitos:
- seis dígitos con el formato DDMMAA que son la fecha de nacimiento 
- un guión 
- cuatro dígitos en los que el último dígito es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Func_denmark_eu_tax_file_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_denmark_id.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Func_denmark_eu_tax_file_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Denmark Personal Identification Number -->
      <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- registreringssystem civil
- RCP
- RCP #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- tarjeta de mantenimiento
- número de tarjeta de seguro de salud
- número de seguro de salud
- identification number
- identifikationsnummer
- identifikationsnummer #
- número de identidad
- krankenkassennummer
- nationalid #
- nationalnumber #
- número nacional
- personalidnumber #
- personalidentityno #
- número de identificación personal
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- SSN
- SSN #
- identificador de patinaje
- Kode de patinaje
- Nummer de patinaje
- skattenummer
- social security number
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
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>Número de la Agencia para la imposición de drogas (DEA)

### <a name="format"></a>Formato

dos letras seguidas por siete dígitos

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código del inscrito 
- una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido o del dígito ' 9 ' del inscrito
- siete dígitos, el último de los cuales es el dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_dea_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_dea_number`
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_dea_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- DEA
- DEA #
- Administración de la aplicación de drogas
- organismo de cumplimiento de drogas


## <a name="estonia-drivers-license-number"></a>Número de permiso de conducción de Estonia

### <a name="format"></a>Formato

dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

dos letras y seis dígitos:
  
- las letras "ET" (sin distinción entre mayúsculas y minúsculas) 
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_estonia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_estonia_eu_driver's_license_number` found. 
    
```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver ' s_license_number

--Permis de conduire
- juhilubade numbrid
- número de juhiloa
- juhiluba


## <a name="estonia-personal-identification-code"></a>Código de identificación personal de Estonia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- un dígito que corresponde al sexo y al siglo de nacimiento (número impar macho, par hembra; 1-2: siglo XIX; 3-4: siglo XX; 5-6: siglo XXI)
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
- tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha
- un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_estonia_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_estonia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- ID-Kaart
- IK
- isikukood #
- isikukood
- identificador maksu
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
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

### <a name="format"></a>Formato

una letra seguida de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una letra seguida de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_estonia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_estonia_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_estonia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_estonia_eu_passport_number` found. 
    
```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

Eesti kodaniku Pass Passi passinumbrid número de documento de número de documento dokumendi NR

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="eu-debit-card-number"></a>Número de tarjeta de débito de la UE

### <a name="format"></a>Formato

16 dígitos

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

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
- [Checo](#czech-drivers-license-number)
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

- [Austria](#austria-identity-card)
- [Bélgica](#belgium-national-number)
- [Bulgaria](#bulgaria-uniform-civil-number)
- [Croacia](#croatia-identity-card-number)
- [Chipre](#cyprus-identity-card)
- [Checo](#czech-personal-identity-number)
- [Dinamarca](#denmark-personal-identification-number)
- [Estonia](#estonia-personal-identification-code)
- [Finlandia](#finland-national-id)
- [Francia](#france-national-id-card-cni)
- [Alemania](#germany-identity-card-number)
- [Grecia](#greece-national-id-card)
- [Hungría](#hungary-personal-identification-number)
- [Irlanda](#ireland-personal-public-service-pps-number)
- [Italia](#italy-fiscal-code)
- [Letonia](#latvia-personal-code)
- [Lituania](#lithuania-personal-code)
- [Luxemburgo](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Países Bajos](#netherlands-citizens-service-bsn-number)
- [Polonia](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Rumania](#romania-personal-numeric-code-cnp)
- [Eslovaquia](#slovakia-personal-number)
- [Eslovenia](#slovenia-unique-master-citizen-number)
- [España](#spain-dni)
- [RU](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>Número de pasaporte de la UE 

Estas son las entidades de la información confidencial de los números de pasaporte de la UE typeThese son las entidades de la agrupación de números de pasaporte de la UE.

- [Austria](#austria-passport-number)
- [Bélgica](#belgium-passport-number)
- [Bulgaria](#bulgaria-passport-number)
- [Croacia](#croatia-passport-number)
- [Chipre](#cyprus-passport-number)
- [Checo](#czech-passport-number)
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

- [Austria](#austria-social-security-number)
- [Bélgica](#belgium-national-number)
- [Croacia](#croatia-personal-identification-oib-number)
- [Checo](#czech-personal-identity-number)
- [Dinamarca](#denmark-personal-identification-number)
- [Finlandia](#finland-national-id)
- [Francia](#france-social-security-number-insee-or-equivalent-identification)
- [Alemania](#germany-identity-card-number)
- [Grecia](#greece-national-id-card)
- [Hungría](#hungary-social-security-number-taj)
- [Portugal](#portugal-citizen-card-number)
- [España](#spain-social-security-number-ssn)
- [Suecia](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>Número de identificación fiscal de la UE

Estas entidades se encuentran en el tipo de información confidencial de número de identificación de impuestos de la UE.

- [Austria](#austria-tax-identification-number)
- [Bélgica](#belgium-national-number)
- [Bulgaria](#bulgaria-uniform-civil-number)
- [Croacia](#croatia-identity-card-number)
- [Chipre](#cyprus-tax-identification-number)
- [Checo](#czech-personal-identity-number)
- [Dinamarca](#denmark-personal-identification-number)
- [Estonia](#estonia-personal-identification-code)
- [Finlandia](#finland-national-id)
- [Francia](#france-tax-identification-number)
- [Alemania](#germany-tax-identification-number)
- [Grecia](#greece-tax-identification-number)
- [Hungría](#hungary-tax-identification-number)
- [Irlanda](#ireland-personal-public-service-pps-number)
- [Italia](#italy-fiscal-code)
- [Letonia](#latvia-personal-code)
- [Lituania](#lithuania-personal-code)
- [Luxemburgo](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Países Bajos](#netherlands-tax-identification-number)
- [Polonia](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Rumania](#romania-personal-numeric-code-cnp)
- [Eslovaquia](#slovakia-personal-number)
- [Eslovenia](#slovenia-tax-identification-number)
- [España](#spain-tax-identification-number)
- [Suecia](#sweden-tax-identification-number)
- [RU](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Número de permiso de conducción de Finlandia

### <a name="format"></a>Formato

diez dígitos y letras que contienen un guión
  
### <a name="pattern"></a>Patrón

diez dígitos y letras que contienen un guión:
  
- seis dígitos 
- un guión
- tres dígitos 
- un dígito o una letra
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_finland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_finland_eu_driver's_license_number` found. 
    
```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver ' s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- Lic kuljettaja.
- körkort
- körkortnummer
- Lic förare.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Número de seguro médico de Finlandia europeo
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de 20 dígitos

### <a name="pattern"></a>Patrón

número de 20 dígitos:

- diez dígitos-8024680246
- un guión o un espacio opcional
- diez dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- El Regex_Finland_European_Health_Insurance_Number regex busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Finland_European_Health_Insurance_Number.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska sjukförsäkringskort
- tarjeta de mantenimiento
- tarjeta de seguro de salud
- número de seguro de salud
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>IDENTIFICACIÓN nacional de Finlandia

### <a name="format"></a>Formato

seis dígitos más un carácter que indica un siglo más tres dígitos más un dígito de control

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- seis dígitos en el formato DDMMAA que son una fecha de nacimiento 
- marcador de siglo (ya sea '-', ' + ' o ' a ') 
- número de identificación personal de tres dígitos 
- un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- la función Func_finnish_national_id encuentra contenido que coincide con el patrón
- se encuentra una palabra clave de Keyword_finnish_national_id
- la suma de comprobación pasa

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- la función Func_finnish_national_id encuentra contenido que coincide con el patrón
- la suma de comprobación pasa

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- identificador no
- número de identificador
- identification number
- identiteetti numero
- número de identidad
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
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
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Número de pasaporte de Finlandia

### <a name="format"></a>Formato
combinación de nueve letras y dígitos

### <a name="pattern"></a>Patrón
combinación de nueve letras y dígitos:
- dos letras (no distingue entre mayúsculas y minúsculas) 
- siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_eu_passport_number_common o Keyword_finland_passport_number.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- Suomalainen Passi
- Passen numero
- Passen numero. #
- Passen numero #
- Passen numero.
- Passi #
- número de pase


## <a name="france-drivers-license-number"></a>Número de permiso de conducción de Francia

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos con validación para descontar patrones similares como los números de teléfono franceses

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- la función Func_french_drivers_license encuentra contenido que coincide con el patrón.
- se encuentra una palabra clave de Keyword_french_drivers_license.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licencia


## <a name="france-health-insurance-number"></a>Número de seguro de estado de Francia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de 21 dígitos

### <a name="pattern"></a>Patrón

número de 21 dígitos:

- diez dígitos
- un espacio opcional
- diez dígitos
- un espacio opcional
- un dígito


### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- el Regex_France_Health_Insurance_Number regex busca contenido que coincide con el patrón.
- se encuentra una palabra clave de Keyword_France_Health_Insurance_Number.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- tarjeta de seguro
- Carta Vitale
- d'assuré social


## <a name="france-national-id-card-cni"></a>Tarjeta de identificación nacional (CNI) de Francia

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_france_eu_national_id_card.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- Carte de Nationale d'identité
- decir Nationale d'idenite no
- CNI #
- CNI
- compte bancaire
- national identification number
- identidad nacional
- nationalidno #
- numéro d'assurance maladie
- numéro de la Vitale de la carte

   
## <a name="france-passport-number"></a>Número de pasaporte de Francia
Esta entidad de tipo de información confidencial está disponible en el tipo de información confidencial de la UE número de pasaporte y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

nueve dígitos y Letras

### <a name="pattern"></a>Patrón

nueve dígitos y letras:
- dos dígitos 
- dos letras (no distingue entre mayúsculas y minúsculas) 
- cinco dígitos

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

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

### <a name="format"></a>Formato

13 dígitos
  
### <a name="pattern"></a>Patrón

13 dígitos
  
- Un dígito que debe ser 0, 1, 2 o 3
- 1 dígito
- Un espacio (opcional) 
- 2 dígitos 
- Un espacio (opcional) 
- 3 dígitos 
- Un espacio (opcional) 
- 3 dígitos 
- Un espacio (opcional) 
- 3 dígitos de control 

  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_france_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_france_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palabras clave

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


## <a name="france-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de Francia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón alfanumérico de 13 caracteres

### <a name="pattern"></a>Patrón

patrón alfanumérico de 13 caracteres:

- dos letras: FR (no distingue mayúsculas de minúsculas)
- un guión o un espacio opcional
- dos letras o dígitos
- espacio, puntos, guiones o comas opcionales
- tres dígitos
- espacio, puntos, guiones o comas opcionales
- tres dígitos
- espacio, puntos, guiones o comas opcionales
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_france_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_france_value_added_tax_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_france_value_added_tax_number encuentra contenido que coincide con el patrón.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- número de IVA
- número de IVA
- IVA #
- impuesto sobre el valor añadido
- identificación de Siren no numéro d'identification Taxe sur de Valeur ajoutée
- taxe valeur ajoutée
- Taxe sur la Valeur ajoutée
- n° TVA
- numéro de TVA
- numéro d'identification Siren


## <a name="germany-drivers-license-number"></a>Número de permiso de conducción de Alemania

### <a name="format"></a>Formato

combinación de 11 dígitos y Letras

### <a name="pattern"></a>Patrón

11 dígitos y letras (no distingue entre mayúsculas y minúsculas):
- un dígito o una letra 
- dos dígitos 
- seis dígitos o letras 
- un dígito 
- un dígito o una letra

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_drivers_license encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_german_drivers_license_number.
- Se supera la suma de comprobación.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- Nr-Führerschein
- Nr-fuhrerschein
- Nr-fuehrerschein
- no-Führerschein
- no-fuhrerschein
- no-fuehrerschein
- n-Führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- dlno


## <a name="germany-identity-card-number"></a>Número de tarjeta de identidad de Alemania

### <a name="format"></a>Formato

desde el 1 de noviembre de 2010: nueve letras y dígitos

desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:10 dígitos

### <a name="pattern"></a>Patrón

desde el 1 de noviembre de 2010:
- una letra (no distingue entre mayúsculas y minúsculas) 
- ocho dígitos

desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:
- diez dígitos

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- determinación
- identifikation
- identifizierungsnummer
- documento de identidad
- número de identidad
- ID-Nummer
- identificador personal
- personalausweis
- persönliche ID Nummer
- persönliche identifikationsnummer
- persönliche-ID-Nummer


## <a name="germany-passport-number"></a>Número de pasaporte de Alemania

### <a name="format"></a>Formato

diez dígitos o letras

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- el primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K) 
- tres dígitos 
- cinco dígitos o Letras de este conjunto (C,-H, J-N, P, R, T, V-Z) 
- un dígito

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_passport encuentra contenido que coincide con el patrón.
- Palabra clave from `Keyword_german_passport` o `Keywords_eu_passport_number_common` found.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_passport_data encuentra contenido que coincide con el patrón.
- Palabra clave from `Keyword_german_passport` o `Keywords_eu_passport_number_common` found.
- Se supera la suma de comprobación.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte


## <a name="germany-tax-identification-number"></a>Número de identificación fiscal de Alemania

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Dos dígitos 
- Un espacio opcional
- Tres dígitos 
- Un espacio opcional
- Tres dígitos 
- Un espacio opcional
- Dos dígitos
- un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_germany_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_germany_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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


## <a name="germany-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de Alemania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón alfanumérico de 11 caracteres

### <a name="pattern"></a>Patrón

patrón alfanumérico de 11 caracteres:

- una letra D o d
- una letra E o e
- un espacio opcional
- tres dígitos
- un espacio o una comas opcionales
- tres dígitos
- un espacio o una comas opcionales
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_germany_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_germany_value_added_tax_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_germany_value_added_tax_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- número de IVA
- número de IVA
- IVA #
- número de IVA mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Número de permiso de conducción de Grecia

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_greece_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_greece_eu_driver's_license_number` found. 
    
```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver ' s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Tarjeta de identificación nacional de Grecia

### <a name="format"></a>Formato

Combinación de 7 u 8 letras y números más un guión

### <a name="pattern"></a>Patrón

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

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- identificador griego
- identificación nacional griega
- tarjeta de identificación personal griega
- identificador de policía griega
- documento de identidad
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Número de pasaporte de Grecia

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_greece_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_greece_eu_passport_number` found. 
- La expresión regular `Regex_greece_eu_passport_date` busca una fecha con el formato dd mmm AA (ejemplo-28 ago 19) o se encuentra una palabra clave from `Keywords_greece_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_greece_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_greece_eu_passport_number` found. 
    
```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Número de la seguridad social de Grecia (AMKA)
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

Once dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

- 6 dígitos como fecha de nacimiento AAMMDD
- 4 dígitos
- un dígito de control
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_greece_eu_ssn` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_greece_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_greece_eu_ssn` busca contenido que coincide con el patrón. 

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- SSN
- SSN #
- n.º de seguridad social
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Número de identificación fiscal de Grecia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_greece_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_greece_eu_tax_file_number` . 
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Número de tarjeta de identidad de Hong Kong (HKID)

### <a name="format"></a>Formato

Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

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

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

Dos letras y seis dígitos:
  
- Dos letras (sin distinción entre mayúsculas y minúsculas) 
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_hungary_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_hungary_eu_driver's_license_number` found. 
    
```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver ' s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Número de identificación personal de Hungría
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

11 dígitos
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Un dígito que corresponde a sexo (1-macho, 2-hembra, otros números también son posibles para los ciudadanos nacidos antes del 1900 o los ciudadanos con doble nacionalidad) 
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
- Tres dígitos que corresponden a un número de serie
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_hungary_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- número de identificador
- identification number
- SZ IG
- SZ. IG.
- SZ. IG.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Número de pasaporte de Hungría

### <a name="format"></a>Formato

Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas por seis o siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_hungary_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_hungary_eu_passport_number` found. 
- La expresión regular `Regex_hungary_eu_passport_date` busca una fecha con el formato dd mmm/MMM AA (ejemplo-01 MÁR/Mar 12) o se encuentra una palabra clave from `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_hungary_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_hungary_eu_passport_number` found. 
    
```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám


## <a name="hungary-social-security-number-taj"></a>Número de seguridad social de Hungría (TAJ)

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_hungary_eu_ssn_or_equivalent` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

Diez dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Diez dígitos:
  
- Un dígito que debe ser "8" 
- Ocho dígitos
- Un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_hungary_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
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


## <a name="hungary-value-added-tax-number"></a>Número del impuesto sobre el valor añadido en Hungría
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón alfanumérico de 10 caracteres

### <a name="pattern"></a>Patrón

modelo alfanumérico de 10 caracteres:

- 2 cartas-HU o Hu
- espacio opcional
- 8 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:

- La función Func_hungarian_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_hungarian_value_added_tax_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:

- La función Func_hungarian_value_added_tax_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- IVA
- número del impuesto sobre el valor añadido
- IVA #
- vatno #
- hungarianvatno #
- Nº de impuestos
- áfa del impuesto sobre el valor añadido
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Número de cuenta permanente de India (PAN)

### <a name="format"></a>Formato

10 letras o dígitos

### <a name="pattern"></a>Patrón

10 letras o dígitos:
- Tres letras (no distingue entre mayúsculas y minúsculas) 
- Una letra en C, P, H, F, A, T, B, L, J, G (no distingue entre mayúsculas y minúsculas)
- Una carta
- Cuatro dígitos 
- Una letra (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_india_permanent_account_number.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Número de cuenta permanente 
- MANO 
   
## <a name="india-unique-identification-aadhaar-number"></a>Número de identificación única (Aadhaar) de India

### <a name="format"></a>Formato

12 dígitos que contienen espacios o guiones opcionales

### <a name="pattern"></a>Patrón

12 dígitos:
- Un dígito que no es 0 ni 1
- Tres dígitos 
- Un guión o un espacio opcional  
- Cuatro dígitos 
- Un guión o un espacio opcional  
- El dígito final que es el dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_india_aadhaar encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_india_aadhar.
- Se supera la suma de comprobación.
- 
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:

- La función Func_india_aadhaar encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

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
### <a name="keywords"></a>Palabras clave
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai
   
## <a name="indonesia-identity-card-ktp-number"></a>Número de tarjeta de identidad (KTP) de Indonesia

### <a name="format"></a>Formato

16 dígitos que contienen puntos opcionales

### <a name="pattern"></a>Patrón

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

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:

- La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_indonesia_id_card.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>Número de cuenta bancaria internacional (IBAN)

### <a name="format"></a>Formato

Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)


### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:

- Código de país de dos letras
- Dos dígitos de control (seguidos de un espacio opcional)  
- 1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)
- 1-3 letras o dígitos

El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:

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

### <a name="keywords"></a>Palabras clave

Ninguno

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Clasificación Internacional de enfermedades (ICD-10-CM)

### <a name="format"></a>Formato

Dictionary

### <a name="pattern"></a>Patrón

Palabra clave

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

### <a name="keywords"></a>Palabras clave

Cualquier término del Diccionario de palabras clave Dictionary_icd_10_updated, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo solo busca el término, no los códigos de seguro.

Cualquier término del Diccionario de palabras clave Dictionary_icd_10_codes, que se basa en la [clasificación internacional de enfermedades, décima revisión, modificación clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo busca sólo los códigos de seguros, no la descripción.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Clasificación Internacional de enfermedades (ICD-9-CM)

### <a name="format"></a>Formato

Dictionary

### <a name="pattern"></a>Patrón

Palabra clave

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

### <a name="keywords"></a>Palabras clave

Cualquier término del Diccionario de palabras clave Dictionary_icd_9_updated, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo solo busca el término, no los códigos de seguro.

Cualquier término del Diccionario de palabras clave Dictionary_icd_9_codes, que se basa en la [clasificación internacional de enfermedades, novena revisión, modificación clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo busca sólo los códigos de seguros, no la descripción.

## <a name="ip-address"></a>Dirección IP

### <a name="format"></a>Formato

#### <a name="ipv4"></a>IPv4
Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4

#### <a name="ipv6"></a>Protocolo
 Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (esta palabra clave distingue entre mayúsculas y minúsculas)
- dirección IP 
- Direcciones IP
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Número de permiso de conducción de Irlanda

### <a name="format"></a>Formato

Seis dígitos seguidos de cuatro letras
  
### <a name="pattern"></a>Patrón

Seis dígitos y cuatro letras:
  
- Seis dígitos
- Cuatro letras (sin distinción entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_ireland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_ireland_eu_driver's_license_number` found. 
    
```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver ' s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Número de pasaporte de Irlanda

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_ireland_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_ireland_eu_passport_number` found. 
- La expresión regular `Regex_ireland_eu_passport_date` busca Date con el formato dd mmm/MMM YYYY (example-01 BEA/MAY 1988) o se encuentra una palabra clave from `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_ireland_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_ireland_eu_passport_number` found.
    
```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir PAS
- fase uimhir
- uimhreacha PAS
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="ireland-personal-public-service-pps-number"></a>Número de servicio público personal (PPS) de Irlanda

### <a name="format"></a>Formato

Formato antiguo (hasta el 31 de diciembre de 2012):
- siete dígitos seguidos de 1-2 Letras 

Nuevo formato (1 de enero de 2013 y posterior):
- siete dígitos seguidos de dos letras

### <a name="pattern"></a>Patrón

Formato antiguo (hasta el 31 de diciembre de 2012):
- siete dígitos 
- de una a dos letras (no distingue entre mayúsculas y minúsculas) 

Nuevo formato (1 de enero de 2013 y posterior):
- siete dígitos 
- una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético 
- Una letra opcional en el rango A-I o "W"

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ireland_pps encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_ireland_eu_national_id_card.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ireland_pps encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- servicio de identidad de cliente
- identification number
- número de identificación personal
- número de servicio público personal
- n.º de servicio personal
- phearsanta seirbhíse poiblí
- n.º de PPS
- número de PPS
- número de PPS
- n.º de servicio de PPS
- ppsn
- ppsno #
- ppsno
- PSP
- n.º de servicio público
- publicserviceno #
- publicserviceno
- número de la seguridad social y de ingresos
- RSI no
- número de RSI
- rsin
- cliente de seirbhís aitheantais
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
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


## <a name="israel-bank-account-number"></a>Número de cuenta bancaria de Israel

### <a name="format"></a>Formato

13 dígitos

### <a name="pattern"></a>Patrón

Con formato
- dos dígitos 
- un guión 
- tres dígitos 
- un guión 
- ocho dígitos

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Número de cuenta bancaria 
- Cuenta bancaria 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Número de identificación nacional de Israel

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos consecutivos

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber #
-   número de identificador
-   n.º de identidad        
-   identitynumber #
-   número de identidad
-   israeliidentitynumber       
-   identificador personal
-   identificador único  

   
## <a name="italy-drivers-license-number"></a>Número de permiso de conducción de Italia

### <a name="format"></a>Formato

una combinación de 10 letras y dígitos

### <a name="pattern"></a>Patrón

una combinación de 10 letras y dígitos:
- una letra (no distingue entre mayúsculas y minúsculas) 
- la letra "A" o "V" (no distingue entre mayúsculas y minúsculas) 
- siete dígitos
- una letra (no distingue entre mayúsculas y minúsculas)

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- Numero di patentes
- patente di guida 
- Guida de patentes
- Guida de patentes
- Guida de patentes

## <a name="italy-fiscal-code"></a>Código fiscal de Italia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

una combinación de letras y dígitos de 16 caracteres en el patrón especificado
  
### <a name="pattern"></a>Patrón

Una combinación de letras y dígitos de 16 caracteres:
- tres letras que corresponden a las tres primeras consonantes en el nombre de la familia
- tres letras que corresponden a los consonantes primero, tercero y cuarto en el nombre
- dos dígitos que corresponden a los últimos dígitos del año de nacimiento
- una letra que corresponde a la carta del mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras de a a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)
- dos dígitos que corresponden al día del mes de nacimiento: para diferenciar entre los sexos, 40 se agrega al día de nacimiento para las mujeres
- cuatro dígitos que corresponden al código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para países extranjeros)
- un dígito de paridad
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_italy_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_italy_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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

### <a name="format"></a>Formato

dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

dos letras o dígitos seguidos de siete dígitos:
  
- dos dígitos o letras (no distingue entre mayúsculas y minúsculas)
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_italy_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_italy_eu_passport_number` found. 
- La expresión regular `Regex_italy_eu_passport_date` busca Date con el formato dd mmm/MMM YYYY (example-01 gen/JAN 1988) o se encontró una palabra clave from `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_italy_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_italy_eu_passport_number` found. 
    
```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- Numero di Passaporto
- número del Passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="italy-value-added-tax-number"></a>Número de impuesto sobre el valor añadido de Italia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón alfanumérico de 13 caracteres con delimitadores opcionales

### <a name="pattern"></a>Patrón

patrón alfanumérico de 13 caracteres con delimitadores opcionales:

- I o i
- T o t
- espacio, punto, guión o coma opcionales
- 11 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_italy_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_italy_value_added_tax_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_italy_value_added_tax_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- número de IVA
- número de IVA
- IVA #
- IVA
- IVA #


## <a name="japan-bank-account-number"></a>Número de cuenta bancaria de Japón

### <a name="format"></a>Formato

siete u ocho dígitos

### <a name="pattern"></a>Patrón

número de cuenta bancaria:
- siete u ocho dígitos
- código de sucursal de cuenta bancaria:
- cuatro dígitos 
- un espacio o un guión (opcional) 
- tres dígitos

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

### <a name="keywords"></a>Palabras clave

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
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>Número de permiso de conducción de Japón

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- listas #
- distribución #
- Lic #
- conducción #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Mi número de Japón-empresa
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de 13 dígitos

### <a name="pattern"></a>Patrón

número de 13 dígitos:

- un dígito de uno a nueve
- 12 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_japanese_my_number_corporate encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_japanese_my_number_corporate.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_japanese_my_number_corporate encuentra contenido que coincide con el patrón.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- número corporativo
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>Mi número-personal de Japón
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de 12 dígitos

### <a name="pattern"></a>Patrón

número de 12 dígitos:

- cuatro dígitos
- un espacio, un punto o un guión opcional
- cuatro dígitos
- un espacio, un punto o un guión opcional
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_japanese_my_number_personal encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_japanese_my_number_personal.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_japanese_my_number_personal encuentra contenido que coincide con el patrón.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- mi número
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード

   
## <a name="japan-passport-number"></a>Número de pasaporte de Japón

### <a name="format"></a>Formato

dos letras seguidas por siete dígitos

### <a name="pattern"></a>Patrón

dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Usuarios
- Passport Number
- N.º de pasaporte
- Passport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パスポートNo.
- 旅券番号
- 旅券番号＃
- ♯ 旅券番号
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Número de tarjeta de residencia de Japón

### <a name="format"></a>Formato

12 letras y dígitos

### <a name="pattern"></a>Patrón

12 letras y dígitos:
- dos letras (no distingue entre mayúsculas y minúsculas)
- ocho dígitos 
- dos letras (no distingue entre mayúsculas y minúsculas)

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Número de tarjeta de residencia
- Nº de tarjeta de residencia
- Tarjeta de residencia #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Número de registro de residente de Japón

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証

   
## <a name="japan-social-insurance-number-sin"></a>Número del seguro social de Japón (SIN)

### <a name="format"></a>Formato

De 7 a 12 dígitos

### <a name="pattern"></a>Patrón

7-12 dígitos:
- cuatro dígitos 
- un guión (opcional) 
- seis dígitos o
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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Número de permiso de conducción de Letonia

### <a name="format"></a>Formato

tres letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

tres letras y seis dígitos:
  
- tres letras (sin distinción entre mayúsculas y minúsculas) 
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_latvia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_latvia_eu_driver's_license_number` found. 
    
```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver ' s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Código personal de Letonia

### <a name="format"></a>Formato

11 dígitos y un guión opcional
  
### <a name="pattern"></a>Patrón

Formato antiguo

11 dígitos y un guión:
  
- seis dígitos que corresponden a la fecha de nacimiento (DDMMAA) 
- un guión
- un dígito que corresponde al siglo de nacimiento ("0" para el siglo XIX, "1" para el siglo XX y "2" para el siglo XXI)
- cuatro dígitos, generados aleatoriamente

Nuevo formato

11 dígitos

- Dos dígitos "32"
- Nueve dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_latvia_eu_national_id_card` o regex `Regex_latvia_eu_national_id_card_new_format` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_latvia_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_latvia_eu_national_id_card` o regex `Regex_latvia_eu_national_id_card_new_format` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- número administrativo
- alvas nē
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
- identifikācijas numurs
- identificador-número
- número individual
- latvija alva
- identificador nacionālais
- national id
- número de identificación nacional
- número de identidad nacional
- national insurance number
- número de registro nacional
- nodokļa numurs
- identificador nodokļu
- nodokļu identifikācija numurs
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
- registration number
- número de ingresos
- social insurance number
- social security number
- código de impuestos estatales
- tax file number
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

### <a name="format"></a>Formato

dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

dos letras o dígitos seguidos de siete dígitos:
  
- dos dígitos o letras (no distingue entre mayúsculas y minúsculas)
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_latvia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_latvia_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_latvia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_latvia_eu_passport_number` found. 
    
```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases NR
- passeport no
- n° du passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="lithuania-drivers-license-number"></a>Número de permiso de conducción de Lituania

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_lithuania_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_lithuania_eu_driver's_license_number` found. 
    
```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver ' s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo número
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Código de Lituania personal
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos sin espacios y delimitadores:
  
- un dígito (1-6) que corresponde al sexo de la persona y al siglo de nacimiento
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- tres dígitos que corresponden al número de serie de la fecha de nacimiento
- un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_lithuania_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_lithuania_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- número de servicio de ciudadanos
- identificador mokesčių
- mokesčių identifikavimas número
- mokesčių identifikavimo número
- numeración mokesčių
- national identification number
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
- unikalus identifikavimo kodas
- unikalus identifikavimo número
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Número de pasaporte de Lituania

### <a name="format"></a>Formato

ocho dígitos o letras sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_lithuania_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_lithuania_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date3` encuentra la fecha en el formato dd mm aaaa o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_lithuania_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_lithuania_eu_passport_number` found. 
    
```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- numeración paso
- paso numeriai
- paso NR

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="luxemburg-drivers-license-number"></a>Número de permiso de conducción de Luxemburgo

### <a name="format"></a>Formato

seis dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

seis dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_luxemburg_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_luxemburg_eu_driver's_license_number` found. 
    
```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver ' s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Luxemburgo número de identificación nacional (personas físicas)
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos:
  
- 11 dígitos 
- dos dígitos de control
    
### <a name="checksum"></a>Suma de comprobación

sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_luxemburg_eu_national_id_card` . 

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number` busca contenido que coincide con el patrón. 


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
- persönliche identifikationsnummer
- identificador único
- identidad única
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Número de pasaporte de Luxemburgo

### <a name="format"></a>Formato

ocho dígitos o letras sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_luxemburg_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_luxemburg_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date3` encuentra la fecha en el formato dd mm aaaa o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_luxemburg_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_luxemburg_eu_passport_number` found. 
    
```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- Luxemburgo Pass
- Luxemburgo passeport
- Luxemburgo Passport
- no de passeport
- no-reisepass
- Nr-reisepass
- numéro de passeport
- red de paso
- paso NR
- passnummer
- nombre passeport
- reisepässe
- reisepass-NR
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Luxemburgo número de identificación nacional (personas no físicas)

### <a name="format"></a>Formato

11 dígitos
  
### <a name="pattern"></a>Patrón

11 dígitos
  
- dos dígitos
- un espacio opcional 
- tres dígitos 
- un espacio opcional
- tres dígitos 
- un espacio opcional
- dos dígitos
- un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number_non_natural` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_luxemburg_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number_non_natural` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- Carta de Sécurité Sociale
- étain no
- étain #
- identificador d'impôt
- identifikatiounsnummer de impuestos de Luxemburgo
- numéro d'étain
- numéro d'identification fiscales de Luxembourgeois
- numéro d'identification fiscal
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- identificador Steier
- steier identifikatiounsnummer
- steier nummer
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

### <a name="pattern"></a>Patrón

12 dígitos:
- seis dígitos con el formato AAMMDD que son la fecha de nacimiento 
- un guión (opcional) 
- Código del punto de nacimiento de dos letras 
- un guión (opcional) 
- tres dígitos aleatorios 
- código de género de un dígito

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

### <a name="keywords"></a>Palabras clave
   
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

### <a name="format"></a>Formato

Combinación de dos caracteres y seis dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

combinación de dos caracteres y seis dígitos:
  
- dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)
- un espacio (opcional)
- tres dígitos
- un espacio (opcional)
- tres dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_malta_eu_driver's_license_number` found. 
    
```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver ' s_license_number

- liċenzja sewqan
- liċenzji sewwieq


## <a name="malta-identity-card-number"></a>Número de tarjeta de identidad de Malta
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

siete dígitos seguidos de una letra
  
### <a name="pattern"></a>Patrón

siete dígitos seguidos de una letra:
  
- siete dígitos 
- una letra en "M, G, A, P, L, H, B, Z" (sin distinción entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_malta_eu_national_id_card` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- número de servicio de ciudadanos
- identificador TAT-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni TAT-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' Identità uniku
- numru Servizz taċ-ċittadin
- numru tat-taxxa
- código numérico personal
- número de identificación único
- número de identidad único
- uniqueidentityno #


## <a name="malta-passport-number"></a>Número de pasaporte de Malta

### <a name="format"></a>Formato

siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

siete dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_malta_eu_passport_number` found. 
- Se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_malta_eu_passport_number` found. 
    
```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- NRU tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="malta-tax-identification-number"></a>Número de identificación fiscal de Malta

### <a name="format"></a>Formato

Para los nacionales de Maltés:
- siete dígitos y una letra en el patrón especificado
  
Nacionales no Maltés y entidades de Maltés:
- nueve dígitos
  
### <a name="pattern"></a>Patrón

Nacionales de Malta: siete dígitos y una letra
  
- siete dígitos 
- una letra (no distingue entre mayúsculas y minúsculas)
    
Nacionales no Maltés y entidades de Maltés: nueve dígitos
  
- nueve dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Expresión regular  `Regex_malta_eu_tax_file_number`  o `Regex_malta_eu_tax_file_number_non_maltese_national` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_malta_eu_tax_file_number` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Expresión regular  `Regex_malta_eu_tax_file_number` o `Regex_malta_eu_tax_file_number_non_maltese_national` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- número de servicio de ciudadanos
- identificador TAT-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni TAT-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' Identità uniku
- numru Servizz taċ-ċittadin
- numru tat-taxxa
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

ocho-nueve dígitos que contienen espacios opcionales

### <a name="pattern"></a>Patrón

ocho-nueve dígitos:
- tres dígitos 
- un espacio (opcional) 
- tres dígitos 
- un espacio (opcional) 
- dos o tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_netherlands_bsn.
- Se supera la suma de comprobación.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card
  
- BSN #
- BSN
- burgerservicenummer
- número de servicio de ciudadanos
- número de persona
- número personal
- código numérico personal
- número relacionado con la persona
- persoonlijk nummer
- persoonlijke numerieke código
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- número social-fiscal
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Número de permiso de conducción de los países bajos

### <a name="format"></a>Formato

diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

diez dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_netherlands_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_netherlands_eu_driver's_license_number` found. 
    
```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver ' s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Número de pasaporte de Holanda

### <a name="format"></a>Formato

nueve letras o dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

nueve letras o dígitos
  
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_netherlands_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_netherlands_eu_passport_number` found. 
- La expresión regular `Regex_netherlands_eu_passport_date` busca Date con el formato dd mmm/MMM YYYY (ejemplo-26 Maa/MAR 2012)

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_netherlands_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_netherlands_eu_passport_number` found. 
    
```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort NR

## <a name="netherlands-tax-identification-number"></a>Número de identificación fiscal de países bajos
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_netherlands_eu_tax_file_number` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_netherlands_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
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


## <a name="netherlands-value-added-tax-number"></a>Número del impuesto sobre el valor añadido en los países bajos
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón alfanumérico de 14 caracteres

### <a name="pattern"></a>Patrón

patrón alfanumérico de 14 caracteres:

- N o n
- L o l
- espacio, punto o guión opcional
- nueve dígitos
- espacio, punto o guión opcional
- B o b
- dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_netherlands_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_netherlands_value_added_tax_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_netherlands_value_added_tax_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- número de IVA
- número de IVA
- IVA #
- wearde tafoege impuestos getadl
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Número de cuenta bancaria de Nueva Zelanda
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

patrón de 14 a 16 dígitos con delimitador opcional

### <a name="pattern"></a>Patrón

patrón de 14 a 16 dígitos con delimitador opcional:

- dos dígitos
- un guión o un espacio opcional
- de tres a cuatro dígitos
- un guión o un espacio opcional
- siete dígitos
- un guión o un espacio opcional
- dos o tres dígitos
- un guión o un espacio de opciones

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_new_zealand_bank_account_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_bank_account_number encuentra contenido que coincide con el patrón.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- cuenta bancaria
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Número de permiso de conducción de Nueva Zelanda
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

modelo alfanumérico de ocho caracteres

### <a name="pattern"></a>Patrón

modelo alfanumérico de ocho caracteres

- dos letras 
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_newzealand_driver_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_newzealand_driver_license_number.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_newzealand_driver_license_number encuentra contenido que coincide con el patrón.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- Lic del conductor
- permiso de conducir
- licencias de conducir
- driverslic
- driverslicence
- driverslicences
- Lic de los drivers
- Controladores conducción
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's licence
- permiso de conducción
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- permiso de conducir #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- permiso de conducción #
- international driving permit
- international driving permits
- Asociación de automóvil NZ
- Asociación de automóviles de Nueva Zelanda


## <a name="new-zealand-inland-revenue-number"></a>Número de ingresos interiores de Nueva Zelanda
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

ocho o nueve dígitos con delimitadores opcionales

### <a name="pattern"></a>Patrón

ocho o nueve dígitos con delimitadores opcionales

- dos o tres dígitos
- un guión o un espacio opcional
- tres dígitos
- un guión o un espacio opcional
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_inland_revenue_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_new_zealand_inland_revenue_number.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_inland_revenue_number encuentra contenido que coincide con el patrón.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- IRD no.
- IRD no #
- NZ IRD
- Nueva Zelanda IRD
- número de IRD
- número de ingresos interiores


## <a name="new-zealand-ministry-of-health-number"></a>Número de Ministerio de salud de Nueva Zelanda

### <a name="format"></a>Formato

tres letras, un espacio (opcional) y cuatro dígitos

### <a name="pattern"></a>Patrón

- tres letras (no distinguen entre mayúsculas y minúsculas) excepto "I" y "O"
- un espacio (opcional) 
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_nz_terms.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- Salud
- régimen
- Número de índice de salud nacional
- número de NHI
- NHI no.
- NHI #
- N.º de índice de salud nacional
- Identificador de índice de salud nacional
- Índice de salud nacional #

## <a name="new-zealand-social-wlefare-number"></a>Número de wlefare social de Nueva Zelanda
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos

- tres dígitos
- un guión opcional
- tres dígitos
- un guión opcional
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_newzealand_social_welfare_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_newzealand_social_welfare_number.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_newzealand_social_welfare_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- bienestar social #
- bienestar social #
- Nº de bienestar social
- número de bienestar social
- swn #

   
## <a name="norway-identification-number"></a>Número de identificación de Noruega

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos:
- seis dígitos con el formato DDMMAA que son la fecha de nacimiento 
- número individual de tres dígitos 
- dos dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_norway_id_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_norway_id_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

12 dígitos:
- cuatro dígitos 
- un guión 
- siete dígitos 
- un guión 
- un dígito

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

### <a name="keywords"></a>Palabras clave
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Id. universal unificado
 
- UMID 
- Tarjeta de identidad 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Número de permiso de conducción de Polonia

### <a name="format"></a>Formato

14 dígitos que contienen 2 barras diagonales
  
### <a name="pattern"></a>Patrón

14 dígitos y 2 barras diagonales:
  
- cinco dígitos 
- barra diagonal
- dos dígitos
- barra diagonal
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_poland_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_poland_eu_driver's_license_number` found. 
    
```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver ' s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Tarjeta de identidad de Polonia

### <a name="format"></a>Formato

tres letras y seis dígitos

### <a name="pattern"></a>Patrón

tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_polish_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.
- Se supera la suma de comprobación.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numerar dowodu osobistego
- Nazwa i número dowodu osobistego
- Nazwa i NR dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. MacOS.

   
## <a name="poland-national-id-pesel"></a>IDENTIFICACIÓN nacional de Polonia (PESEL)

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

- 6 dígitos que representan la fecha de nacimiento en el formato AAMMDD
- 4 dígitos
- 1 dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_pesel_identification_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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

dos letras y siete dígitos

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Números paszportu
- Nº. Paszportu
- Paszport

## <a name="poland-regon-number"></a>Número de REGON de Polonia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de nueve dígitos o 14 dígitos

### <a name="pattern"></a>Patrón

número de nueve dígitos o de 14 dígitos:

- nueve dígitos o 
- nueve dígitos
- virtuales
- cinco dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_polish_regon_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_polish_regon_number.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_polish_regon_number encuentra contenido que coincide con el patrón.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palabras clave

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- identificador REGON
- número estadístico
- identificador estadístico
- n.º estadístico
- número de REGON
- regonid #
- regonno #
- identificador de la compañía
- companyId #
- companyidno #
- números statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Número de identificación fiscal de Polonia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_poland_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_poland_eu_tax_file_number` . 
    
  
```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
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

### <a name="format"></a>Formato

ocho dígitos

### <a name="pattern"></a>Patrón

ocho dígitos

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

### <a name="keywords"></a>Palabras clave

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

### <a name="format"></a>Formato

dos modelos: dos letras seguidas por 5-8 dígitos con caracteres especiales
  
### <a name="pattern"></a>Patrón

Trama 1: dos letras seguidas de 5/6 con caracteres especiales:
- Dos letras (sin distinción entre mayúsculas y minúsculas)
- Un guión 
- Cinco o seis dígitos
- Un espacio
- Un dígito

Patrón 2: una letra seguida de 6/8 dígitos con caracteres especiales:
- Una letra (no distingue entre mayúsculas y minúsculas)
- Un guión 
- Seis u ocho dígitos
- Un espacio
- Un dígito

    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_portugal_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_portugal_eu_driver's_license_number` found. 
    
```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver ' s_license_number

- Carteira de motorista
- carteira motorista
- Carteira de habilitação
- carteira habilitação
- número de Licença
- número Licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- Carta de condução

## <a name="portugal-passport-number"></a>Número de pasaporte de Portugal

### <a name="format"></a>Formato

una letra seguida de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una letra seguida de seis dígitos:
  
- una letra (no distingue entre mayúsculas y minúsculas)
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_portugal_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_portugal_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_portugal_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_portugal_eu_passport_number` found.
    
```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número Passaporte
- pasaporte de Portugal
- Portugués passeport
- Portugués Passaporte
- Passaporte n º
- passeport n º
- números de Passaporte
- pasaportes de Portugal
- número Passaporte
- números Passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="portugal-tax-identification-number"></a>Número de identificación fiscal de Portugal

### <a name="format"></a>Formato

nueve dígitos con espacios opcionales
  
### <a name="pattern"></a>Patrón

- 3 dígitos
- un espacio opcional
- 3 dígitos
- un espacio opcional
- 3 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_portugal_eu_tax_file_number` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_portugal_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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

### <a name="format"></a>Formato

un carácter seguido de ocho dígitos
  
### <a name="pattern"></a>Patrón

un carácter seguido de ocho dígitos:
- una letra (no distingue entre mayúsculas y minúsculas) o un dígito 
- ocho dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_romania_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_romania_eu_driver's_license_number` found. 
    
```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver ' s_license_number

- Perm de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- Perm conducere

## <a name="romania-personal-numeric-code-cnp"></a>Código numérico personal (CNP) de Rumania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

13 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

- 1 dígito desde 1-9
- 6 dígitos que representan la fecha de nacimiento (AAMMDD)
- 2 dígitos que pueden ser 01-52 o 99
- 4 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_romania_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_romania_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
- national id
- national identification number
- număr identificare personal
- număr identitate
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
- tax file number
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

### <a name="format"></a>Formato

ocho o nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho o nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_romania_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_romania_eu_passport_number` found. 
- La expresión regular `Regex_romania_eu_passport_date` busca una fecha con el formato dd mmm/MMM AA (ejemplo-01 Feb/Feb 10) o se encuentra una palabra clave from `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_romania_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_romania_eu_passport_number` found. 
    
```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului numerele pașaportului Pașaport NR

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="russia-passport-number-domestic"></a>Número de pasaporte de Rusia nacional
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de diez dígitos

### <a name="pattern"></a>Patrón

número de 10 dígitos:

- dos dígitos
- un guión o un espacio opcional
- dos dígitos
- un espacio opcional
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- El Regex_Russian_Passport_Number_Domestic regex busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- passport number
- n.º de pasaporte
- usuarios #
- identificador de Passport
- passportno #
- passportnumber #
- паспорт нет
- identificador паспорт
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Número de pasaporte de Rusia internacional
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de nueve dígitos

### <a name="pattern"></a>Patrón

número de nueve dígitos:

- dos dígitos
- un guión o un espacio opcional
- siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- El Regex_Russian_Passport_Number_International regex busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- n.º de pasaporte
- usuarios #
- identificador de Passport
- passportno #
- passportnumber #
- паспорт нет
- identificador паспорт
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Identificación nacional de Arabia Saudí

### <a name="format"></a>Formato

diez dígitos

### <a name="pattern"></a>Patrón

diez dígitos consecutivos

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Número de tarjeta de identidad de registro nacional (NRIC) de Singapur

### <a name="format"></a>Formato

nueve letras y dígitos

### <a name="pattern"></a>Patrón

- nueve letras y dígitos:
- la letra "F", "G", "S" o "T" (no distingue entre mayúsculas y minúsculas) 
- siete dígitos 
- un dígito de control alfabético

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

### <a name="keywords"></a>Palabras clave
   
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

### <a name="format"></a>Formato

un carácter seguido de siete dígitos
  
### <a name="pattern"></a>Patrón

un carácter seguido de siete dígitos
  
- una letra (no distingue entre mayúsculas y minúsculas) o un dígito
- siete dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovakia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_slovakia_eu_driver's_license_number` found. 
    
```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver ' s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Número personal de Eslovaquia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

nueve o diez dígitos que contienen una barra diagonal inversa opcional
  
### <a name="pattern"></a>Patrón

- 6 dígitos que representan la fecha de nacimiento
- barra opcional (/)
- 3 dígitos
- 1 dígito de comprobación opcional
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_slovakia_eu_national_id_card` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_slovakia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- número de nacimiento
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- número de identificador
- n.º de identificación
- identification number
- identifikačná karta č
- identifikačné číslo
- Nº de tarjeta de identidad
- número de tarjeta de identidad
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- SSN #
- SSN
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- n.º de archivo de impuestos
- tax file number
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

### <a name="format"></a>Formato

un dígito o letra seguido de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovakia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_slovakia_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovakia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_slovakia_eu_passport_number` found. 
    
```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- PAS č.
- Passeport n °
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="slovenia-drivers-license-number"></a>Número de permiso de conducción de Eslovenia

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovenia_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_slovenia_eu_driver's_license_number` found. 
    
```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver ' s_license_number

- vozniško dovoljenje
- licencia de številka de vozniška
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Eslovenia número de ciudadanos maestros únicos
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos en el patrón especificado:
  
- siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL) donde "LLL" corresponde a los tres últimos dígitos del año de nacimiento. 
- dos dígitos que corresponden al área de nacimiento "50"
- tres dígitos que corresponden a una combinación de sexo y número de serie de las personas nacidos el mismo día (000-499 para macho y 500-999 para hembras)
- un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_slovenia_eu_national_id_card` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_national_id_card` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- documento de identidad
- identificador Nacionalna
- lista potni de Nacionalni
- national id
- osebna izkaznica
- osebni koda
- NE osebni
- osebni številka
- código personal
- número personal
- código numérico personal
- številka državljana
- número de ciudadano único
- número de identificador único
- número de identidad único
- número único de ciudadano principal
- número de registro único
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Número de pasaporte de Eslovenia

### <a name="format"></a>Formato

dos letras seguidas de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

dos letras seguidas de siete dígitos:
  
- la letra "P"
- una letra mayúscula
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovenia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_slovenia_eu_passport_number` found. 
- La expresión regular `Regex_eu_passport_date1` encuentra una fecha con el formato DD. mm. yyyy o se encuentra una palabra clave de. `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovenia_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_slovenia_eu_passport_number` found. 
    
```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- lista potni #
- rojstva de datos de referencia
- lista potni
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="slovenia-tax-identification-number"></a>Número de identificación fiscal de Eslovenia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

- un dígito desde 1-9
- seis dígitos
- un dígito de control
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_slovenia_eu_tax_file_number` . 
    
Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- n.º de archivo de impuestos
- tax file number
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

### <a name="pattern"></a>Patrón

13 dígitos:
- seis dígitos con el formato AAMMDD que son la fecha de nacimiento 
- cuatro dígitos 
- un indicador de ciudadanía de un solo dígito 
- el dígito "8" o "9" 
- un dígito que es un dígito de suma de comprobación

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

### <a name="keywords"></a>Palabras clave
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- tarjeta de identidad
- ID
- Determinación 
   
## <a name="south-korea-resident-registration-number"></a>Número de registro de residente de Corea del sur

### <a name="format"></a>Formato

13 dígitos que contienen un guión

### <a name="pattern"></a>Patrón

13 dígitos:
- seis dígitos con el formato AAMMDD que son la fecha de nacimiento 
- un guión 
- un dígito determinado por el siglo y el sexo 
- código de región de nacimiento de cuatro dígitos 
- un dígito que se usa para diferenciar a las personas para las que los números anteriores son idénticos 
- un dígito de control.

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

### <a name="keywords"></a>Palabras clave
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- Tarjeta de id. nacional 
- Número de registro de ciudadano 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Número de permiso de conducción de España

### <a name="format"></a>Formato

ocho dígitos seguidos de un carácter
  
### <a name="pattern"></a>Patrón

ocho dígitos seguidos de un carácter:
  
- ocho dígitos 
- un dígito o letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` encuentra contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_spain_eu_driver's_license_number` found. 

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` encuentra contenido que coincide con el patrón. 
    
```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver ' s_license_number

- permisos de conducción
- permisos conducción
- licencia de conducir
- licenciar conducir
- permisos conducir
- permisos de conducir
- permisos de conducir
- permisos conducir
- conducir del cuaderno
- cuaderno de conducir
- licencia de manejo
- licenciar manejo

## <a name="spain-dni"></a>DNI de España
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

ocho dígitos seguidos de un carácter
  
### <a name="pattern"></a>Patrón

siete dígitos seguidos de un carácter
  
- ocho dígitos
- Un guión o un espacio opcional
- una carta de comprobación (sin distinción entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_spain_eu_national_id_card"` . 

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` encuentra contenido que coincide con el patrón. 

    
```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- DNI #
- DNI
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- número de seguro
- national identification number
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

### <a name="format"></a>Formato

una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una combinación de letras y números de ocho o nueve caracteres:
  
- dos dígitos o letras 
- un dígito o letra (opcional)
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_spain_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_spain_eu_passport_number` found. 
- La expresión regular `Regex_spain_eu_passport_date` encuentra una fecha con el formato dd-mm-yyyy o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_spain_eu_passport_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_passport_number` o `Keywords_spain_eu_passport_number` found.
    
```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- usuarios #
- usuarios #
- passportid
- passports
- passportno
- n.º de pasaporte
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n °
- n° passeport
- pasaporte no.
- pasaporte n °
- pasaporte de España

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración


## <a name="spain-social-security-number-ssn"></a>Número de la seguridad social de España (NSS)

### <a name="format"></a>Formato

11 o 12 dígitos

### <a name="pattern"></a>Patrón

11-12 dígitos:
- dos dígitos 
- una barra diagonal (opcional) 
- de siete a ocho dígitos 
- una barra diagonal (opcional) 
- dos dígitos

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

### <a name="keywords"></a>Palabras clave

Ninguno

## <a name="spain-tax-identification-number"></a>Número de identificación fiscal de España
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

siete u ocho dígitos y una o dos letras en el patrón especificado
  
### <a name="pattern"></a>Patrón

Personas físicas españolas con una tarjeta de identidad nacional de España:
  
- ocho dígitos 
- una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Spaniards no residente sin una tarjeta de identidad nacional de España
  
- una letra mayúscula "L" (distingue entre mayúsculas y minúsculas)
- siete dígitos
- una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Spaniards residente a la edad de 14 años sin una tarjeta de identidad nacional de España:
  
- una letra mayúscula "K" (distingue entre mayúsculas y minúsculas)
- siete dígitos 
- una letra mayúscula (distingue entre mayúsculas y minúsculas)
    
Foreigners con un número de identificación de un extranjero
  
- una letra mayúscula que es "X", "Y" o "Z" (distingue entre mayúsculas y minúsculas) 
- siete dígitos
- una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
Foreigners sin un número de identificación de un extranjero
  
- una letra mayúscula que es "M" (distingue entre mayúsculas y minúsculas) 
- siete dígitos
- una letra mayúscula (distingue entre mayúsculas y minúsculas) 
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_tax_file_number` o `Func_spain_eu_DL_and_NI_number_citizen` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_spain_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_tax_file_number` o `Func_spain_eu_DL_and_NI_number_citizen` encuentra contenido que coincide con el patrón. 
    
```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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
- tax file number
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

### <a name="pattern"></a>Patrón

- la cadena "User ID", "User ID", "UID" o "UserId"
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "Password" o "pwd" donde "pwd" no está precedida por una letra minúscula.
- un signo igual (=)
- cualquier carácter que no sea un signo de dólar ($), un símbolo de porcentaje (%), un símbolo mayor que (>), un símbolo de arroba (@), Comillas ("), punto y coma (;), llave izquierda ([) o corchete de apertura ({)
- cualquier combinación de 7-128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")
- un punto y coma (;) o comillas (")

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

### <a name="keywords"></a>Palabras clave

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

### <a name="format"></a>Formato

diez dígitos que contienen un guión
  
### <a name="pattern"></a>Patrón

diez dígitos que contienen un guión:
  
- seis dígitos 
- un guión
- cuatro dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_sweden_eu_driver's_license_number` busca contenido que coincide con el patrón. 
- Palabra clave from  `Keywords_eu_driver's_license_number` o `Keywords_sweden_eu_driver's_license_number` found. 
    
```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- Lic del conductor
- controlador conducción
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- Lic de los drivers
- Controladores conducción
- drivers license
- drivers licenses
- drivers licence
- licencias de conductores
- n.º carné
- n.º carnés
- conducción
- conducción
- n.º carné
- n.º carnés
- Lic del controlador
- controlador de conducción
- licencia del controlador
- licencias de controlador
- permiso de conducción
- licencias de conducir
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- Lic del conductor
- conducción del conductor
- driver's license
- driver's licenses
- driver's licence
- permiso de conducción
- listas #
- distribución #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- Lic del conductor #
- controlador conducción #
- licencia de controlador #
- licencias de controlador #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- Lic de los drivers #
- Controladores conducción #
- licencia de controladores #
- licencias de controladores #
- licencia de conductores #
- licencias de conductores #
- n.º carné #
- n.º carnés #
- conducción #
- conducción #
- n.º carné #
- n.º carnés #
- Lic del controlador #
- controlador de conducción #
- licencia del controlador #
- licencias de controlador #
- permiso de conducción #
- licencias de conducir #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- Lic del conductor #
- conducción del conductor #
- permiso de conducción #
- licencias de conducir #
- permiso de conducción #
- permiso de conducción #
- driving licence 
- driving license
- dlno #
- Lic Cond.
- Cond. licen
- licencia de Cond.
- licencias de Cond.
- licencia de Cond.
- licencias de Cond.
- controlador licen
- Controladores licen
- licen del conductor
- Lic de conducción
- licen de conducción
- licencias de conducción
- driving licence
- driving licences
- permiso de conducción
- Nº DL
- dlno
- número de DL


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver ' s_license_number

- ajokortti
- Perm de conducere
- ajokortin numero
- Lic kuljettajat.
- Lic de controlador.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- Lic förare.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>IDENTIFICACIÓN nacional de Suecia

### <a name="format"></a>Formato

10 o 12 dígitos y un delimitador opcional

### <a name="pattern"></a>Patrón

10 o 12 dígitos y un delimitador opcional:
- dos dígitos (opcionales) 
- Seis dígitos en fecha de formato AAMMDD 
- delimitador de "-" o "+" (opcional)
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función `Func_swedish_national_identifier` busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_swedish_national_identifier`
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función `Func_swedish_national_identifier` busca contenido que coincide con el patrón.
- Se supera la suma de comprobación.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- identificador no
- número de identificador
- identificador #
- n.º de identificación
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- documento de identidad
- n.º de identidad
- número de identidad
- ID-Nummer
- identificador personal
- personnummer #
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>Número de pasaporte de Suecia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial de la UE número de pasaporte y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

ocho dígitos

### <a name="pattern"></a>Patrón

ocho dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- la expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.
- se cumple una de las siguientes condiciones:
    - se encuentra una palabra clave de Keyword_passport.
    - se encuentra una palabra clave de Keyword_sweden_passport.

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

### <a name="keywords"></a>Palabras clave
   
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


## <a name="sweden-tax-identification-number"></a>Número de identificación fiscal de Suecia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

diez dígitos y un símbolo en el patrón especificado
  
### <a name="pattern"></a>Patrón

diez dígitos y un símbolo:
  
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- un signo más o un signo menos
- tres dígitos que hacen que el número de identificación sea único donde: 
  - para los números emitidos antes 1990, el séptimo y el octavo dígito identifican el Condado de nacimiento o las personas que nación en el extranjero
  - el dígito en la novena posición indica el género, ya sea impar o incluso para hembras
- un dígito de control
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_sweden_eu_tax_file_number` . 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_sweden_eu_tax_file_number` busca contenido que coincide con el patrón. 
    
```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- número de identificación personal
- personnummer
- Nummer de identificador de patinaje
- Identifikation de patinaje
- skattebetalarens identifikationsnummer
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

cuatro letras seguidas de 5-31 letras o dígitos

### <a name="pattern"></a>Patrón

cuatro letras seguidas de 5-31 letras o dígitos:
- Código bancario de cuatro letras (no distingue entre mayúsculas y minúsculas) 
- un espacio opcional 
- 4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN)) 
- un espacio opcional 
- una a tres letras o dígitos (el resto del BBAN)

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

### <a name="keywords"></a>Palabras clave
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- rápido #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- BIC #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコード
- SWIFT番号
- BIC番号
- BICコード
- SWIFT コード
- SWIFT 番号
- BIC 番号
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Número AHV de SSN de Suiza
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

número de 13 dígitos

### <a name="pattern"></a>Patrón

número de 13 dígitos:

- tres dígitos-756
- un punto opcional
- cuatro dígitos
- un punto opcional
- cuatro dígitos
- un punto opcional
- dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_swiss_social_security_number_ahv encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keywords_swiss_social_security_number_ahv.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_swiss_social_security_number_ahv encuentra contenido que coincide con el patrón.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- SSN
- pid
- número de seguro
- personalidno #
- social security number
- número de identificación personal
- n.º de identificación personal
- insuranceno #
- uniqueidno #
- n.º de identificación única
- número AVS
- identidad personal no versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- identificador de personnelle de identificación
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Número de identificación nacional de Taiwán

### <a name="format"></a>Formato

una letra (en inglés) seguida de nueve dígitos

### <a name="pattern"></a>Patrón

una letra (en inglés) seguida de nueve dígitos:
- una letra (en inglés, no distingue entre mayúsculas y minúsculas) 
- el dígito "1" o "2" 
- ocho dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwanese_national_id.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

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

- número de pasaporte biométrico: nueve dígitos
- número de pasaporte no biométrico: nueve dígitos

### <a name="pattern"></a>Patrón
número de pasaporte biométrico:
- el carácter "3" 
- ocho dígitos

número de pasaporte no biométrico:
- nueve dígitos

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

### <a name="keywords"></a>Palabras clave

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

diez letras y dígitos

### <a name="pattern"></a>Patrón

diez letras y dígitos:
- dos letras (no distingue entre mayúsculas y minúsculas) 
- ocho dígitos

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

13 dígitos:
- el primer dígito no es ninguno ni nueve 
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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- Número de id.
- Número de identificación
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Número de identificación nacional de Turco

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik no
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>RU número de permiso de conducción
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial del número de licencia de conductor de la UE y está disponible como entidad de tipo independiente de información confidencial.

### <a name="format"></a>Formato

Combinación de 18 letras y dígitos en el formato especificado

### <a name="pattern"></a>Patrón

18 letras y dígitos:
- cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra 
- un dígito 
- cinco dígitos en el formato de fecha MMDDY para la fecha de nacimiento (el séptimo carácter aumenta en 50 si el impulsor es hembra, es decir, 51 a 62 en lugar de 01 a 12)
- dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra 
- cinco dígitos

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

### <a name="keywords"></a>Palabras clave

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

dos letras seguidas de 1-4 dígitos

### <a name="pattern"></a>Patrón

dos letras (no distingue entre mayúsculas y minúsculas) seguidas por números de 1-4

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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>RU número de servicio nacional de salud

### <a name="format"></a>Formato

De 10 a 17 dígitos separados por espacios

### <a name="pattern"></a>Patrón

10-17 dígitos:
- tres o diez dígitos 
- un espacio 
- tres dígitos 
- un espacio 
- cuatro dígitos

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

### <a name="keywords"></a>Palabras clave
   
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

siete caracteres o nueve caracteres separados por espacios o guiones

### <a name="pattern"></a>Patrón

dos patrones posibles:

- dos letras (los NINO válidos usan solo caracteres determinados en este prefijo, que valida este patrón; no distingue entre mayúsculas y minúsculas)
- seis dígitos
- ' A ', ' B ', ' C ' o ' t ' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distingue entre mayúsculas y minúsculas)

O

- dos letras
- un espacio o un guión
- dos dígitos
- un espacio o un guión
- dos dígitos
- un espacio o un guión
- dos dígitos
- un espacio o un guión
- ' A ', ' B ', ' C ' o ' t '

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nino encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_nino.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nino encuentra contenido que coincide con el patrón.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

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
- social security
- great britain
- NI número
- NI no.
- Alec #
- Alec #
- Pensión #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>RU Número de referencia del contribuyente único
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
 
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_uk_eu_tax_file_number` busca contenido que coincide con el patrón. 
- Se encuentra una palabra clave de  `Keywords_uk_eu_tax_file_number` . 
    
```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

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

6-17 dígitos

### <a name="pattern"></a>Patrón

6-17 dígitos consecutivos

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

### <a name="keywords"></a>Palabras clave

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

### <a name="pattern"></a>Patrón

depende del estado (por ejemplo, Nueva York):
- nueve dígitos con formato como DDD DDD DDD coincidirán.
- nueve dígitos, como ddddddddd, no coincidirán.

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

### <a name="keywords"></a>Palabras clave

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

- abreviatura del estado (por ejemplo, "NY") 
- nombre del estado (por ejemplo, "Nueva York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Número de identificación fiscal individual de Estados Unidos (ÉLEN)

### <a name="format"></a>Formato

nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como el cuarto dígito, opcionalmente con formato de espacios o guiones

### <a name="pattern"></a>Patrón

con formato
- el dígito "9" 
- dos dígitos 
- un espacio o un guión 
- un "7" u "8" 
- un dígito 
- un espacio o guión 
- cuatro dígitos

sin formato
- el dígito "9" 
- dos dígitos 
- un "7" u "8" 
- cinco dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_formatted_itin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_itin.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_unformatted_itin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_itin.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_formatted_itin o Func_unformatted_itin busca contenido que coincide con el patrón.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_itin"></a>Keyword_itin

- contribuyente 
- tax id 
- tax identification 
- élen 
- i.t.i.n.
- SSN 
- / 
- social security 
- tax payer 
- itins 
- taxi 
- individual taxpayer 


## <a name="us-social-security-number-ssn"></a>Número de la seguridad social de Estados Unidos (SSN)

### <a name="format"></a>Formato

nueve dígitos, que pueden estar en un patrón con o sin formato

> [!NOTE]
> Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).

### <a name="pattern"></a>Patrón

cuatro funciones buscan SSN en cuatro patrones diferentes:
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

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_ssn"></a>Keyword_ssn

- Número de SSA
- social security number
- seguridad social #
- seguridad social #
- n.º de seguridad social
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

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos consecutivos

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

### <a name="keywords"></a>Palabras clave

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

## <a name="ukraine-passport-domestic"></a>País de pasaporte de Ucrania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- El Regex_Ukraine_Passport_Domestic regex busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Ukraine_Passport_Domestic.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- pasaporte de Ucrania
- passport number
- n.º de pasaporte
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Internacional Ucrania Passport
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- Gobierno de la información
- administración de registros
- Microsoft Cloud App Security

### <a name="format"></a>Formato

modelo alfanumérico de ocho caracteres

### <a name="pattern"></a>Patrón

modelo alfanumérico de ocho caracteres:
- dos letras o dígitos
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- El Regex_Ukraine_Passport_International regex busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Ukraine_Passport_International.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- pasaporte de Ucrania
- passport number
- n.º de pasaporte
- паспорт України
- номер паспорта
