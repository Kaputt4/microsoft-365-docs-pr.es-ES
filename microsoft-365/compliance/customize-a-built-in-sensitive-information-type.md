---
title: Personalizar un tipo de información confidencial integrado
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información acerca de cómo crear un tipo de información confidencial personalizado que le permita usar reglas que cumplan con las necesidades de su organización.
ms.openlocfilehash: 14fb645a4b7f58f609995bc71edae24090c83cc7
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630993"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Personalizar un tipo de información confidencial integrado

Cuando busca información confidencial en el contenido, es necesario describir esa información en lo que se denomina una *regla*. Prevención de pérdida de datos (DLP) de Microsoft Purview incluye reglas para los tipos más comunes de información confidencial que se pueden usar inmediatamente. Para usar estas reglas, deberá incluirlas en una directiva. Quizás quiera ajustar estas reglas integradas para satisfacer las necesidades específicas de su organización y, para hacerlo, puede crear un tipo personalizado de información confidencial. En este tema se muestra cómo personalizar el archivo XML que contiene la colección de reglas existente para detectar una amplia variedad de posible información de tarjeta de crédito.

Puede usar este ejemplo y aplicarlo en otros tipos de información confidencial integrados. Para obtener una lista de los tipos de información confidencial predeterminados y las definiciones XML, vea [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md).

## <a name="export-the-xml-file-of-the-current-rules"></a>Exportar el archivo XML de las reglas actuales

Para exportar el XML, debe [conectarse a Seguridad y cumplimiento PowerShell](/powershell/exchange/connect-to-scc-powershell).

1. En el símbolo del sistema de PowerShell, escriba lo siguiente para mostrar en pantalla las reglas de la organización. Si no creó sus propias reglas, solo verá las reglas integradas y predeterminadas con la etiqueta “Paquete de reglas de Microsoft”.

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. Almacene las reglas de su organización en una variable escribiendo lo siguiente. Almacenar algo en una variable hace que esté disponible fácilmente más adelante en un formato que funcione para los comandos de PowerShell.

   ```powershell
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```

3. Cree un archivo XML con formato con todos esos datos escribiendo lo siguiente.

   ```powershell
   [System.IO.File]::WriteAllBytes('C:\custompath\exportedRules.xml', $ruleCollections.SerializedClassificationRuleCollection)
   ```

   > [!IMPORTANT]
   > Asegúrese de usar la ubicación del archivo donde se almacena realmente el paquete de reglas. `C:\custompath\` es un marcador de posición.

## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>Encontrar en el archivo XML la regla que quiera modificar

Los cmdlets anteriores exportaron toda la *colección de reglas*, que incluye las reglas predeterminadas que proporcionamos. Después, tendrá que buscar específicamente la regla de Número de tarjeta de crédito que quiere modificar.

1. Use un editor de texto para abrir el archivo XML exportado en la sección anterior.

2. Desplácese hasta la etiqueta `<Rules>`, que se encuentra al principio de la sección que contiene las reglas de DLP. Como el archivo XML contiene la información de toda la colección de reglas, también contiene otra información al principio que necesita pasar para llegar a las reglas.

3. Busque *Func_credit_card* para encontrar la definición de la regla de Número de tarjeta de crédito. En el XML, los nombres de regla no pueden contener espacios, por lo que normalmente estos se reemplazan por caracteres de subrayado y, a veces, los nombres de regla se abrevian. Un ejemplo de esto es la regla del Número de seguridad social de EE. UU., que se abrevia como _SSN_. El código XML de la regla del Número de tarjeta de crédito debería tener el aspecto del ejemplo de código siguiente.

   ```xml
   <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
          patternsProximity="300" recommendedConfidence="85">
         <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_credit_card" />
           <Any minMatches="1">
             <Match idRef="Keyword_cc_verification" />
             <Match idRef="Keyword_cc_name" />
             <Match idRef="Func_expiration_date" />
           </Any>
         </Pattern>
       </Entity>
   ```

Ahora que ha encontrado la definición de la regla de Número de tarjeta de crédito en el XML, puede personalizar el XML de la regla para que se adapte a sus necesidades. Para un repaso de las definiciones XML, vea el [Glosario de términos](#term-glossary) al final de este tema.

## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>Modificar el código XML y crear un tipo de información confidencial

En primer lugar, deberá crear un nuevo tipo de información confidencial porque las reglas predeterminadas no se pueden modificar directamente. Puede hacer una amplia variedad de cosas con tipos de información confidencial personalizados, que se describen en [Creación de un tipo de información confidencial personalizada en Seguridad y cumplimiento de PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). En este ejemplo, lo haremos sencillo y solo se eliminarán las evidencias confirmativas y se agregarán palabras clave a la regla Número de tarjeta de crédito.

Todas las definiciones de regla XML se basan en la siguiente plantilla general. Tiene que copiar y pegar el XML de definición de Número de tarjeta de crédito en la plantilla, modificar algunos valores (tenga en cuenta los marcadores de posición ". . ." en el siguiente ejemplo) y, después, cargar el XML modificado como una nueva regla que se pueda usar en directivas.

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." />
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
   <!-- Paste the Credit Card Number rule definition here.-->
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

Ahora tiene algo parecido al siguiente XML. Como los paquetes de reglas y las reglas se identifican por sus GUID únicos, tiene que generar dos GUID: uno para el paquete de reglas y otro para reemplazar el GUID de la regla del Número de tarjeta de crédito. El GUID del ID de entidad en el ejemplo de código siguiente es el que se usa para nuestra definición de regla integrada que tiene que reemplazar. Hay varias maneras de generar GUID, pero puede hacerlo fácilmente en PowerShell escribiendo **[guid]::NewGuid()**.

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f">
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>Quitar el requisito de evidencias corroborativas de un tipo de información confidencial

Ahora que tiene un nuevo tipo de información confidencial que puede cargar en el portal de cumplimiento de Microsoft Purview, el siguiente paso es hacer que la regla sea más específica. Modifique la regla para que solo busque un número de 16 dígitos que pasa la suma de comprobación pero no requiere evidencia corroborativa adicional (como las palabras clave). Para ello, tiene que quitar la parte del código XML que busca la evidencia corroborativa. La evidencia corroborativa es muy útil para reducir los falsos positivos. En este caso, suelen haber determinadas palabras clave o una fecha de expiración cerca del número de la tarjeta de crédito. Si quita esa evidencia, debe ajustar también la seguridad que tiene de haber encontrado un número de tarjeta de crédito. Para ello, reduzca `confidenceLevel`, que es 85 en el ejemplo.

```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>Buscar palabras clave específicas de la organización

