---
title: Ciclo de vida del producto de Escritorio administrado de Microsoft
description: En este artículo se enumeran las especificaciones de dispositivo usadas en el Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841204"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Ciclo de vida del producto de Escritorio administrado de Microsoft

Escritorio administrado de Microsoft beneficia a los usuarios asegurando que siempre usan dispositivos que ofrecen las mejores capacidades de rendimiento, confiabilidad, diseño y seguridad (como la compatibilidad con características como Windows Hello). Para ello, Escritorio administrado de Microsoft mantiene un breve catálogo de dispositivos aprobados [actualizados continuamente.](device-list.md) 
 
En este artículo se detalla el ciclo de vida de los dispositivos a medida que se agregan y se quitan del catálogo aprobado. 

> [!NOTE]
> En este tema, haremos una distinción entre un "dispositivo" y un "producto". Por "dispositivo", nos refieremos a un equipo individual y específico. Por ejemplo, "Número de serie 1234", "Portátil de Bill", "VM compartida XYZ" hacen referencia a dispositivos específicos. Sin embargo, un "producto" hace referencia a una colección o familia de dispositivos. Por ejemplo, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. Esto es importante porque los [](device-list.md)productos se agregan a nuestra lista o catálogo aprobados, y los dispositivos son los que se inscriben en el Escritorio administrado de Microsoft.

## <a name="product-lifecycle"></a>Ciclo de vida del producto

 Por lo general, los productos se mueven a través de estas fases del ciclo de vida:

