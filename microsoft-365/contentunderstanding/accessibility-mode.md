---
title: 'Modo de accesibilidad de SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Aprenda a usar el modo de accesibilidad al entrenar un modelo en SharePoint Syntex.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50081024"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Modo de accesibilidad de SharePoint Syntex

En [SharePoint Syntex,](index.md)los usuarios pueden activar el modo de accesibilidad en todas las etapas de aprendizaje de modelos (etiqueta, aprendizaje, prueba) al trabajar con documentos de ejemplo. El uso del modo de accesibilidad puede ayudar a los usuarios a tener una accesibilidad de teclado más fácil a medida que navegan y etiquetan elementos en el visor de documentos.

Esto ayuda a los usuarios a usar sus teclados para desplazarse por el texto del visor de documentos y escuchar una narración no solo de los valores seleccionados, sino también de acciones (como etiquetar o quitar etiquetas del texto seleccionado) o valores de etiquetas previstos mientras entrena el modelo con documentos de ejemplo adicionales. 


![Modo de accesibilidad](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Requirements

Para escuchar el audio de la narración, asegúrate de activar la aplicación [Narrador](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) en la configuración del Narrador en el sistema Windows 10.

![Activar narrador](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Etiquetado para usuarios de teclado

Para los usuarios de teclado que usan el modo de accesibilidad, si va a etiquetar texto en un documento de ejemplo en el visor, puede usar las siguientes teclas:

- Pestaña: mueve hacia delante y selecciona la siguiente palabra.
- Tab + Mayús: mueve hacia atrás y selecciona la palabra anterior.
- Escriba: Etiqueta o quite una etiqueta de la palabra seleccionada.
- Flecha hacia delante: mueve hacia delante los caracteres individuales de una palabra seleccionada.
- Flecha hacia atrás: mueve hacia atrás los caracteres individuales de una palabra seleccionada.

> [!NOTE]
> Si va a etiquetar varias palabras para una sola etiqueta, debe etiquetar cada palabra.


## <a name="narration"></a>Narración

Para los usuarios del Narrador que usan el modo de accesibilidad, use la misma navegación por teclado descrita para que los usuarios de teclado pasen por el documento de ejemplo en el visor.

Al navegar por los documentos de ejemplo y etiquetar valores de cadena, Narrador le dará al usuario los siguientes mensajes de audio:

- Cuando use el teclado para navegar por el visor de documentos, el audio del Narrador mostrará la cadena seleccionada.
- Dentro de una cadena seleccionada, el audio del Narrador mostrará cada carácter de la cadena a medida que los selecciones mediante la flecha hacia delante o hacia atrás.
- Si selecciona una cadena que se ha etiquetado, narrador mostrará el valor y, a continuación, "etiquetado".  Por ejemplo, si el valor de la etiqueta es "Contoso", el estado será "Costoso etiquetado". 
- En la pestaña de aprendizaje, si selecciona una cadena en el visor de documentos que solo se ha previsto, el audio del Narrador mostrará el valor y, a continuación, "previsto". Esto ocurre cuando el aprendizaje predice un valor en el archivo que no coincide con lo que el usuario ha etiquetado.
- En la pestaña de aprendizaje, si selecciona una cadena en el visor de documentos que se ha etiquetado y previsto, el audio del Narrador mostrará el valor y, a continuación, "etiquetado y previsto". Esto ocurre cuando el aprendizaje se realiza correctamente y hay una coincidencia entre un valor previsto y la etiqueta de usuario.



Después de etiquetar una cadena o de quitar una etiqueta en el visor, el audio del Narrador te advertirá de que guardes los cambios antes de salir.

## <a name="see-also"></a>Consulte también

[Crear un extractor](create-an-extractor.md)</br>

[Crear un clasificador](create-a-classifier.md)</br>










 


  
  



