---
title: Análisis de regresión de memoria
description: Cómo deducir la regresión de memoria
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323108"
---
# <a name="memory-regression-analysis"></a>Análisis de regresión de memoria

Test Base te ayuda a observar con mayor claridad aumentos significativos en el uso de memoria en las máquinas virtuales de prueba que ejecutan tus aplicaciones. Las métricas de rendimiento, como el uso de memoria, pueden ser indicativas del estado general de la aplicación y creemos que esta adición ayudará en gran medida a mantener el rendimiento óptimo de las aplicaciones.

Sigue leyendo para obtener más información o ver este vídeo para obtener un rápido recorrido por las mejoras más recientes. 

Para obtener más información sobre la base de pruebas para la capacidad de M365 para ayudar con el análisis de regresión, consulte Resultados de regresión basados en la confiabilidad del proceso.

<b>Mirar más de cerca las regresiónes de memoria</b>

El panel Base de prueba para M365 muestra la memoria consumida por la aplicación en una nueva actualización de Windows publicada previamente y la compara con la memoria usada por la última actualización Windows lanzamiento. 

Con las mejoras de este mes, el análisis de regresión de memoria ahora se presenta en los procesos favoritos. Las aplicaciones pueden contener varios procesos y puede seleccionar manualmente sus procesos favoritos a través de la pestaña Confiabilidad. A continuación, nuestro servicio identificará las regresiónes de memoria en estos procesos favoritos mientras compara las ejecuciones de prueba en diferentes Windows actualizaciones. Si se detecta una regresión, los detalles sobre la regresión estarán disponibles fácilmente.

Ahora echemos un vistazo a esta característica en detalle y analicemos cómo puede solucionar problemas de regresión de memoria con Windows analizador de rendimiento.

La señal de error causada por una regresión de memoria se muestra en el panel Base de pruebas para M365 en la página Resultados de la prueba en Uso de memoria:

![Resultados de uso de memoria](Media/01_memory-utilization-results.png)


Error en la aplicación debido a un mayor consumo de memoria, también se mostrará como en ```Fail``` la página Resumen de prueba:

![Resultados de resumen de prueba](Media/02_test-summary.png)

Al proporcionar estas señales de error por adelantado, nuestro objetivo es marcar claramente los posibles problemas que pueden interrumpir e afectar a la experiencia del usuario final de la aplicación. 

A continuación, puede descargar los archivos de registro y usar el analizador de rendimiento Windows, o el kit de herramientas preferido, para investigar más. También puede trabajar conjuntamente con el equipo de Test Base para M365 para solucionar el problema y ayudar a evitar problemas que afectan a los usuarios finales.

Las señales de memoria se capturan en la pestaña Uso de memoria del servicio Base de prueba para M365 para todas las ejecuciones de prueba. En el ejemplo siguiente se muestra una ejecución de prueba reciente con la aplicación incorporada "Estrés de memoria de prueba de humo" en la actualización de seguridad de agosto de 2020. (Nuestro equipo escribió esta aplicación para ilustrar las regresión de la memoria).

![Resultados de regresión de memoria](Media/03_memory-regression%20comparison.png)

En este ejemplo, el proceso favorito "USLTestMemoryStress.exe" consumió un promedio de aproximadamente 100 MB en la actualización de agosto anterior a la actualización de julio publicada, de ahí que la Base de pruebas para M365 identificara una regresión. 

Los otros procesos,que se muestran aquí como "USLTestMemoryStress_Aux1.exe" y "USLTestMemoryStress_Aux2.exe", también pertenecen a la misma aplicación, pero consumen aproximadamente la misma cantidad de memoria para las dos versiones, por lo que "pasaron" y se consideraron correctos.

La regresión en el proceso principal se determinó como "estadísticamente significativa" por lo que el servicio se comunicó y resaltó esta diferencia al usuario. Si la comparación no fuera estadísticamente significativa, no se resaltaría. El uso de memoria puede ser ruidoso, por lo que usamos modelos estadísticos para distinguir, entre compilaciones y versiones, diferencias significativas de diferencias intrascendentes. 

Es posible que rara vez se señale una comparación cuando no hay ninguna diferencia verdadera (un falso positivo), pero esto es una contraoferta necesaria para mejorar la probabilidad de identificar correctamente regresión (o verdaderos positivos).

El siguiente paso es comprender qué causó la regresión de la memoria. Puede descargar los archivos zip para ambas ejecuciones desde la opción Descargar archivos de registro, como se muestra a continuación. 

Estos archivos zip contienen los resultados de la ejecución de prueba, incluidos los resultados del script y la memoria y los datos de rendimiento de la CPU que se incluyen en el archivo ETL.

![Archivos de prueba de regresión de memoria](Media/04_memory-regression-test-files.png)

Puede descargar y descomprimir los registros de las dos ejecuciones de prueba, localizar el archivo ETL en cada carpeta y cambiar su nombre como target.etl (para la ejecución de prueba en la actualización de versión anterior) y baseline.etl (para la ejecución de prueba en la última actualización publicada) para simplificar la exploración y la navegación.
 
## <a name="next-steps"></a>Pasos siguientes

Avance al siguiente artículo para empezar a comprender el análisis de regresión inteligente de la CPU.
> [!div class="nextstepaction"]
> [Paso siguiente](cpu.md)

<!---
Add button for next page
-->
