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
description: La prevención de pérdida de datos (DLP) en el Centro de cumplimiento de seguridad incluye 80 tipos de información confidencial listos para su uso &amp; en las directivas DLP. En este artículo se enumeran todos estos tipos de información confidencial y se muestra lo que busca una directiva DLP cuando detecta cada tipo.
ms.openlocfilehash: 431349ffdfc1a9aa05d071ec5ef10d76919f7465
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094750"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definiciones de entidad de tipos de información confidencial

La prevención de pérdida de datos (DLP) en el Centro de cumplimiento incluye muchos tipos de información confidencial que están listos para usarse en las directivas DLP. En este artículo se enumeran todos estos tipos de información confidencial y se muestra lo que busca una directiva DLP cuando detecta cada tipo. Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función. Las evidencias corroborativas, como palabras clave y sumas de comprobación, se pueden usar para identificar un tipo de información confidencial. El nivel de confianza y la proximidad también se usan en el proceso de evaluación.

Los tipos de información confidencial requieren una de estas suscripciones:
- Microsoft 365 E3
- Microsoft 365 E5

Los tipos de información confidencial se usan en:

- [Directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) 
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](retention.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="aba-routing-number"></a>Número de enrutamiento ABA

### <a name="format"></a>Formato

nueve dígitos que pueden estar en un patrón con formato o sin formato

### <a name="pattern"></a>Patrón

Con formato:
- cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8
- un guión
- cuatro dígitos
- un guión
- un dígito

Sin formato: nueve dígitos consecutivos que comienzan por 0, 1, 2, 3, 6, 7 u 8 

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_aba_routing encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ABA_Routing.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- enrutamiento #
- routing no
- número de enrutamiento
- routing transit number
- enrutamiento #
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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- dni 
- documento nacional de identidad 
- documento número 
- documento numero 
- registro nacional de las personas 
- rnp 
   
## <a name="australia-bank-account-number"></a>Número de cuenta bancaria de Australia

### <a name="format"></a>Formato

de seis a diez dígitos con o sin un número de sucursal de estado bancario

### <a name="pattern"></a>Patrón

El número de cuenta es de 6 a 10 dígitos.

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
- iaea

## <a name="australia-business-number"></a>Número comercial de Australia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft


### <a name="format"></a>Formato

11 dígitos con delimitadores opcionales

### <a name="pattern"></a>Patrón

11 dígitos con delimitadores opcionales:

- dos dígitos
- un espacio o un guión opcional
- tres dígitos
- un espacio o un guión opcional
- tres dígitos
- un espacio o un guión opcional
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_australian_business_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_australian_business_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- australia business no
- número de negocio
- abn #
- businessid #
- id. de negocio
- abn
- businessno #

## <a name="australia-company-number"></a>Número de empresa de Australia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_Australian_Company_Number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Australian_Company_Number búsqueda.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- can
- australia company no
- australia company no #
- número de empresa de Australia
- australian company no
- australian company no #
- número de compañía australiana

## <a name="australia-drivers-license-number"></a>Número de licencia de conductor de Australia

### <a name="format"></a>Formato

nueve letras y dígitos

### <a name="pattern"></a>Patrón

nueve letras y dígitos: 

- dos dígitos o letras (no distinguen mayúsculas de minúsculas) 
- dos dígitos 
- cinco dígitos o letras (no distingue entre mayúsculas y minúsculas)

OR

- de una a dos letras opcionales (no distingue entre mayúsculas y minúsculas) 
- de cuatro a nueve dígitos

OR

- nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
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
- Driver'Lic #
- Driver'Lics #
- Driver'Licence #
- Driver'Licences #
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

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'License
- Driver'Licenses
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
- Driver'License #
- Driver'Licenses #
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
- El primer dígito está en el intervalo de 2 a 6
- El no.9 dígito es un dígito de comprobación
- El 10 dígito es el dígito de emisión
- El undécimo dígito (opcional) es el número individual

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- dalo

   
## <a name="australia-passport-number"></a>Número de pasaporte de Australia

### <a name="format"></a>Formato

Una letra seguida de siete dígitos

### <a name="pattern"></a>Patrón

Una letra (sin distingue mayúsculas de minúsculas) seguida de siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_passport o Keyword_australia_passport_number búsqueda.

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
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- (en la ポ)
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passport
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- visa
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>Número de archivo fiscal de Australia

### <a name="format"></a>Formato

de ocho a nueve dígitos

### <a name="pattern"></a>Patrón

de ocho a nueve dígitos que normalmente se presentan con espacios de la siguiente manera:
- tres dígitos 
- un espacio opcional 
- tres dígitos 
- un espacio opcional 
- de dos a tres dígitos donde el último dígito es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- tfn

## <a name="austria-drivers-license-number"></a>Número de licencia de conducción de Austria

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_austria_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_austria_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver de s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Tarjeta de identidad de Austria
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Una combinación de 24 caracteres de letras, dígitos y caracteres especiales
  
### <a name="pattern"></a>Patrón

24 caracteres:
  
-  22 letras (no distingue entre mayúsculas y minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más 
    
- dos letras (no distinguen mayúsculas de minúsculas), dígitos, barras diagonales inversas, barras diagonales, signos más o signos iguales
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_austria_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_austria_eu_national_id_card` clave de. 
   
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
- personalauslichs republik österreich

## <a name="austria-passport-number"></a>Número de pasaporte de Austria

### <a name="format"></a>Formato

Una letra seguida de un espacio opcional y siete dígitos
  
### <a name="pattern"></a>Patrón

Una combinación de una letra, siete dígitos y un espacio:
  
- una letra (no distingue mayúsculas de minúsculas)
- un espacio (opcional)
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_austria_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_austria_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_austria_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_austria_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
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
- un dígito de comprobación
- seis dígitos que corresponden a la fecha de nacimiento (DDMMYY)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
- se encuentra una  `Keywords_austria_eu_ssn_or_equivalent` palabra clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
    
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

- ssn de indeste
- número ehic
- ehic no
- código de seguros
- insurancecode #
- número de seguro
- insurance no
- krankenkassennummer
- krankenversrique
- socialsecurityno
- socialsecurityno #
- social security no
- social security number
- social security code
- sozialversálisissnummer
- sozialversálisissnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versiquemutscode
- versálisissnummer
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_austria_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_austria_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- número de impuestos
 
## <a name="austria-value-added-tax"></a>Austria value added tax
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón alfanumérico de 11 caracteres

### <a name="pattern"></a>Patrón

Patrón alfanumérico de 11 caracteres:

- A o a
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_Austria_Value_Added_Tax encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Austria_Value_Added_Tax búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- número de iva
- vat #
- número de iva de indeste
- vat no.
- vatno #
- número de impuestos del valor agregado
- iva de resa lodo
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- número de identificación de iva
- número atu
- número uid


## <a name="azure-documentdb-auth-key"></a>Clave de autenticación de Azure DocumentDB

### <a name="format"></a>Formato

La cadena "DocumentDb" seguida de los caracteres y cadenas descritos en el siguiente patrón.

### <a name="pattern"></a>Patrón

- La cadena "DocumentDb"
- Cualquier combinación de entre 3 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- Un símbolo mayor que (>), un signo igual (=), una comilla (") o un apóstrofe (')
- Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- Dos signos iguales (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureDocumentDBAuthKey encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.

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

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Cadena de conexión de base de datos IAAS de Azure y cadena de conexión SQL azure

### <a name="format"></a>Formato

La cadena "Server", "server" o "data source" seguida de los caracteres y cadenas descritos en el patrón siguiente, incluida la cadena "cloudapp.azure.<!--no-hyperlink-->com" o "cloudapp.azure.<!--no-hyperlink-->net" o "database.windows.<!--no-hyperlink-->net" y la cadena "Password" o "password" o "pwd".

### <a name="pattern"></a>Patrón

- la cadena "Server", "server" o "data source"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- La cadena "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net" o "database.windows.<!--no-hyperlink-->net"
- cualquier combinación de entre 1 y 300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "Password", "password" o "pwd"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- uno o más caracteres que no son un punto y coma (;), comillas (") o apóstrofe (')
- punto y coma (;), comillas (") o apóstrofe (')

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureConnectionString encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.

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

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Cadena de conexión de Azure IoT

### <a name="format"></a>Formato

La cadena "HostName" seguida de los caracteres y cadenas descritos en el siguiente patrón, incluidas las cadenas "azure-devices.<!--no-hyperlink-->net" y "SharedAccessKey".

### <a name="pattern"></a>Patrón

- la cadena "HostName"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "azure-devices.<!--no-hyperlink-->net"
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "SharedAccessKey"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de 43 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- un signo igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureIoTConnectionString encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.

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

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Contraseña de configuración de publicación de Azure

### <a name="format"></a>Formato

Cadena "userpwd=" seguida de una cadena alfanumérica.

### <a name="pattern"></a>Patrón

- la cadena "userpwd="
- cualquier combinación de 60 letras minúsculas o dígitos
- comillas (")

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzurePublishSettingPasswords encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.


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

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Cadena de conexión de caché redis de Azure

### <a name="format"></a>Formato

La cadena "redis.cache.windows.<!--no-hyperlink-->net" seguido de los caracteres y cadenas descritos en el siguiente patrón, incluida la cadena "password" o "pwd".

### <a name="pattern"></a>Patrón

- la cadena "redis.cache.windows.<!--no-hyperlink-->net"
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "password" o "pwd"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de 43 caracteres con letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- un signo igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureRedisCacheConnectionString encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.

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

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Formato

La cadena "sig" seguida de los caracteres y cadenas descritos en el siguiente patrón.

### <a name="pattern"></a>Patrón

- la cadena "sig"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de entre 43 y 53 caracteres con letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)
- la cadena "%3d"
- cualquier carácter que no sea una letra, dígito o signo de porcentaje en minúsculas o mayúsculas (%)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureSAS encuentra contenido que coincide con el patrón.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Cadena de conexión de bus de servicio de Azure

### <a name="format"></a>Formato

La cadena "EndPoint" seguida de los caracteres y cadenas descritos en el siguiente patrón, incluidas las cadenas "servicebus.windows.<!--no-hyperlink-->net" y "SharedAccesKey".

### <a name="pattern"></a>Patrón

- la cadena "EndPoint"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "servicebus.windows.<!--no-hyperlink-->net"
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "SharedAccessKey"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de 43 caracteres con letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- un signo igual (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureServiceBusConnectionString encuentra contenido que coincide con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.

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

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Clave de cuenta de Azure Storage

### <a name="format"></a>Formato

La cadena "DefaultEndpointsProtocol" seguida de los caracteres y cadenas descritos en el siguiente patrón, incluida la cadena "AccountKey".

### <a name="pattern"></a>Patrón

- la cadena "DefaultEndpointsProtocol"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "AccountKey"
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de 86 caracteres con letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- dos signos iguales (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureStorageAccountKey encuentra contenido que coincide con el patrón.
- La expresión regular CEP_AzureEmulatorStorageAccountFilter no encuentra contenido que coincida con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.

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

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Clave de cuenta de Azure Storage (genérica)

### <a name="format"></a>Formato

Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o signo más (+), precedida o seguida de los caracteres descritos en el patrón siguiente.

### <a name="pattern"></a>Patrón

- de cero a uno del símbolo mayor que (>), apóstrofe ('), signo igual (=), comillas (") o signo de número (#)
- cualquier combinación de 86 caracteres con letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- dos signos iguales (=)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_AzureStorageAccountKeyGeneric encuentra contenido que coincide con el patrón.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Número de licencia de conductor de Bélgica

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_belgium_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_belgium_eu_driver's_license_number` clave.
    
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


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver de s_license_number

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
- numéro permis conduire


## <a name="belgium-national-number"></a>Número nacional de Bélgica

### <a name="format"></a>Formato

11 dígitos más delimitadores opcionales

### <a name="pattern"></a>Patrón

11 dígitos más delimitadores:
- seis dígitos y dos puntos opcionales en el formato AA. MM.DD fecha de nacimiento 
- Delimitador opcional de punto, guión, espacio 
- tres dígitos secuenciales (impares para hombres, incluso para mujer) 
- Delimitador opcional de punto, guión, espacio 
- dos dígitos de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_belgium_national_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_belgium_national_number.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- identificación
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identity
- indeste
- número nacional
- registro nacional
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- número de identificación personal
- personalausweis
- personalidnumber #
- registratie
- registration
- registrationsnumme
- registros
- social security number
- ssn #
- ssn
- steuernummer
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="belgium-passport-number"></a>Número de pasaporte de Bélgica

### <a name="format"></a>Formato

dos letras seguidas de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

dos letras y seguidas de seis dígitos
  
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

 Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_belgium_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_belgium_eu_passport_number` clave. 
- La expresión regular `Regex_eu_passport_date2` encuentra la fecha con el formato DD MM AA o una palabra clave de o se `Keywords_eu_passport_date` `Keywords_belgium_eu_passport_number` encuentra

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_belgium_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_belgium_eu_passport_number` clave. 

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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport trasporte
- Pass-Nr
- Passnummer
- reisepass kein


## <a name="belgium-value-added-tax-number"></a>Número de impuestos sobre el valor agregado de Bélgica
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón alfanumérico de 12 caracteres

### <a name="pattern"></a>Patrón

Patrón alfanumérico de 12 caracteres:

- una letra B o b
- una letra E o e
- un dígito 0
- un dígito del 1 al 9
- un punto opcional, un guión o un espacio
- cuatro dígitos
- un punto opcional, un guión o un espacio
- cuatro dígitos


### <a name="checksum"></a>Suma de comprobación

Sí


### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_belgium_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_belgium_value_added_tax_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- nº tva
- número de iva
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>Número CPF de Brasil

### <a name="format"></a>Formato

11 dígitos incluido un dígito de control y que pueden tener o no formato

### <a name="pattern"></a>Patrón

Con formato:
- tres dígitos
- un punto
- tres dígitos
- un punto
- tres dígitos
- un guión
- dos dígitos que son dígitos de comprobación

Sin formato:
- 11 dígitos, donde los dos últimos dígitos son dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_brazil_cpf encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_cpf.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Identificación
- Registro
- Ingresos
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
- tres dígitos (estos primeros ocho dígitos son el número de registro) 
- una barra diagonal 
- número de rama de cuatro dígitos 
- un guión 
- dos dígitos que son dígitos de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_cnpj.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

Registro Geral (formato antiguo): Nueve dígitos

Registro de Identidade (RIC) (nuevo formato): 11 dígitos

### <a name="pattern"></a>Patrón

Registro de Geral (formato antiguo):
- dos dígitos 
- un punto 
- tres dígitos 
- un punto 
- tres dígitos 
- un guión 
- un dígito que es un dígito de comprobación

Registro de Identidade (RIC) (nuevo formato):
- 10 dígitos 
- un guión 
- un dígito que es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_brazil_rg encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_rg.
- Se supera la suma de comprobación.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
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
- RG (esta palabra clave distingue mayúsculas de minúsculas) 
- RIC (esta palabra clave distingue mayúsculas de minúsculas) 


## <a name="bulgaria-drivers-license-number"></a>Número de licencia de conductor de Bulgaria

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_bulgaria_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_bulgaria_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver de s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Número civil uniforme de Bulgaria
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos sin espacios y delimitadores
  
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- dos dígitos que corresponden al orden de nacimiento
- un dígito que corresponde al género: un dígito par para el varón y un dígito impar para la mujer
- un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_bulgaria_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_bulgaria_eu_national_id_card` clave de. 

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_bulgaria_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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
- indeste #
- indeste
- edinenhdanski nomer
- egn #
- egn
- identification number
- national id
- número nacional
- nationalnumber #
- nationalnumber
- id. personal
- personal no
- número personal
- personalidnumber #
- social security number
- ssn #
- ssn
- identificador civil uniforme
- uniform civil no
- número civil uniforme
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- número de ciudadano único
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ граждански id
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_bulgaria_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_bulgaria_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_bulgaria_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_bulgaria_eu_passport_number` clave. 

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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración

## <a name="canada-bank-account-number"></a>Número de cuenta bancaria de Canadá

### <a name="format"></a>Formato

7 o 12 dígitos

### <a name="pattern"></a>Patrón

Un número de cuenta bancaria de Canadá tiene 7 o 12 dígitos.

Un número de tránsito de cuenta bancaria de Canadá es:
- cinco dígitos 
- un guión 
- tres dígitos O
- un cero "0" 
- ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_bank_account_number.
- La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

   
## <a name="canada-drivers-license-number"></a>Número de licencia de conductor de Canadá

### <a name="format"></a>Formato

Varía según la provincia

### <a name="pattern"></a>Patrón

Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- La abreviatura de la provincia, por ejemplo, AB
- El nombre de la provincia, por ejemplo, Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
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
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
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
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- identificación 
- DL #
- DLS # 
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
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver'Licence # 
- Driver'Licences # 
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
- id # 
- ids # 
- idcard card# 
- idcard cards# 
- idcard # 
- identification card# 
- identification cards# 
- identificación # 

   
## <a name="canada-health-service-number"></a>Número de servicio de salud de Canadá

### <a name="format"></a>Formato

 10 dígitos

### <a name="pattern"></a>Patrón

10 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- desatraba
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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_canada_passport_number o Keyword_passport búsqueda.

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
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- (en la ポ)
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>Número de identificación personal de salud de Canadá (PHIN)

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_phin encuentra contenido que coincide con el patrón.
- Se encuentran al menos dos palabras clave Keyword_canada_phin o Keyword_canada_provinces búsqueda.

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
- Toronto
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

   
## <a name="canada-social-insurance-number"></a>Número de seguro social de Canadá

### <a name="format"></a>Formato

nueve dígitos con guiones o espacios opcionales

### <a name="pattern"></a>Patrón

Con formato:
- tres dígitos 
- un guión o espacio 
- tres dígitos 
- un guión o espacio 
- tres dígitos

Sin formato: nueve dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_canadian_sin encuentra contenido que coincide con el patrón.
- Al menos dos de cualquier combinación de lo siguiente:
    - Se encuentra una palabra clave de Keyword_sin.
    - Se encuentra una palabra clave de Keyword_sin_collaborative.
    - La función Func_eu_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- sins 
- ssn 
- ssns 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- sin # 
- soc ins 
- social ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- Fecha de nacimiento 
- Birthday 
- Fecha de nacimiento 

   
## <a name="chile-identity-card-number"></a>Número de tarjeta de identidad de Chile

### <a name="format"></a>Formato

siete a ocho dígitos más delimitadores de un dígito de comprobación o una letra

### <a name="pattern"></a>Patrón

de siete a ocho dígitos más delimitadores:
- de uno a dos dígitos 
- un período opcional 
- tres dígitos 
- un período opcional 
- tres dígitos 
- un guión 
- un dígito o letra (no distingue entre mayúsculas y minúsculas), que es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_chile_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_chile_id_card.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único resalte
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Contemple
- RUN #
- RUT #
- nationaluniqueroleID #
- identidad nacional
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Identidad de chileno no.
- Número de identidad de chileno
- Identidad de chilena #
- Registro de impuestos único
- Rol único de reeste
- Rol fiscal único
- Número de reeste único
- Número nacional único
- Rol nacional único
- Rol único nacional
- Chile identity no.
- Número de identidad de Chile
- Identidad de Chile #

   
## <a name="china-resident-identity-card-prc-number"></a>Número de tarjeta de identidad residente (PRC) de China

### <a name="format"></a>Formato

18 dígitos

### <a name="pattern"></a>Patrón

18 dígitos:
- seis dígitos que son un código de dirección 
- ocho dígitos con el formato YYYYMMDD, que son la fecha de nacimiento 
- tres dígitos que son un código de pedido 
- un dígito que es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_china_resident_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_china_resident_id.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- PRC 
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

De 14 a 16 dígitos que pueden tener formato o sin formato (dddddddd) y que deben superar la prueba de Luhn.

### <a name="pattern"></a>Patrón

Patrón complejo y sólido que detecta tarjetas de todas las principales marcas de todo el mundo, incluidas Visa, MasterCard, Discover Card, JCB, American Express, tarjetas de obsequios y tarjetas de carta.

### <a name="checksum"></a>Suma de comprobación

Sí, la suma de comprobación de Luhn

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_credit_card encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_cc_verification.
    - Se encuentra una palabra clave de Keyword_cc_name.
    - La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- cod. seguranca
- cod. segurança
- cód. seguranca
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
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- transaction
- número de transacción
- número de referencia
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso
- Visa
- y ahora
- master card
- mc
- y ahora
- master cards
- diner's Club
- diners club
- restaurantsclub
- discover
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carte cartehe
- credit card
- cc #
- cc#:
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
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- cardholder
- card holders
- cardholders
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
- enroute
- en route
- card type
- Cardmember Acct
- cuenta cardmember
- Cardno
- Tarjeta corporativa
- Tarjetas corporativas
- Tipo de tarjeta
- número de cuenta de tarjeta
- cuenta de miembro de tarjeta
- Cardmember Acct.
- card no.
- tarjeta no
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
- karteniriber
- karteniribers
- kreditkarteniriber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
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
- tarjetacabiente
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
- nº. do cartão
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
- Visa que se ha desatricido
- Visa
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


## <a name="croatia-drivers-license-number"></a>Número de licencia de conductor de Croacia

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_croatia_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_croatia_eu_driver's_license_number` clave. 

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver de s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Número de tarjeta de identidad de Croacia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de identificación nacional de la UE. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- alojarstorski broj građana
- número de ciudadano maestro
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="croatia-passport-number"></a>Número de pasaporte de Croacia

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_croatia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_croatia_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_croatia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_croatia_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
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
- 10 dígitos 
- dígito final es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_croatia_eu_tax_file_number búsqueda.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- alojarstorski broj građana
- número de ciudadano maestro
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="croatia-social-security-number-or-equivalent-identification"></a>Número de seguridad social de Croacia o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial Número de la Seguridad Social de la UE o Identificador equivalente.

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- 10 dígitos
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_croatia_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_croatia_eu_ssn_or_equivalent` clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
  
- La función  `Func_croatia_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- número de identificación personal
- número de ciudadano maestro
- national identification number
- social security number
- nationalnumber #
- ssn #
- ssn
- nationalnumber
- bnn #
- bnn
- número de identificación personal
- personalidnumber #
- oib
- osobni identifikacijski broj

## <a name="cyprus-drivers-license-number"></a>Número de licencia de controladores de Chipre

### <a name="format"></a>Formato

12 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

12 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_cyprus_eu_driver's_license_number` clave.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver de s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Tarjeta de identidad de Chipre
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos 
  
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_cyprus_eu_national_id_card` clave de. 
    
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

- id card number
- número de tarjeta de identidad
- kimlik karti
- national identification number
- número de identificación personal
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Número de pasaporte de Chipre

### <a name="format"></a>Formato

una letra seguida de 6 a 8 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una letra seguida de seis a ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_cyprus_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el formato `Regex_cyprus_eu_passport_date` DD/MM/YYYY o se encuentra una palabra clave de `Keywords_cyprus_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_cyprus_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_cyprus_eu_passport_number` clave.  
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
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
- pasaport nuujsı
- Pasaporte no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- expira en
- emitido en


## <a name="cyprus-tax-identification-number"></a>Número de identificación fiscal de Chipre
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

ocho dígitos y una letra en el patrón especificado
  
### <a name="pattern"></a>Patrón

ocho dígitos y una letra:
  
- "0" o "9"
- siete dígitos
- una letra (no distingue mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_cyprus_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_cyprus_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_cyprus_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- código de identificación fiscal
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- tin id
- tin no
- tin #
- vergi kimlik kodu
- vergi kimlik nuanessı
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Número de licencia de conductor checo

### <a name="format"></a>Formato

dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

ocho letras y dígitos:
  
- letra 'E' (no distingue mayúsculas de minúsculas)
- una carta
- un espacio (opcional)
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_czech_republic_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_czech_republic_eu_driver's_license_number` clave. 

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver de s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>Número de pasaporte checo

### <a name="format"></a>Formato

ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos sin espacios ni delimitadores
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_czech_republic_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_czech_republic_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_czech_republic_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_czech_republic_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="czech-personal-identity-number"></a>Número de identidad personal checo

### <a name="format"></a>Formato

nueve dígitos con barra diagonal opcional (formato antiguo) 10 dígitos con barra diagonal opcional (nuevo formato)

### <a name="pattern"></a>Patrón

nueve dígitos (formato antiguo):
- seis dígitos que representan la fecha de nacimiento
- una barra diagonal opcional
- tres dígitos

10 dígitos (nuevo formato):
- seis dígitos que representan la fecha de nacimiento
- una barra diagonal opcional 
- cuatro dígitos donde el último dígito es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:

- La función Func_czech_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_czech_id_card.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:

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
- identificador de república checa
- czechidno #
- daňové číslo
- identifikační číslo
- identity no
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
- pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- social security number
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- número de identificación único

## <a name="czech-social-security-number-or-equivalent-identification"></a>Número de la seguridad social checa o identificación equivalente

Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial Número de la Seguridad Social de la UE o Identificador equivalente.

### <a name="format"></a>Formato

10 dígitos y una barra diagonal inversa en el patrón especificado
  
### <a name="pattern"></a>Patrón

10 dígitos y una barra diagonal inversa:
  
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD): 
- una barra diagonal inversa
- tres dígitos que corresponden a un número de serie que separa a las personas que han nado en la misma fecha
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_czech_republic_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_czech_republic_eu_ssn_or_equivalent` clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_czech_republic_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 

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

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- número de nacimiento
- national identification number
- número de identificación personal
- social security number
- nationalnumber #
- ssn #
- ssn
- número nacional
- número de identificación personal
- personalidnumber #
- rč
- rodné číslo
- rodne cislo

## <a name="denmark-drivers-license-number"></a>Número de licencia de conductor de Dinamarca

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_denmark_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_denmark_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver de s_license_number

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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_denmark_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_denmark_eu_passport_number` clave. 
- La expresión regular `Regex_eu_passport_date2` encuentra la fecha con el formato DD MM AA o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_denmark_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_denmark_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="denmark-personal-identification-number"></a>Número de identificación personal de Dinamarca

### <a name="format"></a>Formato

10 dígitos que contienen un guión

### <a name="pattern"></a>Patrón

10 dígitos:
- seis dígitos en el formato DDMMYY, que son la fecha de nacimiento 
- un guión 
- cuatro dígitos donde el dígito final es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Func_denmark_eu_tax_file_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_denmark_id.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- civilt registreringssystem
- cpr
- cpr #
- geheiheitskarte nummer
- geheiheitsverskarkarte nummer
- tarjeta de estado
- número de la tarjeta del seguro de salud
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
- reise krankenversálisisskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- skat id
- skat kode
- skat nummer
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- código fiscal
- tarjeta de seguro de salud de viajes
- uniqueidentityno #
- número de impuestos
- número de registro de impuestos
- tax id
- número de identificación fiscal
- y ahora #
- taxnumber #
- tax no
- taxno #
- taxnumber
- identificación fiscal no
- tin #
- y ahora #
- numeración #
- tax no #
- tin id
- tin no
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

## <a name="denmark-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Dinamarca o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible el tipo de información confidencial Número de la Seguridad Social de la UE o Identificador equivalente.

### <a name="format"></a>Formato

10 dígitos y un guión en el patrón especificado
  
### <a name="pattern"></a>Patrón

10 dígitos y un guión:
  
- seis dígitos que corresponden a la fecha de nacimiento (DDMMYY) 
- un guión
- cuatro dígitos que corresponden a un número de secuencia

### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_denmark_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_denmark_eu_ssn_or_equivalent` clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_denmark_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- número de identificación personal
- national identification number
- social security number
- nationalnumber #
- ssn #
- ssn
- número nacional
- número de identificación personal
- personalidnumber #
- cpr-nummer
- personnummer

## <a name="drug-enforcement-agency-dea-number"></a>Número de la Agencia Antidrogas (DEA)

### <a name="format"></a>Formato

dos letras seguidas de siete dígitos

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- una letra (no distingue mayúsculas de minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de registrador 
- una letra (no distingue mayúsculas de minúsculas), que es la primera letra del apellido o dígito "9" del registrador.
- siete dígitos, el último de los cuales es el dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_dea_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra `Keyword_dea_number` clave de
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- dea
- dea #
- administración de la aplicación de la ley antidrogas
- agencia antidrogas


## <a name="estonia-drivers-license-number"></a>Número de licencia de conductor de Estonia

### <a name="format"></a>Formato

dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

dos letras y seis dígitos:
  
- las letras "ET" (no distingue entre mayúsculas y minúsculas) 
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_estonia_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_estonia_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver de s_license_number

-- permis de conduire
- juhilrovde desenlacerid
- número de juhiloa
- juhilrov


## <a name="estonia-personal-identification-code"></a>Código de identificación personal de Estonia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- un dígito que corresponde al sexo y al siglo de nacimiento (número impar varón, número par femenil; 1-2: 19 del s. 19; 3-4: 20 del s. XX; 5-6: s. 21)
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
- tres dígitos que corresponden a un número de serie que separa a las personas que han nado en la misma fecha
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_estonia_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_estonia_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_estonia_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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

- id-kaart
- ik
- isikukood #
- isikukood
- maksu id
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
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="estonia-passport-number"></a>Número de pasaporte de Estonia

### <a name="format"></a>Formato

una letra seguida de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una letra seguida de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_estonia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_estonia_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_estonia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_estonia_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="eu-debit-card-number"></a>Número de tarjeta de débito de la UE

### <a name="format"></a>Formato

16 dígitos

### <a name="pattern"></a>Patrón

Patrón complejo y sólido

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- cc # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- americanexpress 
- americano espresso 
- amex 
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
- cardholder 
- cardholders 
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
- carte cartehe 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- check card 
- check cards 
- checkcard
- checkcards 
- chequekaart 
- cirrus 
- cirrus-edc-maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- creditcard 
- creditcards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- debitcard 
- debitcards 
- debito automatico 
- diners club 
- restaurantsclub 
- discover 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- karteniriber 
- karteniribers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteniriber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- maestro 
- master card 
- master cards 
- y ahora 
- y ahora 
- mc 
- mister cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- No. de tarjeta 
- No. do cartao 
- No. do cartão 
- nr carta 
- nr. carta 
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
- nº. do cartão 
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
- switch 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- tarjetacabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-pay 
- visa 
- visa plus 
- visa electron 
- visto 
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
- cod. seg 
- cod. seguranca 
- cod. segurança 
- cod. sicurezza 
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
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. segurança 
- código 
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
- expiration 
- expire 
- expira 
- expiry 
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
- valor 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 


## <a name="eu-drivers-license-number"></a>Número de licencia de conductor de la UE

Estas entidades se encuentran en el número de licencia de conductor de la UE y son tipos de información confidencial.

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
- [Reino Unido](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Número de identificación nacional de la UE

Estas entidades están en el número de identificación nacional de la UE y son tipos de información confidencial.

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
- [Reino Unido](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>Número de pasaporte de la UE 

Estas entidades están en el número de pasaporte de la UE y son tipos de información confidencial. Estas entidades están en el lote de números de pasaporte de la UE.

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
- [Reino Unido](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de la UE o identificación equivalente

Estas entidades que se encuentran en el número de la Seguridad Social de la UE o en una identificación equivalente y son tipos de información confidencial.

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

Estas entidades se encuentran en el tipo de información confidencial del número de identificación fiscal de la UE.

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
- [Reino Unido](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Número de licencia de conductor de Finlandia

### <a name="format"></a>Formato

10 dígitos que contienen un guión
  
### <a name="pattern"></a>Patrón

10 dígitos que contienen un guión:
  
- seis dígitos 
- un guión
- tres dígitos 
- un dígito o una letra
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_finland_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_finland_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver de s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Número de seguro médico europeo de Finlandia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Número de 20 dígitos

### <a name="pattern"></a>Patrón

Número de 20 dígitos:

- 10 dígitos - 8024680246
- un espacio opcional o un guión
- 10 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- El elemento regex Regex_Finland_European_Health_Insurance_Number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Finland_European_Health_Insurance_Number búsqueda.

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
- finska bootukförsäkringskort
- tarjeta de estado
- tarjeta de seguro de salud
- número de seguro de salud
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- bootukförsäkring nummer
- bootukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>Identificación nacional de Finlandia

### <a name="format"></a>Formato

seis dígitos más un carácter que indica un siglo más tres dígitos más un dígito de comprobación

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- seis dígitos en el formato DDMMYY, que son una fecha de nacimiento 
- marcador de century (ya sea '-', '+' o 'a') 
- número de identificación personal de tres dígitos 
- un dígito o una letra (no se puede tener en cuenta mayúsculas de minúsculas) que es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- la función Func_finnish_national_id encuentra contenido que coincide con el patrón
- se encuentra una palabra clave Keyword_finnish_national_id búsqueda
- la suma de comprobación pasa

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- id number
- identification number
- identiteetti numero
- número de identidad
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- tarjeta de identificación nacional
- national id no.
- id. personal
- código de identidad personal
- personalidnumber #
- personbetckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- tutensiónstenumero
- tunnus numero
- tunnuslálisis
- tunnusnumero
- vertitartti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Número de pasaporte de Finlandia

Esta entidad de tipo de información confidencial está disponible en el tipo de información confidencial Número de pasaporte de la UE y está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato
combinación de nueve letras y dígitos

### <a name="pattern"></a>Patrón
combinación de nueve letras y dígitos:
- dos letras (no distingue entre mayúsculas y minúsculas) 
- siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_finland_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_eu_passport_number_common o Keyword_finland_passport_number búsqueda.

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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- número passi


## <a name="france-drivers-license-number"></a>Número de licencia de conductor de Francia

Esta entidad de tipo de información confidencial está disponible en el tipo de información confidencial Número de licencia de conductor de la UE y está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos con validación para descontar patrones similares como los números de teléfono franceses

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- la función Func_french_drivers_license encuentra contenido que coincide con el patrón.
- se encuentra una palabra clave Keyword_french_drivers_license búsqueda.

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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>Número de seguro de salud de Francia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Número de 21 dígitos

### <a name="pattern"></a>Patrón

Número de 21 dígitos:

- 10 dígitos
- un espacio opcional
- 10 dígitos
- un espacio opcional
- un dígito


### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- el elemento regex Regex_France_Health_Insurance_Number encuentra contenido que coincide con el patrón.
- se encuentra una palabra clave Keyword_France_Health_Insurance_Number búsqueda.

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

- insurance card
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>Tarjeta de identificación nacional de Francia (CNI)

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_france_eu_national_id_card búsqueda.

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
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- national identification number
- identidad nacional
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale

   
## <a name="france-passport-number"></a>Número de pasaporte de Francia
Esta entidad de tipo de información confidencial está disponible en el tipo de información confidencial Número de pasaporte de la UE. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

nueve dígitos y letras

### <a name="pattern"></a>Patrón

nueve dígitos y letras:
- dos dígitos 
- dos letras (no distingue entre mayúsculas y minúsculas) 
- cinco dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- (en la ポ)
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Número de la seguridad social de Francia (INSEE) o identificación equivalente
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de la Seguridad Social de la UE y Identificador equivalente. Está disponible como una entidad independiente de tipo de información confidencial.

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
- La función Func_french_insee o Func_fr_insee encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_fr_insee.
- Se supera la suma de comprobación.

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_french_insee o Func_fr_insee encuentra contenido que coincide con el patrón.
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

- insee
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
- Un dígito
- Un espacio (opcional) 
- Dos dígitos 
- Un espacio (opcional) 
- Tres dígitos 
- Un espacio (opcional) 
- Tres dígitos 
- Un espacio (opcional) 
- Tres dígitos de comprobación 

  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_france_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_france_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_france_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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

- numéro d'identification fiscale
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>Número de impuestos del valor agregado de Francia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón alfanumérico de 13 caracteres

### <a name="pattern"></a>Patrón

Patrón alfanumérico de 13 caracteres:

- dos letras: FR (no se puede hacer mayúsculas de minúsculas)
- un espacio opcional o un guión
- dos letras o dígitos
- un espacio opcional, punto, guión o coma
- tres dígitos
- un espacio opcional, punto, guión o coma
- tres dígitos
- un espacio opcional, punto, guión o coma
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_france_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_france_value_added_tax_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- número de iva
- vat no
- vat #
- impuesto sobre el valor agregado
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>Número de licencia de conductor de Alemania

Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de licencia de conductor de la UE. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

combinación de 11 dígitos y letras

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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- ausstelltonsdatum
- ausstelltonsort
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
- nr-führerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-führerschein
- no-fuhrerschein
- no-fuehrerschein
- n-führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dlno


## <a name="germany-identity-card-number"></a>Número de tarjeta de identidad de Alemania

### <a name="format"></a>Formato

desde el 1 de noviembre de 2010: nueve letras y dígitos

del 1 de abril de 1987 al 31 de octubre de 2010: 10 dígitos

### <a name="pattern"></a>Patrón

desde el 1 de noviembre de 2010:
- una letra (no distingue mayúsculas de minúsculas) 
- ocho dígitos

desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:
- 10 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- austanos
- gpid
- identificación
- identifikation
- identifizierungsnummer
- documento de identidad
- número de identidad
- id-nummer
- id. personal
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Número de pasaporte de Alemania

Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de pasaporte de la UE y está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

10 dígitos o letras

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- el primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K) 
- tres dígitos 
- cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z) 
- un dígito

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_german_passport encuentra contenido que coincide con el patrón.
- Se encuentra una `Keyword_german_passport` palabra clave o una palabra `Keywords_eu_passport_number_common` clave.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_german_passport_data encuentra contenido que coincide con el patrón.
- Se encuentra una `Keyword_german_passport` palabra clave o una palabra `Keywords_eu_passport_number_common` clave.
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte


## <a name="germany-tax-identification-number"></a>Número de identificación fiscal de Alemania

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
- Dos dígitos 
- Un espacio opcional
- Tres dígitos 
- Un espacio opcional
- Tres dígitos 
- Un espacio opcional
- Dos dígitos
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_germany_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_germany_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_germany_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- id. de steuer
- steueridentifikationsnummer
- steuernummer
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- z amazing #
- z amazing
- ztellonummer


## <a name="germany-value-added-tax-number"></a>Número de impuestos del valor agregado de Alemania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón alfanumérico de 11 caracteres

### <a name="pattern"></a>Patrón

Patrón alfanumérico de 11 caracteres:

- una letra D o d
- una letra E o e
- un espacio opcional
- tres dígitos
- un espacio o coma opcional
- tres dígitos
- un espacio o coma opcional
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_germany_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_germany_value_added_tax_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- número de iva
- vat no
- vat #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Número de licencia de conductor de Grecia

Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de licencia de conductor de la UE y está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_greece_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_greece_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver de s_license_number

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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_greece_id_card.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- id. griego
- id. nacional griego
- tarjeta de identificación personal de griego
- id. de la policía griego
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_greece_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_greece_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el formato `Regex_greece_eu_passport_date` DD MMM AA (ejemplo: 28 de agosto 19) o se encuentra una palabra clave de `Keywords_greece_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_greece_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_greece_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Número de la Seguridad Social de Grecia (AMKA)
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Once dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

- 6 dígitos como fecha de nacimiento AAMMDD
- 4 dígitos
- un dígito de comprobación
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_greece_eu_ssn` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_greece_eu_ssn_or_equivalent` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_greece_eu_ssn` encuentra contenido que coincide con el patrón. 

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

- ssn
- ssn #
- social security no
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Número de identificación fiscal de Grecia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_greece_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_greece_eu_tax_file_number` clave de. 
    
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
- aόμ|aόμ αριόμός
- aφμ
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- tax registry no
- número del Registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- tin id
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Número de tarjeta de identidad de Hong Kong (HKID)

### <a name="format"></a>Formato

Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final

### <a name="pattern"></a>Patrón

Combinación de 8 o 9 letras:
- De 1 a 2 letras (no distingue entre mayúsculas y minúsculas) 
- Seis dígitos 
- El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_hong_kong_id_card.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- tarjeta de identidad de hong kong
- HKIDC
- id card
- documento de identidad
- hk identity card
- hong kong id
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

   
## <a name="hungary-drivers-license-number"></a>Número de licencia de conductor de Hungría

### <a name="format"></a>Formato

Dos letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

Dos letras y seis dígitos:
  
- Dos letras (no distingue entre mayúsculas y minúsculas) 
- Seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_hungary_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_hungary_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver de s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Número de identificación personal de Hungría
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

11 dígitos
  
### <a name="pattern"></a>Patrón

11 dígitos:
  
- Un dígito que corresponde al sexo (1-varón, 2-mujer, otros números también son posibles para los ciudadanos que nazcan antes de 1900 o los ciudadanos con doble nacionalidad) 
- Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD)
- Tres dígitos que corresponden a un número de serie
- Un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_hungary_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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

- id number
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyaganosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Número de pasaporte de Hungría

### <a name="format"></a>Formato

Dos letras seguidas de seis o siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras seguidas de seis o siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_hungary_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_hungary_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el formato `Regex_hungary_eu_passport_date` DD MMM/MMM AA (ejemplo: 01 MÁR/MAR 12) o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_hungary_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_hungary_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám


## <a name="hungary-social-security-number-taj"></a>Número de la seguridad social de Hungría (TAJ)

### <a name="format"></a>Formato

Nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

Nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_hungary_eu_ssn_or_equivalent` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
    
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

- número de la seguridad social húngaro
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- ssn
- ssn #
- social security no
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
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

10 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

10 dígitos:
  
- Un dígito que debe ser "8" 
- Ocho dígitos
- Un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_hungary_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La función  `Func_hungary_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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

- adó quenosító szám
- adóhatóság szám
- adószám
- tinta húngaro
- hungatiantin #
- autoridad fiscal no
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- número de iva


## <a name="hungary-value-added-tax-number"></a>Número de impuestos del valor agregado de Hungría
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón alfanumérico de 10 caracteres

### <a name="pattern"></a>Patrón

Patrón alfanumérico de 10 caracteres:

- dos letras: HU o hu
- espacio opcional
- ocho dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:

- La función Func_hungarian_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_hungarian_value_added_tax_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:

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

- vat
- número de impuestos del valor agregado
- vat #
- vatno #
- hungarianvatno #
- tax no.
- value added tax áfa
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
- Una letra en C, P, H, F, A, T, B, L, J, G (no distingue mayúsculas de minúsculas)
- Una carta
- Cuatro dígitos 
- Una letra que es un dígito de comprobación alfabético

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_india_permanent_account_number.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- PAN 
   
## <a name="india-unique-identification-aadhaar-number"></a>Número de identificación única de India (Aadhaar)

### <a name="format"></a>Formato

12 dígitos que contienen espacios o guiones opcionales

### <a name="pattern"></a>Patrón

12 dígitos:
- Un dígito que no es 0 o 1
- Tres dígitos 
- Un guión o un espacio opcional  
- Cuatro dígitos 
- Un guión o un espacio opcional  
- El dígito final, que es el dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_india_aadhaar encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_india_aadhar.
- Se supera la suma de comprobación.
- 
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:

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
- aadhaar
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
- Seis dígitos en el formato DDMMYY, que son la fecha de nacimiento 
- Un punto (opcional)  
- Cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:

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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:

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

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Clasificación internacional de enfermedades (ICD-10-CM)

### <a name="format"></a>Formato

Dictionary

### <a name="pattern"></a>Patrón

Palabra clave

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave Dictionary_icd_10_updated búsqueda.
- Se encuentra una palabra clave Dictionary_icd_10_codes búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave Dictionary_icd_10_ actualización.

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

Cualquier término del diccionario de palabras clave Dictionary_icd_10_updated, que se basa en la clasificación internacional de enfermedades, la décima revisión, la modificación galo [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo solo busca el término, no los códigos de seguros.

Cualquier término del diccionario de palabras clave Dictionary_icd_10_codes, que se basa en la clasificación internacional de enfermedades, la décimo revisión, la modificación galo [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo solo busca códigos de seguros, no la descripción.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Clasificación internacional de enfermedades (ICD-9-CM)

### <a name="format"></a>Formato

Dictionary

### <a name="pattern"></a>Patrón

Palabra clave

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave Dictionary_icd_9_updated búsqueda.
- Se encuentra una palabra clave Dictionary_icd_9_codes búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- Se encuentra una palabra clave Dictionary_icd_9_updated búsqueda.

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

Cualquier término del diccionario de palabras clave Dictionary_icd_9_updated, que se basa en la clasificación internacional de enfermedades, la noveno revisión, la modificación de la infección [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo solo busca el término, no los códigos de seguros.

Cualquier término del diccionario de palabras clave Dictionary_icd_9_codes, que se basa en la clasificación internacional de enfermedades, la noveno revisión, la modificación [galo (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo solo busca códigos de seguros, no la descripción.

## <a name="ip-address"></a>Dirección IP

### <a name="format"></a>Formato

#### <a name="ipv4"></a>IPv4:
Patrón complejo que representa las versiones con formato (puntos) y sin formato (sin puntos) de las direcciones IPv4

#### <a name="ipv6"></a>IPv6:
Patrón complejo que representa los números IPv6 con formato (que incluyen dos puntos)

### <a name="pattern"></a>Patrón

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Para IPv6, una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- IP (esta palabra clave distingue mayúsculas de minúsculas)
- dirección IP 
- Direcciones IP
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Número de licencia de conductor de Irlanda

### <a name="format"></a>Formato

Seis dígitos seguidos de cuatro letras
  
### <a name="pattern"></a>Patrón

Seis dígitos y cuatro letras:
  
- Seis dígitos
- Cuatro letras (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
  
- La expresión regular  `Regex_ireland_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_ireland_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver de s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Número de pasaporte de Irlanda

### <a name="format"></a>Formato

Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

Dos letras o dígitos seguidos de siete dígitos:
  
- Dos dígitos o letras (no distinguen mayúsculas de minúsculas)
- Siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_ireland_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_ireland_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el formato `Regex_ireland_eu_passport_date` DD MMM/MMM YYYY (ejemplo: 01 BEA/MAYO 1988) o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_ireland_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_ireland_eu_passport_number` clave.
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="ireland-personal-public-service-pps-number"></a>Número de servicio público personal (PPS) de Irlanda

### <a name="format"></a>Formato

Formato antiguo (hasta el 31 de diciembre de 2012):
- siete dígitos seguidos de 1 a 2 letras 

Nuevo formato (1 de enero de 2013 y posterior):
- siete dígitos seguidos de dos letras

### <a name="pattern"></a>Patrón

Formato antiguo (hasta el 31 de diciembre de 2012):
- siete dígitos 
- de una a dos letras (no distingue entre mayúsculas y minúsculas) 

Nuevo formato (1 de enero de 2013 y posterior):
- siete dígitos 
- una letra (no distingue mayúsculas de minúsculas) que es un dígito de comprobación alfabético 
- Una letra opcional en el rango A-I o "W"

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_ireland_pps encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_ireland_eu_national_id_card búsqueda.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- servicio personal no
- phearsanta seirbhíse poiblí
- pps no
- número pps
- pps num
- pps service no
- ppsn
- ppsno #
- ppsno
- resalte
- servicio público no
- publicserviceno #
- publicserviceno
- número de ingresos y seguros sociales
- rsi no
- rsi number
- rsin
- seirbhís aitheantais client
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="israel-bank-account-number"></a>Número de cuenta bancaria de Israel

### <a name="format"></a>Formato

13 dígitos

### <a name="pattern"></a>Patrón

Con formato:
- dos dígitos 
- un guión 
- tres dígitos 
- un guión 
- ocho dígitos

Sin formato:
- 	13 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
-   id number
-   identity no        
-   identitynumber #
-   número de identidad
-   numberidentitynumber       
-   id. personal
-   identificador único  

   
## <a name="italy-drivers-license-number"></a>Número de licencia de conductor de Italia

Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de licencia de conductor de la UE y está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

una combinación de 10 letras y dígitos

### <a name="pattern"></a>Patrón

una combinación de 10 letras y dígitos:
- una letra (no distingue mayúsculas de minúsculas) 
- la letra "A" o "V" (no distingue mayúsculas de minúsculas) 
- siete dígitos
- una letra (no distingue mayúsculas de minúsculas)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- numero di patente
- patente di guida 
- patente guida
- patenti di guida
- patenti guida

## <a name="italy-fiscal-code"></a>Código fiscal de Italia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

una combinación de 16 caracteres de letras y dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

Una combinación de 16 caracteres de letras y dígitos:
- tres letras que corresponden a las tres primeras consonantes en el nombre de familia
- tres letras que corresponden a la primera, tercera y cuarta consonantes del nombre
- dos dígitos que corresponden a los últimos dígitos del año de nacimiento
- una letra que corresponde a la letra del mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras A a E, H, L, M, P, R a T (por lo tanto, enero es A y octubre es R)
- dos dígitos que corresponden al día del mes de nacimiento: para diferenciar entre sexos, se agregan 40 al día de nacimiento para mujer
- cuatro dígitos que corresponden al código de área específico del territorio en el que la persona ha nazca (los códigos de todo el país se usan para países extranjeros)
- un dígito de paridad
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_italy_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_italy_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_italy_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- código fiscal
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- número de certificado personal
- código personal
- código de identificación personal
- número de identificación personal
- personalcodeno #
- código fiscal
- tax id
- identificación fiscal no
- número de identificación fiscal
- número de identidad fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="italy-passport-number"></a>Número de pasaporte de Italia

### <a name="format"></a>Formato

dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

dos letras o dígitos seguidos de siete dígitos:
  
- dos dígitos o letras (no distinguen mayúsculas de minúsculas)
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_italy_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_italy_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el formato `Regex_italy_eu_passport_date` DD MMM/MMM YYYY (ejemplo: 01 GEN/JAN 1988) o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_italy_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_italy_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiano passaporto
- passaporto italiano
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="italy-value-added-tax-number"></a>Número de impuestos del valor agregado de Italia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón alfanumérico de 13 caracteres con delimitadores opcionales

### <a name="pattern"></a>Patrón

Patrón alfanumérico de 13 caracteres con delimitadores opcionales:

- I o i
- T o t
- espacio opcional, punto, guión o coma
- 11 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_italy_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_italy_value_added_tax_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- número de iva
- vat no
- vat #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Número de cuenta bancaria de Japón

### <a name="format"></a>Formato

siete u ocho dígitos

### <a name="pattern"></a>Patrón

número de cuenta bancaria:
- siete u ocho dígitos
- código de sucursal de la cuenta bancaria:
- cuatro dígitos 
- un espacio o guión (opcional) 
- tres dígitos

Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_jp_bank_account encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_account.
- Una de las siguientes opciones es verdadera:
- La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_branch_code.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

## <a name="japan-drivers-license-number"></a>Número de licencia de conductor de Japón

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- dl #
- dls #
- lic #
- lics #
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


## <a name="japan-my-number---corporate"></a>Mi número de Japón: corporativo
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Número de 13 dígitos

### <a name="pattern"></a>Patrón

Número de 13 dígitos:

- un dígito de uno a nueve
- 12 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_japanese_my_number_corporate encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_japanese_my_number_corporate búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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


## <a name="japan-my-number---personal"></a>Mi número de Japón: personal
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Número de 12 dígitos

### <a name="pattern"></a>Patrón

Número de 12 dígitos:

- cuatro dígitos
- un espacio, punto o guión opcionales
- cuatro dígitos
- un espacio, punto o guión opcionales
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_japanese_my_number_personal encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_japanese_my_number_personal búsqueda.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

dos letras seguidas de siete dígitos

### <a name="pattern"></a>Patrón

dos letras (sin distingue entre mayúsculas y minúsculas) seguidas de siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- Passport
- Passport Number
- Passport No.
- Passport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- )ademásポースNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_jp_residence_card_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_jp_residence_card_number búsqueda.

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
- Tarjeta de residencia no
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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

   
## <a name="japan-social-insurance-number-sin"></a>Número de seguro social de Japón (SIN)

### <a name="format"></a>Formato

De 7 a 12 dígitos

### <a name="pattern"></a>Patrón

7-12 dígitos:
- cuatro dígitos 
- un guión (opcional) 
- seis dígitos O
- De 7 a 12 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_jp_sin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_sin.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- el 保険.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Número de licencia de conductor de Letonia

### <a name="format"></a>Formato

tres letras seguidas de seis dígitos
  
### <a name="pattern"></a>Patrón

tres letras y seis dígitos:
  
- tres letras (no distingue entre mayúsculas y minúsculas) 
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_latvia_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_latvia_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver de s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Código personal de Letonia

### <a name="format"></a>Formato

11 dígitos y un guión opcional
  
### <a name="pattern"></a>Patrón

Formato antiguo

11 dígitos y un guión:
  
- seis dígitos que corresponden a la fecha de nacimiento (DDMMYY) 
- un guión
- un dígito que corresponde al s. de nacimiento ("0" para el s. 19, "1" para el s. XX y "2" para el s. 21)
- cuatro dígitos, generados aleatoriamente

Nuevo formato

11 dígitos

- Dos dígitos "32"
- Nueve dígitos
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_latvia_eu_national_id_card` o regex `Regex_latvia_eu_national_id_card_new_format` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_latvia_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_latvia_eu_national_id_card` o regex `Regex_latvia_eu_national_id_card_new_format` encuentra contenido que coincide con el patrón. 
    
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
- código fiscal
- número de usuario de sanidad
- id #
- id-code
- identification number
- identifikācijas numurs
- id-number
- número individual
- latvija alva
- nacionālais id
- national id
- número de identificación nacional
- número de identidad nacional
- national insurance number
- número de registro nacional
- nodokļa numurs
- nodokļu id
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
- personas kods
- código de identificación de población
- número de servicio público
- registration number
- número de ingresos
- social insurance number
- social security number
- código fiscal del estado
- tax file number
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- número de votante

## <a name="latvia-passport-number"></a>Número de pasaporte de Letonia

### <a name="format"></a>Formato

dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

dos letras o dígitos seguidos de siete dígitos:
  
- dos dígitos o letras (no distinguen mayúsculas de minúsculas)
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_latvia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_latvia_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_latvia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_latvia_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="lithuania-drivers-license-number"></a>Número de licencia de conductor de Lituania

### <a name="format"></a>Formato

ocho dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_lithuania_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_lithuania_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver de s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Código personal de Lituania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

11 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos sin espacios y delimitadores:
  
- un dígito (1-6) que corresponde al género y al siglo de nacimiento de la persona
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- tres dígitos que corresponden al número de serie de la fecha de nacimiento
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_lithuania_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_lithuania_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_lithuania_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- número de servicio del ciudadano
- id. mokesčių
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- national identification number
- código personal
- código numérico personal
- piliečio paslaugos numeris
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_lithuania_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_lithuania_eu_passport_number` clave. 
- La expresión regular `Regex_eu_passport_date3` encuentra la fecha con el formato DD MM YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_lithuania_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_lithuania_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="luxemburg-drivers-license-number"></a>Número de licencia de conductor de Luxemburgo

### <a name="format"></a>Formato

seis dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

seis dígitos 
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_luxemburg_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_luxemburg_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver de s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Número de identificación nacional de Luxemburgo (personas físicas)
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos:
  
- 11 dígitos 
- dos dígitos de comprobación
    
### <a name="checksum"></a>Suma de comprobación

sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_luxemburg_eu_national_id_card` clave de. 

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number` encuentra contenido que coincide con el patrón. 


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

- eindeutige id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- código individual
- id. individual
- identificación individual
- identidad individual
- numéro d'identification personnel
- id. personal
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_luxemburg_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_luxemburg_eu_passport_number` clave. 
- La expresión regular `Regex_eu_passport_date3` encuentra la fecha con el formato DD MM YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_luxemburg_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_luxemburg_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- austanosnummer
- luxemburgués
- luxemburgo passeport
- passport de Luxemburgo
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Número de identificación nacional de Luxemburgo (personas no naturales)

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
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number_non_natural` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_luxemburg_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_luxemburg_eu_tax_file_number_non_natural` encuentra contenido que coincide con el patrón. 
    
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

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- luxemburgo fiscal identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxemburgués
- numéro d'identification fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversiquemutsausmuts
- id. de steier
- steier identifikatiounsnummer
- steier nummer
- id. de steuer
- steueridentifikationsnummer
- steuernummer
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- z amazing #
- z amazing
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Número de tarjeta de identificación de Malasia

### <a name="format"></a>Formato

12 dígitos que contienen guiones opcionales

### <a name="pattern"></a>Patrón

12 dígitos:
- seis dígitos en el formato AAMMDD, que son la fecha de nacimiento 
- un guión (opcional) 
- código de lugar de nacimiento de dos letras 
- un guión (opcional) 
- tres dígitos aleatorios 
- código de género de un dígito

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- ic
- ic no
- id card
- tarjeta de identificación
- documento de identidad
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- tarjeta de identidad de Malasia
- tarjeta de identidad malasia
- nric
- tarjeta de identificación personal

## <a name="malta-drivers-license-number"></a>Número de licencia de conductor de Malta

### <a name="format"></a>Formato

Combinación de dos caracteres y seis dígitos en el patrón especificado
  
### <a name="pattern"></a>Patrón

combinación de dos caracteres y seis dígitos:
  
- dos caracteres (dígitos o letras, no distinguen mayúsculas de minúsculas)
- un espacio (opcional)
- tres dígitos
- un espacio (opcional)
- tres dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_malta_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver de s_license_number

- lioenzja tas-sewqan
- lioenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Número de tarjeta de identidad de Malta
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

siete dígitos seguidos de una letra
  
### <a name="pattern"></a>Patrón

siete dígitos seguidos de una letra:
  
- siete dígitos 
- una letra de "M, G, A, P, L, H, B, Z" (no se puede insensible a mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_malta_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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

- número de servicio del ciudadano
- id tat-taxxa
- identifika numru tal-biljett
- kodicióni numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz tas-ciónittadin
- numru numru num-taxxa
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_malta_eu_passport_number` clave. 
- Se encuentra una palabra `Keywords_eu_passport_date` clave de

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_malta_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_malta_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="malta-tax-identification-number"></a>Número de identificación fiscal de Malta

### <a name="format"></a>Formato

Para nacionales maltés:
- siete dígitos y una letra en el patrón especificado
  
Entidades maltesas y nacionales no maltés:
- nueve dígitos
  
### <a name="pattern"></a>Patrón

Nacionales maltés: siete dígitos y una letra
  
- siete dígitos 
- una letra (no distingue mayúsculas de minúsculas)
    
Entidades maltesas y nacionales no maltés: nueve dígitos
  
- nueve dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión  `Regex_malta_eu_tax_file_number`  regular o encuentra contenido que coincide con el `Regex_malta_eu_tax_file_number_non_maltese_national` patrón. 
- Se encuentra una palabra  `Keywords_malta_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión  `Regex_malta_eu_tax_file_number` regular o encuentra contenido que coincide con el `Regex_malta_eu_tax_file_number_non_maltese_national` patrón. 
    
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

- número de servicio del ciudadano
- id tat-taxxa
- identifika numru tal-biljett
- kodicióni numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz tas-ciónittadin
- numru numru num-taxxa
- código numérico personal
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- número de identificación único
- número de identidad único
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>Número de servicio del ciudadano (BSN) de Países Bajos

### <a name="format"></a>Formato

ocho o nueve dígitos que contienen espacios opcionales

### <a name="pattern"></a>Patrón

ocho nueve dígitos:
- tres dígitos 
- un espacio (opcional) 
- tres dígitos 
- un espacio (opcional) 
- dos o tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
  
- bsn #
- bsn
- servicenummer
- número de servicio del ciudadano
- número de persona
- número personal
- código numérico personal
- número relacionado con la persona
- persoonlijk nummer
- código de numerieke persoonlijke
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

## <a name="netherlands-drivers-license-number"></a>Número de licencia de conductor de Países Bajos

### <a name="format"></a>Formato

diez dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

diez dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_netherlands_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_netherlands_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver de s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Número de pasaporte de Países Bajos

### <a name="format"></a>Formato

nueve letras o dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

nueve letras o dígitos
  
### <a name="checksum"></a>Suma de comprobación

no aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_netherlands_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_netherlands_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el formato `Regex_netherlands_eu_passport_date` DD MMM/MMM YYYY (ejemplo: 26 MAA/MAR 2012)

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_netherlands_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_netherlands_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Número de identificación fiscal de Países Bajos
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

nueve dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos 
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_netherlands_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_netherlands_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_netherlands_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- identificaciones fiscales de lugar
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- número de identificación del impuesto
- número de impuesto
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- identificación fiscal de países bajos
- identificación fiscal de netherland
- hoja de hoja de tinta de países bajos
- hoja de hoja de herland
- tax id
- identificación fiscal no
- número de identificación fiscal
- cuenta de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- tax tal
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>Número de impuestos sobre el valor agregado de Países Bajos
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón alfanumérico de 14 caracteres

### <a name="pattern"></a>Patrón

Patrón alfanumérico de 14 caracteres:

- N o n
- L o l
- espacio opcional, punto o guión
- nueve dígitos
- espacio opcional, punto o guión
- B o b
- dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_netherlands_value_added_tax_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_netherlands_value_added_tax_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- número de iva
- vat no
- vat #
- wearde tafoege tax getal
- btw núnmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Número de cuenta bancaria de Nueva Zelanda
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Patrón de 14 a 16 dígitos con delimitador opcional

### <a name="pattern"></a>Patrón

Patrón de 14 a 16 dígitos con delimitador opcional:

- dos dígitos
- un espacio o un guión opcional
- de tres a cuatro dígitos
- un espacio o un guión opcional
- siete dígitos
- un espacio o un guión opcional
- de dos a tres dígitos
- un espacio o un guión de opciones

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_new_zealand_bank_account_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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


## <a name="new-zealand-drivers-license-number"></a>Número de licencia de conductor de Nueva Zelanda
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

patrón alfanumérico de ocho caracteres

### <a name="pattern"></a>Patrón

patrón alfanumérico de ocho caracteres

- dos letras 
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_newzealand_driver_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_newzealand_driver_license_number búsqueda.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's licence
- driver's licences
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver licence #
- driver licences #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's licence #
- driver's licences #
- international driving permit
- international driving permits
- Asociación de automóviles nz
- asociación de automóviles de Nueva Zelanda


## <a name="new-zealand-inland-revenue-number"></a>Número de ingresos por el interior de Nueva Zelanda
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

ocho o nueve dígitos con delimitadores opcionales

### <a name="pattern"></a>Patrón

ocho o nueve dígitos con delimitadores opcionales

- dos o tres dígitos
- un espacio opcional o un guión
- tres dígitos
- un espacio opcional o un guión
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_inland_revenue_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_new_zealand_inland_revenue_number búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- ird no.
- ird no #
- nz ird
- nueva Zelanda ird
- número ird
- número de ingresos del interior


## <a name="new-zealand-ministry-of-health-number"></a>Número de salud del ministerio de Salud de Nueva Zelanda

### <a name="format"></a>Formato

tres letras, un espacio (opcional) y cuatro dígitos

### <a name="pattern"></a>Patrón

- tres letras (no distingue entre mayúsculas y minúsculas), excepto "I" y "O"
- un espacio (opcional) 
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_nz_terms.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- tratamiento
- Número de índice de estado nacional
- nhi number
- nhi no.
- NHI #
- Índice de mantenimiento nacional No.
- Identificador del índice de estado nacional
- Índice de salud nacional #

## <a name="new-zealand-social-welfare-number"></a>Número de redes sociales de Nueva Zelanda

Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_newzealand_social_welfare_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_newzealand_social_welfare_number búsqueda.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- social desa adoba #
- social desa adoba #
- social y social No.
- número de redes sociales
- swn #

   
## <a name="norway-identification-number"></a>Número de identificación de Noruega

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos:
- seis dígitos en el formato DDMMYY que son la fecha de nacimiento 
- número individual de tres dígitos 
- dos dígitos de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_norway_id_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_norway_id_number.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Identificación
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Número de identificación multipropósito unificado de Filipinas

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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

## <a name="poland-drivers-license-number"></a>Número de licencia de conductor de Polonia

### <a name="format"></a>Formato

14 dígitos que contienen 2 barras diagonales
  
### <a name="pattern"></a>Patrón

14 dígitos y 2 barras diagonales:
  
- cinco dígitos 
- una barra diagonal
- dos dígitos
- una barra diagonal
- siete dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_poland_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_poland_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver de s_license_number

- prawo langdy
- prawa langdy

## <a name="poland-identity-card"></a>Tarjeta de identidad de Polonia

### <a name="format"></a>Formato

tres letras y seis dígitos

### <a name="pattern"></a>Patrón

tres letras (sin distingue entre mayúsculas y minúsculas) seguidas de seis dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.

   
## <a name="poland-national-id-pesel"></a>Identificación nacional de Polonia (PESEL)

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

- seis dígitos que representan la fecha de nacimiento en el formato AAMMDD
- cuatro dígitos
- un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_pesel_identification_number.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- dowód osobisty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości narodowej

   
## <a name="poland-passport-number"></a>Número de pasaporte de Polonia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial número de pasaporte de la UE. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

dos letras y siete dígitos

### <a name="pattern"></a>Patrón

Dos letras (sin distingue entre mayúsculas y minúsculas) seguidas de siete dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- Numer paszportu
- Nr. Paszportu
- Paszport

## <a name="poland-regon-number"></a>Número REGON de Polonia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Número de 9 o 14 dígitos

### <a name="pattern"></a>Patrón

número de nueve o 14 dígitos:

- nueve dígitos o 
- nueve dígitos
- guión
- cinco dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_polish_regon_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_polish_regon_number búsqueda.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- id. de regon
- número estadístico
- identificador estadístico
- estadística no
- número de regon
- regonid #
- regonno #
- id. de compañía
- companyid #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Número de identificación fiscal de Polonia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

11 dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_poland_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_poland_eu_tax_file_number` clave de. 
    
  
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
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- vat id #
- vat id
- vat no
- número de iva
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- bilhete de identidade
- cartão de cidadão
- tarjeta de ciudadano
- número de documento
- documento de identificação
- id number
- identification no
- identification number
- identity card no
- número de tarjeta de identidad
- tarjeta de identificación nacional
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi number


## <a name="portugal-drivers-license-number"></a>Número de licencia de conductor de Portugal

### <a name="format"></a>Formato

dos patrones: dos letras seguidas de 5 a 8 dígitos con caracteres especiales
  
### <a name="pattern"></a>Patrón

Patrón 1: dos letras seguidas de 5/6 con caracteres especiales:
- Dos letras (no distingue entre mayúsculas y minúsculas)
- Un guión 
- Cinco o seis dígitos
- Un espacio
- Un dígito

Patrón 2: una letra seguida de 6/8 dígitos con caracteres especiales:
- Una letra (no distingue mayúsculas de minúsculas)
- Un guión 
- Seis u ocho dígitos
- Un espacio
- Un dígito

    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_portugal_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_portugal_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver de s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Número de pasaporte de Portugal

### <a name="format"></a>Formato

una letra seguida de seis dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una letra seguida de seis dígitos:
  
- una letra (no distingue mayúsculas de minúsculas)
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_portugal_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_portugal_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_portugal_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_portugal_eu_passport_number` clave.
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- pasaporte portugués
- passeport portugués
- passaporte portugués
- passaporte nº
- passeport nº
- números de passaporte
- pasaportes portugueses
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="portugal-tax-identification-number"></a>Número de identificación fiscal de Portugal

### <a name="format"></a>Formato

nueve dígitos con espacios opcionales
  
### <a name="pattern"></a>Patrón

- tres dígitos
- un espacio opcional
- tres dígitos
- un espacio opcional
- tres dígitos
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_portugal_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_portugal_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_portugal_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- nif #
- nif
- número de identificação fisca
- numero fiscal
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>Número de licencia de conductor de Rumania

### <a name="format"></a>Formato

un carácter seguido de ocho dígitos
  
### <a name="pattern"></a>Patrón

un carácter seguido de ocho dígitos:
- una letra (no distingue entre mayúsculas y minúsculas) o dígito 
- ocho dígitos
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_romania_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_romania_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver de s_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>Código numérico personal (CNP) de Rumania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

13 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

- un dígito del 1 al 9
- seis dígitos que representan la fecha de nacimiento (AAMMDD)
- dos dígitos, que pueden ser 01-52 o 99
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_romania_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_romania_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_romania_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- número de seguro
- insurancenumber #
- national id #
- national id
- national identification number
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- código numérico personal
- pin #
- pin
- tax file no
- tax file number
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- número de identificación único
- número de identidad único
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Número de pasaporte de Rumania

### <a name="format"></a>Formato

ocho o nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

ocho o nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_romania_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_romania_eu_passport_number` clave. 
- La expresión regular encuentra la fecha en el formato `Regex_romania_eu_passport_date` DD MMM/MMM YY (ejemplo: 01 FEB/FEB 10) o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_romania_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_romania_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului nuulule pașaportului Pașaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="russia-passport-number-domestic"></a>Número de pasaporte de Rusia nacionales
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Número de 10 dígitos

### <a name="pattern"></a>Patrón

Número de 10 dígitos:

- dos dígitos
- un espacio opcional o un guión
- dos dígitos
- un espacio opcional
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- El elemento regex Regex_Russian_Passport_Number_Domestic encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Russian_Passport_Number búsqueda.

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
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Número de pasaporte internacional de Rusia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

número de nueve dígitos

### <a name="pattern"></a>Patrón

número de nueve dígitos:

- dos dígitos
- un espacio opcional o un guión
- siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- El elemento regex Regex_Russian_Passport_Number_International encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Russian_Passport_Number búsqueda.

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
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Identificación nacional de Arabia Saudí

### <a name="format"></a>Formato

10 dígitos

### <a name="pattern"></a>Patrón

10 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- la letra "F", "G", "S" o "T" (no distingue mayúsculas de minúsculas) 
- siete dígitos 
- un dígito de comprobación alfabético

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_singapore_nric.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- IC 
- Número de identificación de extranjeros 
- FIN 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Número de licencia de conductor de Eslovaquia

### <a name="format"></a>Formato

un carácter seguido de siete dígitos
  
### <a name="pattern"></a>Patrón

un carácter seguido de siete dígitos
  
- una letra (no distingue entre mayúsculas y minúsculas) o dígito
- siete dígitos 
    
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovakia_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_slovakia_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver de s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Número personal de Eslovaquia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

nueve o diez dígitos que contienen barras diagonales inversas opcionales
  
### <a name="pattern"></a>Patrón

- seis dígitos que representan la fecha de nacimiento
- barra diagonal opcional (/)
- tres dígitos
- un dígito de comprobación opcional
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_slovakia_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_slovakia_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_slovakia_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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
- číslo národnej identifikačnejej andy
- číslo občianského preukazu
- daňové číslo
- id number
- identification no
- identification number
- identifikačnáflua č
- identifikačné číslo
- identity card no
- número de tarjeta de identidad
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyaganosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- tax file no
- tax file number
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="slovakia-passport-number"></a>Número de pasaporte de Eslovaquia

### <a name="format"></a>Formato

un dígito o letra seguido de siete dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovakia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_slovakia_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovakia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_slovakia_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="slovenia-drivers-license-number"></a>Número de licencia de conductor de Eslovenia

### <a name="format"></a>Formato

nueve dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

nueve dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovenia_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_slovenia_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver de s_license_number

- vozniško dovoljenje
- vozniška številka licence
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Número de ciudadano maestro único de Eslovenia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

13 dígitos en el patrón especificado:
  
- siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL) donde "LLL" corresponde a los tres últimos dígitos del año de nacimiento 
- dos dígitos que corresponden al área de nacimiento "50"
- tres dígitos que corresponden a una combinación de sexo y número de serie para las personas que nazcan el mismo día (000-499 para los hombres y 500-999 para las mujeres)
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_national_id_card` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_slovenia_eu_national_id_card` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_national_id_card` encuentra contenido que coincide con el patrón. 
    
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
- nacionalna id
- lista nacionalni potni
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- código personal
- número personal
- código numérico personal
- številka državljana
- número de ciudadano único
- número de identificador único
- número de identidad único
- número único de ciudadano maestro
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

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovenia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_slovenia_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el `Regex_eu_passport_date1` formato DD.MM.YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_slovenia_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_slovenia_eu_passport_number` clave. 
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- lista potni #
- datum rojstva
- lista potni
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="slovenia-tax-identification-number"></a>Número de identificación fiscal de Eslovenia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

ocho dígitos sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

- un dígito del 1 al 9
- seis dígitos
- un dígito de comprobación
  
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_slovenia_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_slovenia_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- tax file no
- tax file number
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="south-africa-identification-number"></a>Número de identificación de Sudáfrica

### <a name="format"></a>Formato

13 dígitos que pueden contener espacios

### <a name="pattern"></a>Patrón

13 dígitos:
- seis dígitos en el formato AAMMDD, que son la fecha de nacimiento 
- cuatro dígitos 
- un indicador de nacionalidad de un solo dígito 
- el dígito "8" o "9" 
- un dígito, que es un dígito de suma de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Identificación 
   
## <a name="south-korea-resident-registration-number"></a>Número de registro de residente de Corea del Sur

### <a name="format"></a>Formato

13 dígitos que contienen un guión

### <a name="pattern"></a>Patrón

13 dígitos:
- seis dígitos en el formato AAMMDD, que son la fecha de nacimiento 
- un guión 
- un dígito determinado por el siglo y el género 
- código de región de nacimiento de cuatro dígitos 
- un dígito usado para diferenciar a las personas para las que los números anteriores son idénticos 
- un dígito de comprobación.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_south_korea_resident_number.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

## <a name="spain-drivers-license-number"></a>Número de licencia de conductor de España

### <a name="format"></a>Formato

ocho dígitos seguidos de un carácter
  
### <a name="pattern"></a>Patrón

ocho dígitos seguidos de un carácter:
  
- ocho dígitos 
- un dígito o letra (no distingue entre mayúsculas y minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o encuentra contenido que coincide con el `Func_spain_eu_DL_and_NI_number_foreigner` patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_spain_eu_driver's_license_number` clave. 

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o encuentra contenido que coincide con el `Func_spain_eu_DL_and_NI_number_foreigner` patrón. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver de s_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- permisos conducir
- carrón
- habat de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>DNI de España
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

ocho dígitos seguidos de un carácter
  
### <a name="pattern"></a>Patrón

siete dígitos seguidos de un carácter
  
- ocho dígitos
- Un espacio o un guión opcionales
- una letra de verificación (no distingue mayúsculas de minúsculas)
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o encuentra contenido que coincide con el `Func_spain_eu_DL_and_NI_number_foreigner` patrón. 
- Se encuentra una palabra  `Keywords_spain_eu_national_id_card"` clave de. 

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_DL_and_NI_number_citizen` o encuentra contenido que coincide con el `Func_spain_eu_DL_and_NI_number_foreigner` patrón. 

    
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
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- número de seguro
- national identification number
- identidad nacional
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- número de identificación personal
- identidad personal no
- número de identidad único
- uniqueid #

## <a name="spain-passport-number"></a>Número de pasaporte de España

### <a name="format"></a>Formato

una combinación de ocho o nueve caracteres de letras y números sin espacios ni delimitadores
  
### <a name="pattern"></a>Patrón

una combinación de ocho o nueve caracteres de letras y números:
  
- dos dígitos o letras 
- un dígito o una letra (opcional)
- seis dígitos
    
### <a name="checksum"></a>Suma de comprobación

No aplicable
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_spain_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_spain_eu_passport_number` clave. 
- La expresión regular encuentra la fecha con el formato `Regex_spain_eu_passport_date` DD-MM-YYYY o se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_spain_eu_passport_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_passport_number` palabra clave o una palabra `Keywords_spain_eu_passport_number` clave.
    
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

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
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
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- spain passport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha del problema
- fecha de expiración


## <a name="spain-social-security-number-ssn"></a>Número de la seguridad social de España (SSN)

Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de la Seguridad Social de la UE o Identificador equivalente. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

11 o 12 dígitos

### <a name="pattern"></a>Patrón

De 11 a 12 dígitos:
- dos dígitos 
- una barra diagonal (opcional) 
- de siete a ocho dígitos 
- una barra diagonal (opcional) 
- dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

siete u ocho dígitos y una o dos letras en el patrón especificado
  
### <a name="pattern"></a>Patrón

Personas físicas de España con una tarjeta de identidad nacional de España:
  
- ocho dígitos 
- una letra mayúscula (distingue mayúsculas de minúsculas) 
    
Españoles no residentes sin un documento de identidad nacional de España
  
- una letra mayúscula "L" (distingue mayúsculas de minúsculas)
- siete dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas) 
    
Españoles residentes menores de 14 años sin una tarjeta de identidad nacional de España:
  
- una letra mayúscula "K" (distingue mayúsculas de minúsculas)
- siete dígitos 
- una letra mayúscula (distingue mayúsculas de minúsculas)
    
Con el número de identificación de un ciudadano
  
- una letra mayúscula que es "X", "Y" o "Z" (distingue mayúsculas de minúsculas) 
- siete dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas) 
    
Personas que no tienen el número de identificación de un ciudadano
  
- una letra mayúscula que es "M" (distingue mayúsculas de minúsculas) 
- siete dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas) 
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_tax_file_number` o encuentra contenido que coincide con el `Func_spain_eu_DL_and_NI_number_citizen` patrón. 
- Se encuentra una palabra  `Keywords_spain_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_spain_eu_tax_file_number` o encuentra contenido que coincide con el `Func_spain_eu_DL_and_NI_number_citizen` patrón. 
    
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

- cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- tax file no
- tax file number
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server de conexión

### <a name="format"></a>Formato

La cadena "User Id", "User ID", "uid" o "UserId" seguida de los caracteres y cadenas descritos en el siguiente patrón.

### <a name="pattern"></a>Patrón

- la cadena "User Id", "User ID", "uid" o "UserId"
- cualquier combinación de entre 1 y 200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena "Password" o "pwd" donde "pwd" no está precedida por una letra minúscula
- un signo igual (=)
- cualquier carácter que no sea un signo de dólar ($), símbolo de porcentaje (%), mayor que símbolo (>), símbolo (@), comillas ("), punto y coma (;), llave izquierda([) o corchete izquierdo ({)
- cualquier combinación de 7 a 128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")
- punto y coma (;) o comillas (")

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular CEP_Regex_SQLServerConnectionString encuentra contenido que coincide con el patrón.
- No se encuentra CEP_GlobalFilter palabra clave de la página.
- La expresión regular CEP_PasswordPlaceHolder no encuentra contenido que coincida con el patrón.
- La expresión regular CEP_CommonExampleKeywords no encuentra contenido que coincida con el patrón.

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

- alguna contraseña
- somepassword
- secretPassword
- ejemplo

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- Contraseña o pwd seguido de 0-2 espacios, un signo igual (=), 0-2 espacios y un asterisco (*) -OR-
- Contraseña o pwd seguido de:
    - Signo igual (=)
    - Símbolo menor que (<)
    - Cualquier combinación de 1-200 caracteres con letras mayúsculas o minúsculas, dígitos, asterisco (*), guión (-), subrayado (_) o carácter de espacio en blanco
    - Símbolo mayor que (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tenga en cuenta que técnicamente, este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave).

- contoso
- fabrikam
- northwind
- espacio aislado
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>Número de licencia de conductor de Suecia

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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular  `Regex_sweden_eu_driver's_license_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una  `Keywords_eu_driver's_license_number` palabra clave o una palabra `Keywords_sweden_eu_driver's_license_number` clave. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver de s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- slicence del controlador
- slicences de controlador
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de controladores #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- slicence del controlador #
- slicences de controlador #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- permiso de conducción
- dl no
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver de s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Identificación nacional de Suecia

### <a name="format"></a>Formato

10 o 12 dígitos y un delimitador opcional

### <a name="pattern"></a>Patrón

10 o 12 dígitos y un delimitador opcional:
- dos dígitos (opcional) 
- Seis dígitos en fecha de formato AAMMDD 
- delimitador de "-" o "+" (opcional)
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función `Func_swedish_national_identifier` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra `Keywords_swedish_national_identifier` clave de
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función `Func_swedish_national_identifier` encuentra contenido que coincide con el patrón.
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

- id no
- id number
- id #
- identification no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- documento de identidad
- identity no
- número de identidad
- id-nummer
- id. personal
- personnummer #
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>Número de pasaporte de Suecia
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de pasaporte de la UE y está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

ocho dígitos

### <a name="pattern"></a>Patrón

ocho dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- la expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.
- se cumple una de las siguientes condiciones:
    - se encuentra una palabra clave Keyword_passport búsqueda.
    - se encuentra una palabra clave Keyword_sweden_passport búsqueda.

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
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- (en la ポ) 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>Número de la seguridad social de Suecia o identificación equivalente
Esta entidad de tipo de información confidencial solo está disponible en el tipo de información confidencial Número de la Seguridad Social de la UE o Identificador equivalente.

### <a name="format"></a>Formato

12 dígitos sin espacios y delimitadores
  
### <a name="pattern"></a>Patrón

12 dígitos:
  
- ocho dígitos que corresponden a la fecha de nacimiento (AAAMMDD) 
- tres dígitos que corresponden a un número de serie donde: 
  - el último dígito del número de serie indica el sexo por la asignación de un número impar para el varón y un número par para la mujer
  - Antes de 1990, la asignación de un número de serie correspondía al país en el que se encontraba el portador del número. O bien( si hubo antes de 1947) donde había estado vivo, según los registros fiscales, el 1 de enero de 1947, con un código especial (normalmente 9 como el séptimo dígito) para los investigadores.
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_sweden_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_sweden_eu_ssn_or_equivalent` clave de. 
    
Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función  `Func_sweden_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón. 
    
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

### <a name="keywords"></a>Palabras clave

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- número de identificación personal
- identification number
- id. personal no
- identity no
- identification no
- identificación personal no
- id. de personnummer
- personligt id-nummer
- unikt id-nummer
- personnummer
- identifikationsnumret
- personnummer #
- identifikationsnumret #

## <a name="sweden-tax-identification-number"></a>Número de identificación fiscal de Suecia
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

10 dígitos y un símbolo en el patrón especificado
  
### <a name="pattern"></a>Patrón

10 dígitos y un símbolo:
  
- seis dígitos que corresponden a la fecha de nacimiento (AAMMDD) 
- un signo más o menos
- tres dígitos que hacen que el número de identificación sea único, donde: 
  - para números emitidos antes de 1990, el séptimo y octavo dígito identifican el país de nacimiento o las personas que han nado en el exterior
  - el dígito en la noveno posición indica el género por impar para el varón o incluso para la mujer
- un dígito de comprobación
    
### <a name="checksum"></a>Suma de comprobación

Sí
  
### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_sweden_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_sweden_eu_tax_file_number` clave de. 
    
Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_sweden_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
    
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
- skatt id nummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- sverige tin
- archivo de impuestos
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de impuestos
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="swift-code"></a>Código SWIFT

### <a name="format"></a>Formato

cuatro letras seguidas de 5 a 31 letras o dígitos

### <a name="pattern"></a>Patrón

cuatro letras seguidas de 5 a 31 letras o dígitos:
- código bancario de cuatro letras (no distingue mayúsculas de minúsculas) 
- un espacio opcional 
- 4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN)) 
- un espacio opcional 
- de uno a tres letras o dígitos (resto del BBAN)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFT(SWIFT)
- SWIFT番号
- BIC番号
- BIC
- SWIFT
- SWIFT 番号
- BIC 番号
- BIC
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Número SSN AHV de Suiza
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

Número de 13 dígitos

### <a name="pattern"></a>Patrón

Número de 13 dígitos:

- tres dígitos - 756
- un punto opcional
- cuatro dígitos
- un punto opcional
- cuatro dígitos
- un punto opcional
- dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_swiss_social_security_number_ahv encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keywords_swiss_social_security_number_ahv búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- ssn
- pid
- número de seguro
- personalidno #
- social security number
- número de identificación personal
- identificación personal no.
- insuranceno #
- uniqueidno #
- identificación única no.
- avs number
- identidad personal no versálisissnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversálisissnummer
- id. de personal de identificación
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Número de identificación nacional de Taiwán

### <a name="format"></a>Formato

una letra (en inglés) seguida de nueve dígitos

### <a name="pattern"></a>Patrón

una letra (en inglés) seguida de nueve dígitos:
- una letra (en inglés, no distingue mayúsculas de minúsculas) 
- el dígito "1" o "2" 
- ocho dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwanese_national_id.
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Número de certificado de residente de Taiwán (ARC/TARC)

### <a name="format"></a>Formato

10 letras y dígitos

### <a name="pattern"></a>Patrón

10 letras y dígitos:
- dos letras (no distingue entre mayúsculas y minúsculas) 
- ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

## <a name="thai-population-identification-code"></a>Código de identificación de la población tailandesa

### <a name="format"></a>Formato

13 dígitos

### <a name="pattern"></a>Patrón

13 dígitos:
- el primer dígito no es cero o nueve 
- 12 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_Thai_Citizen_Id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Thai_Citizen_Id búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
  
## <a name="turkish-national-identification-number"></a>Número de identificación nacional turco

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_Turkish_National_Id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Turkish_National_Id búsqueda.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- TC Kimlik No
- TC Kimlik nuanessı
- Vatandaşlık nuanessı
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>Reino Unido número de licencia de conductor
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de licencia de conductor de la UE. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

Combinación de 18 letras y dígitos en el formato especificado

### <a name="pattern"></a>Patrón

18 letras y dígitos:
- Cinco letras (no distinguen mayúsculas de minúsculas) o el dígito "9" en lugar de una letra. 
- Un dígito.
- Cinco dígitos en el formato de fecha MMDDY para la fecha de nacimiento. El séptimo carácter se incrementa en 50 si el controlador es mujer; para examen, de 51 a 62 en lugar de 01 a 12.
- Dos letras (no distinguen mayúsculas de minúsculas) o el dígito "9" en lugar de una letra. 
- Cinco dígitos.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- quadiks 
- motor cars 
- 125 cco 
- sidecar 
- triciclos 
- indeste 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>Reino Unido número de lista de elecciones

### <a name="format"></a>Formato

dos letras seguidas de 1-4 dígitos

### <a name="pattern"></a>Patrón

dos letras (sin distingue entre mayúsculas y minúsculas) seguidas de 1 a 4 números

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

   
## <a name="uk-national-health-service-number"></a>Reino Unido número de servicio de salud nacional

### <a name="format"></a>Formato

De 10 a 17 dígitos separados por espacios

### <a name="pattern"></a>Patrón

10-17 dígitos:
- 3 o 10 dígitos 
- un espacio 
- tres dígitos 
- un espacio 
- cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- nhs 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB 
- D.O.B 
- Fecha de nacimiento 
- Fecha de nacimiento 
   
## <a name="uk-national-insurance-number-nino"></a>Reino Unido número de seguro nacional (NINO)
Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de identificación nacional de la UE. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

siete caracteres o nueve caracteres separados por espacios o guiones

### <a name="pattern"></a>Patrón

dos patrones posibles:

- dos letras (los NINO válidos usan solo ciertos caracteres en este prefijo, que este patrón valida, no distingue entre mayúsculas y minúsculas)
- seis dígitos
- ya sea 'A', 'B', 'C' o 'D' (como el prefijo, solo se permiten ciertos caracteres en el sufijo, no distinguen mayúsculas de minúsculas)

OR

- dos letras
- un espacio o guión
- dos dígitos
- un espacio o guión
- dos dígitos
- un espacio o guión
- dos dígitos
- un espacio o guión
- 'A', 'B', 'C' o 'D'

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_uk_nino encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_nino.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- insurance
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- Número ni
- NI No.
- NI #
- NI #
- insurance #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>Reino Unido Número de referencia de contribuyente único
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

10 dígitos sin espacios y delimitadores
 
  
### <a name="pattern"></a>Patrón

10 dígitos
  
### <a name="checksum"></a>Suma de comprobación

No
  
### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función  `Func_uk_eu_tax_file_number` encuentra contenido que coincide con el patrón. 
- Se encuentra una palabra  `Keywords_uk_eu_tax_file_number` clave de. 
    
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

- número de impuestos
- archivo de impuestos
- tax id
- identificación fiscal no
- número de identificación fiscal
- tax no #
- tax no
- número de registro de impuestos
- y ahora #
- y ahora #
- numeración #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="us-bank-account-number"></a>Número de cuenta bancaria de EE. UU.

### <a name="format"></a>Formato

De 6 a 17 dígitos

### <a name="pattern"></a>Patrón

De 6 a 17 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

## <a name="us-drivers-license-number"></a>Número de licencia de conductor de EE. UU.

### <a name="format"></a>Formato

Depende del estado

### <a name="pattern"></a>Patrón

depende del estado, por ejemplo, Nueva York:
- nueve dígitos con formato como ddd ddd ddd coincidirán.
- nueve dígitos como ddddddddd no coincidirán.

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.
- Se encuentra una palabra clave de Keyword_us_drivers_license.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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

- DL 
- DLS 
- CDL 
- CDLS 
- ID 
- IDs 
- DL # 
- DLS # 
- CDL # 
- CDLS # 
- Id. #
- IDs # 
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
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
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
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
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


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- abreviatura de estado (por ejemplo, "NY") 
- nombre de estado (por ejemplo, "Nueva York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Número de identificación de contribuyente individual (ITIN) de EE. UU.

### <a name="format"></a>Formato

nueve dígitos que empiezan por "9" y contienen un "7" o "8" como cuarto dígito, con formato opcional con espacios o guiones

### <a name="pattern"></a>Patrón

con formato:
- el dígito "9" 
- dos dígitos 
- un espacio o guión 
- un "7" o "8" 
- un dígito 
- un espacio o guión 
- cuatro dígitos

sin formato:
- el dígito "9" 
- dos dígitos 
- un "7" o "8" 
- cinco dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_formatted_itin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_itin.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_unformatted_itin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_itin.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_formatted_itin o Func_unformatted_itin encuentra contenido que coincide con el patrón.

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
- itin 
- i.t.i.n.
- ssn 
- tin 
- social security 
- tax payer 
- itins 
- y ahora 
- individual taxpayer 


## <a name="us-social-security-number-ssn"></a>Número de seguridad social (SSN) de EE. UU.

### <a name="format"></a>Formato

nueve dígitos, que pueden estar en un patrón con formato o sin formato

> [!NOTE]
> Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).

### <a name="pattern"></a>Patrón

Cuatro funciones buscan SSN en cuatro patrones diferentes:
- Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)
- Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)
- Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)
- Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)

