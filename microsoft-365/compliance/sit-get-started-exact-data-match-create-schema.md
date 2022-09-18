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
ms.openlocfilehash: 34ae4d9150ec29fdac4184c30f053b18ca58df74
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799360"
---
# <a name="create-the-schema-for-exact-data-match-based-sensitive-information-types"></a>Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos

## <a name="applies-to"></a>Se aplica a

- Experiencia clásica

Puede crear el esquema y EDM SIT mediante [el Asistente para usar el esquema exacto de coincidencia de datos y el patrón de tipo de información confidencial](#use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard) o [manualmente](#create-exact-data-match-schema-manually-and-upload). También puede combinar ambos mediante un método para crear el esquema y editarlo posteriormente con el otro método.

Si no está familiarizado con SITS basado en EDM o su implementación, debe familiarizarse con:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

Un único esquema EDM se puede usar en varios tipos de información confidencial que usan la misma tabla de datos confidenciales. Puede crear hasta 10 esquemas EDM diferentes en un inquilino de Microsoft 365.


## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Utilice el esquema de coincidencia de datos exactos y el asistente para tipos de información confidencial

Puede usar este asistente para simplificar el proceso de creación de archivos de esquema.

## <a name="pre-requisites"></a>Requisitos previos

- Realice los pasos descritos en [Exportación de datos de origen para obtener información confidencial basada en coincidencias exactas de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type).

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Usar el Esquema de coincidencia exacta de datos y el asistente para información de tipo confidencial

1. En la portal de cumplimiento Microsoft Purview del inquilino, vaya a **Clasificación** >  de **datos Datos exactos que coinciden con los** > **esquemas EDM**.

2. Elija **Crear esquema EDM** para abrir el flotante de configuración del asistente de esquemas.

   ![Control flotante de configuración del Asistente para la creación de esquemas de EDM.](../media/edm-schema-wizard-1.png)

3. Rellene con un **Nombre** y una **Descripción apropiados**.

4. Elija **Omitir delimitadores y puntuación para todos los campos de esquema** si desea ese comportamiento para todo el esquema. Para obtener más información sobre cómo configurar EDM para omitir mayúsculas y minúsculas o delimitadores, consulte [Uso de los campos caseInsensitive e ignoreDelimiters](#using-the-caseinsensitive-and-ignoreddelimiters-fields) para obtener más detalles sobre esta característica.

5. Rellene los valores deseados para el **Campo #1 del esquema** y agregue más campos según sea necesario. Cada campo de esquema debe ser idéntico a los encabezados de columna del archivo de origen de información confidencial.

6. Si lo desea, establezca los valores por campo para:
    1. **El campo se puede buscar**
    1. **El campo no distingue mayúsculas de minúsculas**
    1. **Elija delimitadores y signos de puntuación para omitir este campo.**
    1. **Escriba delimitadores y signos de puntuación personalizados para este campo.**

   > [!IMPORTANT]
   > Al menos uno, pero no se deben designar más de diez campos de esquema como búsqueda.

7. Seleccione **Guardar**. El esquema ahora aparecerá en la lista y estará disponible para su uso.

   > [!IMPORTANT]
   > Si desea eliminar un esquema, y ya está asociado a un tipo de información sensible EDM, primero debe borrar el tipo de información confidencial EDM, luego puede eliminar el esquema. Al eliminar un esquema que tiene asociado un almacén de datos, también se elimina el almacén de datos en un plazo de 24 horas.

## <a name="export-of-the-edm-schema-file-in-xml-format"></a>Exportación del archivo de esquema EDM en formato XML

Si creó el esquema EDM en el Asistente para esquemas EDM, debe exportar el archivo de esquema EDM en formato XML. Lo necesitará en hash [y cargará la tabla de origen de información confidencial para obtener datos exactos que coincidan con la fase de tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) .

1. [Conéctese al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)

2. Para exportar el archivo de esquema EDM, use esta sintaxis:

   ```powershell
   $Schema = Get-DlpEdmSchema -Identity "[your EDM Schema name]"
   Set-Content -Path ".\Schemafile.xml" -Value $Schema.EdmSchemaXML
   ```

3. Guarde este archivo para su uso posterior.

## <a name="create-exact-data-match-schema-manually-and-upload"></a>Creación manual del esquema de coincidencia de datos exacto y carga

En el archivo de esquema, configure una entrada para cada columna de la tabla de origen de información confidencial mediante la sintaxis :

```xml
<Field name="FieldName" searchable="true/false" caseInsensitive="true/false" ignoredDelimiters="delimiter characters" />
```

### <a name="using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>Uso de los campos caseInsensitive e ignoreDelimiters

El siguiente ejemplo XML de esquema usa los campos *caseInsensitive* y *ignoreDelimiters* .

Al incluir el campo *caseInsensitive* establecido en el valor de en la definición de `true` esquema, EDM no excluirá un elemento en función de las diferencias de mayúsculas y minúsculas. Por ejemplo, EDM verá los valores **FOO-1234** y **fOo-1234** como idénticos para el `PatientID` campo.

Cuando se incluye el campo *ignoreDelimiters* con caracteres admitidos, EDM omitirá esos caracteres. Por lo tanto, EDM verá los valores **FOO-1234** y **FOO#1234** como idénticos para el `PatienID` campo.

En este ejemplo, donde `caseInsensitive` se usan y `ignoredDelimiters` , EDM vería **FOO-1234** y **fOo#1234** como idénticos y clasificaría el elemento como un tipo de información confidencial de registro de pacientes.

Ambos parámetros se usan por campo.

> [!IMPORTANT]
> Si configura *espacios* para que se ignoren, esto solo será efectivo para las columnas de campo principal y para las que se define un tipo de información confidencial que puede detectar cadenas de varias palabras. De lo contrario, la comparación se realizará con cada palabra individual del contenido que se está analizando.

La marca *ignoredDelimiters* admite cualquier carácter no alfanumérico; estos son algunos ejemplos:

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
> Al definir el tipo de información confidencial de EDM, *ignoreDelimiters* no afectará a cómo el tipo de información confidencial Clasificación asociado al elemento principal de un patrón EDM identifica el contenido de un elemento. Por lo tanto, si configura *ignoreDelimiters* para un campo que permite búsquedas, debe asegurarse de que el tipo de información confidencial que se usa para un elemento principal basado en ese campo seleccionará cadenas con y sin esos caracteres presentes.
>
> El número de columnas de la tabla de origen de información confidencial y el número de campos del esquema deben coincidir, el orden no importa.

Los caracteres que se usan como *separadores de tokens* se comportan de forma diferente que los demás delimitadores. Estos son algunos ejemplos:
- \ (espacio)
- \\T
- \,
- \.
- \;
- \?
- \!
- \\R
- \\N  

Cuando se incluye un *separador de tokens*, EDM interrumpirá el token donde se encuentra el separador. Por ejemplo, EDM verá el valor **Middle-Last Name** en **Middle-Last** y **Name** para el `LastName` campo. Si se incluye *ignoreDelimiters* para el `LastName` campo con el carácter '-', esa acción solo se produce después de que se rompa el valor. Al final, EDM vería los siguientes valores **MiddleLast** y **Name**.

Para usar los siguientes caracteres como *ignoreDelimiters* y no *separadores de tokens*, debe asociarse al campo una SIT que coincida con el formato correspondiente. Por ejemplo, una SIT que detecta una cadena de varias palabras con guiones en ella debe asociarse al `LastName` campo.
- \.
- \;
- \!
- \?
- \\

Es posible asociar SIT a elementos secundarios mediante PowerShell.

1. Defina el esquema en formato XML (similar al ejemplo siguiente). Asigne a este archivo de esquema **el nombreedm.xml** y configúrelo de modo que para cada columna de la tabla de origen de información confidencial, haya una línea que use la sintaxis :

      `\<Field name="" searchable=""/\>`.

      - Use nombres de columna para los valores *Nombre de campo*.
      - Use *searchable="true"* para los campos en los que desea que se puedan buscar y los campos primarios hasta un máximo de 5 campos. Al menos un campo se debe poder utilizar en búsquedas.

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

   Una vez que haya creado el archivo de esquema EDM en formato XML, tendrá que cargarlo en el servicio en la nube.

2. [Conéctese al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)

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
   > Si desea que los cambios se produzcan sin confirmación, no use `-Confirm:$true` en el paso 3.

> [!NOTE]
> La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos. La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.

## <a name="next-step"></a>Paso siguiente

- [Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)
