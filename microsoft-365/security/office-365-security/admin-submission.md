---
title: Envíos de administración en Office 365, envíos de O365, Office 365 problema de correo no deseado, O365 falso negativo, enviar phish en Office 365, enviar correo electrónico para analizar, correo electrónico sospechoso en Office 365, analizar un mensaje, hacer que Microsoft analice en caso de Phish, hacer que Microsoft busque correo no deseado, enviar correo electrónico, enviar correo electrónico, Dodgy de correo electrónico, correo de actor malo, correo sospechoso, no fiable, informar de mensajes de phish a Microsoft, informar de los correos electrónicos de phish a Microsoft, informar de un correo electrónico malintencionado a Microsoft, notificar el correo electrónico de estafa a Microsoft, notificar malware en correo electrónico a Microsoft, correo no deseado correo electrónico en la bandeja de entrada Office 365, virus en correo electrónico Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo enviar correos sospechosos, direcciones URL y mensajes de suplantación de identidad sospechoso, correo no deseado y otros mensajes potencialmente peligrosos, direcciones URL y archivos desde el inquilino de Office 365 a Microsoft para su análisis.
ms.openlocfilehash: 54cb42f8c02f2f41ad583d640a090509817911ee
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808555"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>Cómo enviar sospechoso de correo no deseado, phish, direcciones URL y archivos a Microsoft para el análisis de Office 365

Los administradores pueden enviar correos electrónicos mediante el identificador de mensajes de red o archivos, las direcciones URL y los archivos para que Microsoft los analice en Office 365. La sección de presentaciones actualizadas sigue incluyendo mensajes de usuario que han sido notificados y disponibles para todos los clientes que usen EOP.

Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo. Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas ETR. 

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Cómo dirigir contenido sospechoso a Microsoft para el análisis de Office 365

Para enviar contenido a Microsoft, haga clic en el botón **nuevo envío** en el lado superior izquierdo de la página envíos. Un control flotante en el lado derecho de la página aparece con la opción de enviar un correo electrónico, una dirección URL o un archivo. 

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar un correo electrónico cuestionable a Microsoft
![Ejemplo de envío de correo electrónico](../media/submission-flyout-email.PNG)
1. Para enviar un correo electrónico, seleccione **correo electrónico** y especifique el **identificador de mensaje de red** de correo electrónico o cargue el archivo de correo electrónico. 

2. Especifique el destinatario o los destinatarios con los que desea ejecutar la comprobación de la Directiva. La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a directivas de nivel de usuario o de inquilino. 

3. Especifique si el correo electrónico se debe haber bloqueado o no. Si el correo electrónico debe haberse bloqueado, especifique si debe haberse bloqueado como correo no deseado, suplantación de identidad (phishing) o malware. Si no está seguro de qué tipo puede ser, use su mejor criterio.  

* Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.

* Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos. Para ver más información sobre el envío, haga clic en el vínculo estado. Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo. Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo. 

4. Haga clic en el botón **Enviar** .

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar una dirección URL sospechosa a Microsoft
![Ejemplo de envío de correo electrónico](../media/submission-url-flyout.png)
1. Para enviar una dirección URL, seleccione **dirección URL** en el control flotante. Escriba la dirección URL completa, incluido el protocolo (**https://**). 

* Si seleccionó **debería haber sido filtrada**, especifique si la dirección URL es phishing o malware.

2. Haga clic en el botón **Enviar** . 


### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar un archivo sospechoso a Microsoft
![Ejemplo de envío de correo electrónico](../media/submission-file-flyout.PNG)
1. Para enviar un **archivo de selección de archivo desde** el control flotante y cargar el archivo que desea examinar. 

2. Haga clic en el botón **Enviar** .


## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365 (plan 2)](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
  

