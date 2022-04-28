---
title: Configuración de la detección de privilegios de abogado-cliente en eDiscovery (Premium)
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
description: Use el modelo de detección de privilegios abogado-cliente para usar la detección basada en aprendizaje automático de contenido con privilegios al revisar el contenido en un caso de exhibición de documentos electrónicos (Premium) de Microsoft Purview.
ms.openlocfilehash: 359dccc041a0655ade291a37e511038a50148f7b
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094039"
---
# <a name="set-up-attorney-client-privilege-detection-in-ediscovery-premium"></a>Configuración de la detección de privilegios de abogado-cliente en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Un aspecto importante y costoso de la fase de revisión de cualquier proceso de exhibición de documentos electrónicos es revisar los documentos para obtener contenido con privilegios. Microsoft Purview eDiscovery (Premium) proporciona detección basada en aprendizaje automático de contenido con privilegios para que este proceso sea más eficaz. Esta característica se denomina *detección de privilegios de abogado-cliente*.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se habilita la detección de privilegios de abogado-cliente, el modelo de detección de privilegios abogado-cliente procesará todos los documentos de un conjunto de revisión al [analizar los datos](analyzing-data-in-review-set.md) del conjunto de revisión. El modelo busca dos cosas:

- Contenido con privilegios: el modelo usa el aprendizaje automático para determinar la probabilidad de que el documento contenga contenido de naturaleza legal.

- Participantes: como parte de la configuración de la detección de privilegios abogado-cliente, tiene que enviar una lista de abogados para su organización. A continuación, el modelo compara los participantes del documento con la lista de abogados para determinar si un documento tiene al menos un participante que es abogado.

El modelo genera las tres propiedades siguientes para cada documento:

- **AttorneyClientPrivilegeScore:** La probabilidad de que el documento sea de naturaleza jurídica; los valores de la puntuación están entre **0** y **1**.

- **HasAttorney:** Esta propiedad se establece en **true** si uno de los participantes del documento aparece en la lista de abogados; de lo contrario, el valor es **false**. El valor también se establece en **false** si su organización no cargó una lista de abogados.

- **IsPrivilege:** Esta propiedad se establece en **true** si el valor de **AttorneyClientPrivilegeScore** está por encima del umbral *o* si el documento tiene un participante de abogado; De lo contrario, el valor se establece en **false**.

Estas propiedades (y sus valores correspondientes) se agregan a los metadatos de archivo de los documentos de un conjunto de revisión, como se muestra en la captura de pantalla siguiente:

![Propiedades de privilegios de abogado-cliente que se muestran en los metadatos del archivo.](../media/AeDAttorneyClientPrivilegeMetadata.png)

Estas tres propiedades también se pueden buscar dentro de un conjunto de revisión. Para obtener más información, consulte [Consulta de los datos de un conjunto de revisión](review-set-search.md).

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Configuración del modelo de detección de privilegios abogado-cliente

Para habilitar el modelo de detección de privilegios abogado-cliente, su organización tiene que activarlo y cargar una lista de abogados.

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>Paso 1: Activar la detección de privilegios de abogado-cliente

Una persona que sea administrador de eDiscovery en su organización (miembro del subgrupo administrador de eDiscovery en el grupo de roles del Administrador de exhibición de documentos electrónicos) debe hacer que el modelo esté disponible en los casos de eDiscovery (Premium).

