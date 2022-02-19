---
title: Validadores regex de tipo de información confidencial y comprobaciones adicionales
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar validadores REGEX y comprobaciones adicionales en los tipos de información de sentisitve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 615d4757be16b3171005105aea8148536e6f3015
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "62902704"
---
# <a name="sensitive-information-type-regex-validators-and-additional-check"></a>Validadores REGEX de tipo de información confidencial y comprobación adicional

> [!IMPORTANT]
> El soporte técnico y el servicio al cliente de Microsoft no puede ayudar a crear clasificaciones personalizadas o patrones de expresiones regulares. Los ingenieros de soporte técnico pueden ofrecer soporte limitado para la característica como, por ejemplo, proporcionar patrones de expresiones regulares de ejemplo para propósitos de prueba o ayudar con la solución de problemas de un patrón de expresión regular existente que no se activa de la forma esperada. Pero no pueden garantizar que el desarrollo personalizado que coincida con el contenido cumplirá sus requisitos u obligaciones.

## <a name="sensitive-information-type-regular-expression-validators"></a>Validadores de expresiones regulares de tipo de información confidencial

### <a name="checksum-validator"></a>Validador de suma de comprobación

Si necesita ejecutar una suma de comprobación en un dígito de una expresión regular, puede usar el *validador de suma de comprobación*. Por ejemplo, diga que necesita crear un SIT para un número de licencia de ocho dígitos donde el último dígito es un dígito de suma de comprobación que se valida con un cálculo mod 9. Ha configurado el algoritmo de suma de comprobación de este tipo:

```console
Sum = digit 1 * Weight 1 + digit 2 * weight 2 + digit 3 * weight 3 + digit 4 * weight 4 + digit 5 * weight 5 + digit 6 * weight 6 + digit 7 * weight 7 + digit 8 * weight 8
Mod value = Sum % 9
If Mod value == digit 8
    Account number is valid
If Mod value != digit 8
    Account number is invalid
```

1. Defina el elemento principal con esta expresión regular:

   ```console
   \d{8}
   ```

2. A continuación, agregue el validador de suma de comprobación.

3. Agregue los valores de peso separados por comas, la posición del dígito de comprobación y el valor mod. Para obtener más información acerca de la operación Modulo, vea [Modulo operation](https://en.wikipedia.org/wiki/Modulo_operation).

   > [!NOTE]
   > Si el dígito de comprobación no forma parte del cálculo de suma de comprobación, use 0 como el peso del dígito de comprobación. Por ejemplo, en el caso anterior, el peso 8 será igual a 0 si el dígito de comprobación no se va a usar para calcular el dígito de comprobación.

   :::image type="content" alt-text="captura de pantalla del validador de suma de comprobación configurado." source="../media/checksum-validator.png" lightbox="../media/checksum-validator.png":::

### <a name="date-validator"></a>Validador de fechas

Si un valor de fecha incrustado en la expresión regular forma parte de un nuevo patrón que está creando, puede usar el validador de fechas para probar que cumple los criterios. Por ejemplo, diga que desea crear un SIT para un número de identificación de empleado de nueve dígitos. Los seis primeros dígitos son la fecha de contratación en formato DDMMYY y los tres últimos son números generados aleatoriamente. Para validar que los seis primeros dígitos tienen el formato correcto.

1. Defina el elemento principal con esta expresión regular:

   ```console
   \d{9}
   ```

2. A continuación, agregue el validador de fecha.

3. Seleccione el formato de fecha y el desplazamiento de inicio. Dado que la cadena de fecha es los seis primeros dígitos, el desplazamiento es `0`.

   :::image type="content" alt-text="captura de pantalla del validador de fecha configurado." source="../media/date-validator.png" lightbox="../media/date-validator.png":::

### <a name="functional-processors-as-validators"></a>Procesadores funcionales como validadores

Puede usar procesadores de funciones para algunos de los SIT más usados como validadores. Esto le permite definir su propia expresión regular al mismo tiempo que garantiza que pasan las comprobaciones adicionales necesarias por el SIT. Por ejemplo, Func_India_Aadhar garantizará que la expresión regular personalizada definida por usted pase la lógica de validación necesaria para la tarjeta Aadhar india. Para obtener más información sobre las funciones DLP que se pueden usar como validadores, vea [Funciones de tipo de información confidencial](sit-functions.md). 

### <a name="luhn-check-validator"></a>Validador de comprobación de Luhn

Puede usar el validador de comprobación de Luhn si tiene un tipo de información confidencial personalizado que incluye una expresión regular que debe pasar el algoritmo [Luhn](https://en.wikipedia.org/wiki/Luhn_algorithm).

## <a name="sensitive-information-type-additional-checks"></a>Comprobaciones adicionales de tipo de información confidencial

Aquí tiene las definiciones y algunos ejemplos de las comprobaciones adicionales disponibles.

**Excluir coincidencias específicas**: Esta comprobación le permite definir palabras clave para excluir al detectar coincidencias del patrón que esté editando. Por ejemplo, puede excluir números de prueba de tarjeta de crédito como "4111111111111111", para que no aparezcan como número válido.

**Empezar o no empezar con caracteres**: Esta comprobación le permite definir los caracteres con que los elementos coincidentes pueden o no pueden empezar. Por ejemplo, si quiere que el patrón detecte solo números de tarjeta de crédito que empiece con 41, 42 o 43, seleccione **Empieza con** y agregue 41, 42 y 43 a la lista, separados por comas. 

**Terminar o no terminar con caracteres**: Esta comprobación le permite definir los caracteres con que los elementos coincidentes pueden o no pueden terminar. Por ejemplo, si su número de Id. de empleado no puede terminar con 0 o 1, seleccione **No termina con** y agregue 0 y 1 a la lista, separados por comas.

**Excluir caracteres duplicados**: esta comprobación le permite ignorar coincidencias en las que todos los dígitos son los mismos. Por ejemplo, si el número de Id. de empleado tiene seis dígitos y no son iguales, puede seleccionar **Excluir caracteres duplicados** para excluir 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999, y 000000 de la lista de coincidencias válidas para la Id. del empleado.

**Incluir o excluir prefijos**: Esta comprobación le permite definir las palabras clave que deben o no deben aparecer inmediatamente antes de la entidad coincidente. En función de su selección, las entidades aparecerán o no como coincidencias si son precedidas por los prefijos que incluya aquí. Por ejemplo, si **Excluye** el prefijo **GUID:**, toda entidad precedida por **GUID:** no se considerará una coincidencia.

**Incluir o excluir sufijos**: Esta comprobación le permite definir las palabras clave que deben o no deben aparecer inmediatamente después de la entidad coincidente. En función de su selección, las entidades aparecerán o no como coincidencias si aparecen seguidas de los sufijos que incluya aquí. Por ejemplo, si **Excluye** el sufijo **GUID:**, cualquier texto seguido de **GUID:** no se considerará una coincidencia.
