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
description: En este artículo se proporciona información general sobre los tipos de información confidencial y cómo detectan información confidencial, como el seguro social, la tarjeta de crédito o los números de cuenta bancaria para identificar elementos confidenciales.
ms.openlocfilehash: 2a7f639097203f06795945dbd08fa64db3a1f0df
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66944051"
---
# <a name="learn-about-sensitive-information-types"></a>Obtener más información acerca de los tipos de información confidencial

La identificación y clasificación de elementos confidenciales que están bajo el control de las organizaciones es el primer paso en la [materia de Information Protection](./information-protection.md).  Microsoft Purview proporciona tres formas de identificar elementos para que se puedan clasificar:

- manualmente por los usuarios
- reconocimiento automatizado de patrones, como los tipos de información confidencial
- [aprendizaje automático](classifier-learn-about.md)

Los tipos de información confidencial (SIT) son clasificadores basados en patrones. Detectan información confidencial, como el seguro social, la tarjeta de crédito o los números de cuenta bancaria para identificar elementos confidenciales, consulte [Definiciones de entidades de tipos de información confidencial](sensitive-information-type-entity-definitions.md) para obtener una lista completa de todos los SIT.

Microsoft proporciona un gran número de SIT preconfigurados o puede crear los suyos propios.

## <a name="sensitive-information-types-are-used-in"></a>Los tipos de información confidencial se usan en

- [directivas de Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](retention.md)
- [Administración de riesgos internos](insider-risk-management.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Priva](/privacy/priva)



## <a name="categories-of-sensitive-information-types"></a>Categorías de tipos de información confidencial

### <a name="built-in-sensitive-information-types"></a>Tipos de información confidencial integrados

Microsoft crea estos SIT en la consola de cumplimiento de forma predeterminada. Estos SIT no se pueden editar, pero se pueden usar como plantillas y copiarse para crear tipos de información confidencial personalizados. Consulte [Definiciones de entidades de tipo información confidencial](sensitive-information-type-entity-definitions.md) para obtener una lista completa de todos los SIT.

### <a name="named-entity-sensitive-information-types"></a>Tipos de información confidencial de entidades con nombre

