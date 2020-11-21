---
title: Sugerencias de seguridad en mensajes de correo electrónico
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo EOP y Office 365 protegen contra el correo no deseado, el phishing y la prevención de malware al agregar una sugerencia de seguridad a la parte superior de los correos electrónicos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e36887e2bb0146c86a8a4f1526f1e712a38b46ba
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376624"
---
# <a name="safety-tips-in-email-messages"></a>Sugerencias de seguridad en mensajes de correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online Protection (EOP) y Microsoft 365 protegen el correo no deseado, el phishing y la prevención de malware. Hoy en día, algunos de estos ataques están tan bien diseñados que parecen legítimos. No siempre es suficiente enviar mensajes a la carpeta correo electrónico no deseado. Ahora, cuando revise el correo electrónico en Outlook o en Outlook en la web o en cualquier cliente de correo electrónico, EOP comprueba automáticamente el remitente y agrega una sugerencia de seguridad en la parte superior del correo electrónico.

Las sugerencias de seguridad de Outlook no dependen de la versión de Outlook que está usando, ya que la sugerencia de seguridad se ha averiguado abierto e insertado directamente en el cuerpo del mensaje. Esto significa que la sugerencia de seguridad se mostrará en cualquier cliente de correo electrónico que esté usando. Se realiza en el nivel de filtro de correo electrónico y no se representa en el nivel de cliente de correo, por lo que no solo se muestra en ninguna versión de Outlook, sino que también se muestra en cualquier cliente de correo electrónico.

La sugerencia de seguridad, un mensaje codificado por colores, le avisará de los mensajes potencialmente perjudiciales. La mayoría de los mensajes de la bandeja de entrada no tienen una sugerencia de seguridad. Solo las verá cuando EOP y Microsoft 365 tienen información que necesita para evitar los ataques de correo no deseado, de suplantación de identidad (phishing) y de malware. Si se muestran sugerencias de seguridad en la bandeja de entrada, puede usar los siguientes ejemplos para obtener más información sobre cada tipo de sugerencia de seguridad.

- Correo sospechoso (sugerencia de seguridad roja).

    ![Captura de pantalla que muestra una sugerencia de seguridad roja.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Una sugerencia de seguridad roja en un correo electrónico significa que el mensaje que ha recibido contiene algo sospechoso, como una estafa de suplantación de identidad (phishing). Le recomendamos que elimine este tipo de mensaje de correo electrónico de la bandeja de entrada sin abrirlo.

- Correo seguro (sugerencia de seguridad verde).

    ![Captura de pantalla que muestra una sugerencia de seguridad de color verde.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Además de los mensajes no seguros, también le mostraremos los mensajes válidos de los remitentes en los que confíe con una sugerencia de seguridad verde. Una sugerencia de seguridad verde en un correo electrónico significa que se ha comprobado el remitente del mensaje y que se ha comprobado que es seguro. Microsoft mantiene esta lista de remitentes de confianza que incluyen organizaciones financieras y otros usuarios que se falsifican o suplantan con frecuencia.

## <a name="working-with-safety-tips"></a>Trabajar con sugerencias de seguridad

Las sugerencias de seguridad siempre están habilitadas para Outlook en la web, aunque no todos los mensajes recibirán ninguna. Los administradores pueden desactivar las sugerencias de seguridad para otros clientes de correo electrónico como Outlook. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

Si no está de acuerdo con el modo en que EOP ha clasificado un mensaje (es decir, si el mensaje no es correo no deseado o se debería haber marcado como correo no deseado), puede enviar los mensajes a Microsoft para su análisis a fin de mejorar su experiencia. Para obtener instrucciones, consulte [informes de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md). También puede hacer clic en el vínculo comentarios de la sugerencia de seguridad para enviar comentarios directamente a Microsoft para ayudarnos a mejorar.
