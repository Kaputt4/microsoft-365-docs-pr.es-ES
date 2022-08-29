---
title: Análisis de regresión de CPU
description: Descripción de los resultados y las métricas de regresión para el consumo de CPU
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 59038c1bd13299587ef0ed75f446e405ed64bba5
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315885"
---
# <a name="intelligent-cpu-regression-analysis"></a>Análisis de regresión de CPU inteligente

El uso de CPU puede indicar si una aplicación se ve afectada por una actualización del sistema operativo. 

Test Base para Microsoft 365 proporciona a los desarrolladores de software información sobre las regresiones de rendimiento de CPU que se producen cuando su aplicación se ejecuta en diferentes versiones de una próxima actualización del sistema operativo Windows (SO). 

Estas regresiones de CPU permiten a los desarrolladores detectar y resolver problemas de aplicaciones (y posibles errores) antes de que la actualización del sistema operativo se implemente ampliamente, lo que evita una mala experiencia para el usuario final.


### <a name="how-cpu-regression-analysis-works"></a>Funcionamiento del análisis de regresión de CPU ###

Como usuario de Test Base, puede cargar los archivos binarios de la aplicación (en un único archivo .zip), junto con los scripts de prueba asociados y seleccionar la versión del sistema operativo Windows en la que desea probar la aplicación en el Portal de base de pruebas de Azure. 

A continuación, el servicio Test Base ejecuta los scripts de prueba y realiza el **análisis de regresión de CPU**. 

El servicio comprueba si el uso de CPU de la aplicación en la versión preliminar de la actualización del sistema operativo de destino está en línea con el uso de CPU para la versión publicada del sistema operativo. 

El uso de LA CPU no es una comparación similar al 100 % porque los procesos que se ejecutan en las dos versiones del sistema operativo pueden ser o no una coincidencia exacta debido a diferentes versiones del sistema operativo; sin embargo, el análisis realizado por Test Base puede mostrar si el uso de CPU para la aplicación se ve afectado por una próxima actualización del sistema operativo y, específicamente, qué procesos han retrocedido de las ejecuciones de pruebas anteriores.

En la instantánea siguiente, hay dos versiones del sistema operativo con las que se comparan los usos de CPU para la misma aplicación. 
-   La pestaña Uso de CPU muestra los límites superior e inferior del uso de ambas versiones en percentiles 90 y 10, respectivamente. 
-   Los gráficos muestran la serie temporal de uso de CPU junto con el uso medio. 

Los clientes ahora pueden usar la funcionalidad para determinar si el uso de CPU de su aplicación se ve afectado por las actualizaciones del sistema operativo y, específicamente, qué procesos han retrocedido de su ejecución anterior.


![Análisis de regresión de CPU.](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a>Identificación del proceso pertinente ###

Aquí se describe cómo identificar los procesos con regresión en la aplicación. 

El análisis de la regresión de rendimiento requiere el seguimiento de diferentes tipos de contadores de rendimiento para cada proceso que se ejecuta en una máquina virtual durante la ejecución de la prueba. 

Este análisis captura una gran cantidad de variables para una gran cantidad de procesos para una aplicación determinada. No todos los procesos están asociados a una ejecución o aplicación. Para solucionar este desafío, se aplica un algoritmo de clasificación de información mutua mediante la teoría de la probabilidad y la información para averiguar qué procesos son más relevantes para una aplicación determinada. 

Una aplicación se puede considerar un tipo de variable aleatoria discreta mientras que un proceso se considera otro tipo de variable aleatoria discreta. La asociación de las dos variables aleatorias se mide mediante probabilidades condicionales para su relevancia. 

A continuación, los procesos se muestran en el orden de su relevancia para cada aplicación. También puede usar como favorito un subconjunto de procesos que se pueden supervisar, de forma predeterminada, junto con los procesos pertinentes para el análisis de regresión de CPU. Una vez detectada una regresión, puede descargar el kit de herramientas de Windows Analizador de rendimiento y analizar los motivos de las regresiones de rendimiento de la CPU. 

Windows Analizador de rendimiento toma el registro de seguimiento de eventos (ETL) como entradas y estos archivos .etl están disponibles en los archivos de registro descargables para las ejecuciones de prueba en el portal. Si desea obtener más información sobre la depuración del rendimiento de la CPU, consulte la documentación de Windows Analizador de rendimiento.

