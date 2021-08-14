---
title: Importar un conjunto de términos con un formato basado en SKOS
description: Obtenga información sobre cómo importar un conjunto de términos con un formato basado en SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: edf7afd1eaa8497af6e71d3cc2e2562bb1e349d6c212c59db12a0b435e7f1c15
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53891600"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importar un conjunto de términos con un formato basado en SKOS

Puede importar un conjunto de términos con un formato basado en SKOS. Para más información sobre el formato, consulte [Referencia de formato SKOS de la taxonomía de SharePoint](skos-format-reference.md). Esta característica requiere una licencia de [SharePoint Syntex](index.md).

Le recomendamos mantener sus archivos de importación con menos de 20 000 términos. Los archivos de mayor tamaño pueden aumentar el tiempo necesario para la validación y la importación.

1. En el Centro de administración de SharePoint, expanda **Servicios de contenido** y, después, haga clic en **Almacén de términos**.

2. Seleccione el grupo de términos en el que quiere importar el conjunto de términos.

3. En la barra de comandos, haga clic en **Importar conjunto de términos**.

4. Si desea descargar un archivo de ejemplo para usarlo como plantilla, haga clic en **sample-metadata.ttl** para obtener un archivo de ejemplo que use el formato basado en SKOS.

5. Cree el archivo de importación que contiene los conjuntos de términos y los términos que desee importar.

6. En **Formato de archivo**, selecione **SKOS (*.ttl)**.

7. Haga clic en **Examinar**, desplácese al archivo de importación y agréguelo.

8. Haga clic en **Importar**. No cierre el panel hasta que finalice la importación.

Si la importación del archivo se ha realizado correctamente, se mostrará un mensaje que así lo indicará, se actualizará el almacén de términos y podrá navegar a los conjuntos de términos recién creados.

## <a name="see-also"></a>Consulte también

[Introducción a los metadatos administrados](/sharepoint/managed-metadata)

[Información general de la comprensión mediante documentos](document-understanding-overview.md)

[Importar conjuntos de términos (nivel de sitio)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
