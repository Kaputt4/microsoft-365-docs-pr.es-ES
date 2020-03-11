---
title: Ciclo de vida de productos de escritorio administrado de Microsoft
description: En este tema se enumeran las especificaciones de dispositivos usadas en el escritorio administrado por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: b65724a1eee35149d473fb69ff646b5ef5751b2c
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583177"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Ciclo de vida de productos de escritorio administrado de Microsoft

Ventajas del escritorio administrado por Microsoft los usuarios finales aseguran que siempre usen dispositivos que ofrecen el mejor rendimiento, confiabilidad, diseño y capacidades de seguridad (por ejemplo, compatibilidad con características como Windows Hello). Para ello, el escritorio administrado de Microsoft mantiene un breve catálogo de los [dispositivos aprobados](device-list.md)que se actualizan de forma continua. 
 
Este tema detalla el ciclo de vida de los dispositivos a medida que se agregan y se quitan del catálogo aprobado. 

> [!NOTE]
> En este tema, realizaremos una distinción entre un "dispositivo" y un "producto". Por "Device", significa un equipo individual específico. Por ejemplo, "número de serie 1234", "portátil de la factura", "VM compartida XYZ" hacen referencia a dispositivos específicos. Un "producto", sin embargo, hace referencia a una colección o a una familia de dispositivos. Por ejemplo, "equipo portátil Fabrikam", "equipo portátil Adatum ZX450", etc. Esto es importante porque los productos que se agregan a la lista, el catálogo y los dispositivos [aprobados](device-list.md)son los que se inscriben en el escritorio administrado por Microsoft.

## <a name="product-lifecycle"></a>Ciclo de vida del producto

 Generalmente, los productos se desplazan a través de estas fases del ciclo de vida:

