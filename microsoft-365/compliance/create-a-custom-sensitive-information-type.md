---
title: Crear tipos de información confidencial personalizados
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
description: Obtenga información sobre cómo crear, modificar, quitar y probar tipos de información confidencial personalizados en el Centro de cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2526ab9fdde4e5cedbbf3e831e6ec8ac9a6a5747
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "62900819"
---
# <a name="create-custom-sensitive-information-types-in-the-compliance-center"></a>Crear tipos de información confidencial personalizados en el Centro de cumplimiento

Si los tipos de información confidencial predefinidos no satisfacen sus necesidades, puede crear sus propios tipos de información confidencial personalizados. Al hacerlo, puede copiar uno de los tipos predefinidos y modificarlo o definirlo completamente usted mismo.

Los tipos de información confidencial personalizados se agregan al paquete de reglas denominado Microsoft.SCCManaged.CustomRulePack `Microsoft.SCCManaged.CustomRulePack`.

Hay dos formas de crear un tipo de información confidencial:

- [Desde cero (usted define completamente todos los elementos)](#create-a-custom-sensitive-information-type)
- [Copiando un tipo de información confidencial existente y modificándolo](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>Antes de empezar

- Debe estar familiarizado con los tipos de información confidencial y saber de qué se componen. Consulte [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md). Es fundamental comprender los roles de:
    - [Las expresiones regulares](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/): los tipos de información confidencial de Microsoft 365 usan el motor Boost.RegEx 5.1.3
    - Listas de palabras clave: puede crear las suyas a medida que defina el tipo de información confidencial o elegir entre listas de palabras clave existentes.
    - [Diccionario de palabras clave](create-a-keyword-dictionary.md)
    - [Funciones de tipo de información confidencial](sit-functions.md)
    - [Niveles de confianza](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- Debe contar con los permisos de administrador global o de administrador de cumplimiento para crear, probar e implementar un tipo de información confidencial personalizada por medio de la interfaz de usuario. Vea [Acerca de las funciones de administración](/office365/admin/add-users/about-admin-roles)en Office 365.


- Su organización debe tener una suscripción, como Office 365 Enterprise, que incluye la prevención de pérdida de datos (DLP). [Ver Política de Mensajería y Servicio de ServiceDescription](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc) 


> [!IMPORTANT]
> El soporte técnico y el servicio al cliente de Microsoft no puede ayudar a crear clasificaciones personalizadas o patrones de expresiones regulares. Los ingenieros de soporte técnico pueden ofrecer soporte limitado para la característica como, por ejemplo, proporcionar patrones de expresiones regulares de ejemplo para propósitos de prueba o ayudar con la solución de problemas de un patrón de expresión regular existente que no se activa de la forma esperada. Pero no pueden garantizar que el desarrollo personalizado que coincida con el contenido cumplirá sus requisitos u obligaciones.

## <a name="create-a-custom-sensitive-information-type"></a>Crear un tipo de información confidencial personalizado

Use este procedimiento para crear un nuevo tipo de información confidencial y definirlo usted mismo por completo. 

1. En el Centro de cumplimiento, ve a **Clasificación** \> de datos **Tipos de información confidencial** y elige **Crear tipo de información confidencial**.

2. Rellene los valores de **Nombre** y **Descripción** y elija **Siguiente**.

3. Elija **Crear patrón**. Puede crear varios patrones, cada uno con diferentes elementos y niveles de confianza, a medida que defina el nuevo tipo de información confidencial.

4. Elija el valor predeterminado del Nivel de confianza para el patrón. Los valores son **Confianza baja**, **Confianza media** y **Confianza alta**.

5. Elegir y definir el **Elemento principal**. El elemento principal puede ser una **Expresión regular** con un validador opcional, una **lista de palabras clave**, un **diccionario de palabras clave** o una de las **funciones preconfiguradas**. Para obtener más información sobre las funciones DLP, vea [Funciones de tipo de información confidencial](sit-functions.md). Para obtener más información sobre la fecha y los validadores de suma de comprobación, consulte Validadores de expresiones [regulares](sit-regex-validators-additional-checks.md#sensitive-information-type-regular-expression-validators) de tipo de información confidencial.

6. Rellene un valor para **Proximidad de caracteres**.

7. (Opcional) Si los tiene, agregue elementos de soporte. Los elementos de soporte pueden ser una expresión regular con un validador opcional, una lista de palabras clave, un diccionario de palabras clave o una de las funciones predefinidas. Los elementos de soporte pueden tener su propia **configuración de proximidad de** caracteres. 

8. (Opcional) Agregar [**comprobaciones adicionales**](sit-regex-validators-additional-checks.md#sensitive-information-type-additional-checks) de la lista de comprobaciones disponibles.

9. Seleccione **Crear**.

10. Elija **Siguiente**.

11. Elija el **nivel de confianza recomendado** de este tipo de información confidencial.

12. Revise la configuración y elija **Enviar**.

    > [!IMPORTANT]
    > Microsoft 365 usa el rastreador de búsqueda para identificar y clasificar información confidencial en los sitios de SharePoint Online y OneDrive para la Empresa. Para identificar el nuevo tipo de información confidencial personalizado en el contenido existente, se necesita volver a rastrear el contenido. El contenido se rastrea en función de una programación, pero puede volver a rastrear de forma manual el contenido de una colección de sitios, lista o biblioteca. Para obtener más información, vea [Solicitar manualmente el rastreo y una nueva indexación de un sitio, una biblioteca o una lista](/sharepoint/crawl-site-content).

13. En la **clasificación de datos**, verá todos los tipos de información confidencial. Elija **Actualizar** y luego encuentre el tipo de información confidencial que ha creado con la herramienta de búsqueda o explorando.

### <a name="copy-and-modify-a-sensitive-information-type"></a>Copiar y modificar un tipo de información confidencial existente

Use este procedimiento para crear un nuevo tipo de información confidencial que se base en un tipo de información confidencial existente. 

> [!NOTE]
> Estos SIT no se pueden copiar:
> - Número de licencia de conducir de Canadá
> - Número de licencia de conducir de la UE
> - Número de identificación nacional de la UE
> - Número de pasaporte de la UE
> - Número de seguridad social de la UE o identificación equivalente
> - Número de identificación fiscal de la UE
> - Clasificación internacional de las enfermedades (ICD-10-CM)
> - Clasificación internacional de las enfermedades (ICD-9-CM)
> - Número de licencia de conducir de EE. UU.

También puede crear tipos de información confidencial con PowerShell y usar las funciones de coincidencia de datos exacta. Para obtener más información sobre estos métodos, vea:
- [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimientol](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

1. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial que desee copiar.

2. En el menú flotante, elija **Copiar**.

3. En la lista de tipos de información confidencial, seleccione **Actualizar** y examine o busque la copia que acaba de hacer. Se admite la búsqueda de cadenas parciales, por lo que puede buscar `copy` y la búsqueda le devolverá todos los tipos de información confidencial con la cadena `copy` en el nombre. 

4. Rellene los valores de **Nombre** y **Descripción** y elija **Siguiente**.

5. Elija su copia del tipo de información confidencial y seleccione **Editar**. 

6. Asigne al tipo de información confidencial un **Nombre** y **Descripción** nuevos.

7. Puede elegir editar o quitar los patrones existentes y agregar otros nuevos. Elija el valor predeterminado del Nivel de confianza para el nuevo patrón. Los valores son **Confianza baja**, **Confianza media** y **Confianza alta**.

8. Elegir y definir el **Elemento principal**. El elemento principal puede ser una **Expresión regular**, una **lista de palabras clave**, un **diccionario de palabras clave** o una de las **funciones preconfiguradas**. Vea Funciones [de tipo de información confidencial](sit-functions.md).

9. Rellene un valor para **Proximidad de caracteres**.

10. (Opcional) Si tiene elementos **de soporte técnico o** [**comprobaciones**](sit-regex-validators-additional-checks.md#sensitive-information-type-additional-checks) adicionales, agrégrelos. Si es necesario, puede agrupar los **Elementos de apoyo**.

11. Seleccione **Crear**.

12. Elija **Siguiente**.

13. Elija el **nivel de confianza recomendado** de este tipo de información confidencial.

14. Revise la configuración y elija **Enviar**.

## <a name="test-a-sensitive-information-type"></a>Cómo probar un tipo de información confidencial personalizado

Puede probar cualquier tipo de información confidencial en la lista. Le recomendamos que pruebe todos los tipos de información confidencial que cree antes de usarlos en una directiva.

1. Prepare dos archivos, por ejemplo documentos de Word. Uno debe tener contenido que coincida con los elementos especificados en el tipo de información confidencial y el otro elementos que no coincidan.

2. En el Centro de cumplimiento, vaya a **Clasificación de datos** \> **Tipos de información confidencial**. Elija el tipo de información confidencial de la lista para abrir el panel de detalles y elija **Probar**.

3. Cargue un archivo y elija **Probar**.

4. En la página **Resultados de coincidencia**, revise los resultados y, después, seleccione **Finalizar**.

## <a name="custom-sensitive-information-types-limits"></a>Límites de tipos de información confidencial personalizados

Para garantizar un alto rendimiento y una latencia inferior, existen limitaciones en las configuraciones de SIT personalizadas.

|Límite|Valor|
|--------|--------|
|número máximo de SIT personalizados creados a través del Centro de cumplimiento| 500 |
|longitud máxima de expresión regular| 1024 caracteres|
|longitud máxima de un término determinado en una lista de palabras clave| 50 caracteres|
|número máximo de términos en la lista de palabras clave| 2048|
|número máximo de regexes distintos por tipo de información confidencial| 20|
|tamaño máximo de un diccionario de palabras clave (compresión posterior)| 1 MB (~1.000.000 caracteres)|
|número máximo de SIT basados en diccionario de palabras clave en un inquilino|50 |

> [!NOTE] 
> Si tienes una empresa que necesita crear más de 500 SIT personalizados, genera un vale de soporte técnico.

### <a name="instance-count-supported-values-for-sit"></a>Valores admitidos de recuento de instancias para SIT

El límite de recuento de instancias SIT se aplica cuando los SIT se usan en estas soluciones:

- Directivas DLP
- Protección de la información
- Gobierno de la información
- Cumplimiento de la comunicación
- Records Management
- Microsoft Defender for Cloud Apps
- Microsoft Priva

Para que un elemento analizado cumpla los criterios de regla, el número de instancias únicas de un SIT en cualquier elemento único debe estar entre los valores mínimo y máximo. Esto se denomina recuento **de instancias**.

- **Campo** mínimo: el límite inferior (número mínimo) de instancias únicas de un SIT que se deben encontrar en un elemento para desencadenar una coincidencia. El campo min admite valores de:
    - De 1 a 500
- **Campo** máximo: el límite superior del número de instancias únicas de un SIT que se pueden encontrar en un elemento y que aún desencadenan una coincidencia. El campo máximo admite valores de:
    - 1 a 500: úselo cuando desee establecer un límite superior específico de 500 o menos en el número de instancias de un SIT en un elemento.
    - Any: `Any` se usa cuando desee que se cumplan los criterios de recuento de instancias únicos cuando se encuentra un número indefinido de instancias únicas de un SIT en un elemento analizado y ese número de instancias únicas cumple o supera el número mínimo de instancias únicas. En otras palabras, los criterios de recuento de instancias únicos se cumplen siempre que se cumpla el valor mínimo.

Por ejemplo, si desea que la regla desencadene una coincidencia cuando se encuentran al menos 500 instancias únicas de un SIT en un solo elemento,  `500` establezca el valor mínimo en y el **valor** `Any`máximo en .

> [!NOTE]
> Microsoft 365 Information Protection es compatible con los idiomas del juego de caracteres de doble byte para:
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
>
>Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).

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
>    - (?<!\d) ([4][0-9]{3} [\-?\-\t]*[0-9]{4})
>
> Se recomienda utilizar una coincidencia de cadenas en lugar de una coincidencia de palabras en una lista de palabras clave.
