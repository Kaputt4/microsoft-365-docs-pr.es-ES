---
title: Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos
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
description: Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6bd411411c3075259bd3b9fc74ec3f558171fce7
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526296"
---
# <a name="create-the-schema-for-exact-data-match-based-sensitive-information-types"></a>Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos

Puede crear el esquema y EDM SIT mediante el Asistente para usar [](#use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard) el esquema exacto de coincidencia de datos y el patrón de tipo de información [confidencial o manualmente](#create-exact-data-match-schema-manually-and-upload). También puede combinar ambos mediante un método para crear el esquema y editarlo posteriormente con el otro método.

Si no está familiarizado con SITS basado en EDM o su implementación, debe familiarizarse con:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

Un único esquema EDM se puede usar en varios tipos de información confidencial que usan la misma tabla de datos confidenciales. Puede crear hasta 10 esquemas EDM diferentes en un Microsoft 365 inquilino.

## <a name="working-with-specific-types-of-data"></a>Trabajar con tipos de datos específicos

Por motivos de rendimiento, es fundamental que use patrones que minimicen el número de coincidencias innecesarias. Por ejemplo, puede usar un tipo de información confidencial basado en la expresión regular.

`\b\w*\b`

Esto coincidiría con todas las palabras o números individuales de cualquier documento o correo electrónico. Esto provocaría que el servicio se sobrecargase con coincidencias y se perdera la detección de coincidencias verdaderas. El uso de patrones más precisos puede evitar esta situación. Estas son algunas recomendaciones para identificar la configuración correcta para algunos tipos comunes de datos.

**Direcciones de** correo electrónico: las direcciones de correo electrónico pueden ser fáciles de identificar, pero como son tan comunes en el contenido, pueden causar una carga significativa en el sistema si se usan como campo principal. Úsenlos solo como evidencia secundaria. Si deben usarse como evidencia principal, `From` `To` intente definir un tipo de información confidencial personalizado que use lógica para excluir su uso como o campos en los correos electrónicos y excluir aquellos con la dirección de correo electrónico de su empresa para reducir el número de cadenas innecesarias que deben coincidir.

**Teléfono:** los Teléfono pueden venir en muchos formatos diferentes, incluidos o excluidos los prefijos de país, los códigos de área y los separadores. Para reducir los falsos negativos mientras se mantiene la carga al mínimo, úsenlos solo como elementos secundarios, excluyan todos los separadores probables, como paréntesis y guiones, y solo incluyan en la tabla de datos confidenciales la parte que siempre estará presente en el número de teléfono.

**Nombres** de persona: no use los nombres de las personas como elementos principales si usa un tipo de información confidencial basado en una expresión regular como elemento de clasificación para este tipo de EDM, ya que son difíciles de distinguir de las palabras comunes.

Si debe usar un elemento principal difícil de identificar con un patrón específico, como un nombre de código de proyecto que podría generar muchas coincidencias que se procesarán, asegúrese de incluir palabras clave en el tipo de información confidencial que use como elemento de clasificación para el tipo de EDM. Por ejemplo, si usa nombres de código de proyecto que pueden ser palabras normales, `project` puede usar la palabra como evidencia adicional necesaria cerca del patrón basado en expresiones regulares del nombre del proyecto en el tipo confidencial usado como elemento de clasificación para el tipo EDM. O puede considerar el uso de un tipo confidencial basado en un diccionario normal como elemento de clasificación para su SIT de EDM.

Al intentar hacer coincidir cadenas numéricas, especifique los intervalos permitidos de números, como el número de dígitos o los dígitos iniciales, si se conoce. Si necesita coincidir con un intervalo de números relativamente flexible, puede usar palabras clave en la SIT base para reducir el número de coincidencias. Por ejemplo, si intenta hacer coincidir los números de cuenta que constan de 7 a 11 dígitos, `account`agregue las palabras , , `customer``acct.` al SIT como evidencia adicional necesaria. Esto reduce la probabilidad de coincidencias innecesarias que podrían provocar que EDM procese los límites de coincidencias.

Si un campo que necesita usar como elemento principal sigue un patrón simple que puede causar un gran número de coincidencias y no puede agregar la presencia de palabras clave como evidencia adicional en el tipo de información confidencial, también puede requerir un número mínimo de repeticiones de ese patrón. Por ejemplo, puede usar un tipo de información confidencial personalizado definido de la siguiente manera para detectar al menos otros 29 números de cinco dígitos que rodean un número potencial de cinco dígitos que coincida con EDM:

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

En algunos casos, es posible que tenga que identificar determinados números de identificación de cuentas o registros que por motivos históricos no siguen un patrón estandarizado. Por ejemplo, `Medical Record Numbers` puede estar compuesto de muchas permutaciones diferentes de letras y números dentro de la misma organización. Aunque al principio podría ser difícil identificar un patrón, una inspección más estrecha a menudo te permite restringir un patrón que describe todos los valores válidos sin causar un número excesivo de coincidencias no válidas. Por ejemplo, se puede detectar que "todas las MRN tienen al menos siete caracteres de longitud, tienen al menos dos dígitos numéricos y, si tienen alguna letra, empiezan por uno". La creación de una expresión regular basada en estos criterios debería permitir minimizar coincidencias innecesarias al capturar todos los valores deseados, y un análisis posterior podría permitir una mayor precisión al definir patrones independientes que describen diferentes formatos.

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Utilice el esquema de coincidencia de datos exactos y el asistente para tipos de información confidencial

Puede usar este asistente para simplificar el proceso de creación de archivos de esquema.

## <a name="pre-requisites"></a>Requisitos previos

- Realice los pasos descritos en [Exportar datos de origen para el tipo exacto de información confidencial basada en coincidencias de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type).

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Usar el Esquema de coincidencia exacta de datos y el asistente para información de tipo confidencial

1. En el Microsoft 365 de cumplimiento del espacio empresarial vaya a **Clasificación de** >  **datosExact datos coincide** >  **con los esquemas DEEDM**.

2. Elija **Crear esquema EDM** para abrir el flotante de configuración del asistente de esquemas.

   ![Menú desplegable de configuración del Asistente para la creación de esquemas de EDM.](../media/edm-schema-wizard-1.png)

3. Rellene con un **Nombre** y una **Descripción apropiados**.

4. Elija **Omitir delimitadores y puntuación** para todos los campos de esquema si desea ese comportamiento para todo el esquema. Para obtener más información sobre cómo configurar EDM para omitir mayúsculas o minúsculas, consulte [Using the caseInsensitive and ignoredDelimiters fields](#using-the-caseinsensitive-and-ignoreddelimiters-fields) para obtener más información sobre esta característica.

5. Rellene los valores deseados para el **Campo #1 del esquema** y agregue más campos según sea necesario. Cada campo de esquema debe ser idéntico a los encabezados de columna del archivo de origen de información confidencial.

6. Si lo desea, establezca los valores por campo para:
    1. **El campo es de búsqueda**
    1. **Field no tiene mayúsculas de minúsculas**
    1. **Elegir delimitadores y puntuación para omitir para este campo**
    1. **Escriba delimitadores personalizados y puntuación para este campo**

   > [!IMPORTANT]
   > Al menos uno, pero no más de cinco de los campos de su esquema deben ser designados como de búsqueda.

7. Seleccione **Guardar**. El esquema ahora se mostrará y estará disponible para su uso.

   > [!IMPORTANT]
   > Si desea eliminar un esquema, y ya está asociado a un tipo de información sensible EDM, primero debe borrar el tipo de información confidencial EDM, luego puede eliminar el esquema. Al eliminar un esquema que tiene un almacén de datos asociado también se elimina el almacén de datos en 24 horas.

## <a name="export-of-the-edm-schema-file-in-xml-format"></a>Exportación del archivo de esquema EDM en formato XML

Si creó el esquema EDM en el Asistente para esquema de EDM, debe exportar el archivo de esquema de EDM en formato XML. Lo necesitará en la tabla [Hash y cargará](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) la tabla de origen de información confidencial para la fase exacta de tipos de información confidencial de coincidencia de datos.

1. [Conéctese al Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Para exportar el archivo de esquema de EDM, use esta sintaxis:

   ```powershell
   $Schema = Get-DlpEdmSchema -Identity "[your EDM Schema name]"
   Set-Content -Path ".\Schemafile.xml" -Value $Schema.EdmSchemaXML
   ```

3. Guarde este archivo para su uso posterior.

## <a name="create-exact-data-match-schema-manually-and-upload"></a>Crear un esquema de coincidencia de datos exacto manualmente y cargarlo

En el archivo de esquema, configure una entrada para cada columna de la tabla de origen de información confidencial con la sintaxis:

```xml
<Field name="FieldName" searchable="true/false" caseInsensitive="true/false" ignoredDelimiters="delimiter characters" />
```

### <a name="using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>Uso de los campos caseInsensitive y ignoredDelimiters

El siguiente ejemplo XML de esquema usa *los campos caseInsensitive* y *ignoredDelimiters* .

Al incluir el *campo caseInsensitive* `true` establecido en el valor de en la definición de esquema, EDM no excluirá un elemento en función de las diferencias entre mayúsculas y minúsculas. Por ejemplo, EDM verá que los valores **FOO-1234** y **fOo-1234** son idénticos para el `PatientID` campo.

Al incluir el campo *ignoredDelimiters* con caracteres admitidos, EDM omitirá esos caracteres. Por lo tanto, EDM verá que los **valores FOO-1234** y **FOO#1234** son idénticos para el `PatienID` campo.

En este ejemplo, `caseInsensitive` `ignoredDelimiters` donde ambos y se usan, EDM vería **FOO-1234** y **fOo#1234** como idénticos y clasificaría el elemento como un tipo de información confidencial de registro de pacientes.

Ambos parámetros se usan por campo.

> [!IMPORTANT]
> Si configura espacios *que* se omitirán, esto solo será eficaz para las columnas de campo principal y para las que se define un tipo de información confidencial que puede detectar cadenas de varias palabras. De lo contrario, se realizará la comparación con cada palabra individual del contenido que se está analizando.

La *marca ignoredDelimiters* admite cualquier carácter no alfanumérico, estos son algunos ejemplos:

- \.
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

El indicador `ignoredDelimiters` no es compatible con:

- caracteres 0-9
- A-Z
- a-z
- \"
- \,

> [!IMPORTANT]
> Al definir el tipo de información confidencial de EDM, *ignoreDelimiters* no afectará al modo en que el tipo de información confidencial Classification asociado al elemento principal de un patrón EDM identifica el contenido de un elemento. Por lo tanto, si configura *ignoreDelimiters* para un campo que permite buscar, debe asegurarse de que el tipo de información confidencial usado para un elemento principal basado en ese campo elija cadenas con y sin esos caracteres presentes.
>
> El número de columnas de la tabla de origen de información confidencial y el número de campos del esquema deben coincidir, el orden no importa.

1. Defina el esquema en formato XML (similar al ejemplo siguiente). Asigne un nombre a **edm.xml** archivo de esquema y configúrelo de forma que para cada columna de la tabla de origen de información confidencial, haya una línea que use la sintaxis:

      `\<Field name="" searchable=""/\>`.

      - Use nombres de columna para los valores *Nombre de campo*.
      - Use *searchable="true"* para los campos que desea que se puedan buscar y los campos principales hasta un máximo de 5 campos. Al menos un campo se debe poder utilizar en búsquedas.

      Por ejemplo, el siguiente archivo XML define el esquema para una base de datos de registros de pacientes, con cinco campos especificados para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*.

      (Puede copiar, modificar y usar nuestro ejemplo).

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

   Una vez que haya creado el archivo de esquema de EDM en formato XML, debe cargarlo en el servicio en la nube.

2. [Conéctese al Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).

3. Para cargar el esquema de base de datos, ejecute el siguiente comando:

      ```powershell
      New-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
      ```

      Se le pedirá que confirme lo siguiente:

      > Confirmar
      >
      > ¿Está seguro de que desea realizar esta acción?
      >
      > Se importará el nuevo esquema EDM para el almacén de datos "registrospacientes".
      >
      > ¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):

   > [!TIP]
   > Si desea que los cambios se produzcan sin confirmación, no use `-Confirm:$true` el paso 3.

> [!NOTE]
> La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos. La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.

## <a name="next-step"></a>Paso siguiente

- [Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)