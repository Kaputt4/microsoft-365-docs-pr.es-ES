---
title: Crear una consulta para buscar datos confidenciales almacenados en los sitios
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
description: Use la prevención de pérdida de datos (DLP) en SharePoint Online para detectar documentos que contienen datos confidenciales en todo el inquilino.
ms.openlocfilehash: 1bb3ed0286f719f9ea9210b4952044081213914f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638331"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Crear una consulta para buscar datos confidenciales almacenados en los sitios

Los usuarios suelen almacenar datos confidenciales, como números de tarjeta de crédito, números de seguridad social o personales, en sus sitios y, con el tiempo, esto puede exponer a una organización a un riesgo significativo de pérdida de datos. Los documentos almacenados en sitios, incluidos OneDrive para la Empresa sitios, se pueden compartir con personas ajenas a la organización que no deberían tener acceso a la información. Con Prevención de pérdida de datos de Microsoft Purview (DLP) en SharePoint Online, puede detectar documentos que contienen datos confidenciales en todo el inquilino. Después de detectar los documentos, puede trabajar con los propietarios de documentos para proteger los datos. Este tema puede ayudarle a formar una consulta para buscar datos confidenciales.

> [!NOTE]
> La detección electrónica o eDiscovery y DLP son características premium que requieren [el plan 2 de SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=510080).

## <a name="forming-a-basic-dlp-query"></a>Formación de una consulta básica de DLP

Una consulta básica de DLP está formada por tres partes: SensitiveType, intervalo de recuento e intervalo de confianza. Como se muestra en el gráfico siguiente, **SensitiveType:"\<type\>"** es obligatorio y ambos **|\<count range\>** son **|\<confidence range\>** opcionales.