Los SIT de entidad con nombre también se muestran en la consola de cumplimiento de forma predeterminada. Detectan nombres de personas, direcciones físicas y términos y condiciones médicos. No se pueden editar ni copiar. Consulte [Más información sobre las entidades con nombre ](named-entities-learn.md#learn-about-named-entities) para obtener más información. Los SIT de entidad con nombre se incluyen en dos tipos:

**un-bundled**

Estos SIT de entidad con nombre tienen un enfoque más estrecho, como un único país o una única clase de términos. Úselas cuando necesite una directiva DLP con un ámbito de detección más restringido. Consulte [Ejemplos de SIT de entidades con nombre](named-entities-learn.md#examples-of-named-entity-sits).

**Liado**

Los SIT de entidad con nombre agrupados detectan todas las coincidencias posibles en una clase, como Todas las direcciones físicas. Úselos como criterios generales en las directivas DLP para detectar elementos confidenciales. Consulte [Ejemplos de SIT de entidades con nombre](named-entities-learn.md#examples-of-named-entity-sits).

### <a name="custom-sensitive-information-types"></a>Tipos de información confidencial personalizada

Si los tipos de información confidencial preconfigurados no satisfacen sus necesidades, puede crear sus propios tipos de información confidencial personalizados que defina completamente o puede copiar uno de los integrados y modificarlo. Consulte [Creación de un tipo de información confidencial personalizada en el Centro de cumplimiento](create-a-custom-sensitive-information-type.md) para obtener más información.

### <a name="exact-data-match-sensitive-information-types"></a>Coincidencia exacta de datos con tipos de información confidencial

Todos los SIT basados en EDM se crean desde cero. Se usan para detectar elementos que tienen valores exactos que se definen en una base de datos de información confidencial. Consulte [Información sobre los tipos de información confidencial basados en coincidencias de datos exactas](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) para obtener más información.

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Partes fundamentales de un tipo de información confidencial

Cada entidad de tipo de información confidencial se define mediante estos campos:

- name: cómo se hace referencia al tipo de información confidencial
- description: describe lo que busca el tipo de información confidencial.
- pattern: un patrón define lo que detecta un tipo de información confidencial. Consta de los siguientes componentes.
  - Elemento principal: elemento principal que busca el tipo de información confidencial. Puede ser una **expresión regular** con o sin una validación de suma de comprobación, una **lista de palabras clave**, un **diccionario de palabras clave** o una **función**.
  - Elemento auxiliar: elementos que actúan como evidencia auxiliar que ayudan a aumentar la confianza de la coincidencia. Por ejemplo, la palabra clave "SSN" se encuentra cerca de un número SSN. Puede ser una expresión regular con o sin validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.
  - Nivel de confianza: los niveles de confianza (alto, medio, bajo) reflejan la cantidad de pruebas auxiliares detectadas junto con el elemento principal. Cuantos más pruebas auxiliares contenga un elemento, mayor será la confianza en que un elemento coincidente contiene la información confidencial que está buscando.
  - Proximidad: número de caracteres entre el elemento principal y el elemento auxiliar.

![Diagrama de evidencia corroborativa y ventana de proximidad.](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Obtenga más información sobre los niveles de confianza en este breve vídeo.

 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]

### <a name="example-sensitive-information-type"></a>Ejemplo de tipo de información confidencial

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

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

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
- Tarjeta de identidad nacional de identificación
- DNI
- Registro Nacional de Personas de NIC
- Documento Nacional de Identidad
- Registro nacional de las personas
- Identidad
- Identificación

### <a name="more-on-confidence-levels"></a>Más información sobre los niveles de confianza

En una definición de entidad de tipo de información confidencial, el **nivel de confianza** refleja cuánta evidencia auxiliar se detecta además del elemento principal. Cuantos más pruebas auxiliares contenga un elemento, mayor será la confianza en que un elemento coincidente contiene la información confidencial que está buscando. Por ejemplo, las coincidencias con un nivel de confianza alto contendrán más pruebas auxiliares cerca del elemento principal, mientras que las coincidencias con un nivel de confianza bajo contendrán poca o ninguna evidencia auxiliar en proximidad.

Un nivel de confianza alto devuelve el menor número de falsos positivos, pero podría dar lugar a más falsos negativos. Los niveles de confianza bajo o medio devuelve más falsos positivos, pero pocos a cero falsos negativos.

- **baja confianza**: los elementos coincidentes contendrán el menor número de falsos negativos, pero los más falsos positivos. La confianza baja devuelve todas las coincidencias de confianza baja, media y alta. El nivel de confianza bajo tiene un valor de 65.
- **confianza media**: los elementos coincidentes contendrán una cantidad media de falsos positivos y falsos negativos. La confianza media devuelve todas las coincidencias de confianza media y alta. El nivel de confianza medio tiene un valor de 75.
- **alta confianza**: los elementos coincidentes contendrán el menor número de falsos positivos, pero los más falsos negativos. La confianza alta solo devuelve coincidencias de confianza alta y tiene un valor de 85.

Debe usar patrones de alto nivel de confianza con recuentos bajos, por ejemplo, de cinco a diez, y patrones de confianza bajos con recuentos más altos, por ejemplo, 20 o más.

> [!NOTE]
> Si tiene directivas existentes o tipos de información confidencial (SIT) personalizados definidos mediante niveles de confianza basados en números (también conocidos como precisión), se asignarán automáticamente a los tres niveles de confianza discretos; confianza baja, confianza media y confianza alta en la interfaz de usuario de Security @ Compliance Center.
>
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza de entre 76 y 100 se asignarán a una alta confianza.
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza de entre 66 y 75 se asignarán a confianza media.
> - Todas las directivas con precisión mínima o patrones SIT personalizados con niveles de confianza inferiores o iguales a 65 se asignarán a una confianza baja.

## <a name="creating-custom-sensitive-information-types"></a>Crear tipos de información confidencial personalizados

Puede elegir entre varias opciones para crear tipos de información confidencial personalizados en el Centro de cumplimiento.

- **Usar la interfaz de usuario** : puede configurar un tipo de información confidencial personalizada mediante la interfaz de usuario del Centro de cumplimiento. Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave. Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).

- **Usar EDM** : puede configurar tipos de información confidencial personalizados mediante la clasificación basada en coincidencia exacta de datos (EDM). Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente. Consulte [Información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types).

- **Usar PowerShell** : puede configurar tipos de información confidencial personalizados mediante PowerShell. Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración. Consulte [Creación de un tipo de información confidencial personalizada en PowerShell de cumplimiento de seguridad &](create-a-custom-sensitive-information-type-in-scc-powershell.md).

> [!NOTE]
> Los niveles de confianza mejorados están disponibles para su uso inmediato en los servicios de prevención de pérdida de datos de Microsoft Purview, protección de la información, cumplimiento de comunicaciones, administración del ciclo de vida de datos y administración de registros.
> Information Protection ahora admite idiomas de juego de caracteres de doble byte para:
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
>
> Este soporte está disponible para tipos de información confidencial. Consulte las [notas de la versión de la compatibilidad de Information Protection con juegos de caracteres de doble byte](mip-dbcs-relnotes.md) para obtener más información.

> [!TIP]
> Para detectar patrones que contengan caracteres chinos/japoneses y caracteres de un solo byte o para detectar patrones que contengan chino/japonés e inglés, defina dos variantes de la palabra clave o regex.
>
> - Por ejemplo, para detectar una palabra clave como "机密的document", utilice dos variantes de la palabra clave; una con un espacio entre el texto japonés y el inglés y otra sin espacio entre el texto japonés y el inglés. Por lo tanto, las palabras clave que deben agregarse en el SIT deben ser "机密的document" y "机密的document". Del mismo modo, para detectar la frase "東京オリンピック2020", se deben utilizar dos variantes: "東京オリンピック 2020" y "東京オリンピック2020"".
>
> Junto con caracteres de byte chino, japonés o doble, si la lista de palabras clave o frases también contiene palabras no chinas o japonesas (como solo inglés), debe crear dos listas de diccionarios o palabras clave. Uno para las palabras clave que contienen caracteres chinos, japoneses o de dos bytes; y otro solo para inglés.
>
> - Por ejemplo, si desea crear una palabra clave dictionary/list con tres frases "Extremadamente confidencial", "機密性が高い" y "机密的document", debe crear dos listas de palabras clave.
>     1. Extremadamente confidencial
>     2. 機密性が高い, 机密的document y 机密的 document
>
> Al crear una regex que utilice un guión de doble byte o un punto de doble byte, asegúrese de escapar ambos caracteres como se escaparía un guión o un punto en una regex. A continuación le mostramos un ejemplo de regex a modo de referencia:
>
> `(?<!\d)([4][0-9]{3}[\-?\-\t]*[0-9]{4}`
>
> Se recomienda usar la coincidencia de cadena en lugar de la coincidencia de palabras en una lista de palabras clave.

## <a name="for-further-information"></a>Para obtener más información

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
- [Creación de un tipo de información confidencial personalizada en PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

Para obtener información sobre cómo usar tipos de información confidencial para cumplir con las normativas de privacidad de datos, consulte Implementación de la [protección de la información para las regulaciones de privacidad de datos con Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
