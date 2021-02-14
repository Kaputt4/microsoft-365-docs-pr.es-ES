---
title: Configurar la detección de privilegios abogado-cliente en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el modelo de detección de privilegios abogado-cliente para usar la detección basada en aprendizaje automático del contenido con privilegios al revisar el contenido en un caso de eDiscovery avanzado.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358046"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Configurar la detección de privilegios abogado-cliente en eDiscovery avanzado

Un aspecto importante y costoso de la fase de revisión de cualquier proceso de exhibición de documentos electrónicos es la revisión de documentos para obtener contenido con privilegios. EDiscovery avanzado proporciona detección basada en aprendizaje automático de contenido con privilegios para que este proceso sea más eficaz. Esta característica se denomina *detección de privilegios abogado-cliente.*

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se habilita la detección de privilegios abogado-cliente, el modelo de detección [](analyzing-data-in-review-set.md) de privilegios abogado-cliente procesará todos los documentos de un conjunto de revisión al analizar los datos del conjunto de revisión. El modelo busca dos cosas:

- Contenido con privilegios: el modelo usa aprendizaje automático para determinar la probabilidad de que el documento contenga contenido de naturaleza legal.

- Participantes: como parte de la configuración de la detección de privilegios abogado-cliente, debe enviar una lista de abogados para su organización. A continuación, el modelo compara los participantes del documento con la lista de abogados para determinar si un documento tiene al menos un abogado participante.

El modelo genera las tres propiedades siguientes para cada documento:

- **AttorneyClientPrivilegeScore:** La probabilidad de que el documento sea legal por naturaleza; los valores de la puntuación están entre **0** y **1**.

- **HasAttorney:** Esta propiedad se establece en **true si** uno de los participantes del documento aparece en la lista de abogados; de lo contrario, el valor es **false**. El valor también se establece en **false** si su organización no ha cargado una lista de abogados.

- **IsPrivilege:** Esta propiedad se establece en **true** si el valor de  **AttorneyClientPrivilegeScore** está por encima del umbral o si el documento tiene un abogado participante; de lo contrario, el valor se establece en **false**.

Estas propiedades (y sus valores correspondientes) se agregan a los metadatos de archivo de los documentos en un conjunto de revisión, como se muestra en la siguiente captura de pantalla:

![Propiedades de privilegios abogado-cliente que se muestran en metadatos de archivo](../media/AeDAttorneyClientPrivilegeMetadata.png)

Estas tres propiedades también se pueden buscar dentro de un conjunto de revisión. Para obtener más información, [vea Consultar los datos de un conjunto de revisión.](review-set-search.md)

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Configurar el modelo de detección de privilegios abogado-cliente

Para habilitar el modelo de detección de privilegios abogado-cliente, su organización debe activarlo y, a continuación, cargar una lista de abogados.

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>Paso 1: Activar la detección de privilegios abogado-cliente

Una persona que sea administrador de exhibición de documentos electrónicos en su organización (miembro del subgrupo administrador de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos) debe hacer que el modelo esté disponible en los casos de eDiscovery avanzado.

1. En el Centro de & cumplimiento, vaya a **eDiscovery > eDiscovery avanzado.**

2. En la **página principal de eDiscovery** avanzado, en **el** icono Configuración, haga clic **en Configurar la configuración de análisis global.**

   ![Seleccione "Configurar características experimentales"](../media/AeDExperimentalFeatures.png)

3. En la **pestaña Configuración de Análisis,** seleccione **Administrar la configuración de privilegios abogado-cliente.**

4. En la **página desplegable de privilegios abogado-cliente,** use el botón de alternancia para activar la característica y, a continuación, **seleccione Guardar**.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Paso 2: Cargar una lista de abogados (opcional)

Para aprovechar al máximo el modelo de detección de privilegios abogado-cliente y usar los resultados de la detección de Has **Attorney** o **Potentially Privileged** que se describió anteriormente, le recomendamos que cargue una lista de direcciones de correo electrónico para los abogados y el personal legal que trabajan para su organización. 

Para cargar una lista de abogados para que la use el modelo de detección de privilegios abogado-cliente:

1. Cree un archivo .csv (sin una fila de encabezado) y agregue la dirección de correo electrónico para cada persona adecuada en una línea independiente. Guarde este archivo en el equipo local.

2. En la **página principal de eDiscovery** avanzado, en el icono Configuración, seleccione Configurar características **experimentales** y, a continuación, seleccione Administrar la configuración de **privilegios abogado-cliente.** 

   Se **muestra la página de** privilegios abogado-cliente y se activa el botón de alternancia de detección de privilegios **abogado-cliente.**

   ![Página desplegable de privilegios abogado-cliente](../media/AeDUploadAttorneyList.png)

3. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo .csv que creó en el paso 1.

4. Seleccione **Guardar para** cargar la lista de abogados.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Usar el modelo de detección de privilegios abogado-cliente

Siga los pasos de esta sección para usar la detección de privilegios abogado-cliente para los documentos de un conjunto de revisión.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Paso 1: Crear un grupo de etiquetas inteligentes con el modelo de detección de privilegios abogado-cliente

Una de las formas principales de ver los resultados de la detección de privilegios abogado-cliente en el proceso de revisión es mediante el uso de un grupo de etiquetas inteligentes. Un grupo de etiquetas inteligentes indica los resultados de la detección de privilegios abogado-cliente y muestra los resultados en línea junto a las etiquetas de un grupo de etiquetas inteligentes. Esto le permite identificar rápidamente documentos con privilegios potenciales durante la revisión del documento. Además, también puede usar las etiquetas del grupo de etiquetas inteligentes para etiquetar documentos como con privilegios o sin privilegios. Para obtener más información acerca de las etiquetas inteligentes, vea [Configurar etiquetas inteligentes en eDiscovery avanzado.](smart-tags.md)

1. En el conjunto de revisión que contiene los documentos  que ha analizado en el paso 1, seleccione Administrar conjunto de revisión y, a continuación, **seleccione Administrar etiquetas.**
 
2. En **Etiquetas,** seleccione el menú desplegable junto **a Agregar** grupo y, a continuación, seleccione Agregar grupo de **etiquetas inteligentes.**

   ![Seleccione "Agregar grupo de etiquetas inteligentes"](../media/AeDCreateSmartTag.png)

3. On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.

   Se muestra un grupo de etiquetas denominado **Privilegio abogado-cliente.** Contiene dos etiquetas secundarias **denominadas Positive** y **Negative**, que corresponden a los posibles resultados producidos por el modelo.

   ![Grupo de etiquetas inteligentes con privilegios abogado-cliente](../media/AeDAttorneyClientSmartTagGroup.png)

3. Cambie el nombre del grupo de etiquetas y las etiquetas según corresponda para su revisión. Por ejemplo, puede cambiar el nombre **De positivo** a **Privilegiado** y **Negativo** a **No privilegiado.**

### <a name="step-2-analyze-a-review-set"></a>Paso 2: Analizar un conjunto de revisión

Al analizar los documentos de un conjunto de revisión, también se ejecutará el modelo de detección de privilegios abogado-cliente y se agregarán las propiedades correspondientes (que se describen en Cómo [funciona?](#how-does-it-work) a todos los documentos del conjunto de revisión. Para obtener más información acerca del análisis de datos en el conjunto de revisión, vea Analizar datos en un [conjunto de revisión en eDiscovery avanzado.](analyzing-data-in-review-set.md)

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Paso 3: Usar el grupo de etiquetas inteligentes para revisar el contenido con privilegios

Después de analizar el conjunto de revisión y configurar las etiquetas inteligentes, el siguiente paso es revisar los documentos. Si el modelo ha determinado que el documento tiene privilegios potenciales, la etiqueta inteligente correspondiente en el **panel** de etiquetado indicará los siguientes resultados producidos por la detección de privilegios abogado-cliente:

- Si el documento tiene contenido que puede ser legal, la etiqueta **Contenido** legal se muestra junto a la etiqueta inteligente correspondiente (que en este caso es la **etiqueta positiva** predeterminada).

- Si el documento tiene un participante que se encuentra en la lista de abogados de su organización, la etiqueta **Abogado** se muestra junto a la etiqueta inteligente correspondiente (que en este caso también es la etiqueta **positiva** predeterminada).

- Si el documento tiene contenido que puede ser legal y tiene un  participante  que se encuentra en la lista de abogados, se muestran tanto el contenido legal como las etiquetas de abogado.  

Si el modelo determina que un documento no contiene contenido de naturaleza legal o que no contiene un participante de la lista de abogados, no se muestra ninguna etiqueta en el panel de etiquetado.

Por ejemplo, las capturas de pantalla siguientes muestran dos documentos. El primero contiene contenido de naturaleza legal y tiene un participante que se encuentra en la lista de abogados. El segundo no contiene ninguno y, por lo tanto, no muestra ninguna etiqueta.

![Documento con etiquetas de contenido abogado y jurídico](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sin etiquetas](../media/AeDTaggingPanelNegative.png)

Después de revisar un documento para ver si contiene contenido con privilegios, puede etiquetar el documento con la etiqueta adecuada.
