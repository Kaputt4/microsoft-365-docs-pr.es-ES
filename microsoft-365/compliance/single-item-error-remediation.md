---
title: Corrección de errores en un único elemento
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Puede corregir un error de procesamiento en un documento en un conjunto de revisión en eDiscovery (Premium) sin tener que seguir el proceso de corrección masiva de errores.
ms.openlocfilehash: e8ace66eefadf5ce959bc01150ba21e232429131
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092357"
---
# <a name="single-item-error-remediation-in-ediscovery-premium"></a>Corrección de errores de un solo elemento en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La corrección de errores ofrece a los usuarios de Microsoft Purview eDiscovery (Premium) la capacidad de corregir los problemas de datos que impiden que eDiscovery (Premium) procese correctamente el contenido. Por ejemplo, los archivos protegidos con contraseña no se pueden procesar porque esos archivos están bloqueados o cifrados. Anteriormente, solo podía corregir errores de forma masiva mediante [este flujo de trabajo](error-remediation-when-processing-data-in-advanced-ediscovery.md). Pero a veces, no tiene sentido corregir errores en varios archivos cuando no está seguro de si alguno de esos archivos responde al caso que está investigando. También podría no tener sentido corregir errores antes de que haya tenido la oportunidad de revisar los metadatos del archivo (como la ubicación del archivo o quién tenía acceso) para ayudarle a tomar decisiones iniciales sobre la capacidad de respuesta. Una nueva característica denominada *corrección de errores de elemento único* proporciona a los administradores de exhibición de documentos electrónicos la capacidad de ver los metadatos de los archivos con un error de procesamiento y, si es necesario, corregir el error directamente en el conjunto de revisión. En el artículo se describe cómo identificar, omitir y corregir archivos con errores de procesamiento en un conjunto de revisión.

## <a name="identify-documents-with-errors"></a>Identificación de documentos con errores

Ahora se identifican los documentos con errores de procesamiento en un conjunto de revisión (con un banner). Puede corregir o omitir el error. En la captura de pantalla siguiente se muestra el banner de error de procesamiento de un documento de Word en un conjunto de revisión protegido con contraseña. Observe también que puede ver los metadatos de archivo de los documentos con errores de procesamiento.

![Banner mostrado para el documento con error de procesamiento.](../media/SIERimage1.png)

También puede buscar documentos que tengan errores de procesamiento mediante la condición **De estado de procesamiento** al [consultar los documentos de un conjunto de revisión](review-set-search.md).

![Use la condición de estado de procesamiento para buscar documentos de error.](../media/SIERimage2.png)

### <a name="ignore-errors"></a>Omitir errores

Para omitir un error de procesamiento, haga clic en **Omitir** en el banner de error de procesamiento. Cuando se omite un error, el documento se quita del [flujo de trabajo de corrección de errores en masa](error-remediation-when-processing-data-in-advanced-ediscovery.md). Una vez que se omite un error, el banner del documento cambia de color e indica que se omitió el error de procesamiento. En cualquier momento, puede revertir la decisión de omitir el error haciendo clic en **Revertir**.

![Haga clic en Omitir para omitir el error de procesamiento.](../media/SIERimage3.png)

También puede buscar todos los documentos que tenían un error de procesamiento que se omitió mediante la condición *Errores de procesamiento omitidos* al consultar documentos en un conjunto de revisión.

![Use la condición Errores de procesamiento omitidos para buscar documentos de error omitidos.](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>Corrección de un documento con errores

En ocasiones, es posible que tenga que corregir un error de procesamiento en documentos (quitando una contraseña, descifrando un archivo cifrado o recuperando un documento dañado) y, a continuación, agregue el documento corregido al conjunto de revisión. Esto le permite revisar y exportar el documento de error junto con los demás documentos del conjunto de revisión. 

Para corregir un único documento, siga estos pasos:

1. Haga clic en **DescargarDescargar**  >  original para descargar una copia del archivo en un equipo local.

   ![Descargue el documento con el error de procesamiento.](../media/SIERimage5.png)

2. Corrija el error en el archivo sin conexión. Para los archivos cifrados, que requerirían software de descifrado, para quitar la protección con contraseña, proporcione la contraseña y guarde el archivo o use un descifrador de contraseñas. Después de corregir el archivo, vaya al paso siguiente.

3. En el conjunto de revisión, seleccione el archivo con el error de procesamiento que corrigió y, a continuación, haga clic en **Corregir**.

   ![Haga clic en Corrección en el banner del documento con un error de procesamiento.](../media/SIERimage6.png)


4. Haga clic en **Examinar**, vaya a la ubicación del archivo corregido en el equipo local y, a continuación, seleccione el archivo.

   ![Haga clic en Examinar y seleccione el archivo corregido en el equipo local.](../media/SIERimage7.png)

    Después de seleccionar el archivo corregido, se carga automáticamente en el conjunto de revisión. Puede realizar un seguimiento del estado de procesamiento del archivo.

    ![Se muestra el estado del proceso de corrección.](../media/SIERimage8.png)

   Una vez completado el procesamiento, puede ver el documento corregido.

    ![Puede ver el archivo corregido en el formato nativo del conjunto de revisión.](../media/SIERimage9.png)

Para obtener más información sobre lo que sucede cuando se corrige un documento, consulte [Qué ocurre cuando se corrigen los archivos](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).

## <a name="search-for-remediated-documents"></a>Búsqueda de documentos corregidos

Puede buscar todos los documentos de un conjunto de revisión que se corrigieron mediante la condición **Keywords** y especificando el siguiente par property:value: **IsFromErrorRemediation:true**. Esta propiedad también está disponible en el archivo de carga de exportación al exportar documentos desde un conjunto de revisión.
