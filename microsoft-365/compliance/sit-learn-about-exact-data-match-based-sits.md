---
title: Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre los tipos de información confidencial basados en coincidencias exactas de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25a48a13e66803dec592680c0ad0e9c01b611dc0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66949291"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos

[Los tipos de información confidencial](sensitive-information-type-learn-about.md) se usan para ayudar a identificar elementos confidenciales de modo que pueda evitar que se compartan involuntariamente o de forma inapropiada, para ayudar a localizar los datos pertinentes en eDiscovery y para aplicar acciones de gobernanza a determinados tipos de información. Defina un tipo de información confidencial (SIT) personalizado en función de:

- patrones
- evidencia de palabras clave como *empleado*, *número de seguro social* o *identificador*
- proximidad de caracteres a la evidencia en un patrón determinado
- niveles de confianza

¿Pero qué ocurre si desea un tipo de información confidencial (SIT) personalizado que use valores de datos exactos o casi exactos, en lugar de uno que encuentre coincidencias basadas en patrones genéricos? Con la clasificación basada en coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizado diseñado para:

- ser dinámico y actualizarse fácilmente
- ser más escalable
- generar menos falsos positivos
- funcionar con datos confidenciales estructurados
- controlar la información confidencial de forma más segura, no compartirla con nadie, incluido Microsoft
- usarse con varios servicios en la nube de Microsoft.

![Clasificación basada en EDM.](../media/EDMClassification.png)

La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial. La base de datos se puede actualizar diariamente y puede contener hasta 100 millones de filas de datos. Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables. Además, puede usar la clasificación basada en EDM con [directivas, como directivas de prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md) o [directivas de archivos de Microsoft Cloud App Security](/cloud-app-security/data-protection-policies).

> [!NOTE]
> Microsoft Purview Information Protection admite idiomas de juego de caracteres de doble byte para:
>
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
>
> Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).

## <a name="whats-different-in-an-edm-sit"></a>¿Qué es diferente en un SIT de EDM?

Cuando se trabaja con SIT de EDM, resulta útil comprender algunos conceptos que son únicos para ellos.  

### <a name="schema"></a>Esquema

El esquema es un archivo xml que define:

- Nombre del esquema, más adelante denominado *DataStore*. 
- Los nombres de campo que contiene la tabla de origen de información confidencial. Hay una asignación 1:1 del nombre del campo de esquema al nombre de columna de tabla de origen de información confidencial.
- Qué campos se pueden buscar.
- Cualquier parámetro de modificación de búsqueda, denominado *coincidencia configurable*, como omitir delimitadores y mayúsculas de minúsculas en los valores buscados.

### <a name="sensitive-information-source-table"></a>Tabla de origen de información confidencial

La tabla de origen confidencial contiene los valores de información confidencial que buscará EDM SIT. Se compone de columnas y filas. Los encabezados de columna son los nombres de campo, las filas son una instancia de datos y cada celda contiene los valores de esa instancia para ese campo.

Este es un ejemplo sencillo de una tabla de origen de información confidencial.

|Nombre|Apellidos|Fecha de nacimiento|
|---|---|---|
|Isaías|Langer| 05-05-1960|
|Ana|Bowman|11-24-1971|
|Oscar|Ward|02-12-1998|

### <a name="rule-package"></a>Paquete de reglas

Cada SIT tiene un paquete de reglas. Use el paquete de reglas en una SIT de EDM para definir:

- Coincide, que especifican el campo que será el elemento principal que se usará en la búsqueda exacta. Puede ser una expresión regular con o sin una validación de suma de comprobación, una lista de palabras clave, un diccionario de palabras clave o una función.
- Clasificación, que especifica la coincidencia de tipos confidenciales que desencadena la búsqueda de EDM.
- Elemento auxiliar que son elementos que, cuando se encuentran, proporcionan pruebas auxiliares que ayudan a aumentar la confianza de la coincidencia. Por ejemplo, la palabra clave "SSN" se encuentra cerca de un número SSN. Puede ser una expresión regular con o sin validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.
- Los niveles de confianza (alto, medio, bajo) reflejan la cantidad de pruebas auxiliares detectadas junto con el elemento principal. Cuantos más pruebas auxiliares contenga un elemento, mayor será la confianza en que un elemento coincidente contiene la información confidencial que está buscando. Consulte [Partes fundamentales de un tipo de información confidencial](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) para obtener más información sobre los niveles de confianza.
Proximidad: número de caracteres entre el elemento principal y el elemento auxiliar

