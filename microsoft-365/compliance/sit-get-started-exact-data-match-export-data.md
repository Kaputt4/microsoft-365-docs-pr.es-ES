---
title: Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo exportar datos de origen para el tipo de información confidencial basada en coincidencias exactas de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8253ff73d53100c986a2bd8580830703c9f4b363
ms.sourcegitcommit: 19e16b16f144159b55bb4c544403e3642b69e335
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62818533"
---
# <a name="export-source-data-for-exact-data-match-based-sensitive-information-type"></a>Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos


La tabla de datos confidenciales es un archivo de texto que contiene filas de valores con los que comparará el contenido de los documentos para identificar datos confidenciales. Estos valores pueden ser información de identificación personal, registros de productos u otros datos confidenciales en formato de texto que desee detectar en el contenido y realizar acciones de protección.

Una vez exportados los datos en uno de los formatos admitidos, puede continuar con la creación de un esquema de EDM.

## <a name="defining-your-edm-sensitive-type"></a>Definir el tipo confidencial de EDM

Al definir el tipo confidencial de EDM, una de las decisiones más importantes es qué campos serán campos principales. Los campos principales deben seguir un patrón detectable y definirse como campos (columnas) que se pueden buscar en el esquema de EDM. Los campos secundarios no necesitan seguir ningún patrón, ya que se compararán con todas las coincidencias de texto que rodean a los campos principales.

Use estas reglas para decidir qué columnas debe usar como campos principales:

- Si debe detectar datos confidenciales en función de la presencia de un solo valor que coincida con un campo en la tabla de datos confidenciales, independientemente de la presencia de otros datos confidenciales que lo rodean, esa columna debe definirse como un elemento principal para un tipo de EDM. 
- Si se deben detectar varias combinaciones de campos diferentes en la tabla de datos confidenciales en el contenido, identifique las columnas que son comunes a la mayoría de estas combinaciones y designe como elementos principales y combinaciones de los demás campos como elementos secundarios.
- Si una columna que desea usar como campo principal no sigue un patrón detectable, como cualquier cadena de texto o sigue patrones detectables que estarían presentes en algún lugar en un gran porcentaje de documentos o correos electrónicos, intente elegir otras columnas mejor estructuradas como elementos principales.

Por ejemplo, `full name`si tiene las columnas , , `date of birth``account number`y `Social Security Number`, incluso si los nombres y apellidos son las columnas que serán comunes a las distintas combinaciones de datos que desea detectar, estas cadenas no siguen patrones fácilmente identificables y pueden ser difíciles de definir como un tipo de información confidencial. Esto se debe a que es posible que algunos nombres ni siquiera comiencen con mayúsculas, pueden estar formados por dos, tres o más palabras e incluso pueden contener números u otros caracteres no alfabéticos. La fecha de nacimiento puede identificarse con mayor facilidad, pero como todos los correos electrónicos y la mayoría de los documentos contendrán al menos una fecha, tampoco es un buen candidato. Los números de seguridad social y los números de cuenta son buenos candidatos para su uso como campo principal.

## <a name="save-sensitive-data-in-csv-tsv-or-pipe-separated-format"></a>Guardar datos confidenciales en .csv, .tsv o formato separado por canalización

1. Identifique la información confidencial que quiera usar. Exporte los datos a una aplicación, como Microsoft Excel, y guarde el archivo en un archivo de texto. El archivo se puede guardar en .csv (valores separados por comas), .tsv (valores separados por tabulaciones) o en formato separado por |). El formato .tsv se recomienda en casos en los que los valores de datos pueden incluir comas, como direcciones de calle.
El archivo de datos puede incluir un máximo de:
   - Hasta 100 millones de filas de datos confidenciales
   - Hasta 32 columnas (campos) por origen de datos
   - Hasta 5 columnas (campos) marcadas como utilizables en búsquedas

2. Estructura los datos confidenciales del archivo .csv o .tsv de forma que la primera fila incluya los nombres de los campos usados para la clasificación basada en EDM. En el archivo, es posible que tenga nombres de campo como "ssn", "fecha de nacimiento", "nombre", "apellido". Los nombres de encabezado de las columnas no pueden contener espacios ni guiones bajos. Por ejemplo, el archivo .csv de ejemplo que usamos en este artículo se denomina *RegistrosPacientes.csv* y sus columnas *IdPaciente*, *NEM*, *Apellido*, *Nombre*, *NSS*, etc.

3. Preste atención al formato de los campos de datos confidenciales. En concreto, los campos que pueden contener comas en su contenido, por ejemplo, una dirección de calle que contiene el valor "Seattle,WA" se analizarán como dos campos independientes cuando se analice si se selecciona el formato .csv. Para evitar esto, use el formato .tsv o rodeado de la coma que contiene valores entre comillas dobles en la tabla de datos confidenciales. Si las comas que contienen valores también contienen espacios, debe crear un SIT personalizado que coincida con el formato correspondiente. Por ejemplo, un SIT que detecta cadenas de varias palabras con comas y espacios en ella.

## <a name="next-step"></a>Paso siguiente

- [Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)

## <a name="see-also"></a>Vea también

- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
