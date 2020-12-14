---
title: Modificar el esquema de coincidencia de datos exactos para usar la coincidencia configurable
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información acerca de cómo modificar un esquema de EDM para usar la coincidencia configurable.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2211e4d99d97fcce241a5f4c3ea7c9d8122ca9d7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656810"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Modificar el esquema de coincidencia de datos exactos para usar la coincidencia configurable

La clasificación basada en la coincidencia de datos exactos le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial. Cuando necesite permitir el uso de variantes de una cadena exacta, puede usar la *coincidencia configurable* para indicar a Microsoft 365 que omita mayúsculas y minúsculas y otros delimitadores. 

> [!IMPORTANT]
> Use este procedimiento para modificar un esquema EDM y un archivo de datos existentes.

1. Desinstale **EdmUploadAgent.exe** del equipo que usa para conectarse a Microsoft 365 para propósitos de esquema de EDM y carga de archivos de datos.

2. Descargue el archivo **EdmUploadAgent.exe** apropiado para su suscripción mediante los siguientes vínculos:
    - [Comercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639): la mayoría de los clientes comerciales deben usarlo
    - [GCC alto](https://go.microsoft.com/fwlink/?linkid=2137521): está específicamente diseñado para los suscriptores de nube de administración pública de alta seguridad
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) : está específicamente diseñado para los clientes de la nube del Departamento de Defensa de Estados Unidos

3. Autorice al agente de carga de EDM, abra la ventana del símbolo del sistema (como administrador) y ejecute el siguiente comando:

   `EdmUploadAgent.exe /Authorize`

4. Si no tiene una copia actual del esquema existente, debe descargar una copia del esquema existente y ejecutar este comando:

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. Personalice el esquema para que todas las columnas usen “caseInsensitive” y/o “ignoredDelimiters”.  El valor predeterminado de "caseInsensitive" es "false" y de "ignoredDelimiters" es una cadena vacía. 

> [!NOTE]
> El tipo de información confidencial personalizado subyacente o el tipo de información confidencial integrado que se usa para detectar el patrón de regex general debe admitir la detección de las entradas de variantes que aparecen en ignoredDelimiters. Por ejemplo, el tipo de información confidencial integrado del número de la seguridad social de Estados Unidos (SSN) puede detectar variaciones en los datos que incluyen guiones, espacios o la falta de espacios entre los números agrupados que componen el SSN. Como resultado, solo los delimitadores que son relevantes para incluir en ignoredDelimiters de EDM para los datos SSN son: guion y espacio.

Este es un esquema de ejemplo en el que se simula la coincidencia que no distingue mayúsculas de minúsculas creando las columnas adicionales necesarias para reconocer las variaciones de mayúsculas y minúsculas en los datos confidenciales.

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

En el ejemplo anterior, las variantes de la columna `PolicyNumber` original ya no serán necesarias si se agregan tanto `caseInsensitive` como `ignoredDelimiters`.

Para actualizar este esquema para que EDM use la coincidencia configurable, utilice las marcas `caseInsensitive` y `ignoredDelimiters`.  Este es el aspecto que tiene:

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

El indicador `ignoredDelimiters` admite cualquier carácter no alfanumérico. Aquí se muestran algunos ejemplos:
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

6. Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

7. Actualice el esquema ejecutando estos cmdlets uno por vez:

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. Si es necesario, actualice el archivo de datos para que coincida con la nueva versión de esquema.

> [!TIP]
> De forma opcional, puede ejecutar una validación en el archivo CSV antes de cargarlo ejecutando lo siguiente:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>Para más información sobre todos los parámetros admitidos de EdmUploadAgent.exe >, ejecute
>
> `EdmUploadAgent.exe /?`

9. Abra la ventana del símbolo del sistema (como administrador) y ejecute el siguiente comando para obtener el hash y cargar los datos confidenciales:

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>Artículos relacionados

- [Crear un tipo de información confidencial personalizado con una clasificación basada en la coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Tipos de información confidencial personalizados](custom-sensitive-info-types.md)
- [Información general de directivas DLP](data-loss-prevention-policies.md)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)
- [New-DlpEdmSchema](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)