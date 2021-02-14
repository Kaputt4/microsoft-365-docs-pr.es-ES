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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Use la prevención de pérdida de datos (DLP) en SharePoint Online para detectar documentos que contienen datos confidenciales en todo el espacio empresarial.
ms.openlocfilehash: b6a0943aa4e71b61c5f430034d9e445462eebde7
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817709"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Crear una consulta para buscar datos confidenciales almacenados en los sitios

A menudo, los usuarios almacenan datos confidenciales, como números de tarjeta de crédito, números de la seguridad social o personales, en sus sitios y, con el tiempo, esto puede exponer a una organización a un riesgo significativo de pérdida de datos. Los documentos almacenados en sitios, incluidos los sitios de OneDrive para la Empresa, se pueden compartir con personas ajenas a la organización que no deberían tener acceso a la información. Con la prevención de pérdida de datos (DLP) en SharePoint Online, puede detectar documentos que contienen datos confidenciales en todo el espacio empresarial. Después de descubrir los documentos, puede trabajar con los propietarios de los documentos para proteger los datos. Este tema puede ayudarle a crear una consulta para buscar datos confidenciales.
  
> [!NOTE]
> La detección electrónica o la exhibición de documentos electrónicos y DLP son características premium que requieren [SharePoint Online Plan 2.](https://go.microsoft.com/fwlink/?LinkId=510080) 
  
## <a name="forming-a-basic-dlp-query"></a>Formación de una consulta básica de DLP

Una consulta básica de DLP está formada por tres partes: SensitiveType, intervalo de recuento e intervalo de confianza. Como se muestra en el siguiente gráfico, **SensitiveType:" \<type\> es** obligatorio y ambos **|\<count range\>** son **|\<confidence range\>** opcionales. 
  
![Consulta de ejemplo dividida entre obligatorio y opcional](../media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>Tipo confidencial: obligatorio

¿Qué es cada parte? Las consultas DLP de SharePoint suelen comenzar con la propiedad y un nombre de tipo de información del inventario de tipos de información `SensitiveType:"` confidencial y terminan con un archivo [](https://go.microsoft.com/fwlink/?LinkID=509999) `"` . También puede usar el nombre de un tipo personalizado de [información confidencial](create-a-custom-sensitive-information-type.md) que creó para su organización. Por ejemplo, tal vez esté buscando documentos que contienen números de tarjetas de crédito. En tal caso, usaría el siguiente formato:  `SensitiveType:"Credit Card Number"` . Debido a que no se ha incluyedo el intervalo de recuento o el intervalo de confianza, la consulta devuelve todos los documentos en los que se detecta un número de tarjeta de crédito. Esta es la consulta más sencilla que se puede ejecutar y devuelve la mayoría de los resultados. Tenga en cuenta que la ortografía y el espaciado del tipo confidencial son importantes. 
  
### <a name="ranges---optional"></a>Intervalos: opcionales

Las dos partes siguientes son rangos, por lo que vamos a examinar rápidamente el aspecto de un rango. En las consultas DLP de SharePoint, un rango básico se representa mediante dos números separados por dos puntos, que tienen este aspecto:  `[number]..[number]` . Por ejemplo, si  `10..20` se usa, ese intervalo capturaría números entre 10 y 20. Hay muchas combinaciones de intervalos diferentes y varias de ellas se tratan en este tema. 
  
Vamos a agregar un intervalo de recuento a la consulta. Puede usar el intervalo de recuento para definir el número de repeticiones de información confidencial que un documento debe contener antes de que se incluya en los resultados de la consulta. Por ejemplo, si desea que la consulta devuelva solo documentos que contengan exactamente cinco números de tarjeta de crédito, use:  `SensitiveType:"Credit Card Number|5"` . El intervalo de recuento también puede ayudar a identificar los documentos que suponen altos niveles de riesgo. Por ejemplo, su organización puede considerar como un riesgo alto los documentos con cinco o más números de tarjeta de crédito. Para buscar documentos que se ajusten a este criterio, use esta consulta:  `SensitiveType:"Credit Card Number|5.."` . Como alternativa, puede encontrar documentos con cinco o menos números de tarjeta de crédito mediante esta consulta:  `SensitiveType:"Credit Card Number|..5"` . 
  
#### <a name="confidence-range"></a>Intervalo de confianza

Por último, el intervalo de confianza es el nivel de confianza con el que el tipo confidencial detectado coincide en realidad. Los valores para el intervalo de confianza funcionan de forma similar al intervalo de recuento. Puede crear una consulta sin incluir un intervalo de recuento. Por ejemplo, para buscar documentos con cualquier número de números de tarjeta de crédito (siempre que el intervalo de confianza sea 85 por ciento o superior), use esta consulta:  `SensitiveType:"Credit Card Number|*|85.."` . 
  
> [!IMPORTANT]
> El asterisco ( `*` ) es un carácter comodín que significa que cualquier valor funciona. Puede usar el carácter comodín ( ) en el intervalo de recuento o en el intervalo de confianza, pero no `*` en un tipo confidencial. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Propiedades de consulta y operadores de búsqueda adicionales disponibles en el centro de exhibición de documentos electrónicos

DLP en SharePoint también presenta la propiedad LastSensitiveContentScan, que puede ayudarle a buscar archivos analizados en un período de tiempo específico. Para obtener ejemplos de consulta  `LastSensitiveContentScan` con la propiedad, vea [los ejemplos de consultas complejas](#examples-of-complex-queries) en la sección siguiente. 
  
Puede usar no solo propiedades específicas de DLP para crear una consulta, sino también propiedades de búsqueda de exhibición de documentos electrónicos estándar de SharePoint, como  `Author` o  `FileExtension` . Puede usar operadores para crear consultas complejas. Para obtener la lista de propiedades y operadores disponibles, consulte la entrada de blog Uso de propiedades y operadores de búsqueda con [exhibición de documentos](https://go.microsoft.com/fwlink/?LinkId=510093) electrónicos. 
  
## <a name="examples-of-complex-queries"></a>Ejemplos

Los ejemplos siguientes usan diferentes tipos confidenciales, propiedades y operadores para ilustrar cómo puede refinar las consultas para encontrar exactamente lo que está buscando.
  
|**Query**|**Explicación**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |El nombre puede parecer extraño porque es tan largo, pero es el nombre correcto para ese tipo confidencial. Asegúrese de usar nombres exactos del inventario de [tipos de información confidencial.](https://go.microsoft.com/fwlink/?LinkID=509999) También puede usar el nombre de un tipo personalizado de [información confidencial](create-a-custom-sensitive-information-type.md) que creó para su organización.  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |Esto devuelve documentos con al menos una coincidencia con el tipo confidencial "Número de tarjeta de crédito". Los valores de cada intervalo son los respectivos valores mínimos y máximos. Una forma más sencilla de escribir esta consulta es , pero ¿dónde está  `SensitiveType:"Credit Card Number"` la diversión en eso?  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |Esto devuelve documentos con entre 5 y 25 números de tarjeta de crédito que se analizaron desde el 11 de agosto de 2018 hasta el 13 de agosto de 2018.  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |Esto devuelve documentos con entre 5 y 25 números de tarjeta de crédito que se analizaron desde el 11 de agosto de 2018 hasta el 13 de agosto de 2018. Los archivos con extensión XLSX no se incluyen en los resultados de la consulta.  `FileExtension` es una de las muchas propiedades que puede incluir en una consulta. Para obtener más información, vea [Uso de propiedades y operadores de búsqueda con exhibición de documentos electrónicos.](https://go.microsoft.com/fwlink/?LinkId=510093)  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |Esto devuelve los documentos que contienen un número de tarjeta de crédito o un número de seguro social.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Ejemplos

No todas las consultas son iguales. En la tabla siguiente se proporcionan ejemplos de consultas que no funcionan con DLP en SharePoint y se describe por qué.
  
|**Consulta no compatible**|**Motivo**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |Debe agregar, al menos, un número.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" no es un nombre de tipo confidencial válido. Solo los nombres del inventario [de tipos de información](https://go.microsoft.com/fwlink/?LinkID=509999) confidencial funcionan en consultas DLP.  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |Cero no es válido como el valor mínimo o el valor máximo de un intervalo.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Puede ser difícil de ver, pero hay más espacio en blanco entre "Crédito" y "Tarjeta" que hace que la consulta no sea válida. Use nombres de tipo confidencial exactos del inventario [de tipos de información confidencial.](https://go.microsoft.com/fwlink/?LinkID=509999)  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |La parte de dos períodos no debe estar separada por un espacio.  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |Hay demasiados delimitadores de canalización (|). En su lugar, sigue este formato: `SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |Dado que los valores de confianza representan un porcentaje, no pueden superar los 100. Elija un número del 1 al 100 en su lugar.  <br/> |
   
## <a name="for-more-information"></a>Más información

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Ejecutar una búsqueda de contenido](content-search.md)
- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
  

