---
title: Obtener más información acerca de los tipos de información confidencial
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: En este artículo se proporciona información general sobre los tipos de información confidencial y cómo detectan información confidencial como números de cuenta bancaria, tarjeta de crédito o seguridad social para identificar elementos confidenciales
ms.openlocfilehash: 6bc15ae90d591e2f2c4e432dce025201c9f13c18
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "62903792"
---
# <a name="learn-about-sensitive-information-types"></a>Obtener más información acerca de los tipos de información confidencial

Identificar y clasificar elementos confidenciales que están bajo el control de las organizaciones es el primer paso de la disciplina [de Protección de la información](./information-protection.md).  Microsoft 365 proporciona tres formas de identificar elementos para que se puedan clasificar:

- manualmente por los usuarios
- reconocimiento automatizado de patrones, como tipos de información confidencial
- [aprendizaje automático](classifier-learn-about.md)

Los tipos de información confidencial (SIT) son clasificadores basados en patrones. Detectan información confidencial como seguridad social, tarjeta de crédito o números de cuenta bancaria para identificar elementos confidenciales, consulte [Definiciones](sensitive-information-type-entity-definitions.md) de entidades de tipos de información confidencial para obtener una lista completa de todos los SIT.

Microsoft proporciona un gran número de SIT preconfigurados o puede crear los suyos propios.

## <a name="sensitive-information-types-are-used-in"></a>Los tipos de información confidencial se usan en

- [Directivas de prevención de pérdida de datos](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](retention.md)
- [Administración de riesgos internos](insider-risk-management.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Administración de riesgos interna](insider-risk-management-solution-overview.md)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Priva](/privacy/priva)

## <a name="categories-of-sensitive-information-types"></a>Categorías de tipos de información confidencial

### <a name="built-in-sensitive-information-types"></a>Integrados en tipos de información confidencial

Microsoft crea estos SIT en la consola de cumplimiento de forma predeterminada. Estos SIT no se pueden editar, pero se pueden usar como plantillas y copiarse para crear tipos de información confidencial personalizados.

### <a name="named-entity-sensitive-information-types"></a>Tipos de información confidencial de entidad con nombre