### <a name="checksum"></a>Suma de comprobación

No


### <a name="definition"></a>Definición

Una directiva DLP tiene la confianza alta de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_ssn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La función Func_unformatted_ssn busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.

Una directiva DLP tiene confianza baja en que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- social security no
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID
   
## <a name="us--uk-passport-number"></a>EE.UU. / Reino Unido passport number
Reino Unido La entidad de tipo de información confidencial de número de pasaporte está disponible en el tipo de información confidencial número de pasaporte de la UE. Está disponible como una entidad independiente de tipo de información confidencial.

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- (en la ポ) 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="ukraine-passport-domestic"></a>Pasaporte nacional de Ucrania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

nueve dígitos

### <a name="pattern"></a>Patrón

nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- El elemento regex Regex_Ukraine_Passport_Domestic encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Ukraine_Passport_Domestic búsqueda.

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

- passport de ucrania
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Pasaporte internacional de Ucrania
Este tipo de información confidencial solo está disponible para su uso en:
- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- gobierno de la información
- administración de registros
- Seguridad de aplicaciones en la nube de Microsoft

### <a name="format"></a>Formato

patrón alfanumérico de ocho caracteres

### <a name="pattern"></a>Patrón

Patrón alfanumérico de ocho caracteres:
- dos letras o dígitos
- seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
- El elemento regex Regex_Ukraine_Passport_International encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave Keyword_Ukraine_Passport_International búsqueda.

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

- passport de ucrania
- passport number
- passport no
- паспорт України
- номер паспорта
