---
title: Corrección de errores en un único elemento
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Puede corregir un error de procesamiento en un documento en un conjunto de revisión en eDiscovery avanzado sin tener que seguir el proceso de corrección de errores en masa.
ms.openlocfilehash: c318148900d891304ebcb9b4a88abfe52f43c05e
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285846"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>Corrección de errores de un solo elemento en eDiscovery avanzado

La corrección de errores proporciona a los usuarios avanzados de eDiscovery la capacidad de rectificar problemas de datos que impiden que eDiscovery avanzado procese correctamente el contenido. Por ejemplo, los archivos protegidos con contraseña no se pueden procesar porque estos archivos están bloqueados o cifrados. Anteriormente, solo podían corregirse los errores en masa con [este flujo de trabajo](error-remediation-when-processing-data-in-advanced-ediscovery.md). Pero, a veces, no tiene sentido corregir los errores en varios archivos cuando no está seguro de si alguno de estos archivos responde al caso que está investigando. También es posible que no tenga sentido corregir los errores antes de que haya tenido la oportunidad de revisar los metadatos del archivo (como la ubicación del archivo o quién tenía acceso) para ayudarle a tomar decisiones delanteras sobre la capacidad de respuesta. Una nueva característica denominada *corrección de errores de elemento único* proporciona a los administradores de eDiscovery la capacidad de ver los metadatos de los archivos con un error de procesamiento y, si es necesario, corregir el error directamente en el conjunto de revisión. En el artículo se describe cómo identificar, omitir y solucionar los archivos con errores de procesamiento en un conjunto de revisión.

## <a name="identify-documents-with-errors"></a>Identificación de documentos con errores

Los documentos con errores de procesamiento en un conjunto de revisiones ahora están identificados (con un banner). Puede corregir o ignorar el error. En la siguiente captura de pantalla se muestra el mensaje de error de procesamiento de un documento de Word en un conjunto de revisión protegido con contraseña. Observe también que puede ver los metadatos de archivo de los documentos con errores de procesamiento.

![Banner mostrado para un documento con un error de procesamiento](../media/SIERimage1.png)

También puede buscar documentos que tienen errores de procesamiento mediante la condición de **Estado de procesamiento** cuando [consulta los documentos en un conjunto de revisión](review-set-search.md).

![Usar la condición estado de procesamiento para buscar documentos de error](../media/SIERimage2.png)

### <a name="ignore-errors"></a>Omitir errores

Puede omitir un error de procesamiento haciendo clic en **omitir** en el banner de error de procesamiento. Cuando se omite un error, el documento se quita del [flujo de trabajo de corrección de errores en masa](error-remediation-when-processing-data-in-advanced-ediscovery.md). Después de omitir un error, el titular del documento cambia de color e indica que se ha omitido el error de procesamiento. En cualquier momento, puede revertir la decisión para omitir el error; para ello, haga clic en **revertir**.

![Haga clic en Omitir para omitir el error de procesamiento](../media/SIERimage3.png)

También puede buscar todos los documentos que tuvieron un error de procesamiento que se omitió mediante la condición *errores de procesamiento omitidos* al consultar los documentos en un conjunto de revisión.

![Use la condición errores de procesamiento omitidos para buscar documentos de error omitidos](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>Corregir un documento con errores

A veces, es posible que se le solicite corregir un error de procesamiento en los documentos (quitando una contraseña, descifrando un archivo cifrado o recuperando un documento dañado) y, a continuación, agregue el documento corregido al conjunto de revisión. Esto le permite revisar y exportar el documento de error junto con el resto de los documentos en el conjunto de revisión. 

Para corregir un único documento, siga estos pasos:

1. Haga clic en **Descargar**  >  **Descargar original** para descargar una copia del archivo en un equipo local.

   ![Descargar el documento con el error de procesamiento](../media/SIERimage5.png)

2. Corrija el error en el archivo sin conexión. En el caso de los archivos cifrados, sería necesario el software de descifrado para quitar la protección con contraseña, proporcionar la contraseña y guardar el archivo o usar un Cracker con contraseña. Una vez corregido el archivo, vaya al paso siguiente.

3. En el conjunto de revisiones, seleccione el archivo con el error de procesamiento que ha corregido y, a continuación, haga clic en **corrección**.

   ![Hacer clic en corrección en el encabezado del documento con error de procesamiento](../media/SIERimage6.png)


4. Haga clic en **examinar**, vaya a la ubicación del archivo corregido en el equipo local y, a continuación, seleccione el archivo.

   ![Haga clic en examinar y seleccione el archivo corregido en el equipo local.](../media/SIERimage7.png)

    Después de seleccionar el archivo corregido, éste se carga automáticamente en el conjunto de revisión. Puede realizar un seguimiento del estado de procesamiento del archivo.

    ![Se muestra el estado del proceso de corrección](../media/SIERimage8.png)

   Una vez finalizado el procesamiento, puede ver el documento corregido.

    ![Puede ver el archivo corregido en el formato nativo en el conjunto de revisiones](../media/SIERimage9.png)

Para obtener más información sobre lo que sucede cuando se corrige un documento, vea [lo que ocurre cuando se corrigen los archivos](error-remediation.md#what-happens-when-files-are-remediated).

## <a name="search-for-remediated-documents"></a>Buscar documentos corregidos

Puede buscar todos los documentos en un conjunto de revisión corregido con la condición **palabras clave** y especificando el siguiente par de propiedad: valor: **IsFromErrorRemediation: true**. Esta propiedad también está disponible en el archivo de carga de exportación al exportar documentos de un conjunto de revisión.