- [Versión y evaluación del producto](#product-release-and-evaluation)
- [Período de disponibilidad principal del producto](#product-primary-availability-period)
- [Período de gracia del producto](#product-grace-period)
- [Retirada del producto](#product-retirement)


En esta ilustración se muestra toda la secuencia:

![ciclo de vida: a partir de la disponibilidad general del producto, la "disponibilidad principal" dura dos años. Durante este tiempo, finaliza la ventana de certificación y, en algún momento, se incorpora el dispositivo. Al final de la disponibilidad principal, el producto se archiva y comienza el "período de gracia" de tres años. A partir de la incorporación del dispositivo, tiene un período de uso de 3 años hasta que se quita de la administración. Al final del período de gracia, quitamos el producto del catálogo.](../../media/non-dark1-edits.PNG)

Los productos permanecen en el catálogo hasta <em></em> 24 meses, pero los dispositivos permanecen bajo administración durante tres años en función de sus fechas de inscripción individuales. De hecho, cada producto tiene tres fechas importantes, pero cada dispositivo solo tiene una. En el caso de los productos, <em></em>estas tres fechas se calculan en función de la fecha de aprobación y, por lo tanto, publicamos estas fechas tras la aprobación para que siempre pueda mirar hacia delante y planear adecuadamente todo el ciclo de vida del producto.

En esta tabla se muestran las fechas de ejemplo de un producto teórica:


|Producto  |Fecha de aprobación  |Fin de la disponibilidad principal  |Fin de la elegibilidad  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Portátil Adatum   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

En esta tabla se muestran fechas de ejemplo para dispositivos *teóricas:*


|Id. de dispositivo  |Fecha de inscripción  |Fecha de retirada  |
|---------|---------|---------|
|Equipo #123412     |  2/3/2018       |  2/3/2021       |
|Escritorio #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Versión y evaluación del producto

El ciclo de vida del producto se inicia cuando un fabricante publica el producto públicamente:

![línea de tiempo del ciclo de vida que muestra el período de lanzamiento y evaluación](../../media/non-dark3-edits.PNG)

Durante esta fase, el equipo de ingeniería de Escritorio administrado de Microsoft realiza su evaluación y certificación de un producto. El equipo evalúa aspectos como la confiabilidad y el rendimiento con Windows, el cumplimiento de una línea base de hardware, la opinión del mercado y la preparación de inventario y canales, entre otras cosas. Este proceso suele demorar aproximadamente seis semanas.
  
Escritorio administrado de Microsoft solo evaluará los dispositivos para su certificación en los primeros seis meses de disponibilidad. Esta directiva garantiza que siempre estamos centrando nuestros esfuerzos en la última generación de hardware.
 
Al final de esta fase, Escritorio administrado de Microsoft agrega el producto a la lista [aprobada,](device-list.md)liberando de forma eficaz el producto para las inscripciones de clientes. Independientemente de la fecha en la  que un dispositivo está certificado, su fecha de aprobación se vuelve a fecha de fecha de disponibilidad general del producto. 


## <a name="product-primary-availability-period"></a>Período de disponibilidad principal del producto

Este período es el núcleo de la disponibilidad del producto:

![línea de tiempo del ciclo de vida que muestra la disponibilidad principal](../../media/non-dark4-edits.PNG)

Cualquier dispositivo inscrito durante este período recibe los tres años completos de soporte técnico del Escritorio administrado de Microsoft (como se muestra en la escala de tiempo azul). Este período dura hasta una fecha de finalización establecida en 24 meses a partir de la fecha de disponibilidad general.

Puede considerar este período como una "inscripción abierta" eficaz, por lo que para maximizar el valor del Escritorio administrado de Microsoft, debe dirigirse a los modelos de adquisición y los productos seleccionados para que se ajusten a este período. Como ejemplo pequeño, debe evitar la instalación en un período de lanzamiento de dos años con un producto que se encuentra en su último mes de disponibilidad principal: la mayoría de esos dispositivos no recibirán los tres años completos de administración de Escritorio administrado de Microsoft (vea el período de gracia para obtener más información). [](#product-grace-period)  

## <a name="product-grace-period"></a>Período de gracia del producto

El período de gracia del producto es un período de tres años después de la disponibilidad principal. Esta fase le permite inscribir dispositivos que son de una familia de productos compatibles, pero que siguen siendo firmes con las promesas de Escritorio administrado de Microsoft con respecto al hardware moderno y el rendimiento de los dispositivos. Esta fase es ideal para los clientes que han tomado decisiones de adquisición antes de conocer el Escritorio administrado de Microsoft. 

Si ha comprado recientemente dispositivos aprobados antes de inscribirse en el Escritorio administrado de Microsoft, aún puede inscribirlos, pero no recibirá un total de tres años de administración. En su lugar, no cumplirán la fecha de retirada, independientemente de cuándo se inscribieron. En segundo plano, escritorio administrado de Microsoft tratará estos dispositivos como si estuvieran inscritos en el último día de disponibilidad principal. En esta ilustración, puedes ver este escenario al tener en cuenta que tanto el dispositivo azul como el verde terminan el mismo día, a pesar de su diferencia de un año en la inscripción:


![línea de tiempo del ciclo de vida que muestra el período de gracia](../../media/non-dark2-edits.PNG)

El ejemplo de Fabrikam Laptop de la tabla anterior ilustra esta situación: 

|Producto  |Fecha de aprobación  |Fin de la disponibilidad principal  |Fin de la elegibilidad  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Como cliente, puede inscribir equipos portátiles Fabrikam hasta el 1/6/2022; sin embargo, todos se tratarán como si los inscribas el 1/6/2019. Si inscribe un portátil Fabrikam el 1/6/2021, solo tendrá un año de administración. Esta directiva le permite extraer ciclos de vida parciales de productos que se han admitido anteriormente, en lugar de tener que adquirir nuevos dispositivos prematuramente. 

Por último, durante esta fase, el dispositivo se quita de la lista [de](device-list.md) dispositivos y se mueve a la [lista de dispositivos archivados.](archived-device-list.md)


## <a name="product-retirement"></a>Retirada del producto

La retirada del producto es la fase final del ciclo de vida. En esta fase, no se pueden inscribir nuevos dispositivos de ese tipo de producto en el Escritorio administrado de Microsoft y, por definición, todos los dispositivos existentes están ahora fuera de su período de tres años permitido. Durante este tiempo, Escritorio administrado de Microsoft quitará el dispositivo de la lista pública por completo. También es durante esta fase donde, si aún no ha adquirido sustituciones, empezará a ver una reducción de los servicios a medida que el Escritorio administrado de Microsoft empieza a disminuir en los dispositivos que no cumplen las normas. 

## <a name="devices-that-are-out-of-compliance"></a>Dispositivos que no cumplen las normas

Un dispositivo está fuera de cumplimiento cuando ha transcurrido la ventana permitida para la administración de Escritorio administrado de Microsoft. Esta situación se produce cuando el dispositivo ha alcanzado tres años de administración o cuando ese tipo de producto se quita del catálogo de dispositivos, lo que ocurra primero. Siempre debe dirigirse a los ciclos de adquisición de forma que los nuevos dispositivos se implementen antes de que los dispositivos actuales que no cumplan los requisitos.

El equipo de Escritorio administrado de Microsoft sabe que los ciclos de adquisiciones son largos y se planean en torno a presupuestos de larga duración. Para asegurarte de que siempre eres consciente del estado [](https://aka.ms/mmdportal) de la población del dispositivo, proporcionamos un sitio web que enumera todos los dispositivos bajo administración, su antigüedad y un estado que indica su cumplimiento. El sitio web le ayuda a tener siempre la información más reciente sobre la antigüedad del dispositivo y puede usar el informe en cualquier ciclo de planeación de adquisiciones. 







