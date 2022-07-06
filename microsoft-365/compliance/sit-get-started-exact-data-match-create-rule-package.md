---
title: Crear un paquete de reglas o tipo de información confidencial de coincidencia exacta de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Crear un paquete de reglas o tipo de información confidencial de coincidencia exacta de datos
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16da97f249eff856fd1b0e671d71d813b3cbac73
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66628515"
---
# <a name="create-exact-data-match-sensitive-information-typerule-package"></a>Crear un paquete de reglas o tipo de información confidencial de coincidencia exacta de datos

Puede crear un tipo de información confidencial (SIT) de coincidencia exacta de datos (EDM) mediante [el esquema EDM y el asistente sit](#use-the-edm-schema-and-sit-wizard) en el Centro de cumplimiento o crear [manualmente](#create-a-rule-package-manually) el archivo XML del paquete de reglas. También puede combinar ambos mediante un método para crear el esquema y editarlo posteriormente con el otro método.

Si no está familiarizado con SITS basado en EDM o su implementación, debe familiarizarse con:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtenga información sobre tipos de información confidencial basada en coincidencias de datos exactas](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

## <a name="use-the-edm-schema-and-sit-wizard"></a>Uso del esquema EDM y el Asistente para SIT

Puede usar este asistente para crear los archivos de tipo de información confidencial (SIT) para ayudar a simplificar el proceso.

Un tipo de información confidencial de EDM se compone de uno o varios patrones. Cada patrón describe una combinación de evidencia (campos del esquema) que se usará para identificar contenido confidencial en un documento o correo electrónico.

## <a name="pre-requisites"></a>Requisitos previos

Siga los pasos descritos en estos artículos:

1. [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
2. [Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)
3. [Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)

- Si va a crear un tipo de información confidencial de EDM mediante el asistente o el archivo XML del paquete de reglas a través de PowerShell, debe tener permisos de administrador global o administrador de cumplimiento para crear, probar e implementar un tipo de información confidencial personalizada a través de la interfaz de usuario. Consulte [Acerca de los roles de administrador en Office 365](/office365/admin/add-users/about-admin-roles).
- Identifique uno de los SIT integrados que se van a usar como tipo de información confidencial de elementos principales.
  - Si ninguno de los tipos de información confidencial integrados coincidirá con los datos de la columna seleccionada, tendrá que crear un tipo de información confidencial personalizado que lo haga.
  - Si seleccionó la opción Delimitadores omitidos para la columna de elemento principal en el esquema, asegúrese de que la SIT personalizada que cree coincidirá con los datos con y sin los delimitadores seleccionados.
  - Si usa un SIT integrado, asegúrese de que detectará exactamente las cadenas que desea seleccionar y no incluirá ningún carácter circundante ni excluirá ninguna parte válida de la cadena tal como se almacena en la tabla de información confidencial.

Consulte [Definiciones de entidades de tipo de información confidencial](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) y [Creación de tipos de información confidencial personalizados en el Centro de cumplimiento](create-a-custom-sensitive-information-type.md).

### <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Usar el Esquema de coincidencia exacta de datos y el asistente para información de tipo confidencial

1. En el portal de cumplimiento Microsoft Purview del inquilino, vaya a **Clasificación** >  de **datos Coincidencias exactas de datos**.

2. Elija **Tipos de información confidencial EDM** y **Crear Tipo de información confidencial EDM** para abrir el asistente de configuración de tipos de información confidencial.

3. Elija **Elegir un esquema EDM existente** y elija el esquema que creó en [Crear el esquema para los tipos de información confidencial basados en coincidencias de datos exactas](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types).

4. Elija **Siguiente** y seleccione **Crear patrón**.

5. Elija el **Nivel de confianza** y **Elemento primario**. Para más información sobre los niveles de confianza, consulte [Información sobre los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types).

6. Elija el **tipo de información confidencial del elemento Principal** con el que asociarlo para definir con qué texto del documento se comparará con todos los valores del campo del elemento principal. Consulte [Tipo de información confidencial según definiciones de entidades](sensitive-information-type-entity-definitions.md) para obtener más información sobre los tipos de información confidencial disponibles.

   > [!IMPORTANT]
   > Seleccione un tipo de información confidencial que coincida estrechamente con el formato del contenido que desea encontrar. Seleccionar un tipo de información confidencial que coincida con contenido innecesario, como uno que coincida con todas las cadenas de texto o todos los números, puede provocar una carga excesiva en el sistema, lo que podría provocar que se perdiese información confidencial.

7. Elija **los elementos auxiliares** y las opciones de coincidencia.

8. Elija **Listo** y **Siguiente**.

9. Elija su **Nivel de confianza y la proximidad de su personaje**. Este será el valor predeterminado para todo el tipo de información confidencial de EDM.

10. Elija **Crear patrón** si desea crear patrones adicionales para el tipo de información confidencial de EDM.

11. Elija **Siguiente** y rellene con un **Nombre** y una **Descripción para los administradores**.

12. Revise y elija **Enviar**.

### <a name="edit-or-delete-the-sensitive-information-type-pattern"></a>Editar o eliminar el patrón de tipo de información confidencial

1. Abra **Clasificación de** datos del Centro  >  de **cumplimiento** > **Coincidencias exactas de datos**.

2. Elija **tipos de información confidencial de EDM**.

3. Elija el sit de EDM que desea editar.

4. Elija **Edit EDM sensitive info type (Editar tipo de información confidencial de EDM** ) o **Delete EDM sensitive info type (Eliminar tipo de información confidencial de EDM** ) en el control flotante.

## <a name="working-with-specific-types-of-data"></a>Trabajar con tipos de datos específicos

Por motivos de rendimiento, es fundamental usar patrones que minimicen el número de coincidencias innecesarias. Por ejemplo, puede usar un tipo de información confidencial basado en la expresión regular.

`\b\w*\b`

Esto coincidiría con cada palabra o número individual en cualquier documento o correo electrónico. Esto provocaría que el servicio se sobrecargara con coincidencias y que se perdiese la detección de coincidencias verdaderas. El uso de patrones más precisos puede evitar esta situación. Estas son algunas recomendaciones para identificar la configuración adecuada para algunos tipos comunes de datos.

**Direcciones de correo electrónico**: las direcciones de correo electrónico pueden ser fáciles de identificar, pero como son tan comunes en el contenido, pueden provocar una carga significativa en el sistema si se usan como campo principal. Úselas solo como evidencia secundaria. Si se deben usar como evidencia principal, intente definir un tipo de información confidencial personalizada que use lógica para excluir su uso como `From` o `To` campos en los correos electrónicos y excluir aquellos con la dirección de correo electrónico de su empresa para reducir el número de cadenas innecesarias que deben coincidir.

**Números de teléfono**: los números de teléfono pueden tener muchos formatos diferentes, incluidos o excluidos prefijos de país, códigos de área y separadores. Para reducir los falsos negativos mientras se mantiene la carga al mínimo, úselos solo como elementos secundarios, excluya todos los separadores probables, como paréntesis y guiones, y solo incluya en la tabla de datos confidenciales la parte que siempre estará presente en el número de teléfono.

**Nombres de persona**: no use los nombres de persona como elementos principales si usa un tipo de información confidencial basado en una expresión regular como elemento de clasificación para este tipo EDM, ya que son difíciles de distinguir de palabras comunes.

Si debe usar un elemento principal que sea difícil de identificar con un patrón específico, como un nombre de código de proyecto que podría generar muchas coincidencias para procesarse, asegúrese de incluir palabras clave en el tipo de información confidencial que usa como elemento de clasificación para el tipo EDM. Por ejemplo, si usa nombres de código de proyecto que pueden ser palabras regulares, puede usar la palabra `project` como evidencia adicional necesaria cerca del patrón basado en expresiones regulares del nombre del proyecto en el tipo confidencial que se usa como elemento de clasificación para el tipo EDM. O bien, podría considerar el uso de un tipo confidencial basado en un diccionario normal como elemento de clasificación para el SIT de EDM.

Al intentar hacer coincidir cadenas numéricas, especifique los intervalos permitidos de números, como el número de dígitos o los dígitos iniciales, si se conocen. Si necesita coincidir con un intervalo de números relativamente flexible, puede usar palabras clave en el SIT base para reducir el número de coincidencias. Por ejemplo, si intenta hacer coincidir los números de cuenta que constan de entre 7 y 11 dígitos, agregue las palabras `account`, `customer`, `acct.` a SIT como evidencia adicional necesaria. Esto reduce la probabilidad de coincidencias innecesarias que podrían hacer que EDM procese la superación de los límites de coincidencias.

Si un campo que necesita usar como elemento principal sigue un patrón simple que puede provocar un gran número de coincidencias y no puede agregar la presencia de palabras clave como evidencia adicional en el tipo de información confidencial, también puede requerir un número mínimo de repeticiones de ese patrón. Por ejemplo, podría usar un tipo de información confidencial personalizado definido de la siguiente manera para detectar al menos otros 29 números de cinco dígitos que rodean un número potencial de cinco dígitos para que coincida con EDM:

```xml
 <Entity id="98703510-18b3-43d4-961f-15317594beb7"
                  patternsProximity="300"
                  recommendedConfidence="85"
                  relaxProximity="false">
                  <Pattern confidenceLevel="85"
                              proximity="300">
                              <IdMatch idRef="MRN"/>
                              <Match idRef="30 AccountNrs"
                                    minCount="30"
                                    proximity="3000"
                                    uniqueResults="true"/>
                  </Pattern>
      </Entity>
      <Regex id="30 AccountNrs">\d{5}</Regex>
```

En algunos casos, es posible que tenga que identificar determinados números de identificación de cuenta o registro que, por motivos históricos, no siguen un patrón estandarizado. Por ejemplo, `Medical Record Numbers` se puede componer de muchas permutaciones diferentes de letras y números dentro de la misma organización. Aunque al principio podría ser difícil identificar un patrón, una inspección más estrecha a menudo permite restringir un patrón que describe todos los valores válidos sin provocar un número excesivo de coincidencias no válidas. Por ejemplo, se podría detectar que "todos los MRN tienen al menos siete caracteres de longitud, tienen al menos dos dígitos numéricos y, si tienen letras en ellos, comienzan por uno". La creación de una expresión regular basada en estos criterios debe permitir minimizar las coincidencias innecesarias al capturar todos los valores deseados, y un análisis adicional podría permitir una mayor precisión mediante la definición de patrones independientes que describen distintos formatos.

## <a name="create-a-rule-package-manually"></a>Creación manual de un paquete de reglas

Este procedimiento muestra cómo crear un archivo en formato XML denominado paquete de reglas (con codificación Unicode) y, a continuación, cargarlo en Microsoft Purview mediante cmdlets de PowerShell de cumplimiento de seguridad &.

> [!NOTE]
> Si el SIT al que se asigna puede detectar pruebas corroborativas de varias palabras, los elementos secundarios que defina en un paquete de reglas creado manualmente se pueden asignar a SIT. Por ejemplo, el nombre `John Smith` no coincidiría como elemento secundario porque se compararía `John` y `Smith` se encontraría en el contenido por separado con el término `John Smith` cargado en uno de los campos, si ese campo de evidencia corroborativa no se asignara a una SIT que pueda detectar ese patrón.
>
> Hay un límite de 10 paquetes de reglas en un inquilino de Microsoft 365. Dado que un paquete de reglas puede contener un número arbitrario de tipos de información confidencial, puede evitar crear un nuevo paquete de reglas cada vez que desee definir un nuevo tipo de información confidencial mediante este método, en su lugar exportar un paquete de reglas existente y agregar los tipos de información confidencial al XML antes de volver a cargarlo.

1. Cree un paquete de reglas en formato XML (con codificación Unicode), similar al siguiente ejemplo: (Puede copiar, modificar y usar nuestro ejemplo).

   Al configurar el paquete de reglas, asegúrese de hacer referencia correctamente al archivo de tabla de origen de información confidencial delimitada .csv, .tsv o canalización (|) y **edm.xml** archivo de esquema. Puede copiar, modificar y usar nuestro ejemplo. En este xml de ejemplo, los siguientes campos deben personalizarse para crear el tipo confidencial de EDM:

   - **RulePack id y ExactMatch id**: use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) para generar un GUID.

   - **Datastore**: este campo especifica el almacén de datos de búsqueda de EDM que se va a usar. Proporcione el nombre del origen de datos del esquema EDM configurado.

   - **idMatch**: este campo señala al elemento principal para EDM.
   - **Coincidencias**: especifica el campo que se va a usar en la búsqueda exacta. Se proporciona un nombre de campo que se puede buscar en el esquema EDM para DataStore.
   - **Clasificación**: este campo especifica la coincidencia del tipo de información confidencial que desencadena la búsqueda de EDM. Puede usar el nombre o GUID de un tipo de información confidencial integrado o personalizado existente.

   > [!NOTE]
   > Tenga en cuenta que cualquier cadena que coincida con la SIT proporcionada se aplicará un hash y se comparará con todas las entradas de la tabla de origen de información confidencial. Para evitar problemas de rendimiento si elige un SIT personalizado para el elemento de clasificación, no use uno que coincida con un gran porcentaje de contenido. Por ejemplo, uno que coincida con "cualquier número" o "cualquier palabra de cinco letras". Puede diferenciarla agregando palabras clave auxiliares o incluyendo el formato en la definición de la clasificación personalizada SIT.

   - **Coincidencia**: este campo apunta a pruebas adicionales encontradas en la proximidad de idMatch.
   - **Coincidencias**: proporcione cualquier nombre de campo en el esquema EDM para DataStore.
   - **Recurso idRef:** En esta sección se especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales.
     - Proporcione guid para exactmatch id.
     - **Nombre** &  **descripción**: personalice según sea necesario.

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. Cargue el paquete de reglas ejecutando el siguiente comando de PowerShell:

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('.\\rulepack.xml'))
   ```

> [!NOTE]
> La sintaxis del archivo de paquete de reglas es la misma que para otros tipos de información confidencial. Para obtener detalles completos sobre la sintaxis del archivo de paquete de reglas y para obtener opciones de configuración adicionales, y para obtener instrucciones sobre cómo modificar y eliminar tipos de información confidencial mediante PowerShell, [cree un tipo de información confidencial personalizado mediante PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md#create-a-custom-sensitive-information-type-using-powershell).

## <a name="next-step"></a>Paso siguiente

- [Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)