Los SIT de entidad con nombre también se muestran en la consola de cumplimiento de forma predeterminada. Detectan nombres de personas, direcciones físicas y términos y condiciones médicas. No se pueden editar ni copiar. Vea, [Obtenga información sobre las entidades con nombre (versión preliminar)](named-entities-learn.md#learn-about-named-entities-preview) para obtener más información. Los SIT de entidad con nombre se incluyen en dos tipos:

**un-bundled**

Estos SIT de entidad con nombre tienen un enfoque más estrecho, como un solo país o una sola clase de términos. Úselos cuando necesite una directiva DLP con un ámbito de detección más estrecho. Vea ejemplos [de SIT de entidad con nombre](named-entities-learn.md#examples-of-named-entity-sits).

**bundled**

Los SIT de entidad con nombre agrupados detectan todas las coincidencias posibles en una clase, como Todas las direcciones físicas. Úsenlos como criterios generales en las directivas DLP para detectar elementos confidenciales. Vea ejemplos [de SIT de entidad con nombre](named-entities-learn.md#examples-of-named-entity-sits).

### <a name="custom-sensitive-information-types"></a>Tipos de información confidencial personalizada

Si los tipos de información confidencial preconfigurados no satisfacen sus necesidades, puede crear sus propios tipos de información confidencial personalizados que defina completamente o puede copiar uno de los integrados y modificarlo. Consulte Crear [un tipo de información confidencial personalizada en el Centro de cumplimiento](create-a-custom-sensitive-information-type.md) para obtener más información.

### <a name="exact-data-match-sensitive-information-types"></a>Datos exactos coinciden con tipos de información confidencial

Todos los SIT basados en EDM se crean desde cero. Se usan para detectar elementos que tienen valores exactos que se definen en una base de datos de información confidencial. Vea, [Obtenga información sobre los tipos exactos de información confidencial basada en coincidencias de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) para obtener más información.

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Partes fundamentales de un tipo de información confidencial

Cada entidad de tipo de información confidencial se define mediante estos campos:

- nombre: cómo se hace referencia al tipo de información confidencial
- descripción: describe lo que busca el tipo de información confidencial
- patrón: un patrón define lo que detecta un tipo de información confidencial. Consta de los siguientes componentes.
    - Elemento principal: el elemento principal que busca el tipo de información confidencial. Puede ser una expresión **regular con** o sin una validación de suma de comprobación, una lista de palabras **clave, un** **diccionario de** palabras clave o una **función**.
    - Elemento de soporte: elementos que actúan como pruebas de soporte que ayudan a aumentar la confianza de la coincidencia. Por ejemplo, la palabra clave "SSN" cerca de un número SSN. Puede ser una expresión regular con o sin validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.
    - Nivel de confianza: los niveles de confianza (altos, medianos, bajos) reflejan la cantidad de evidencia de soporte que se detectó junto con el elemento principal. Cuanto más evidencia de soporte técnico contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que está buscando.
    - Proximidad: número de caracteres entre el elemento principal y el elemento de soporte.

![Diagrama de evidencia corroborativa y ventana de proximidad.](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Obtenga más información sobre los niveles de confianza en este vídeo


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  



### <a name="example-sensitive-information-type"></a>Tipo de información confidencial de ejemplo


#### <a name="argentina-national-identity-dni-number"></a>Número de identidad nacional (DNI) de Argentina

### <a name="format"></a>Formato

Ocho dígitos separados por puntos

### <a name="pattern"></a>Patrón

Ocho dígitos:
- dos dígitos
- un punto
- tres dígitos
- un punto
- tres dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene confianza mediana en que se ha detectado este tipo de información confidencial si, en una proximidad de 300 caracteres:
- La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_argentina_national_id.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Número de identidad nacional de Argentina 
- Identity 
- Identificación tarjeta de identidad nacional 
- DNI 
- Registro nacional de personas de NIC 
- Documento Nacional de Identidad 
- Registro nacional de las personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Más información sobre los niveles de confianza

En una definición de entidad de tipo de información **confidencial, el** nivel de confianza refleja la cantidad de evidencia compatible que se detecta además del elemento principal. Cuanto más evidencia de soporte técnico contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que está buscando. Por ejemplo, las coincidencias con un nivel de confianza alto contendrán evidencias más compatibles cerca del elemento principal, mientras que las coincidencias con un nivel de confianza bajo contendrán poca o ninguna evidencia compatible en proximidad. 

Un nivel de confianza alto devuelve el menor número de falsos positivos, pero puede dar como resultado más falsos negativos. Los niveles de confianza bajos o medianos devuelven más falsos positivos, pero de pocos a cero falsos negativos.

- **confianza baja**: los elementos coincidentes contendrán el menor número de falsos negativos, pero los más falsos positivos. La confianza baja devuelve todas las coincidencias de confianza baja, media y alta. El nivel de confianza bajo tiene un valor de 65.
- **confianza media**: los elementos coincidentes contendrán una cantidad promedio de falsos positivos y falsos negativos. La confianza media devuelve todas las coincidencias de confianza media y alta. El nivel de confianza medio tiene un valor de 75.
- **confianza alta**: los elementos coincidentes contendrán el menor número de falsos positivos, pero los negativos más falsos. La confianza alta solo devuelve coincidencias de elevada confianza y tiene un valor de 85.  

Debe usar patrones de alto nivel de confianza con recuentos bajos, por ejemplo, de cinco a diez, y patrones de confianza bajos con recuentos más altos, por ejemplo, 20 o más.

> [!NOTE]
> Si tiene directivas existentes o tipos de información confidencial personalizados (SIT) definidos con niveles de confianza basados en números (también conocidos como precisión), se asignarán automáticamente a los tres niveles de confianza discretos; confianza baja, confianza media y confianza alta, en toda la interfaz de usuario del Centro de seguridad y cumplimiento.
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza de entre 76 y 100 se asignarán a una elevada confianza. 
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza de entre 66 y 75 se asignarán a confianza mediana.
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza inferiores o iguales a 65 se asignarán a una confianza baja. 

## <a name="creating-custom-sensitive-information-types"></a>Crear tipos de información confidencial personalizados

Puede elegir entre varias opciones para crear tipos de información confidencial personalizados en el Centro de cumplimiento.

- **Usar la interfaz de** usuario: puedes configurar un tipo de información confidencial personalizada mediante la interfaz de usuario del Centro de cumplimiento. Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave. Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).

- **Usar EDM** : puede configurar tipos de información confidencial personalizados mediante la clasificación basada en Coincidencia exacta de datos (EDM). Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente. Consulte [Información sobre tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types).

- **Usar PowerShell** : puede configurar tipos de información confidencial personalizados con PowerShell. Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración. Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).

> [!NOTE]
> Los niveles de confianza mejorados están disponibles para su uso inmediato en Prevención de pérdida de datos para servicios de Microsoft 365, Microsoft Information Protection para servicios Microsoft 365, Cumplimiento de comunicaciones, Gobierno de la información y Administración de registros.
> Microsoft 365 Information Protection ahora admite idiomas de juego de caracteres de doble byte para:
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
> 
> Este soporte está disponible para tipos de información confidencial. Consulte Information [protection support for double byte character sets release notes](mip-dbcs-relnotes.md) for more information.

> [!TIP]
> Para detectar patrones que contengan caracteres chinos/japoneses y caracteres de un solo byte o para detectar patrones que contengan chino/japonés e inglés, defina dos variantes de la palabra clave o regex.
> - Por ejemplo, para detectar una palabra clave como "机密的document", utilice dos variantes de la palabra clave; una con un espacio entre el texto japonés y el inglés y otra sin espacio entre el texto japonés y el inglés. Por lo tanto, las palabras clave que deben agregarse en el SIT deben ser "机密的document" y "机密的document". Del mismo modo, para detectar la frase "東京オリンピック2020", se deben utilizar dos variantes: "東京オリンピック 2020" y "東京オリンピック2020"".
> 
> Junto con caracteres de chino,japonés/doble byte, si la lista de palabras clave/frases también contiene palabras no chinas/japonesas (como solo inglés), debe crear dos diccionarios/listas de palabras clave. Uno para las palabras clave que contienen caracteres chinos, japoneses o de dos bytes; y otro solo para inglés. 
> - Por ejemplo, si desea crear un diccionario o una lista de palabras clave con tres frases "Extremadamente confidencial", "機密性 机密的 
>     1. Extremadamente confidencial
>     2. 機密性が高い, 机密的document y 机密的 document
> 
> Al crear una regex que utilice un guión de doble byte o un punto de doble byte, asegúrese de escapar ambos caracteres como se escaparía un guión o un punto en una regex. A continuación le mostramos un ejemplo de regex a modo de referencia:
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> Se recomienda usar coincidencia de cadena en lugar de coincidencia de palabras en una lista de palabras clave.

## <a name="for-further-information"></a>Para obtener más información
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
- [Crear un tipo de información confidencial personalizada en PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

Para obtener información sobre cómo usar tipos de información confidencial para cumplir con las normativas de privacidad de datos, vea [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