1. En el portal de cumplimiento de Microsoft Purview, vaya a [eDiscovery (Premium)](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic en **configuración de eDiscovery (Premium).**

   ![Seleccionar la configuración de eDiscovery (Premium)](..\media\HistoricalVersions1.png)

2. En la página **Configuración**, seleccione la pestaña **Análisis** y, a continuación, cambie el botón de alternancia **de detección de privilegios abogado-cliente** a activado.

   ![Haga clic en alternar para activar la detección de privilegios de abogado-cliente.](..\media\TurnOnAttorneyClientPrivilegeDetection.png)

3. Haga clic en **Guardar** para guardar el cambio.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Paso 2: Upload una lista de abogados (opcional)

Para aprovechar al máximo el modelo de detección de privilegios de abogado-cliente y usar los resultados de la detección **de has attorney** o **potencialmente con privilegios** que se describió anteriormente, le recomendamos que cargue una lista de direcciones de correo electrónico para los abogados y el personal legal que trabajan para su organización.

Para cargar una lista de abogados para que la use el modelo de detección de privilegios abogado-cliente:

1. Cree un archivo .csv (sin una fila de encabezado) y agregue la dirección de correo electrónico de cada usuario adecuado en una línea independiente. Guarde este archivo en su equipo local.

2. En **la página Configuración** eDiscovery (Premium), seleccione la pestaña **Análisis**.

   Se muestra la página **Privilegios de abogado-cliente** y el botón de alternancia **de detección de privilegios Detección de privilegios de abogado-cliente** está activado.

   ![Página de control flotante de privilegios de abogado-cliente](..\media\AeDUploadAttorneyList1.png)

3. Seleccione **Elegir archivo** y, a continuación, busque y seleccione el archivo .csv que creó en el paso 1.

4. Seleccione **Guardar** para cargar la lista de abogados.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Uso del modelo de detección de privilegios abogado-cliente

Siga los pasos de esta sección para usar la detección de privilegios de abogado-cliente para documentos de un conjunto de revisión.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Paso 1: Crear un grupo de etiquetas inteligentes con el modelo de detección de privilegios abogado-cliente

Una de las formas principales de ver los resultados de la detección de secreto profesional entre abogado y cliente en el proceso de revisión es mediante un grupo de etiquetas inteligentes. Un grupo de etiquetas inteligentes indica los resultados de la detección de secreto profesional entre abogado y cliente y muestra los resultados en línea junto a las etiquetas de un grupo de etiquetas inteligentes. Esto le permite identificar rápidamente documentos potencialmente con privilegios durante la revisión de documentos. Además, también puede usar las etiquetas del grupo de etiquetas inteligentes para etiquetar documentos como secretos o no secretos. Para obtener más información sobre las etiquetas inteligentes, vea [Configurar etiquetas inteligentes en eDiscovery (Premium)](smart-tags.md).

1. En el conjunto de revisión que contiene los documentos que analizó en el paso 1, seleccione **Administrar conjunto de revisión** y, a continuación, seleccione **Administrar etiquetas**.

2. En **Etiquetas**, seleccione la lista desplegable junto a **Agregar grupo** y, a continuación, seleccione **Agregar grupo de etiquetas inteligentes**.

   ![Seleccione "Agregar grupo de etiquetas inteligentes".](../media/AeDCreateSmartTag.png)

3. En la página **Elegir un modelo para la etiqueta inteligente** , elija **Seleccionar** junto a **Privilegios de abogado-cliente**.

   Se muestra un grupo de etiquetas denominado **Privilegios de abogado-cliente** . Contiene dos etiquetas secundarias denominadas **Positive** y **Negative**, que corresponden a los posibles resultados generados por el modelo.

   ![Grupo de etiquetas inteligentes con privilegios de abogado-cliente.](../media/AeDAttorneyClientSmartTagGroup.png)

3. Cambie el nombre del grupo de etiquetas y las etiquetas según corresponda para la revisión. Por ejemplo, puede cambiar el nombre **Positivo** a **Con privilegios** y **Negativo** a **No con privilegios**.

### <a name="step-2-analyze-a-review-set"></a>Paso 2: Analizar un conjunto de revisión

Al analizar los documentos de un conjunto de revisión, también se ejecutará el modelo de detección de privilegios abogado-cliente y las propiedades correspondientes (descritas en [¿Cómo funciona?](#how-does-it-work)) se agregarán a cada documento del conjunto de revisión. Para obtener más información sobre el análisis de datos en el conjunto de revisión, vea [Analizar datos en un conjunto de revisión en eDiscovery (Premium)](analyzing-data-in-review-set.md).

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Paso 3: Uso del grupo de etiquetas inteligentes para revisar el contenido con privilegios

Después de analizar el conjunto de revisión y configurar etiquetas inteligentes, el siguiente paso es revisar los documentos. Si el modelo ha determinado que el documento tiene potencialmente privilegios, la etiqueta inteligente correspondiente en el **panel Etiquetado** indicará los siguientes resultados generados por la detección de privilegios abogado-cliente:

- Si el documento tiene contenido que puede ser de naturaleza legal, la etiqueta **Contenido legal** se muestra junto a la etiqueta inteligente correspondiente (que en este caso es la etiqueta **positiva** predeterminada).

- Si el documento tiene un participante que se encuentra en la lista de abogados de su organización, la etiqueta **Abogado** se muestra junto a la etiqueta inteligente correspondiente (que en este caso también es la etiqueta **positiva** predeterminada).

- Si el documento tiene contenido que puede ser de naturaleza legal *y* tiene un participante en la lista de abogados, se muestran tanto el **contenido legal**  como las etiquetas de **abogado** . 

Si el modelo determina que un documento no contiene contenido de naturaleza legal o que no contiene un participante de la lista de abogados, ninguna etiqueta se muestra en el panel de etiquetado.

Por ejemplo, en las capturas de pantalla siguientes se muestran dos documentos. El primero contiene contenido de naturaleza legal y tiene un participante en la lista de abogados. El segundo no contiene ninguna y, por lo tanto, no muestra ninguna etiqueta.

![Documente con etiquetas de contenido de Abogado y Legal.](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sin etiquetas.](../media/AeDTaggingPanelNegative.png)

Después de revisar un documento para ver si contiene contenido con privilegios, puede etiquetar el documento con la etiqueta adecuada.
