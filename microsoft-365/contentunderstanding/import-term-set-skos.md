---
title: Importar un conjunto de términos mediante un formato basado en SKOS
description: Obtener información sobre cómo importar un conjunto de términos mediante un formato basado en SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296074"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importar un conjunto de términos mediante un formato basado en SKOS

Puede importar un conjunto de términos con un formato basado en SKOS. Para obtener más información sobre el formato, consulte [SharePoint TAXONOMY SKOS Format Reference](skos-format-reference.md).

Se recomienda mantener los archivos de importación en menos de 20.000 términos. Los archivos de mayor tamaño pueden aumentar el tiempo necesario para la validación y la importación.

1. En el centro de administración de SharePoint, expanda **servicios de contenido**y, a continuación, haga clic en **almacén de términos**.

2. Seleccione el grupo de términos en el que desea importar el conjunto de términos.

3. En la barra de comandos, haga clic en **importar conjunto de términos**.
 
4.  Si desea descargar un archivo de ejemplo para usarlo como plantilla, haga clic en **Sample-Metadata. TTL** para obtener un archivo de ejemplo que usa el formato basado en SKOS.
 
5.  Cree el archivo de importación que contenga los conjuntos de términos & términos que desea importar.

6.  En **formato de archivo**, seleccione **SKOS (*. TTL)**.

7.  Haga clic en **examinar** y vaya a y agregue el archivo de importación.

8.  Haga clic en **Importar**. No cierre el panel hasta que se complete la importación.

Si se ha importado correctamente el archivo, se mostrará un mensaje de operación correcta y se actualizará el almacén de términos y se podrá navegar a los conjuntos de términos recién creados.

## <a name="see-also"></a>Consulte también

[Introducción a los metadatos administrados](https://docs.microsoft.com/sharepoint/managed-metadata)

[Información general sobre el documento](document-understanding-overview.md)

[Importación de conjuntos de términos (nivel de sitio)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)