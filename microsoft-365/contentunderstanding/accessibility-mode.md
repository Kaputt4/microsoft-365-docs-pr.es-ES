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
description: Obtenga información sobre cómo usar el modo de accesibilidad al entrenar un modelo en SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515153"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Modo de accesibilidad de SharePoint Syntex

En [SharePoint Syntex,](index.md)los usuarios pueden activar el modo de accesibilidad en todas las fases del aprendizaje del modelo (etiqueta, aprendizaje, prueba) al trabajar con documentos de ejemplo. El uso del modo de accesibilidad puede ayudar a los usuarios a tener una accesibilidad de teclado más fácil a medida que navegan y etiquetan elementos en el visor de documentos.

Esto ayuda a los usuarios a usar sus teclados para navegar por el texto en el visor de documentos y escuchar una narración no solo de los valores seleccionados, sino también de acciones (como etiquetar o quitar el etiquetado del texto seleccionado) o valores de etiquetas predichos al entrenar el modelo con documentos de ejemplo adicionales. 


![Modo de accesibilidad](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Requisitos

Para escuchar el audio de la narración, asegúrate de activar la aplicación [narrador](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) en la configuración del narrador en el sistema Windows 10.

![Activar narrador](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Etiquetado para usuarios de teclado

Para los usuarios de teclado que usan el modo de accesibilidad, si va a etiquetar texto en un documento de ejemplo en el visor, puede usar las siguientes teclas:

- Tab: te mueve hacia delante y selecciona la siguiente palabra.
- Tab + Mayús: te mueve hacia atrás y selecciona la palabra anterior.
- Escriba: Etiqueta o quita una etiqueta de la palabra seleccionada.
- Flecha derecha: te mueve hacia delante a través de caracteres individuales de una palabra seleccionada.
- Flecha izquierda: te mueve hacia atrás a través de caracteres individuales de una palabra seleccionada.

> [!NOTE]
> Si va a etiquetar varias palabras para una sola etiqueta, debe etiquetar cada palabra.


## <a name="narration"></a>Narración

Para los usuarios del narrador que usan el modo de accesibilidad, use la misma navegación del teclado descrita para que los usuarios de teclado puedan pasar por el documento de ejemplo en el visor.

A medida que navegue por los documentos de ejemplo y los valores de cadena de etiqueta, narrador le dará al usuario los siguientes mensajes de audio:

- Al usar el teclado para navegar por el visor de documentos, el audio del narrador mostrará la cadena seleccionada.
- Dentro de una cadena seleccionada, el audio del narrador mostrará cada carácter de la cadena al seleccionarlos mediante las teclas de flecha izquierda o derecha.
- Si selecciona una cadena que se ha etiquetado, narrador mostrará el valor y, a continuación, "etiquetado".  Por ejemplo, si el valor de la etiqueta es "Contoso", se mostrará "Costoso etiquetado". 
- En la pestaña de aprendizaje, si selecciona una cadena en el visor de documentos que solo se ha predicho, el audio del narrador mostrará el valor y, a continuación, "predijo". Esto ocurre cuando el aprendizaje predice un valor en el archivo que no coincide con lo que ha etiquetado el usuario.
- En la pestaña de aprendizaje, si selecciona una cadena en el visor de documentos que se ha etiquetado y predicho, el audio del narrador mostrará el valor y, a continuación, "etiquetado y predicho". Esto ocurre cuando el aprendizaje se realiza correctamente y hay una coincidencia entre un valor predicho y la etiqueta de usuario.



Después de etiquetar una cadena o de quitar una etiqueta en el visor, el audio del narrador le advertirá que guarde los cambios antes de salir.

## <a name="see-also"></a>Consulte también

[Crear un extractor](create-an-extractor.md)</br>

[Crear un clasificador](create-a-classifier.md)</br>










 


  
  



