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
ms.openlocfilehash: 806c5043d21be15d965814101fe87c00785ca996
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914613"
---
# <a name="learn-about-sensitive-information-types"></a>Obtener más información acerca de los tipos de información confidencial

Identificar y clasificar elementos confidenciales que están bajo el control de las organizaciones es el primer paso de la disciplina [de Protección de la información.](./information-protection.md)  Microsoft 365 proporciona tres formas de identificar elementos para que se puedan clasificar:

- manualmente por los usuarios
- reconocimiento automatizado de patrones, como tipos de información confidencial
- [aprendizaje automático](classifier-learn-about.md)

Los tipos de información confidencial son clasificadores basados en patrones. Detectan información confidencial como seguridad social, tarjeta de crédito o números de cuenta bancaria para identificar elementos confidenciales, consulte [Definiciones](sensitive-information-type-entity-definitions.md) de entidades de tipos de información confidencial

## <a name="sensitive-information-types-are-used-in"></a>Los tipos de información confidencial se usan en

- [Directivas de prevención de pérdida de datos](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](retention.md)
- [Administración de riesgos de Insider](insider-risk-management.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Administración de riesgos interna](insider-risk-management-solution-overview.md)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Administración de privacidad](/privacy/solutions/privacymanagement/privacy-management)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Partes fundamentales de un tipo de información confidencial

Cada entidad de tipo de información confidencial se define mediante estos campos:

- nombre: cómo se hace referencia al tipo de información confidencial
- descripción: describe lo que busca el tipo de información confidencial
- patrón: un patrón define lo que detecta un tipo de información confidencial. Consta de los siguientes componentes
    - Elemento principal: el elemento principal que busca el tipo de información confidencial. Puede ser una expresión **regular con** o sin una validación de suma de comprobación, una lista de palabras **clave,** un **diccionario** de palabras clave o una **función**.
    - Elemento de soporte: elementos que actúan como pruebas de soporte que ayudan a aumentar la confianza de la coincidencia. Por ejemplo, la palabra clave "SSN" cerca de un número SSN. Puede ser una expresión regular con o sin validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.
    - Nivel de confianza: los niveles de confianza (altos, medianos, bajos) reflejan la cantidad de evidencia de soporte que se detectó junto con el elemento principal. Cuanto más evidencia de soporte técnico contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que está buscando.
    - Proximidad: número de caracteres entre el elemento principal y el elemento de soporte técnico

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
- Identidad 
- Identificación tarjeta de identidad nacional 
- DNI 
- Registro nacional de personas de NIC 
- Documento Nacional de Identidad 
- Registro nacional de las personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Más información sobre los niveles de confianza

En una definición de entidad de tipo de información **confidencial,** el nivel de confianza refleja la cantidad de evidencia compatible que se detecta además del elemento principal. Cuanto más evidencia de soporte técnico contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que está buscando. Por ejemplo, las coincidencias con un nivel de confianza alto contendrán evidencias más compatibles cerca del elemento principal, mientras que las coincidencias con un nivel de confianza bajo contendrán poca o ninguna evidencia compatible en proximidad. 

Un nivel de confianza alto devuelve el menor número de falsos positivos, pero puede dar como resultado más falsos negativos. Los niveles de confianza bajos o medianos devuelven más falsos positivos, pero de pocos a cero falsos negativos.

- **confianza baja:** valor de 65, los elementos coincidentes contendrán el menor número de falsos negativos, pero los más falsos positivos. La confianza baja devuelve todas las coincidencias de confianza baja, media y alta.
- **confianza media:** valor de 75, los elementos coincidentes contendrán una cantidad promedio de falsos positivos y falsos negativos. La confianza media devuelve todas las coincidencias de confianza media y alta.  
- **elevada confianza:** valor de 85, los elementos coincidentes contendrán el menor número de falsos positivos, pero los negativos más falsos. La confianza alta solo devuelve coincidencias de confianza alta.  

Debe usar patrones de alto nivel de confianza con recuentos bajos, por ejemplo, de cinco a diez, y patrones de confianza bajos con recuentos más altos, por ejemplo, 20 o más.

> [!NOTE]
> Si tiene directivas existentes o tipos de información confidencial personalizados (SIT) definidos con niveles de confianza basados en números (también conocidos como precisión), se asignarán automáticamente a los tres niveles de confianza discretos; confianza baja, confianza media y confianza alta, en toda la interfaz de usuario del Centro de seguridad y cumplimiento.
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza de entre 76 y 100 se asignarán a una elevada confianza. 
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza de entre 66 y 75 se asignarán a confianza mediana.
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza inferiores o iguales a 65 se asignarán a una confianza baja. 

## <a name="creating-custom-sensitive-information-types"></a>Crear tipos de información confidencial personalizados

Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:

- **Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad. Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave. Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).

- **Usar EDM** Puede establecer los tipos de información confidencial mediante la clasificación basada en la coincidencia exacta de los datos (EDM). Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente. Vea Obtener información sobre tipos de información confidencial [basados en coincidencias exactas de datos.](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

- **Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell. Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración. Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
> Los niveles de confianza mejorados están disponibles para su uso inmediato en Prevención de pérdida de datos para servicios de Microsoft 365, Microsoft Information Protection para servicios Microsoft 365, Cumplimiento de comunicaciones, Gobierno de la información y Administración de registros.
> Microsoft 365 Information Protection ahora admite idiomas de juego de caracteres de doble byte para:
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
> 
> Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).

> [!TIP]
> Para detectar patrones que contengan caracteres chinos/japoneses y caracteres de un solo byte o para detectar patrones que contengan chino/japonés e inglés, defina dos variantes de la palabra clave o regex.
> - Por ejemplo, para detectar una palabra clave como "机密的document", utilice dos variantes de la palabra clave; una con un espacio entre el texto japonés y el inglés y otra sin espacio entre el texto japonés y el inglés. Por lo tanto, las palabras clave que deben agregarse en el SIT deben ser "机密的document" y "机密的document". Del mismo modo, para detectar la frase "東京オリンピック2020", se deben utilizar dos variantes: "東京オリンピック 2020" y "東京オリンピック2020"".
> 
> Junto con los caracteres chinos/japoneses y de dos bytes, si la lista de palabras clave o frases también contiene palabras no chinas o no japonesas (solo en inglés), se recomienda crear dos diccionarios o listas de palabras clave. Uno para las palabras clave que contienen caracteres chinos, japoneses o de dos bytes; y otro solo para inglés. 
> - Por ejemplo, si desea crear una lista o diccionario de palabras clave con tres frases "Extremadamente confidencial", "機密性が高い" y "机密的document", deberá crear dos listas de teclado. 
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
