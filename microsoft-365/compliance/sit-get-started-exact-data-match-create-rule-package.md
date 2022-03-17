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
ms.openlocfilehash: e44d18bc1a779ace95fb2f64171ff0bf91de57ed
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526046"
---
# <a name="create-exact-data-match-sensitive-information-typerule-package"></a>Crear un paquete de reglas o tipo de información confidencial de coincidencia exacta de datos

Puede crear un tipo de información confidencial (SIT) de coincidencia exacta de datos (EDM) con el esquema [EDM](#use-the-edm-schema-and-sit-wizard) y el asistente SIT en el Centro de cumplimiento o crear manualmente el archivo XML del paquete de [reglas.](#create-a-rule-package-manually) También puede combinar ambos mediante un método para crear el esquema y editarlo posteriormente con el otro método.

Si no está familiarizado con sits basado en EDM o su implementación, debe familiarizarse con:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

## <a name="use-the-edm-schema-and-sit-wizard"></a>Usar el esquema EDM y el asistente sit

Puede usar este asistente para crear los archivos de tipo de información confidencial (SIT) para simplificar el proceso.

Un tipo de información confidencial de EDM se compone de uno o más patrones. Cada patrón describe una combinación de evidencias (campos del esquema) que se usarán para identificar contenido confidencial en un documento o correo electrónico.

## <a name="pre-requisites"></a>Requisitos previos

Realice los pasos descritos en estos artículos:

1. [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
2. [Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)
3. [Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)

- Tanto si va a crear un tipo de información confidencial de EDM con el asistente o el archivo XML del paquete de reglas a través de PowerShell, debe tener permisos de administrador global o administrador de cumplimiento para crear, probar e implementar un tipo de información confidencial personalizada a través de la interfaz de usuario. Consulta [Acerca de los roles de administrador en Office 365](/office365/admin/add-users/about-admin-roles).
- Identifique uno de los SIT integrados que se usarán como tipo de información confidencial de elementos primarios.
  - Si ninguno de los tipos de información confidencial integrados coincidirá con los datos de la columna seleccionada, tendrá que crear un tipo de información confidencial personalizado que lo haga.
  - Si seleccionó la opción Delimitadores ignorados para la columna de elemento principal del esquema, asegúrese de que el SIT personalizado que cree coincida con los datos con y sin los delimitadores seleccionados.
  - Si usa un SIT integrado, asegúrese de que detectará exactamente las cadenas que desea seleccionar y no incluirá caracteres circundantes ni excluirá ninguna parte válida de la cadena tal como se almacena en la tabla de información confidencial.

Vea [Definiciones de entidad de tipo de información confidencial](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) y [Crear tipos de información confidencial personalizados en el Centro de cumplimiento](create-a-custom-sensitive-information-type.md).

### <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Usar el Esquema de coincidencia exacta de datos y el asistente para información de tipo confidencial

1. En el Centro de cumplimiento de Microsoft 365 para su inquilino vaya a **Clasificación de datos** > **coincidencias de datos exactos**.

2. Elija **Tipos de información confidencial EDM** y **Crear Tipo de información confidencial EDM** para abrir el asistente de configuración de tipos de información confidencial.

3. Elija **Elegir un esquema EDM** existente y elija el esquema que creó en Crear el esquema para los tipos exactos de información confidencial basada en coincidencias [de datos](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types).

4. Elija **Siguiente** y seleccione **Crear patrón**.

5. Elija el **Nivel de confianza** y **Elemento primario**. Para obtener más información sobre los niveles de confianza, vea [Learn about sensitive information types](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types).

6. Elija el **tipo de** información confidencial del elemento primario con el que asociarlo para definir el texto del documento que se comparará con todos los valores del campo de elemento principal. Consulte [Tipo de información confidencial según definiciones de entidades](sensitive-information-type-entity-definitions.md) para obtener más información sobre los tipos de información confidencial disponibles.

   > [!IMPORTANT]
   > Seleccione un tipo de información confidencial que coincida estrechamente con el formato del contenido que desea buscar. Seleccionar un tipo de información confidencial que coincida con contenido innecesario, como uno que coincida con todas las cadenas de texto, o todos los números, puede provocar una carga excesiva en el sistema, lo que podría provocar la pérdida de información confidencial. Vea la sección Procedimientos recomendados del artículo Introducción a la coincidencia exacta de datos de esta documentación para obtener recomendaciones sobre cómo seleccionar un tipo de información confidencial que se va a usar aquí.

7. Elija los **elementos de soporte técnico y** las opciones de coincidencia.

8. Elija **Listo** y **Siguiente**.

9. Elija su **Nivel de confianza y la proximidad de su personaje**. Este será el valor predeterminado para todo el tipo de información confidencial de EDM.

10. Elige **Crear patrón** si quieres crear patrones adicionales para el tipo de información confidencial de EDM.

11. Elija **Siguiente** y rellene con un **Nombre** y una **Descripción para los administradores**.

12. Revise y elija **Enviar**.

### <a name="edit-or-delete-the-sensitive-information-type-pattern"></a>Editar o eliminar el patrón de tipo de información confidencial

1. Open **Compliance centerData** >  **classificationExact** >  **data matches**.

2. Elige **tipos de información confidencial de EDM**.

3. Elija el SIT de EDM que desea editar.

4. Elija **Editar tipo de información confidencial de EDM** o Eliminar el tipo de información confidencial **de EDM** del control desplegable.

## <a name="create-a-rule-package-manually"></a>Crear un paquete de reglas manualmente

Este procedimiento muestra cómo crear un archivo en formato XML denominado paquete de reglas (con codificación Unicode) y, a continuación, cargarlo en Microsoft 365 mediante cmdlets de PowerShell del Centro de cumplimiento.

> [!NOTE]
> Si la SIT a la que asigna puede detectar pruebas corroborativas de varias palabras, los elementos secundarios que defina en un paquete de reglas creado manualmente se pueden asignar al SIT. Por ejemplo, `John Smith` `John` `Smith` `John Smith` el nombre no coincidiría como un elemento secundario porque se compararía y se encontraría en el contenido por separado con el término cargado en uno de los campos, si ese campo de evidencia corroborativa no se asigna a un SIT que pueda detectar ese patrón.
>
> Hay un límite de 10 paquetes de reglas en un Microsoft 365 inquilino. Dado que un paquete de reglas puede contener un número arbitrario de tipos de información confidencial, puede evitar crear un nuevo paquete de reglas cada vez que desee definir un nuevo tipo de información confidencial con este método, en su lugar exporte un paquete de reglas existente y agregue los tipos de información confidencial al XML antes de volver a cargarlo.

1. Cree un paquete de reglas en formato XML (con codificación Unicode), similar al siguiente ejemplo: (Puede copiar, modificar y usar nuestro ejemplo).

   Al configurar el paquete de reglas, asegúrese de hacer referencia correctamente al archivo de tabla de origen de información confidencial delimitado .csv, .tsv o pipe (|) y al archivo de esquemaedm.xmlinformación **** confidencial. Puede copiar, modificar y usar nuestro ejemplo. En este xml de ejemplo, es necesario personalizar los siguientes campos para crear el tipo confidencial de EDM:

   - **RulePack id y ExactMatch id**: use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) para generar un GUID.

   - **Datastore**: este campo especifica el almacén de datos de búsqueda de EDM que se va a usar. Se proporciona el nombre del origen de datos del esquema EDM configurado.

   - **idMatch**: este campo señala al elemento principal para EDM.
   - **Coincidencias**: especifica el campo que se usará en la búsqueda exacta. Se proporciona un nombre de campo que se puede buscar en el esquema EDM para DataStore.
   - **Clasificación**: este campo especifica la coincidencia de tipo de información confidencial que desencadena la búsqueda de EDM. Puede usar el nombre o GUID de un tipo de información confidencial personalizada o integrada existente.

   > [!NOTE]
   > Tenga en cuenta que cualquier cadena que coincida con el SIT proporcionado se hash y se comparará con cada entrada de la tabla de origen de información confidencial. Para evitar problemas de rendimiento si elige un SIT personalizado para el elemento de clasificación, no use uno que coincida con un gran porcentaje de contenido. Por ejemplo, uno que coincida con "cualquier número" o "cualquier palabra de cinco letras". Puede diferenciarlo agregando palabras clave compatibles o incluyendo el formato en la definición de la clasificación personalizada SIT.

   - **Match**: este campo apunta a pruebas adicionales encontradas cerca de idMatch.
   - **Coincidencias**: proporciona cualquier nombre de campo en esquema de EDM para DataStore.
   - **IdRef de recursos:** Esta sección especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales
     - Se proporciona GUID para el identificador ExactMatch.
     - **Nombre** &  **descripción**: personalizar según sea necesario.

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

2. Upload el paquete de reglas ejecutando el siguiente comando de PowerShell:

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('.\\rulepack.xml'))
   ```

> [!NOTE]
> La sintaxis del archivo de paquete de reglas es la misma que para otros tipos de información confidencial. Para obtener detalles completos sobre la sintaxis del archivo de paquete de reglas y las opciones de configuración adicionales, y para obtener instrucciones sobre cómo modificar y eliminar tipos de información confidencial con PowerShell, cree un tipo de información confidencial personalizado con [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md#create-a-custom-sensitive-information-type-using-powershell).

## <a name="next-step"></a>Paso siguiente

- [Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)