![Consulta de ejemplo dividida en obligatoria y opcional.](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>Tipo confidencial: obligatorio

¿Qué es cada parte? Las consultas DLP de SharePoint normalmente comienzan con la propiedad `SensitiveType:"` y un nombre de tipo de información del [inventario de tipos de información confidencial](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) y terminan con .`"` También puede usar el nombre de un [tipo de información confidencial personalizado](create-a-custom-sensitive-information-type.md) que creó para su organización. Por ejemplo, tal vez esté buscando documentos que contienen números de tarjetas de crédito. En tal instancia, usaría el formato siguiente:  `SensitiveType:"Credit Card Number"`. Dado que no incluye el intervalo de recuento ni el intervalo de confianza, la consulta devuelve todos los documentos en los que se detecta un número de tarjeta de crédito. Esta es la consulta más sencilla que se puede ejecutar y devuelve la mayoría de los resultados. Tenga en cuenta que la ortografía y el espaciado del tipo confidencial son importantes.

### <a name="ranges---optional"></a>Intervalos: opcionales

Las dos partes siguientes son intervalos, por lo que vamos a examinar rápidamente el aspecto de un rango. En las consultas DLP de SharePoint, un intervalo básico se representa mediante dos números separados por dos puntos, lo que tiene este aspecto:  `[number]..[number]`. Por ejemplo, si  `10..20` se usa, ese intervalo capturaría números de 10 a 20. Hay muchas combinaciones de intervalos diferentes y varias de ellas se tratan en este tema.

Vamos a agregar un intervalo de recuento a la consulta. Puede usar el intervalo de recuento para definir el número de repeticiones de información confidencial que un documento debe contener antes de que se incluya en los resultados de la consulta. Por ejemplo, si desea que la consulta devuelva solo documentos que contengan exactamente cinco números de tarjeta de crédito, use esto:  `SensitiveType:"Credit Card Number|5"`. El intervalo de recuento también puede ayudar a identificar los documentos que suponen altos niveles de riesgo. Por ejemplo, su organización puede considerar como un riesgo alto los documentos con cinco o más números de tarjeta de crédito. Para buscar documentos que ajusten este criterio, use esta consulta:  `SensitiveType:"Credit Card Number|5.."`. Como alternativa, puede encontrar documentos con cinco o menos números de tarjeta de crédito mediante esta consulta:  `SensitiveType:"Credit Card Number|..5"`.

#### <a name="confidence-range"></a>Intervalo de confianza

Por último, el intervalo de confianza es el nivel de confianza con el que el tipo confidencial detectado coincide en realidad. Los valores para el intervalo de confianza funcionan de forma similar al intervalo de recuento. Puede crear una consulta sin incluir un intervalo de recuento. Por ejemplo, para buscar documentos con cualquier número de números de tarjeta de crédito (siempre que el intervalo de confianza sea del 85 por ciento o superior), use esta consulta:  `SensitiveType:"Credit Card Number|*|85.."`.

> [!IMPORTANT]
> El asterisco ( `*` ) es un carácter comodín que significa que cualquier valor funciona. Puede usar el carácter comodín ( `*` ) en el intervalo de recuento o en el intervalo de confianza, pero no en un tipo confidencial.

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Propiedades de consulta y operadores de búsqueda adicionales disponibles en el centro de exhibición de documentos electrónicos

DLP en SharePoint también presenta la propiedad LastSensitiveContentScan, que puede ayudarle a buscar archivos examinados dentro de un período de tiempo específico. Para ver ejemplos de consultas con la  `LastSensitiveContentScan` propiedad , vea los [ejemplos de consultas complejas](#examples-of-complex-queries) en la sección siguiente.

Puede usar no solo propiedades específicas de DLP para crear una consulta, sino también propiedades de búsqueda estándar de eDiscovery de SharePoint, como  `Author` o  `FileExtension`. Puede usar operadores para crear consultas complejas. Para obtener la lista de propiedades y operadores disponibles, vea la entrada de blog [Uso de propiedades y operadores de búsqueda con eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) .

## <a name="examples-of-complex-queries"></a>Ejemplos

En los ejemplos siguientes se usan diferentes tipos confidenciales, propiedades y operadores para ilustrar cómo puede refinar las consultas para encontrar exactamente lo que está buscando.

<br>

****

|Query|Explicación|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|El nombre puede parecer extraño porque es tan largo, pero es el nombre correcto para ese tipo confidencial. Asegúrese de usar nombres exactos del [inventario de tipos de información confidencial](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help). También puede usar el nombre de un [tipo de información confidencial personalizado](create-a-custom-sensitive-information-type.md) que creó para su organización.|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|Esto devuelve documentos con al menos una coincidencia con el tipo confidencial "Número de tarjeta de crédito". Los valores de cada intervalo son los respectivos valores mínimos y máximos. Una manera más sencilla de escribir esta consulta es  `SensitiveType:"Credit Card Number"`, pero ¿dónde está la diversión en eso?|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|Esto devuelve documentos con entre 5 y 25 números de tarjeta de crédito que se escanearon del 11 de agosto de 2018 al 13 de agosto de 2018.|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|Esto devuelve documentos con entre 5 y 25 números de tarjeta de crédito que se escanearon del 11 de agosto de 2018 al 13 de agosto de 2018. Los archivos con una extensión XLSX no se incluyen en los resultados de la consulta.  `FileExtension` es una de las muchas propiedades que puede incluir en una consulta. Para obtener más información, vea [Uso de propiedades y operadores de búsqueda con eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery).|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|Esto devuelve los documentos que contienen un número de tarjeta de crédito o un número de seguro social.|
|

## <a name="examples-of-queries-to-avoid"></a>Ejemplos

No todas las consultas son iguales. En la tabla siguiente se proporcionan ejemplos de consultas que no funcionan con DLP en SharePoint y se describe por qué.

<br>

****

|Consulta no compatible|Reason|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|Debe agregar, al menos, un número.|
|`SensitiveType:"NotARule"`|"NotARule" no es un nombre de tipo confidencial válido. Solo los nombres del [inventario de tipos de información confidencial](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) funcionan en consultas DLP.|
|`SensitiveType:"Credit Card Number|0"`|Cero no es válido como el valor mínimo o el valor máximo de un intervalo.|
|`SensitiveType:"Credit Card Number"`|Es posible que sea difícil de ver, pero hay espacio en blanco adicional entre "Crédito" y "Tarjeta" que hace que la consulta no sea válida. Use nombres de tipos confidenciales exactos del [inventario de tipos de información confidencial](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help).|
|`SensitiveType:"Credit Card Number|1. .3"`|La parte de dos períodos no debe estar separada por un espacio.|
|`SensitiveType:"Credit Card Number| |1..|80.."`|Hay demasiados delimitadores de canalización (\|). Siga este formato en su lugar: `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|Dado que los valores de confianza representan un porcentaje, no pueden superar los 100. Elija un número del 1 al 100 en su lugar.|
|

## <a name="for-more-information"></a>Más información

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Ejecutar una búsqueda de contenido](content-search.md)
- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