- [Lanzamiento y evaluación del producto](#product-release-and-evaluation)
- [Período de disponibilidad principal del producto](#product-primary-availability-period)
- [Período de gracia del producto](#product-grace-period)
- [Retirada de productos](#product-retirement)


En esta ilustración se muestra toda la secuencia:

![escala de tiempo del ciclo de vida: comenzando con la disponibilidad general del producto, "disponibilidad principal" dura dos años. Durante este tiempo, la ventana de certificación finaliza y en algún punto en el que el dispositivo está incorporado. Al final de la disponibilidad principal, el producto se archiva y comienza el "período de gracia" de tres años. Desde el momento en que el dispositivo está incorporado, tiene un período de 3 años de uso hasta que se quita de la administración. Al final del período de gracia, se quita el producto del catálogo.](../../media/non-dark1-edits.PNG)

Los productos permanecen en el catálogo durante un máximo de 24 meses, pero los <em>dispositivos</em> permanecen bajo la administración durante 3 años según sus fechas de inscripción individuales. De hecho, cada producto tiene tres fechas importantes, pero cada dispositivo solo tiene una. Para los productos, las tres fechas se calculan en función de la <em>fecha de aprobación</em>y, por lo tanto, publicamos estas fechas tras la aprobación, de modo que siempre pueda seguir adelante y planear adecuadamente el ciclo de vida completo del producto.

En esta tabla se muestran las fechas de ejemplo para un producto teórico:


|Producto  |Fecha de aprobación  |Fin de la disponibilidad principal  |Fin de la elegibilidad  |
|---------|---------|---------|---------|
|Portátil Fabrikam    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Portátil Adatum   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

En esta tabla se muestran las fechas de ejemplo para *dispositivos*teóricos:


|IDENTIFICADOR de dispositivo  |Fecha de inscripción  |Fecha de retirada  |
|---------|---------|---------|
|#123412 de equipo portátil     |  2/3/2018       |  2/3/2021       |
|#321513 de escritorio     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Lanzamiento y evaluación del producto

El ciclo de vida del producto comienza cuando un fabricante publica públicamente el producto:

![escala de tiempo de ciclo de vida que muestra el período de lanzamiento y evaluación](../../media/non-dark3-edits.PNG)

Durante esta fase, el equipo de ingeniería de escritorio administrado por Microsoft realiza su evaluación y certificación de un producto. El equipo evalúa cosas como la confiabilidad y el rendimiento con Windows, el cumplimiento de una línea de base de hardware, el comportamiento del mercado y la preparación del canal y del inventario, entre otras cosas. Este proceso suele tardar aproximadamente 6 semanas.
  
Microsoft Managed Desktop solo evaluará los dispositivos para la certificación en los primeros 6 meses de disponibilidad. Esto garantiza que siempre nos centraremos en el esfuerzo de la última generación de hardware.
 
Al final de esta fase, Microsoft Managed Desktop agrega el producto a la [lista aprobada](device-list.md), lo que libera eficazmente el producto por los clientes inscritos. Independientemente de la fecha en la que se certifica un dispositivo, la **fecha aprobada** es la fecha de la disponibilidad general del producto. 


## <a name="product-primary-availability-period"></a>Período de disponibilidad principal del producto

Este período es la base de la disponibilidad del producto:

![escala de tiempo de ciclo de vida que muestra disponibilidad principal](../../media/non-dark4-edits.PNG)

Cualquier dispositivo inscrito durante este período recibe los tres años de soporte técnico completos desde el escritorio administrado de Microsoft (como se muestra en la escala de tiempo azul). Este período dura hasta que se establezca una fecha de finalización de 24 meses a partir de la fecha de disponibilidad general.

Puede pensar en este período como "abrir inscripción" de manera eficaz, para maximizar el valor del escritorio administrado por Microsoft, debe dirigir los modelos de compras y los productos seleccionados para que entren dentro de este período. Como ejemplo pequeño, un cliente debe evitar la liquidación en un período de distribución de dos años con un producto que está en el último mes de disponibilidad principal; la mayoría de estos dispositivos no recibirán los tres años completos de la administración administrada de escritorio de Microsoft (consulte [período de gracia](#product-grace-period) para obtener más información).  

## <a name="product-grace-period"></a>Período de gracia del producto

El período de gracia del producto es un período de tres años que sigue a la disponibilidad principal. Esta fase le permite inscribir dispositivos que provienen de una familia de productos admitidos, pero mantener la empresa en las promesas del escritorio administrado de Microsoft con el rendimiento de dispositivos y hardware modernos. Esta fase es ideal para los clientes que han tomado decisiones de contratación antes de conocer sobre el escritorio administrado por Microsoft. 

Si ha comprado recientemente una cantidad de dispositivos aprobados antes de inscribirse en el escritorio administrado de Microsoft, todavía puede inscribirse, pero no recibirá un total de tres años de administración. En su lugar, se quedarán sin cumplimiento en la fecha de retiro, independientemente de Cuándo estaban inscritos. En segundo plano, el escritorio administrado de Microsoft tratará estos dispositivos como si estuvieran inscritos en el último día de la disponibilidad principal. En esta ilustración, puede ver este escenario indicando que el dispositivo azul y verde terminan el mismo día, a pesar de la diferencia de un año en la inscripción:


![escala de tiempo de ciclo de vida que muestra período de gracia](../../media/non-dark2-edits.PNG)

El ejemplo de equipo portátil de Fabrikam de la tabla anterior muestra esta situación: 

|Producto  |Fecha de aprobación  |Fin de la disponibilidad principal  |Fin de la elegibilidad  |
|---------|---------|---------|---------|
|Portátil Fabrikam    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Como cliente, puede inscribir a los portátiles de Fabrikam hasta el 6/1/2022, pero todos se tratarán como si los hubiera inscrito en 6/1/2019. Si inscribe a un equipo portátil de Fabrikam el 6/1/2021 solo obtendrá un año de administración. Esta directiva permite extraer los ciclos de vida parciales de los productos admitidos anteriormente, en lugar de tener que adquirir nuevos dispositivos prematuramente. 

Por último, durante esta fase, el dispositivo se quita de la [lista de dispositivos](device-list.md) y se mueve a la [lista de dispositivos archivados](archived-device-list.md).


## <a name="product-retirement"></a>Retirada de productos

La jubilación del producto es la fase final del ciclo de vida. En esta fase, no se pueden inscribir dispositivos nuevos de ese tipo de producto en el escritorio administrado por Microsoft y, por definición, todos los dispositivos existentes ahora están fuera de su plazo de tres años permitidos. Durante este tiempo, el escritorio administrado de Microsoft quitará el dispositivo de la lista pública por completo. También es durante esta fase en el que, si aún no ha adquirido sustituciones, empezará a ver los servicios reducidos a medida que Microsoft Managed Desktop comienza a bajar a los dispositivos que no cumplen los requisitos. 

## <a name="devices-that-are-out-of-compliance"></a>Dispositivos que no son compatibles

Un dispositivo no cumple los requisitos cuando ha transcurrido su ventana permitida para la administración de escritorio administrada de Microsoft. Esto ocurre cuando el dispositivo ha alcanzado los tres años de administración o cuando el tipo de producto se ha quitado del catálogo de dispositivos, lo que ocurra primero. Siempre debe dirigirse a sus ciclos de adquisición de manera que los nuevos dispositivos se implementen antes de que los dispositivos actuales salgan del cumplimiento.

El equipo de escritorio administrado de Microsoft sabe que los ciclos de adquisición son largos y planificados en torno a presupuestos de larga duración. Para asegurarse de que siempre tiene en cuenta el estado de su llenado de dispositivos, proporcionamos un [sitio web](https://aka.ms/mmdportal) con una lista de todos los dispositivos de administración, su antigüedad y un estado que indica el cumplimiento. Esto significa que siempre tiene la información más reciente sobre la antigüedad del dispositivo y puede usar el informe en cualquier ciclo de planeación de la compra. 







