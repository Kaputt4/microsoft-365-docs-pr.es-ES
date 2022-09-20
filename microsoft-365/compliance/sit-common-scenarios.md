---
title: Escenarios de uso comunes para tipos de información confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: robmazz
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
description: Cómo implementar escenarios de casos de uso de tipos de información confidencial comunes
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8afef4cdb027c8e2ccbb029a70df885dc685cb2d
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67819213"
---
# <a name="common-usage-scenarios-for-sensitive-information-types"></a>Escenarios de uso comunes para tipos de información confidencial

En este artículo se describe cómo implementar algunos escenarios comunes de casos de uso de tipos de información confidencial (SIT). Puede usar estos procedimientos como ejemplos y adaptarlos a sus necesidades específicas.

## <a name="protect-credit-card-numbers"></a>Protección de números de tarjeta de crédito

Contoso Bank debe clasificar los números de tarjeta de crédito que emiten como confidenciales. Sus tarjetas de crédito comienzan con un conjunto de patrones de seis dígitos. Les gustaría personalizar la definición de tarjeta de crédito de fábrica para detectar solo los números de tarjeta de crédito a partir de sus patrones de seis dígitos.

**Solución sugerida**

1. Cree una copia de la tarjeta de crédito SIT. Siga los pasos para [copiar y modificar un tipo de información confidencial](create-a-custom-sensitive-information-type.md#copy-and-modify-a-sensitive-information-type) para copiar la tarjeta de crédito SIT.
1. Edite el patrón de alta confianza. Siga los pasos descritos en [editar o eliminar el patrón de tipo de información confidencial](sit-get-started-exact-data-match-create-rule-package.md#edit-or-delete-the-sensitive-information-type-pattern).
1. Agregue la comprobación "comienza con" y agregue la lista de dígitos bin (con formato & sin formato). Por ejemplo, para asegurarse de que solo las tarjetas de crédito a partir de 411111 & 433512 deben considerarse válidas, agregue lo siguiente a la lista 4111 11, 4111-11, 411111, 4335 12, 4335-12, 433512.
1. Repita el paso 2 & 3 para el patrón de confianza baja.

## <a name="test-numbers-similar-to-social-security-numbers"></a>Números de prueba similares a los números del Seguro Social

Contoso ha identificado algunos números de prueba de nueve dígitos que desencadenan coincidencias de falsos positivos en la directiva de prevención de pérdida de datos de Microsoft Purview (DLP) de Número de seguridad social (SSN). Les gustaría excluir estos números de la lista de coincidencias válidas para SSN.

**Solución sugerida**

1. Cree una copia del SIT de SSN. Siga los pasos para [copiar y modificar un tipo de información confidencial](create-a-custom-sensitive-information-type.md#copy-and-modify-a-sensitive-information-type) para copiar el SIT de SSN.
1. Edite el patrón de alta confianza. Siga los pasos descritos en [editar o eliminar el patrón de tipo de información confidencial](sit-get-started-exact-data-match-create-rule-package.md#edit-or-delete-the-sensitive-information-type-pattern).
1. Agregue los números que se van a excluir en la comprobación adicional "Excluir valores específicos". Por ejemplo, para excluir 239-23-532 & 23923532, bastará con agregar 23923532.
1. Repita el paso 2 & 3 para otros patrones de confianza.

## <a name="phone-numbers-in-signature-trigger-match"></a>Números de teléfono en coincidencia de desencadenador de firma

Contoso, con sede en Australia, detecta que los números de teléfono de las firmas de correo electrónico desencadenan una coincidencia para su directiva DLP de número de empresa de Australia.

**Solución sugerida**

Agregue un grupo "not" en elementos auxiliares mediante una lista de palabras clave que contenga palabras clave usadas habitualmente en la firma del correo electrónico, como "Phone", "Mobile", "email", "Thanks and regards", etc. Mantenga la proximidad de esta lista de palabras clave a un valor más pequeño, como 50 caracteres, para mejorar la precisión. Para obtener más información, consulte [Introducción a los tipos de información confidencial personalizados](create-a-custom-sensitive-information-type.md).

## <a name="unable-to-trigger-aba-routing-policy"></a>No se puede desencadenar la directiva de enrutamiento de ABA

La directiva DLP no puede desencadenar la directiva de número de enrutamiento de ABA en archivos de Excel grandes porque la palabra clave necesaria no se encuentra en 300 caracteres.

**Solución sugerida**

Cree una copia de la SIT integrada y edítela para cambiar la proximidad de la lista de palabras clave de "300 caracteres" a "En cualquier lugar del documento".

> [!TIP]
> Puede editar la lista de palabras clave para incluir o excluir palabras clave que sean relevantes para su organización.

## <a name="unable-to-detect-credit-card-numbers-with-unusual-delimiters"></a>No se pueden detectar números de tarjeta de crédito con delimitadores inusuales

Contoso Bank ha observado que algunos de sus empleados comparten números de tarjeta de crédito con "/" como delimitador, por ejemplo, 4111/1111/1111/1111, que no se detecta en la definición de tarjeta de crédito de fábrica. Contoso quiere definir su propia expresión regular y validarla mediante LuhnCheck.

**Solución sugerida**

1. Cree una copia de la tarjeta de crédito SIT mediante los pasos descritos [en Personalización de un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md).
1. Adición de un nuevo patrón
1. En el elemento principal, seleccione expresión regular.
1. Defina la expresión regular que incluye "/" como parte de la expresión regular y, a continuación, elija validador y seleccione luhncheck o func_credit_card para asegurarse de que el regex también pasa LuhnCheck.

## <a name="ignore-a-disclaimer-notice"></a>Omitir un aviso de declinación de responsabilidades

Muchas organizaciones agregan declinaciones de responsabilidades legales, declaraciones de divulgación, firmas u otra información en la parte superior o inferior de los mensajes de correo electrónico que entran o salen de sus organizaciones y, en algunos casos, incluso dentro de las organizaciones. Los propios empleados colocan firmas, como citas motivacionales, mensajes sociales, etc. Una declinación de responsabilidades o una firma puede contener los términos presentes en el léxico de un CC y pueden generar una gran cantidad de falsos positivos.  

Por ejemplo, una declinación de responsabilidades típica podría contener palabras como confidencial o confidencial, y una directiva que busque información confidencial la detectará como un incidente, lo que provocará muchos falsos positivos. Por lo tanto, proporcionar a los clientes la opción de omitir la declinación de responsabilidades puede reducir los falsos positivos y aumentar la eficacia del equipo de cumplimiento.

### <a name="example-of-disclaimer"></a>Ejemplo de declinación de responsabilidades

Tenga en cuenta la siguiente declinación de responsabilidades:

AVISO IMPORTANTE:La información incluida en el presente correo electrónico es confidencial, siendo para el uso exclusivo del destinatario arriba mencionado. Los mensajes de correo electrónico dirigidos a clientes de Contoso pueden contener información confidencial y protegida por la ley. Le rogamos que no lea, copie, reenvíe o guarde este mensaje si no es el destinatario señalado. Si ha recibido este mensaje por error, le rogamos que lo devuelva a la dirección de remitente arriba mencionada y borre el mensaje.

Si el SIT se ha configurado para detectar una palabra clave confidencial, el patrón invocará una coincidencia cada vez que se use una declinación de responsabilidades en el correo electrónico, lo que dará lugar a una gran cantidad de falsos positivos.

### <a name="ignore-disclaimer-using-prefix-and-suffix-in-sit"></a>Omitir la declinación de responsabilidades mediante el prefijo y el sufijo en SIT

Una manera de pasar por alto las instancias de palabras clave en la declinación de responsabilidades es excluir las instancias de palabras clave que van precedidas de un prefijo y seguidas de un sufijo.

Tenga en cuenta esta declinación de responsabilidades:

AVISO IMPORTANTE: Este mensaje de correo electrónico está pensado para ser recibido únicamente por personas *con derecho a recibir la* **información confidencial que puede contener**. Los mensajes de correo electrónico dirigidos a clientes de Contoso pueden contener información confidencial y protegida por la ley. Le rogamos que no lea, copie, reenvíe o guarde este mensaje si no es el destinatario señalado. Si ha recibido este mensaje por error, le rogamos que lo devuelva a la dirección de remitente arriba mencionada y borre el mensaje.

Tenemos dos instancias de la palabra clave "confidential" y si configuramos sit para pasar por alto las instancias de esta palabra clave precedidas por prefijos (en cursiva en el ejemplo) y seguidas de sufijos (en negrita en el ejemplo), podemos lograr omitir las declinaciones de responsabilidades en la mayoría de los casos.

Para omitir la declinación de responsabilidades mediante el prefijo y el sufijo:

1. Agregue comprobaciones adicionales en el SIT actual para excluir el texto de prefijo y sufijo a la palabra clave que queremos omitir en la declinación de responsabilidades.
1. Elija excluir el prefijo y, en el cuadro de texto **Prefijos** , escriba **información que contenga**.
1. Elija excluir el sufijo y, en el cuadro de texto **Sufijos** , escriba **y con privilegios legales**.
1. Repita este proceso para otras instancias de las palabras clave en la declinación de responsabilidades, como se muestra en el siguiente gráfico.

### <a name="ignore-disclaimer-by-excluding-secondary-elements"></a>Omitir la declinación de responsabilidades excluyendo elementos secundarios

Otra manera de agregar una lista de elementos auxiliares (instancias de declinación de responsabilidades) que se deben excluir es excluir elementos secundarios.

Tenga en cuenta esta declinación de responsabilidades:

AVISO IMPORTANTE:La información incluida en el presente correo electrónico es confidencial, siendo para el uso exclusivo del destinatario arriba mencionado. Los mensajes de correo electrónico dirigidos a clientes de Contoso pueden contener información confidencial y protegida por la ley. Le rogamos que no lea, copie, reenvíe o guarde este mensaje si no es el destinatario señalado. Si ha recibido este mensaje por error, le rogamos que lo devuelva a la dirección de remitente arriba mencionada y borre el mensaje.

Tenemos dos instancias de la palabra clave "confidential" en este ejemplo. Si configuramos sit para pasar por alto las instancias de esta palabra clave en la declinación de responsabilidades (subrayado como rojo), podemos lograr omitir las declinaciones de responsabilidades en la mayoría de los casos.

:::image type="content" source="../media/sit-scenario-edit-pattern.png" alt-text="Puede agregar más condiciones al patrón para excluir instancias adicionales en la declinación de responsabilidades.":::

Para omitir la declinación de responsabilidades mediante elementos secundarios:

1. Seleccione **No ninguno de estos** grupos en los elementos auxiliares.
1. Agregue las instancias de declinación de responsabilidades que queremos omitir como una lista o diccionario de palabras clave.
1. Agregue las palabras clave como una nueva línea que queremos omitir. Recuerde que la longitud de cada texto no puede tener más de 50 caracteres.
1. Establezca la proximidad de este elemento en 50-60 caracteres del elemento principal.
