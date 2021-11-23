---
title: Recopilar datos adjuntos en la nube en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
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
description: Use colecciones en Advanced eDiscovery recopilar datos adjuntos en la nube para su revisión en una investigación o caso.
ms.openlocfilehash: bdf30fea0e168d4b36175296f524ade13539970b
ms.sourcegitcommit: 7f0c5b55e2966c0c1ce6a153a4e6a7ec035bd818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2021
ms.locfileid: "61137164"
---
# <a name="collect-cloud-attachments-in-advanced-ediscovery-preview"></a>Recopilar datos adjuntos en la nube Advanced eDiscovery (versión preliminar)

Los datos adjuntos en la nube son vínculos a documentos que normalmente se almacenan SharePoint sitio y OneDrive. Por lo tanto, en lugar de adjuntar una copia real de un documento en un mensaje de correo electrónico o una conversación de chat de Teams, tiene la opción de compartir un vínculo al archivo. Los datos adjuntos en la nube son una forma eficaz de compartir documentos y colaborar con otras personas de la organización. Pero los datos adjuntos en la nube presentan desafíos durante el flujo de trabajo de exhibición de documentos electrónicos porque solo se devuelve el vínculo de datos adjuntos en la nube y no el contenido real del documento compartido en una búsqueda de exhibición de documentos electrónicos. Para hacer frente a este desafío, Advanced eDiscovery proporciona dos soluciones para recopilar datos adjuntos en la nube:  

- Recopilación de la versión en directo de un documento al que está vinculado en un archivo adjunto de la nube.

- Recopilación de la versión del documento en el momento en que se compartió en datos adjuntos de la nube.

## <a name="collecting-cloud-attachments"></a>Recopilación de datos adjuntos en la nube

Al crear una colección de borradores y los resultados de búsqueda contienen elementos que incluyen datos adjuntos en la nube, tiene la opción de recopilar el destino de los datos adjuntos de la nube al confirmar el borrador de colección en un conjunto de revisión. Al seleccionar esta opción, Advanced eDiscovery los documentos que están vinculados en los datos adjuntos de la nube al conjunto de revisión. Esto le permite revisar los documentos de destino y determinar si el documento es relevante para su caso o investigación.

En la siguiente captura de pantalla se muestra la opción de incluir los destinos de los datos adjuntos en la nube al confirmar una colección en un conjunto de revisión.

![La opción de incluir datos adjuntos en la nube al confirmar una colección en un conjunto de revisión](../media/CollectCloudAttachments1.png)

> [!NOTE]
>- Si usa el nuevo formato [de](advanced-ediscovery-new-case-format.md) caso en Advanced eDiscovery, la opción para incluir datos adjuntos en la nube en el conjunto de revisión está seleccionada de forma predeterminada y no puede ser no seleccionada.<br/>
>- También tiene la opción de incluir todas las versiones (además de la versión que se compartió) de datos adjuntos en la nube en el conjunto de opiniones.  
Para obtener instrucciones sobre cómo confirmar una colección en un conjunto de revisión, vea [Commit a draft collection to a review set](commit-draft-collection.md).

## <a name="collecting-the-version-shared-in-a-cloud-attachment"></a>Recopilación de la versión compartida en datos adjuntos de la nube

El Advanced eDiscovery de trabajo para recopilar datos adjuntos de la nube solo incluye agregar la versión más actual de los datos adjuntos de la nube a un conjunto de revisión. Esto significa que la versión que se recopila y se agrega a un conjunto de revisión puede ser diferente de la versión que se compartió originalmente en los datos adjuntos de la nube. Por lo tanto, es posible que el contenido que estaba presente en los datos adjuntos de la nube en el momento en que se compartió se haya quitado y no exista en la versión actual que se agrega al conjunto de revisión.

Las organizaciones ahora tienen la opción de usar Microsoft 365 de retención para conservar la versión de un documento en el momento en que se compartió como datos adjuntos de la nube. Para ello, la organización puede crear una etiqueta de retención, elegir la opción aplicar la etiqueta a los datos adjuntos de la nube y, a continuación, aplicar automáticamente la etiqueta a los documentos almacenados en SharePoint y OneDrive. Después de configurar esta configuración, se crea una copia de un documento en el momento en que se comparte el archivo. Además, si el documento se modifica y se vuelve a compartir como datos adjuntos en la nube, también se conserva la versión modificada. Si el archivo se modifica y se vuelve a compartir, se conserva una nueva copia del archivo como una nueva versión.

Conservar las versiones compartidas de datos adjuntos en la nube puede ayudar a su organización a establecer el ámbito de la conservación y la recopilación de contenido potencialmente relevante para la versión específica del documento que se compartió en lugar de la versión actual en directo. Después de implementar esta solución de retención, tanto la versión actual en directo de los datos adjuntos de la nube como la versión que se compartió en los datos adjuntos de la nube se recopilan y se agregan a un conjunto de revisión.

Para obtener instrucciones sobre cómo configurar una etiqueta de retención y aplicarla automáticamente a datos adjuntos en la nube, consulte [Auto-apply labels to cloud attachments](apply-retention-labels-automatically.md#auto-apply-labels-to-cloud-attachments).

La siguiente captura de pantalla muestra un documento adjunto en la nube, denominado *XYZ Research.docx*, que se agregó a un conjunto de revisión. El documento se compartió como datos adjuntos de la nube en una Teams conversación de chat. El conjunto de revisión también contiene la versión que se compartió originalmente en los datos adjuntos de la nube. Observe que el sistema genera el nombre de esta versión de los datos adjuntos en la nube y el autor se identifica **como SharePoint**.

![La versión de datos adjuntos de la nube que se compartió en un conjunto de revisión](../media/CollectCloudAttachments2.png)

Además, la versión actual en directo y la versión compartida tienen el mismo valor de propiedad **FamilyId,** que es el mismo que **el FamilyId** para el objeto primario (como un mensaje de correo electrónico o una conversación de chat de Teams). Esto le permite agrupar datos adjuntos en la nube con el elemento en el que se compartieron.

Después de implementar la etiqueta de retención y aplicar automáticamente la etiqueta a documentos de SharePoint, sigue seleccionando la opción para recopilar datos adjuntos en la nube al confirmar un borrador de colección en un conjunto de revisión. Cuando se recopilan los datos adjuntos de la nube, tanto la versión actual en directo como la versión que se compartió originalmente se agregan al conjunto de revisión.