### <a name="you-supply-your-own-schema-and-data"></a>Proporcione su propio esquema y datos.

[Microsoft Purview incluye más de 200 SITS](sensitive-information-type-entity-definitions.md) con esquemas predefinidos, patrones regex, palabras clave y niveles de confianza. Con los SIT de EDM, es responsable de definir el esquema, así como los campos primarios y secundarios que identifican elementos confidenciales. Dado que el esquema y los valores de datos principales y secundarios son muy confidenciales, los cifrará a través de una función [hash](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes) que incluya un valor [de sal](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.) generado o autosufirmado aleatoriamente. Esos valores hash se cargan en el servicio, por lo que los datos confidenciales nunca están abiertos.

### <a name="primary-and-secondary-support-elements"></a>Elementos de soporte técnico principal y secundario

Al crear una SIT de EDM, se define un campo de *elemento principal* en el paquete de reglas. Los campos principales son los elementos para los que se buscará todo el contenido y que deben seguir un patrón definido para poder identificarse. Cuando se encuentra el elemento principal en elementos examinados, EDM buscará los elementos *secundarios* o auxiliares, que no necesitan seguir un patrón y su proximidad al elemento principal. EDM requiere que el elemento principal se pueda detectar primero a través de una SIT existente. Consulte [Definiciones de entidades de tipo información confidencial](sensitive-information-type-entity-definitions.md) para obtener una lista completa de los SIT disponibles. Tendrá que encontrar uno de los que detecta la clase que quiere que detecte el SIT de EDM. Por ejemplo, si el esquema sit de EDM tiene el número de seguridad social de EE. UU. como elemento principal, al crear el esquema EDM, lo asociaría con el número de [seguridad social (SSN) SIT de EE. UU.](sit-defn-us-social-security-number.md)

## <a name="how-matching-works"></a>Funcionamiento de la coincidencia

EDM busca coincidencias comparando el contenido que encuentra con una tabla de datos confidenciales que defina. Las pruebas de coincidencia se realizan mediante una combinación de reglas y patrones tradicionales para asegurarse de que los datos coincidentes son una instancia real de los datos que desea buscar y proteger. En esencia, EDM funciona comparando las cadenas de los documentos y los correos electrónicos con los valores de una tabla de datos confidenciales que proporcione para averiguar si los valores del contenido están presentes en la tabla mediante la comparación de hashes criptográficos unidireccionales.

> [!TIP]
> Una práctica común consiste en combinar el uso de tipos de información confidencial de EDM y los tipos de información confidencial normales en los que se basan en reglas DLP, con umbrales diferentes. Por ejemplo, podría usar un tipo de información confidencial de EDM que busque números de seguridad social y otros datos, con requisitos estrictos y tolerancia baja donde una o varias coincidencias provocarán una alerta DLP y usarán el tipo de información confidencial normal, como el número de seguridad social de EE. UU. integrado, para recuentos más altos.  

## <a name="services-that-edm-supports"></a>Servicios compatibles con EDM


|Servicio  |Ubicaciones  |
|---------|---------|
| Prevención de pérdida de datos de Microsoft Purview    | - SharePoint online </br>- OneDrive para la Empresa </br>- Chat de Teams </br>- Exchange Online </br>- Dispositivos       |
|Microsoft Defender for Cloud Apps     | - SharePoint Online </br>- OneDrive para la Empresa        |
|Etiquetado automático (lado del servicio)     |- SharePoint online </br>- OneDrive para la Empresa </br>- Exchange Online         |
|Etiquetado automático (lado cliente)     |- Word </br>- Excel </br>- PowerPoint </br>- Clientes de escritorio de Exchange         |
|Clave administrada por el cliente     |- SharePoint online </br>- OneDrive para la Empresa </br>- Chat de Teams </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Clientes de escritorio de Exchange </br>- Dispositivos         |
|eDiscovery     |- SharePoint online </br>- OneDrive para la Empresa </br>- Chat de Teams </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Clientes de escritorio de Exchange  |
|Administración de riesgos de Insider     |- SharePoint online </br>- OneDrive para la Empresa </br>- Chat de Teams </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Clientes de escritorio de Exchange      |

## <a name="see-also"></a>Consulte también

- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
