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
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 91366e8f255d277d4d40de4c4cd3330283da718c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166455"
---
# <a name="learn-about-sensitive-information-types"></a>Obtener más información acerca de los tipos de información confidencial

Identificar y clasificar elementos confidenciales que están bajo el control de su organización es el primer paso de la disciplina [de Protección de la información.](protect-information.md)  Microsoft 365 ofrece tres formas de identificar elementos para que se puedan clasificar:

- manualmente por los usuarios
- reconocimiento de patrones automatizado, como los tipos de información confidencial
- [aprendizaje automático](classifier-learn-about.md)

Los tipos de información confidencial son clasificadores basados en patrones. Detectan información confidencial, como números de cuentas bancarias, tarjetas de crédito o seguridad social, para identificar elementos confidenciales, ver definiciones de entidad de [tipos de información confidencial](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>Los tipos de información confidencial se usan en

- [Directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) 
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](retention.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Partes fundamentales de un tipo de información confidencial

Cada entidad de tipo de información confidencial se define mediante estos campos:

- nombre: cómo se hace referencia al tipo de información confidencial
- description: describe lo que busca el tipo de información confidencial
- patrón: un patrón define lo que detecta un tipo de información confidencial. Consta de los siguientes componentes
    - Elemento principal: el elemento principal que busca el tipo de información confidencial. Puede ser una expresión **regular con o** sin una validación de suma de comprobación, una lista de palabras clave, un diccionario de palabras clave o una **función**.  
    - Elemento de apoyo: elementos que actúan como evidencia de apoyo que ayudan a aumentar la confianza de la coincidencia. Por ejemplo, la palabra clave "SSN" cerca de un número de SSN. Puede ser una expresión regular con o sin una validación de suma de comprobación, lista de palabras clave, diccionario de palabras clave.
    - Nivel de confianza: los niveles de confianza (alto, medio, bajo) reflejan cuánta evidencia de apoyo se detectó junto con el elemento principal. Cuanto más evidencia de apoyo contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que buscas.
    - Proximidad: número de caracteres entre el elemento principal y el elemento de apoyo

![Diagrama de prueba corroboradora y ventana de proximidad](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Obtenga más información sobre los niveles de confianza en este vídeo


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Ejemplo de tipo de información confidencial


## <a name="argentina-national-identity-dni-number"></a>Número de identidad nacional (DNI) de Argentina

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

Una directiva DLP tiene confianza media de que se detecta este tipo de información confidencial si, en una proximidad de 300 caracteres:
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
- Registro nacional de personas nic 
- Documento Nacional de Identidad 
- Registro nacional de las personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Más información sobre los niveles de confianza

En una definición de entidad de tipo de información **confidencial,** el nivel de confianza refleja cuánta evidencia de apoyo se detecta además del elemento principal. Cuanto más evidencia de apoyo contenga un elemento, mayor será la confianza de que un elemento coincidente contenga la información confidencial que buscas. Por ejemplo, las coincidencias con un nivel de confianza alto contendrán más evidencias de apoyo cerca del elemento principal, mientras que las coincidencias con un nivel de confianza bajo contendrán poca o ninguna evidencia de apoyo en proximidad. 

Un nivel de confianza alto devuelve el menor número de falsos positivos, pero puede dar como resultado más falsos negativos. Los niveles de confianza bajos o medianos devuelven más falsos positivos, pero algunos a cero falsos negativos.

- **confianza baja:** valor de 65, los elementos coincidentes contendrán el menor número de falsos negativos, pero los más falsos positivos.  
- **confianza media:** valor de 75, los elementos coincidentes contendrán una cantidad media de falsos positivos y falsos negativos.  
- **confianza alta:** valor de 85, los elementos coincidentes contendrán el menor número de falsos positivos, pero los más falsos negativos.  

Debes usar patrones de nivel de confianza alto con recuentos bajos, por ejemplo, de cinco a diez, y patrones de confianza baja con recuentos más altos, por ejemplo, 20 o más.

## <a name="creating-custom-sensitive-information-types"></a>Crear tipos de información confidencial personalizados

Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:

- **Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad. Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave. Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).

- **Usar EDM** Puede establecer los tipos de información confidencial mediante la clasificación basada en la coincidencia exacta de los datos (EDM). Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente. Vea [Crear un tipo de información confidencial personalizado con coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell. Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración. Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
> Los niveles de confianza mejorados están disponibles para su uso inmediato en prevención de pérdida de datos para los servicios de Microsoft 365, Microsoft Information Protection para servicios de Microsoft 365, cumplimiento de comunicaciones, gobierno de información y administración de registros.

> Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés

>Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).

## <a name="for-further-information"></a>Para obtener más información
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
- [Crear un tipo personalizado de información confidencial en PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
