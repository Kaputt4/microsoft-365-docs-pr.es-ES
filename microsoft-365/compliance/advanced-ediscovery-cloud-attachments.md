---
title: Recopilación de datos adjuntos en la nube en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: 04/05/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use colecciones en eDiscovery de Microsoft Purview (Premium) para recopilar datos adjuntos en la nube para su revisión en una investigación o caso.
ms.openlocfilehash: 0a0d3dab3942dbdfcfa896d8e2f59fd2e2dca813
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64935728"
---
# <a name="collect-cloud-attachments-in-microsoft-purview-ediscovery-premium-preview"></a>Recopilación de datos adjuntos en la nube en Microsoft Purview eDiscovery (Premium) (versión preliminar)

Los datos adjuntos en la nube son vínculos a documentos que normalmente se almacenan en SharePoint sitio y OneDrive. Por lo tanto, en lugar de adjuntar una copia real de un documento en un mensaje de correo electrónico o un Teams conversación de chat, tiene la opción de compartir un vínculo al archivo. Los datos adjuntos en la nube son una manera eficaz de compartir documentos y colaborar con otras personas de la organización. Sin embargo, los datos adjuntos en la nube presentan desafíos durante el flujo de trabajo de eDiscovery porque solo el vínculo de datos adjuntos en la nube y no el contenido real del documento compartido se devuelven en una búsqueda de exhibición de documentos electrónicos. Para abordar este desafío, eDiscovery (Premium) proporciona dos soluciones para recopilar datos adjuntos en la nube:  

- Recopilación de la versión activa de un documento vinculado a en un archivo adjunto en la nube.

- Recopilación de la versión del documento en el momento en que se compartió en un archivo adjunto en la nube.

## <a name="collecting-cloud-attachments"></a>Recopilación de datos adjuntos en la nube

Al crear una colección de borradores y los resultados de la búsqueda contienen elementos que incluyen datos adjuntos en la nube, tiene que tener la opción de recopilar el destino de los datos adjuntos en la nube al confirmar la colección de borradores en un conjunto de revisión. Al seleccionar esta opción, eDiscovery (Premium) agrega los documentos vinculados en los datos adjuntos de la nube al conjunto de revisión. Esto le permite revisar los documentos de destino y determinar si el documento es relevante para su caso o investigación.

En la captura de pantalla siguiente se muestra la opción de incluir los destinos de los datos adjuntos en la nube al confirmar una colección en un conjunto de revisión.

![La opción para incluir datos adjuntos en la nube al confirmar una colección en un conjunto de revisión](../media/CollectCloudAttachments1.png)

> [!NOTE]
>- Si usa el [nuevo formato de caso](advanced-ediscovery-new-case-format.md) en eDiscovery (Premium), la opción para incluir datos adjuntos en la nube en el conjunto de revisión está seleccionada de forma predeterminada y no se puede anular la selección.<br/>
>- También tiene la opción de incluir todas las versiones (además de la versión compartida) de los datos adjuntos en la nube en el conjunto de revisión.  
Para obtener instrucciones sobre cómo confirmar una colección en un conjunto de revisión, consulte [Confirmación de una colección de borradores en un conjunto de revisión](commit-draft-collection.md).

## <a name="collecting-the-version-shared-in-a-cloud-attachment"></a>Recopilación de la versión compartida en un archivo adjunto en la nube

El flujo de trabajo de eDiscovery (Premium) para recopilar datos adjuntos en la nube solo incluye agregar la versión más reciente de un archivo adjunto en la nube a un conjunto de revisión. Esto significa que la versión recopilada y agregada a un conjunto de revisión podría ser diferente de la versión que se compartió originalmente en los datos adjuntos en la nube. Por lo tanto, es posible que el contenido que estaba presente en los datos adjuntos en la nube en el momento en que se compartió se haya quitado y no exista en la versión actual que se agrega al conjunto de revisión.

Las organizaciones ahora tienen la opción de usar Microsoft 365 etiquetas de retención para conservar la versión de un documento en el momento en que se compartió como datos adjuntos en la nube. Para ello, su organización puede crear una etiqueta de retención, elegir la opción aplicar la etiqueta a los datos adjuntos en la nube y, a continuación, aplicar automáticamente la etiqueta a los documentos almacenados en SharePoint y OneDrive. Después de configurar esta configuración, se crea una copia de un documento en el momento en que se comparte el archivo. Además, si el documento se modifica y se vuelve a compartir como datos adjuntos en la nube, también se conserva la versión modificada. Si el archivo se modifica y se vuelve a compartir, se conserva una nueva copia del archivo como una nueva versión.

Conservar las versiones compartidas de los datos adjuntos en la nube puede ayudar a su organización a limitar la conservación y la colección de contenido potencialmente relevante para la versión específica del documento que se ha compartido en lugar de la versión activa actual. Después de implementar esta solución de retención, tanto la versión activa actual de un archivo adjunto en la nube como la versión compartida en los datos adjuntos en la nube se recopilan y agregan a un conjunto de revisión.

Para obtener instrucciones sobre cómo configurar una etiqueta de retención y aplicarla automáticamente a los datos adjuntos en la nube, consulte [Aplicación automática de etiquetas a los datos adjuntos en la nube](apply-retention-labels-automatically.md#auto-apply-labels-to-cloud-attachments).

En la captura de pantalla siguiente se muestra un documento de datos adjuntos en la nube, denominado *XYZ Research.docx*, que se agregó a un conjunto de revisión. El documento se compartió como datos adjuntos en la nube en una conversación de chat Teams. El conjunto de revisión también contiene la versión que se compartió originalmente en los datos adjuntos en la nube. Observe que el sistema genera el nombre de esta versión de los datos adjuntos en la nube y que el autor se identifica como **SharePoint**.

![Versión de los datos adjuntos en la nube que se compartieron en un conjunto de revisión](../media/CollectCloudAttachments2.png)

Además, la versión activa actual y la versión compartida tienen el mismo valor de propiedad **FamilyId**, que es el mismo que el **FamilyId** para el objeto primario (como un mensaje de correo electrónico o una conversación de chat Teams). Esto le permite agrupar los datos adjuntos en la nube con el elemento en el que se compartieron.

Después de implementar la etiqueta de retención y aplicar automáticamente la etiqueta a SharePoint documentos, sigue seleccionando la opción para recopilar datos adjuntos en la nube al confirmar una colección de borradores en un conjunto de revisión. Cuando se recopilan los datos adjuntos en la nube, tanto la versión activa actual como la versión que se compartió originalmente se agregan al conjunto de revisión.