Quizás quiera requerir evidencia confirmativa pero con palabras claves diferentes o adicionales, y quizás quiera cambiar dónde buscar esa evidencia. Puede ajustar el valor de `patternsProximity` para aumentar o reducir el radio donde se buscará la evidencia confirmativa alrededor del número de 16 dígitos. Para agregar sus propias palabras clave, debe definir una lista de palabras clave y hacer referencia a ella en su regla. El siguiente código XML agrega las palabras clave "company card" y "Contoso card" para que los mensajes que contengan esas frases a menos de 150 caracteres de un número de tarjeta de crédito se identifiquen como número de tarjeta de crédito.

```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>Cargar la regla

Para cargar la regla, siga el procedimiento siguiente.

1. Guárdela como un archivo .xml con codificación Unicode. Es importante porque la regla no funcionará si se guarda con una codificación diferente.

2. [Conéctese al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)

3. En el símbolo del sistema de PowerShell, escriba lo siguiente.

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('C:\custompath\MyNewRulePack.xml'))
   ```

   > [!IMPORTANT]
   > Asegúrese de usar la ubicación del archivo donde se almacena realmente el paquete de reglas. `C:\custompath\` es un marcador de posición.

4. Para confirmar, escriba “Y” y presione **Entrar**.

5. Compruebe que la nueva regla se haya cargado y su nombre para mostrar escribiendo lo siguiente:

   ```powershell
   Get-DlpSensitiveInformationType
   ```

Para empezar a usar la nueva regla para detectar información confidencial, tiene que agregarla a una directiva DLP. Para obtener información sobre cómo agregar la regla a una directiva, vea [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md).

## <a name="term-glossary"></a>Glosario de términos

Estas son las definiciones de los términos que encontró en este procedimiento.

<br>

****

|Término|Definición|
|---|---|
|Entidad|Las entidades son lo que llamamos tipos de información confidencial, como números de tarjeta de crédito. Cada entidad tiene un GUID único como ID. Si copia un GUID y lo busca en el código XML, encontrará la definición de regla XML y todas las traducciones localizadas de esa regla XML. Para encontrar esta definición, puede buscar el GUID de la traducción y, después, buscar por ese GUID.|
|Funciones|El archivo XML hace referencia a `Func_credit_card`, que es una función en código compilado. Las funciones se usan para ejecutar expresiones regulares complejas y verificar que las sumas de comprobación de nuestras reglas integradas coinciden. Como esto se produce en el código, algunas de las variables no aparecen en el archivo XML.|
|IdMatch|Este es el identificador para el que el patrón está intentando encontrar coincidencias, por ejemplo, un número de tarjeta de crédito.|
|Listas de palabras clave|El archivo XML también hace referencia a `keyword_cc_verification` y `keyword_cc_name`, que son listas de palabras en las que buscamos coincidencias dentro de `patternsProximity` para la entidad. Actualmente no se muestran en el archivo XML.|
|Patrón|El patrón contiene la lista de lo que el tipo confidencial está buscando. Incluye palabras clave, regexe y funciones internas, que realizan tareas como verificar sumas de comprobación. Los tipos de información confidencial pueden tener varios patrones con confianzas únicas. Esto resulta útil para crear un tipo de información confidencial que devuelve una confianza alta si se encuentra evidencia confirmativa y una confianza menor si se encuentra poca o ninguna evidencia confirmativa.|
|Patrón confidenceLevel|Este es el nivel de confianza en el que el motor de DLP encontró una coincidencia. Este nivel de confianza está asociado con una coincidencia del patrón si se cumplen los requisitos del patrón. Esta es la medida de la confianza que debe tener en cuenta al usar las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).|
|patternsProximity|Cuando encontramos lo que parece un patrón de número de tarjeta de crédito, `patternsProximity` es la proximidad alrededor de la cual buscaremos una evidencia confirmativa.|
|recommendedConfidence|Este es el nivel de confianza que le recomendamos para esta regla. La confianza recomendada se aplica a entidades y afinidades. En el caso de las entidades, este número nunca se evalúa según el valor de `confidenceLevel` del patrón. Es simplemente una sugerencia para ayudar a elegir un nivel de confianza si quiere aplicar uno. Para las afinidades, el valor de `confidenceLevel` del patrón necesita ser mayor que el número de `recommendedConfidence` para que se invoque una acción de regla de flujo de correo. El valor de `recommendedConfidence` es el nivel de confianza predeterminado que se usa en las reglas de flujo de correo que invoca una acción. Si quiere, puede cambiar manualmente la regla de flujo de correo para que, en su lugar, se invoque según el nivel de confianza del patrón.|
|

## <a name="for-more-information"></a>Más información

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
