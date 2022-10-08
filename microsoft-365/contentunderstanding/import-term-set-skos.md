---
title: Importar un conjunto de términos con un formato basado en SKOS
description: Obtenga información sobre cómo importar un conjunto de términos mediante un formato basado en SKOS.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.service: microsoft-365-enterprise
ms.topic: article
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: admindeeplinkSPO
search.appverid: ''
ms.localizationpriority: high
ms.openlocfilehash: 411c4e3303d6bb20370d540de998f9e6ea95105d
ms.sourcegitcommit: cbb9a89499d42f4a029e18780bee408946e1671d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68026038"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importar un conjunto de términos con un formato basado en SKOS

Puede importar un conjunto de términos con un formato basado en SKOS. Para más información sobre el formato, consulte [Referencia de formato SKOS de la taxonomía de SharePoint](skos-format-reference.md). Esta característica requiere una licencia de [SharePoint Syntex](index.md).

Le recomendamos mantener sus archivos de importación con menos de 20 000 términos. Los archivos de mayor tamaño pueden aumentar el tiempo necesario para la validación y la importación.

1. En el Centro de administración de SharePoint, expanda **Servicios de contenido** y, después, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185073" target="_blank">**Almacén de términos**</a>.

2. Seleccione el grupo de términos en el que quiere importar el conjunto de términos.

3. En la barra de comandos, haga clic en **Importar conjunto de términos**.

4. Si desea descargar un archivo de ejemplo para usarlo como plantilla, haga clic en **sample-metadata.ttl** para obtener un archivo de ejemplo que use el formato basado en SKOS.

5. Cree el archivo de importación que contiene los conjuntos de términos y los términos que desee importar.

6. En **Formato de archivo**, selecione **SKOS (*.ttl)**.

7. Haga clic en **Examinar**, desplácese al archivo de importación y agréguelo.

8. Click **Import**. Do not close the panel until the import completes.

Si la importación del archivo se ha realizado correctamente, se mostrará un mensaje que así lo indicará, se actualizará el almacén de términos y podrá navegar a los conjuntos de términos recién creados.

## <a name="see-also"></a>Consulte también

[Introducción a los metadatos administrados](/sharepoint/managed-metadata)

[Información general de la comprensión mediante documentos](document-understanding-overview.md)

[Importar conjuntos de términos (nivel de sitio)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
