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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre los tipos exactos de información confidencial basada en coincidencias de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6b8b2bb5387257bf016e751713b9cba61de9691
ms.sourcegitcommit: 2716cb48cc6127f6b851d177af23f276fb07bfc9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61426476"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos

[](sensitive-information-type-learn-about.md) Los tipos de información confidencial se usan para ayudar a identificar elementos confidenciales de modo que pueda evitar que se compartan de forma involuntaria o inapropiada, para ayudar a localizar datos relevantes en la exhibición de documentos electrónicos y para aplicar acciones de gobierno a determinados tipos de información. Defina un tipo de información confidencial personalizado (SIT) en función de:

- patrones
- evidencia de palabras clave *como empleado,* *número de seguridad social* o *id.*
- proximidad de caracteres a la evidencia en un patrón determinado
- niveles de confianza

Pero, ¿qué ocurre si desea un tipo de información confidencial personalizado (SIT) que use valores de datos exactos o casi exactos, en lugar de uno que encontró coincidencias basadas en patrones genéricos? Con la clasificación basada en Coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizado diseñado para:

- ser dinámico y actualizarse fácilmente
- ser más escalable
- generar menos falsos positivos
- funcionar con datos confidenciales estructurados
- controlar la información confidencial de forma más segura, sin compartirla con nadie, incluido Microsoft
- usarse con varios servicios en la nube de Microsoft.

![Clasificación basada en EDM.](../media/EDMClassification.png)

La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial. La base de datos se puede actualizar diariamente y puede contener hasta 100 millones de filas de datos. Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables. Y puede usar la clasificación basada en EDM con directivas, como [directivas de prevención de pérdida de datos](dlp-learn-about-dlp.md) o [directivas de archivo de Microsoft Cloud App Security](/cloud-app-security/data-protection-policies).

> [!NOTE]
> Microsoft 365 Information Protection es compatible con los idiomas del juego de caracteres de doble byte para:
>
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
>
> Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).

## <a name="whats-different-in-an-edm-sit"></a>Qué es diferente en un SIT de EDM

Cuando trabaja con EDM SIT, es útil comprender algunos conceptos que son exclusivos de ellos.  

### <a name="schema"></a>Esquema

El esquema es un archivo xml que define:

- El nombre del esquema, más adelante denominado *DataStore*. 
- Los nombres de campo que contiene la tabla de origen de información confidencial. Hay una asignación 1:1 del nombre del campo de esquema al nombre de columna de la tabla de origen de información confidencial.
- Qué campos se pueden buscar.
- Cualquier parámetro de modificación de búsqueda, denominado *coincidencia configurable,* como ignorar delimitadores y mayúsculas de minúsculas en los valores buscados.

### <a name="sensitive-information-source-table"></a>Tabla de origen de información confidencial

La tabla de origen confidencial contiene los valores de información confidencial que buscará EDM SIT. Está hecho de columnas y filas. Los encabezados de columna son los nombres de campo, las filas son una instancia de datos y cada celda contiene los valores de esa instancia para ese campo.

Este es un ejemplo sencillo de una tabla de origen de información confidencial.

|Nombre  |Apellidos  |Fecha de nacimiento  |
|---------|---------|---------|
|Isía   |Langer  | 05-05-1960 |
|Ana   |Bowman         |11-24-1971 |
|Óscar   |Ward         |02-12-1998 |


### <a name="rule-package"></a>Paquete de reglas

Cada SIT tiene un paquete de reglas. El paquete de reglas se usa en un SIT de EDM para definir:

- Coincide, que especifica el campo que será el elemento principal que se usará en la búsqueda exacta. Puede ser una expresión regular con o sin una validación de suma de comprobación, una lista de palabras clave, un diccionario de palabras clave o una función.
- Clasificación, que especifica la coincidencia de tipo confidencial que desencadena la búsqueda de EDM.
- Elemento de soporte que son elementos que, cuando se encuentran, proporcionan pruebas que ayudan a aumentar la confianza de la coincidencia. Por ejemplo, la palabra clave "SSN" cerca de un número SSN. Puede ser una expresión regular con o sin validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.
- Los niveles de confianza (alto, medio, bajo) reflejan la cantidad de pruebas de soporte que se detectó junto con el elemento principal. Cuanto más evidencia de soporte técnico contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que está buscando. Vea, [Partes fundamentales de un tipo de información confidencial](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) para obtener más información sobre los niveles de confianza.
Proximidad: número de caracteres entre el elemento principal y el elemento de soporte técnico

### <a name="you-supply-your-own-schema-and-data"></a>Proporcionar su propio esquema y datos

Microsoft 365 incluye más de [200 SITS](sensitive-information-type-entity-definitions.md) con esquemas predefinidos, patrones de regex, palabras clave y niveles de confianza. Con los SIT de EDM, es responsable de definir el esquema, así como los campos primarios y secundarios que identifican elementos confidenciales. Dado que el esquema y los valores de datos principales y secundarios son altamente confidenciales, los cifrarás mediante una función [hash](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes) que incluya un valor de sal generado aleatoriamente o autoaprobado. [](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.) A continuación, esos valores hash se cargan en el servicio, por lo que los datos confidenciales nunca están abiertos.

### <a name="primary-and-secondary-support-elements"></a>Elementos de soporte principal y secundario

Al crear un SIT de EDM, se define un campo *de elemento* principal en el paquete de reglas. Los campos principales son los elementos para los que se buscará todo el contenido y que deben seguir un patrón definido para poder identificarse. Cuando el elemento principal se encuentra en elementos analizados,  EDM buscará los elementos secundarios o de soporte, que no necesitan seguir un patrón, y su proximidad al elemento principal. EDM requiere que el elemento principal se pueda detectar primero a través de un SIT existente. Vea [Definiciones de entidad de tipo de información confidencial](sensitive-information-type-entity-definitions.md) para obtener una lista completa de los SIT disponibles. Tendrás que encontrar una de las que detecte la clase que quieres que detecte tu SIT de EDM. Por ejemplo, si el esquema SIT de EDM tiene el número de seguridad social de Estados Unidos como elemento principal, al crear el esquema de EDM, lo asociaría con el SIT del número de seguridad [social (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn) de Estados Unidos.


## <a name="how-matching-works"></a>Cómo funciona la coincidencia

EDM busca coincidencias comparando el contenido que encuentra con una tabla de datos confidenciales que defina. Las pruebas de coincidencia se realizan con una combinación de reglas y patrones tradicionales para garantizar que los datos coincidentes son una instancia real de los datos que desea buscar y proteger. En esencia, EDM funciona comparando las cadenas de los documentos y los correos electrónicos con los valores de una tabla de datos confidenciales que proporciona para averiguar si los valores del contenido están presentes en la tabla comparando hashes criptográficos unicos.

> [!TIP]
> Una práctica común es combinar el uso de tipos de información confidencial de EDM y los tipos de información confidencial normales en los que se basan en reglas DLP, con umbrales diferentes. Por ejemplo, puede usar un tipo de información confidencial de EDM que busca números de seguridad social y otros datos, con requisitos estrictos y poca tolerancia donde una o más coincidencias provocarán una alerta DLP y usarán el tipo de información confidencial normal, como el número de seguridad social integrado de Estados Unidos para recuentos más altos.  

## <a name="see-also"></a>Consulte también

- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
   
