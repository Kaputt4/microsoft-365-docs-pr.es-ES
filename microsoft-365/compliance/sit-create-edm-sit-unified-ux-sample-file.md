---
title: Creación de un archivo de ejemplo sit de EDM para la nueva experiencia
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
description: Cree el archivo de ejemplo que se usará en la nueva experiencia.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d14a336602a2945bcf19b182c22784c12489cdba
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360780"
---
# <a name="create-edm-sit-sample-file-for-the-new-experience"></a>Creación de un archivo de ejemplo sit de EDM para la nueva experiencia

La creación y puesta a disposición de un tipo de información confidencial (SIT) basado en una coincidencia exacta de datos (EDM) es un proceso de varias fases. Se pueden usar en las directivas de prevención de pérdida de datos de Microsoft Purview, eDiscovery y ciertas tareas de gobernanza de contenido En este artículo se describen el flujo de trabajo y los vínculos a los procedimientos de cada fase mediante la experiencia clásica.

## <a name="applies-to"></a>Se aplica a

- Nueva experiencia

Si quiere crear una sit de EDM con la experiencia clásica, consulte Creación de una [experiencia clásica sit de EDM](sit-create-edm-sit-classic-ux-workflow.md).

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que ha completado los pasos descritos en [Exportación de datos de origen para obtener información confidencial basada en coincidencias exactas de datos](sit-get-started-exact-data-match-export-data.md).

## <a name="formatting-the-sample-file"></a>Dar formato al archivo de ejemplo

El sistema extraerá los nombres de columna del archivo de ejemplo para crear el esquema y recomendará los SIT base a los que asignar los datos de campo de ejemplo. Debe tener el mismo formato que el archivo de tabla de información confidencial de origen y debe contener valores sintéticos que sean representativos de los datos reales. El archivo se puede guardar en .csv (valores separados por comas), .tsv (valores separados por tabulaciones) o en formato separados por canalización (|), pero debe ser el mismo que el archivo de tabla de información confidencial de origen real. El formato .tsv se recomienda en los casos en los que los valores de datos pueden incluir comas, como direcciones postales.

- Use entre 10 y 20 filas de datos para asegurarse de que el sistema tiene suficientes ejemplos con los que trabajar.
- Los valores de campo que contienen comas deben estar entre comillas *"*.
- La primera fila debe ser la fila de encabezado y contener nombres de columna.
- El archivo debe contener al menos una fila de datos.
- Cada fila de datos debe contener el número correcto de campos, correspondientes a los encabezados.
- El archivo de ejemplo contiene hasta 32 columnas.
- El archivo de ejemplo puede superar los 2,5 MB de tamaño.
- Los nombres de columna (campo) deben comenzar con una letra, tener al menos tres caracteres de longitud y constar solo de caracteres alfanuméricos (A-Z, a-z, 0-9) y no pueden incluir espacios, caracteres de subrayado u otros caracteres especiales. 

Por ejemplo, si los datos reales tienen este aspecto y usan el formato delimitado por tabulaciones (.tsv).

![imagen que muestra una tabla separada por tabulaciones con cuatro columnas y tres filas de datos de datos reales artificiales](../media/sit-edm-tsv-actual-file.png)

A continuación, el archivo de ejemplo debe tener los mismos encabezados de columna, pero usar valores sintéticos para las filas, como este

![imagen que muestra una tabla separada por tabulaciones con cuatro columnas y tres filas de datos representativos sintéticos](../media/sit-edm-tsv-sample-file.png)

> [!TIP]
> En la nueva experiencia, puede elegir entre cargar el archivo de ejemplo o escribir manualmente los valores de archivo de ejemplo. En cualquier caso, se recomienda crear el archivo de ejemplo.

## <a name="next-step"></a>Paso siguiente

- **Para obtener una nueva experiencia**: [Creación de un paquete de reglas y esquema sit de EDM](sit-create-edm-sit-unified-ux-schema-rule-package.md)